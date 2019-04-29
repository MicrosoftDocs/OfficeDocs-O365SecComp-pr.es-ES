---
title: Aislamiento y control de acceso de Office 365 en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: una explicación del aislamiento y el control de acceso dentro de las distintas aplicaciones de Office 365.'
ms.openlocfilehash: 748da21f5b5048bb4ae4c14700ed482fd6d0058c
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402898"
---
# <a name="isolation-and-access-control-in-office-365"></a>Aislamiento y Control de acceso en Office 365

Azure Active Directory y Office 365 usan un modelo de datos muy complejo que incluye decenas de servicios, cientos de entidades, miles de relaciones y decenas de miles de atributos. En un nivel alto, Azure Active Directory y los directorios de servicio son los contenedores de los inquilinos y los destinatarios que se mantienen sincronizados mediante protocolos de replicación basados en el estado. Además de la información de directorio contenida en Azure Active Directory, cada una de las cargas de trabajo de servicio tiene su propia infraestructura de servicios de directorio.
 
![Sincronización de datos del espacio empresarial de Office 365](media/office-365-isolation-tenant-data-sync.png)

Dentro de este modelo, no hay un único origen de datos de directorio. Sistemas específicos que poseen partes individuales de datos, pero ningún sistema único contiene todos los datos. Los servicios de Office 365 cooperan con Azure Active Directory en este modelo de datos. Azure Active Directory es el "sistema de verdad" para datos compartidos, que normalmente son datos pequeños y estáticos que usan todos los servicios. El modelo federado usado en Office 365 y Azure Active Directory proporciona la vista compartida de los datos.

Office 365 usa el almacenamiento físico y el almacenamiento en la nube de Azure. Exchange Online (incluida la protección en línea de Exchange) y Skype empresarial usan su propio almacenamiento para los datos de clientes. SharePoint Online usa el almacenamiento de SQL Server y Azure Storage, de ahí la necesidad de un aislamiento adicional de los datos de cliente en el nivel de almacenamiento.

## <a name="exchange-online"></a>Exchange Online

Exchange Online almacena los datos de clientes dentro de los buzones. Los buzones de correo se hospedan en bases de datos del motor de almacenamiento extensible (ESE) denominadas bases de datos de buzones. Esto incluye los buzones de usuario, los buzones vinculados, los buzones compartidos y los buzones de carpetas públicas. Los buzones de usuario incluyen contenido guardado de Skype empresarial, como historiales de conversaciones.

El contenido de los buzones de usuario incluye:

- Mensajes de correo electrónico y datos adjuntos
- Información de disponibilidad y calendario
- Contactos
- Tareas
- Notas
- Grupos
- Datos de inferencia

Cada base de datos de buzones de correo de Exchange Online contiene buzones de varios inquilinos. Un código de autorización protege cada buzón de correo, incluido en un arrendamiento. De forma predeterminada, solo el usuario asignado tiene acceso a un buzón. La lista de control de acceso (ACL) que protege a un buzón de correo contiene una identidad autenticada por Azure Active Directory en el nivel de espacio empresarial. Los buzones de cada inquilino están limitados a identidades autenticadas en el proveedor de autenticación del inquilino, que solo incluye a los usuarios de ese inquilino. El contenido del espacio empresarial A no puede ser obtenido de ninguna manera por los usuarios del inquilino B, a menos que lo apruebe explícitamente el inquilino A.

## <a name="skype-for-business"></a>Skype Empresarial

Skype empresarial almacena datos en varios lugares:

- La información de usuarios y cuentas, que incluye los extremos de conexión, los identificadores de inquilino, los planes de marcado, la configuración de itinerancia, el estado de presencia, las listas de contactos, etc., se almacena en los servidores de Active Directory de Skype empresarial y en varios servidores de base de datos de Skype empresarial. Las listas de contactos se almacenan en el buzón de correo de Exchange online del usuario si el usuario está habilitado para ambos productos o en servidores de Skype empresarial si el usuario no lo está. Los servidores de base de datos de Skype empresarial no tienen particiones por inquilino, pero el aislamiento de datos multiinquilino se aplica mediante el control de acceso basado en roles (RBAC).
- El contenido de la reunión y los datos cargados se almacenan en recursos compartidos del sistema de archivos distribuido (DFS). Este contenido también se puede archivar en Exchange Online si está habilitado. Los recursos compartidos DFS no tienen particiones por espacio empresarial. el contenido está protegido con ACL y la función de multiinquilino se aplica a través de RBAC.
- Los registros de detalles de llamadas, que son el historial de actividades, como el historial de llamadas, las sesiones de mensajería instantánea, el uso compartido de aplicaciones, el historial de mi, etc., también se pueden almacenar en Exchange Online, pero la mayoría de los registros de detalles de llamadas se almacenan temporalmente en los servidores de registro de detalles de llamadas (CDR). El contenido no se divide en particiones por inquilino, pero la función de multiinquilino se aplica a través de RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online tiene varios mecanismos independientes que proporcionan aislamiento de datos. Almacena los objetos como código abstracto dentro de las bases de datos de la aplicación. Por ejemplo, cuando un usuario carga un archivo en SharePoint Online, el archivo se desensambla, traduce a código de aplicación y se almacena en varias tablas en varias bases de datos.

Si un usuario puede obtener acceso directo al almacenamiento que contiene los datos, el contenido no se puede interpretar como un usuario ni un sistema que no sea SharePoint Online. Estos mecanismos incluyen las propiedades y el control de acceso de seguridad. Todos los recursos de SharePoint Online están protegidos por el código de autorización y la Directiva RBAC, incluso dentro de un arrendamiento. La lista de control de acceso (ACL) que protege un recurso contiene una identidad autenticada en el nivel de espacio empresarial. Los datos de SharePoint Online para un espacio empresarial se limitan a las identidades autenticadas por el proveedor de autenticación para el inquilino.

Además de las ACL, una propiedad de nivel de inquilino que especifica el proveedor de autenticación (que es el Azure Active Directory específico del inquilino), se escribe una vez y no se puede cambiar una vez establecido. Una vez que se ha establecido la propiedad de inquilino de proveedor de autenticación para un espacio empresarial, no se puede cambiar mediante ninguna API expuesta a un inquilino.

Se usa un *SubscriptionId* único para cada inquilino. Todos los sitios de clientes pertenecen a un inquilino y se les asigna un *SubscriptionId* único para el inquilino. La propiedad *SubscriptionId* de un sitio se escribe una vez y es permanente. Una vez que se ha asignado a un inquilino, no se puede mover un sitio a un inquilino diferente. El *SubscriptionId* es la clave que se usa para crear el ámbito de seguridad para el proveedor de autenticación y está ligado al espacio empresarial.

SharePoint Online usa SQL Server y Azure Storage para el almacenamiento de metadatos de contenido. La clave de partición del almacén de contenido es *SiteId* en SQL. Cuando se ejecuta una consulta SQL, SharePoint Online usa un *SiteId* verificado como parte de una comprobación de *SubscriptionId* a nivel de inquilino.

SharePoint Online almacena el contenido de los archivos cifrados en blobs de Microsoft Azure. Cada granja de servidores de SharePoint Online tiene su propia cuenta de Microsoft Azure y todos los blobs guardados en Azure se cifran individualmente con una clave almacenada en el almacén de contenido de SQL. La clave de cifrado protegida en el código por la capa de autorización y no expuesta directamente al usuario final. SharePoint Online tiene supervisión en tiempo real para detectar cuándo una solicitud HTTP lee o escribe datos para más de un espacio empresarial. Se realiza un seguimiento de la *suscripción* de identidad de solicitud en el *subscriptionId* del recurso al que se tiene acceso. Los usuarios finales nunca deben realizar solicitudes para obtener acceso a recursos de más de un espacio empresarial. Las solicitudes de servicio en un entorno de varios inquilinos son la única excepción. Por ejemplo, el rastreador de búsqueda extrae los cambios de contenido de toda la base de datos a la vez. Normalmente esto implica consultar sitios de más de un espacio empresarial en una sola solicitud de servicio, que se realiza por motivos de eficiencia.
