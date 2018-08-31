---
title: Aislamiento de Office 365 y Control de acceso en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Una explicación de aislamiento y control de acceso dentro de las distintas aplicaciones de Office 365.'
ms.openlocfilehash: c1989bc546df357740ea963a1a241dfa14557931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536748"
---
# <a name="isolation-and-access-control-in-office-365"></a>Aislamiento y Control de acceso en Office 365

Office 365 y Azure Active Directory usan un modelo de datos altamente complejo que incluye decenas de servicios, cientos de entidades, miles de relaciones y decenas de miles de atributos (entidades, relaciones y atributos suelen ser específicos de la aplicación). En un nivel alto, Azure Active Directory y los directorios del servicio son los contenedores de los inquilinos y destinatarios y se mantienen sincronizados con los protocolos de replicación basada en el estado. Además de la información de Active directory se conserva dentro de Azure Active Directory, cada uno de los servicios tiene su propia infraestructura de servicios de directorio (por ejemplo, servicios de directorio de Exchange Online, SharePoint Online Directory Services, etcetera). 
 
![Sincronización de datos del inquilino de Office 365](media/office-365-isolation-tenant-data-sync.png)

Dentro de este modelo, no hay ningún origen de datos de Active directory único. Cada parte individual de datos pertenece a un sistema específico, pero ningún sistema único contiene todos los datos. Servicios de Office 365 cooperan con Azure Active Directory para obtener el modelo de datos. Azure Active Directory es el "sistema de verdad" para los datos compartidos, que normalmente son pequeños y estáticos datos utilizados con frecuencia por cada servicio. El modelo federado usado en Office 365 y Azure Active Directory proporciona la vista compartida de los datos.

Office 365 usa almacenamiento físico y el almacenamiento de Azure en la nube. Exchange Online (incluido Exchange Online Protection) y Skype para la empresa utilizan su propio almacenamiento de información para los datos de cliente. SharePoint Online aprovecha su almacenamiento de SQL Server y el almacenamiento de Azure, lo que necesita la necesidad de aislamiento adicionales de los datos de cliente en el nivel de almacenamiento.

## <a name="exchange-online"></a>Exchange Online
Exchange Online almacena datos de los clientes dentro de los buzones de correo que se hospedan dentro de las bases de datos de motor de almacenamiento Extensible (ESE) denominados bases de datos de buzón de correo. Esto incluye los buzones de usuario, buzones de correo vinculados, buzones de correo compartidos y buzones de carpetas públicas. Los buzones de usuario también pueden incluir guardada Skype para contenido empresarial, como los historiales de conversación. El contenido del buzón de usuario incluye mensajes de correo electrónico y datos adjuntos de correo electrónico, información de libre/ocupado y el calendario, contactos, tareas, notas, grupos y datos de inferencia.

Cada base de datos de buzón de correo de Exchange Online contiene los buzones de correo de varios inquilinos. Todos los buzones se protegen mediante código de autorización, incluido dentro de un arrendamiento. Como con una implementación local de Exchange, de forma predeterminada sólo el usuario asignado tiene acceso a un buzón de correo. La lista de control de acceso (ACL) que protege un buzón de correo contiene una identidad que se autentica mediante Active Directory en el nivel de inquilino de Azure. Los buzones de correo para un determinado inquilino se limitan a las identidades autenticadas con el proveedor de autenticación que multiempresa, que incluyen sólo los usuarios de ese inquilino. Contenido que pertenecen a TenantA no en modo alguno pueden obtenerse por los usuarios de TenantB, a menos que estén aprobados explícitamente por TenantA.

## <a name="skype-for-business"></a>Skype Empresarial
Skype para la empresa almacena los datos en varios lugares:
- Cuenta de información, que incluye los extremos de la conexión, identificadores de arrendatario, planes de marcado, configuración, estado de presencia, las listas de contactos, etc., de movilidad y de usuario se almacena en la Skype para los servidores de Active Directory de negocio, así como en diversas Skype para la base de datos empresariales servidores. Las listas de contactos se almacenan en el buzón del usuario Exchange Online Si el usuario está habilitado para ambos productos, o en Skype para servidores empresariales si el usuario no es. Skype para los servidores de base de datos de negocio no están divididas por inquilino, pero se exige el aislamiento de multiempresa de los datos a través de RBAC.
- Contenido, de las reuniones, como contenido a los usuarios cargan durante Skype para reuniones de negocios, se almacenan en los recursos compartidos del sistema de archivos distribuido. Este contenido también se puede archivar en Exchange Online siempre está habilitado el archivado. Los recursos compartidos DFS no están divididas por inquilino, pero se protege el contenido con las ACL y varios inquilinos se aplican a través de RBAC.
- Registros de detalles de llamadas, que es el historial de actividad, como historial de llamadas, sesiones de mensajería instantánea, uso compartido de aplicaciones, historial de mensajería instantánea, etc., también se pueden almacenar en Exchange Online, pero la mayoría de los registros de detalles de llamadas se almacena temporalmente en los servidores de registro (CDR) de todos los detalles de llamada. Contenido no se divide por inquilino, pero multiempresa se aplica a través de RBAC.

## <a name="sharepoint-online"></a>SharePoint Online
Existen varios mecanismos independientes único a SharePoint Online que proporcionan el aislamiento de datos. SharePoint Online almacena objetos como abstracta código dentro de las bases de datos de aplicación. Por ejemplo, cuando un usuario carga un archivo en SharePoint Online, ese archivo se desmontar y traducir a código de la aplicación y se almacena en varias tablas a través de varias bases de datos.

Si un usuario podría obtener acceso directo al almacenamiento de información que contiene los datos, el contenido no sería puedan interpretar a una persona o un sistema distinto de SharePoint Online. Estos mecanismos incluyen propiedades y control de acceso de seguridad. Como se describió anteriormente, todos los recursos de SharePoint Online se protegen mediante el código de autorización y la directiva de RBAC, incluido dentro de un arrendamiento. La lista de control de acceso (ACL) que protege un recurso contiene una identidad que se autentica en el nivel de inquilino. Al igual que con Exchange Online, SharePoint Online, datos de un determinado inquilino se limitan a las identidades autenticadas con el proveedor de autenticación que multiempresa, que incluyen sólo los usuarios de ese inquilino.

Además de las ACL, una propiedad de nivel de inquilino que especifica el proveedor de autenticación (que es específica de inquilinos Azure Active Directory), se escribe una vez y no se puede cambiar una vez establecida. Una vez que se ha establecido la propiedad inquilino de proveedor de autenticación para un inquilino, no se puede cambiar mediante cualquier API expuestas a un inquilino.

Un único *SubscriptionId* también se usa para cada inquilino. Todos los sitios de los clientes son propiedad de un inquilino y se asignan a un único *SubscriptionId* para el inquilino. La propiedad *SubscriptionId* en un sitio se escribe una vez y no se puede cambiar. Una vez que se asigna un sitio a un inquilino, no se puede mover a un inquilino diferente más adelante mediante la API del almacén de contenido. El *SubscriptionId* también es la clave que se usa para crear el ámbito de la seguridad para el proveedor de autenticación y está relacionada con el inquilino.

SharePoint Online utiliza almacenamiento de Azure y SQL Server para el almacenamiento de contenido. En el nivel de SQL, la clave de partición del almacén de contenido es *SiteId*. Cuando se ejecuta una consulta SQL, SharePoint Online usa un *SiteId* que se ha comprobado como parte de una comprobación de *SubscriptionId* inquilino.

SharePoint Online almacena objetos BLOB binarios de archivo (por ejemplo, las secuencias de archivo) en Microsoft Azure. Cada granja de servidores de SharePoint Online tiene su propia cuenta de Microsoft Azure y se cifran todos los BLOB guardados en Azure individualmente mediante una clave que se almacena en el almacén de contenido de SQL. La clave de cifrado no se expone directamente a los usuarios finales y está protegida en el código por la capa de autorización. Por último, SharePoint Online tiene la supervisión en tiempo real en su lugar para detectar cuándo una solicitud HTTP lee o escribe los datos de más de un inquilino. Esto hace seguimiento el *SubscriptionId* de la identidad de la solicitud contra la *SubscriptionId* del recurso que se tiene acceso. Una solicitud de acceso a los recursos de más de un inquilino nunca debe producirse por el usuario final. Puede ocurrir aunque las solicitudes de servicio en un entorno de varios inquilino. Por ejemplo, el Rastreador de búsqueda extrae los cambios en el contenido de una base de datos completa a la vez. Normalmente, esto implica consultar sitios del inquilino más de una en una solicitud de servicio único, que se realiza por motivos de eficacia.
