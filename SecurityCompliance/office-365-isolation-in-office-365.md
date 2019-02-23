---
title: Aislamiento y control de acceso de Office 365 en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: una explicación del aislamiento y el control de acceso dentro de las distintas aplicaciones de Office 365.'
ms.openlocfilehash: 734c92a6f3185a25faf9aade1ba235444ed762da
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216860"
---
# <a name="isolation-and-access-control-in-office-365"></a>Aislamiento y Control de acceso en Office 365

Azure Active Directory y Office 365 usan un modelo de datos muy complejo que incluye decenas de servicios, cientos de entidades, miles de relaciones y decenas de miles de atributos (las entidades, las relaciones y los atributos suelen ser específicos de las aplicaciones). En un nivel alto, Azure Active Directory y los directorios de servicio son los contenedores de los inquilinos y los destinatarios, y se mantienen sincronizados mediante protocolos de replicación basados en el estado. Además de la información de directorio contenida en Azure Active Directory, cada uno de los servicios también tiene su propia infraestructura de servicios de directorio (por ejemplo, servicios de directorio de Exchange Online, servicios de directorio de SharePoint Online, etc.). 
 
![Sincronización de datos del espacio empresarial de Office 365](media/office-365-isolation-tenant-data-sync.png)

Dentro de este modelo, no hay un único origen de datos de directorio. Cada dato individual es propiedad de un sistema específico, pero ningún sistema único contiene todos los datos. Los servicios de Office 365 cooperan con Azure Active Directory para obtener el modelo de datos. Azure Active Directory es el "sistema de verdad" para datos compartidos, que normalmente son datos pequeños y estáticos que se usan con frecuencia en cada servicio. El modelo federado usado en Office 365 y Azure Active Directory proporciona la vista compartida de los datos.

Office 365 usa el almacenamiento físico y el almacenamiento en la nube de Azure. Exchange Online (incluida la protección en línea de Exchange) y Skype empresarial usan su propio almacenamiento para los datos de clientes. SharePoint Online aprovecha tanto el almacenamiento de SQL Server como el almacenamiento de Azure, lo que requiere la necesidad de un aislamiento adicional de los datos de cliente en el nivel de almacenamiento.

## <a name="exchange-online"></a>Exchange Online
Exchange Online almacena los datos de los clientes en buzones que se hospedan en bases de datos del motor de almacenamiento extensible (ESE) denominadas bases de datos de buzones de correo. Esto incluye los buzones de usuario, los buzones vinculados, los buzones compartidos y los buzones de carpetas públicas. Los buzones de usuario también pueden incluir contenido guardado de Skype empresarial, como historiales de conversaciones. El contenido de los buzones de usuario incluye correos electrónicos y datos adjuntos de correo electrónico, calendario y información de disponibilidad, contactos, tareas, notas, grupos y datos de inferencia.

Cada base de datos de buzones de correo de Exchange Online contiene buzones de varios inquilinos. Todos los buzones de correo están protegidos por código de autorización, incluso dentro de un arrendamiento. Al igual que con una implementación local de Exchange, de forma predeterminada, solo el usuario asignado tiene acceso a un buzón. La lista de control de acceso (ACL) que protege a un buzón de correo contiene una identidad autenticada por Azure Active Directory en el nivel de espacio empresarial. Los buzones de un inquilino determinado se limitan a identidades autenticadas en el proveedor de autenticación de ese inquilino, que solo incluyen usuarios de ese espacio empresarial. El contenido que pertenece al espacio empresarial no se puede obtener de ninguna manera por los usuarios de TenantB, a menos que el espacio empresarial lo apruebe explícitamente.

## <a name="skype-for-business"></a>Skype Empresarial
Skype empresarial almacena datos en una amplia variedad de lugares:
- La información de usuarios y cuentas, que incluye los extremos de conexión, los identificadores de inquilino, los planes de marcado, la configuración de itinerancia, el estado de presencia, las listas de contactos, etc., se almacena en los servidores de Active Directory de Skype empresarial, así como en varias bases de datos de Skype empresarial. servidores. Las listas de contactos se almacenan en el buzón de correo de Exchange online del usuario si el usuario está habilitado para ambos productos o en servidores de Skype empresarial si el usuario no lo está. Los servidores de base de datos de Skype empresarial no tienen particiones por inquilino, pero el aislamiento de datos de varios inquilinos se aplica a través de RBAC.
- El contenido de la reunión, como los usuarios de contenido que se cargan durante las reuniones de Skype empresarial, se almacena en recursos compartidos del sistema de archivos distribuido. Este contenido también se puede archivar en Exchange Online el archivado proporcionado está habilitado. Los recursos compartidos DFS no tienen particiones por inquilino, pero el contenido está protegido con ACL y la función de multiinquilino se aplica a través de RBAC.
- Los registros de detalles de llamadas, que son el historial de actividades, como el historial de llamadas, las sesiones de mensajería instantánea, el uso compartido de aplicaciones, el historial de mi, etc., también se pueden almacenar en Exchange Online, pero la mayoría de los registros de detalles de llamadas se almacenan temporalmente en los servidores de registro de detalles de llamadas (CDR). El contenido no se divide en particiones por inquilino, pero la función de multiinquilino se aplica a través de RBAC.

## <a name="sharepoint-online"></a>SharePoint Online
Hay varios mecanismos independientes exclusivos de SharePoint Online que proporcionan aislamiento de datos. SharePoint Online almacena objetos como código abstracto dentro de las bases de datos de la aplicación. Por ejemplo, cuando un usuario carga un archivo en SharePoint Online, ese archivo se desmonta y se traduce a código de aplicación y se almacena en varias tablas en varias bases de datos.

Si un usuario puede obtener acceso directo al almacenamiento que contiene los datos, el contenido no se puede interpretar como un usuario ni un sistema que no sea SharePoint Online. Estos mecanismos incluyen las propiedades y el control de acceso de seguridad. Como se ha descrito anteriormente, todos los recursos de SharePoint Online están protegidos por el código de autorización y la Directiva RBAC, incluso dentro de un arrendamiento. La lista de control de acceso (ACL) que protege a un recurso contiene una identidad que se autentica en el nivel de inquilino. Al igual que con Exchange Online, en SharePoint Online, los datos de un inquilino determinado se limitan a identidades autenticadas en el proveedor de autenticación de ese inquilino, que solo incluyen usuarios de ese espacio empresarial.

Además de las ACL, una propiedad de nivel de inquilino que especifica el proveedor de autenticación (que es el Azure Active Directory específico del inquilino), se escribe una vez y no se puede cambiar una vez establecido. Una vez que se ha establecido la propiedad de inquilino de proveedor de autenticación para un espacio empresarial, no se puede cambiar mediante ninguna API expuesta a un inquilino.

También se usa un *SubscriptionId* único para cada inquilino. Todos los sitios de clientes son propiedad de un espacio empresarial y tienen asignado un *SubscriptionId* único para el inquilino. La propiedad *SubscriptionId* de un sitio se ha escrito una vez y no se puede cambiar. Una vez que se asigna un sitio a un inquilino, no se puede mover a un inquilino diferente más adelante mediante la API de almacén de contenido. *SubscriptionId* también es la clave que se usa para crear el ámbito de seguridad para el proveedor de autenticación y está ligada al espacio empresarial.

SharePoint Online usa SQL Server y Azure Storage para el almacenamiento de contenido. En el nivel de SQL, la clave de partición del almacén de contenido es *SiteId*. Cuando se ejecuta una consulta SQL, SharePoint Online usa un *SiteId* que se ha comprobado como parte de una comprobación de *SubscriptionId* a nivel de inquilino.

SharePoint Online almacena blobs binarios de archivo (por ejemplo, las secuencias de archivos) en Microsoft Azure. Cada granja de servidores de SharePoint Online tiene su propia cuenta de Microsoft Azure y todos los blobs guardados en Azure se cifran individualmente con una clave que se almacena en el almacén de contenido de SQL. La clave de cifrado no se expone directamente al usuario final y está protegida en el código por la capa de autorización. Por último, SharePoint Online tiene una supervisión en tiempo real para detectar cuándo una solicitud HTTP lee o escribe datos para más de un espacio empresarial. Para ello, realiza un seguimiento del *subscriptionId* de la identidad de solicitud con el *subscriptionId* del recurso al que se está accediendo. Una solicitud que tiene acceso a recursos de más de un espacio empresarial nunca debe realizarla el usuario final. Sin embargo, puede suceder para solicitudes de servicio en un entorno de varios inquilinos. Por ejemplo, el rastreador de búsqueda extrae los cambios de contenido de toda la base de datos a la vez. Normalmente esto implica consultar sitios de más de un espacio empresarial en una sola solicitud de servicio, que se realiza por motivos de eficiencia.
