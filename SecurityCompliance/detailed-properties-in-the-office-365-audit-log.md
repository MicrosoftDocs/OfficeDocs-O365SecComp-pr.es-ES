---
title: Propiedades detalladas del registro de auditoría de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: DeScripciones de las propiedades adicionales que se incluyen en un registro de auditoría de Office 365.
ms.openlocfilehash: f64b514b777c08048e0f904c17e21c235f8a6f23
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257658"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Propiedades detalladas del registro de auditoría de Office 365

Al exportar los resultados de una búsqueda de registros de auditoría desde el centro de seguridad & cumplimiento, tiene la opción de descargar todos los resultados que cumplan los criterios de búsqueda. Para ello, seleccione **exportar resultados** \> **descargar todos los resultados** en la página de **búsqueda de registros de auditoría** . Para obtener más información, vea [Buscar en el registro de auditoría en el Office 365](search-the-audit-log-in-security-and-compliance.md).
  
 Cuando se exportan todos los resultados de una búsqueda de registro de auditoría, los datos sin procesar del registro de auditoría unificada de Office 365 se copian a un archivo de valores separados por comas (CSV) que se descargan en el equipo local. Este archivo contiene información adicional de la entrada del registro de auditoría en una columna denominada **detalles**. Esta columna contiene una propiedad de varios valores para varias propiedades del registro de auditoría. Cada uno de los pares **propiedad: valor** de esta propiedad de varios valores se separan con una coma. 
  
En la tabla siguiente se describen las propiedades que se incluyen (según el servicio de Office 365 en el que se produce un evento) en la columna de **detalle** de múltiples propiedades. El **servicio de Office 365 que tiene esta** columna de propiedad indica el servicio y el tipo de actividad (usuario o administrador) que incluye la propiedad. Para obtener información más detallada acerca de estas propiedades o sobre las propiedades que podrían no aparecer en este tema, consulte [Office 365 Management Activity Schema API](https://go.microsoft.com/fwlink/p/?LinkId=717993).
  
> [!TIP]
> Puede usar la consulta Power en Excel para dividir esta columna en varias columnas para que cada propiedad tenga su propia columna. Esto le permitirá ordenar y filtrar por una o varias de estas propiedades. Para obtener información sobre cómo hacerlo, vea la sección "dividir una columna por delimitador" en [dividir una columna de texto (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662). 
  
|**Propiedad**|**Descripción**|**Servicio de Office 365 que tiene esta propiedad**|
|:-----|:-----|:-----|
|Actor|La cuenta de servicio o usuario que realizó la acción.|Azure Active Directory|
|AddOnName|El nombre de un complemento que se agregó, quitó o actualizó en un equipo. El tipo de complementos de Microsoft Teams es un bot, un conector o una pestaña.|Microsoft Teams|
|AddOnType|El tipo de complemento que se ha agregado, quitado o actualizado en un equipo. Los siguientes valores indican el tipo de complemento.  <br/> **1** -indica un bot.<br/> **2** -indica un conector.<br/> **3** -indica una tabulación.|Microsoft Teams|
|AzureActiveDirectoryEventType|El tipo de evento de Azure Active Directory. Los siguientes valores indican el tipo de evento.  <br/> **0** -indica un evento de inicio de sesión de cuenta.<br/> **1** -indica un evento de seguridad de la aplicación de Azure.|Azure Active Directory|
|ChannelGuid|El identificador de un canal de Microsoft Teams. El equipo en el que se encuentra el canal se identifica mediante las propiedades **TeamName** y **TeamGuid** .|Microsoft Teams|
|ChannelName|El nombre de un canal de Microsoft Teams. El equipo en el que se encuentra el canal se identifica mediante las propiedades **TeamName** y **TeamGuid** .|Microsoft Teams|
|Client|El dispositivo cliente, el sistema operativo del dispositivo y el explorador del dispositivo usado para el evento de inicio de sesión (por ejemplo, Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Información sobre el cliente de correo electrónico que se usó para realizar la operación, como la versión de explorador, la versión de Outlook y la información del dispositivo móvil.|Exchange (actividad de buzón de correo)|
|ClientIP|La dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.|Exchange y Azure Active Directory|
|ClientIPAddress|Igual que ClientIP.|SharePoint|
|CreationTime|La fecha y hora en formato Hora universal coordinada (UTC) en las que el usuario ha realizado la actividad.|Todo|
|DestinationFileExtension|La extensión del archivo que se copia o mueve. Esta propiedad solo se muestra para las actividades de usuario de los y FileMoved.|SharePoint|
|DestinationFileName|El nombre del archivo se copia o se mueve. Esta propiedad solo se muestra para las acciones los y FileMoved.|SharePoint|
|DestinationRelativeUrl|La dirección URL de la carpeta de destino donde se copia o se mueve un archivo. La combinación de los valores de **SiteURL**, **DestinationRelativeURL**y las propiedades **DestinationFileName** es igual que el valor de la propiedad **objectId** , que es el nombre de la ruta de acceso completa del archivo que se copió. Esta propiedad solo se muestra para las actividades de usuario de los y FileMoved.|SharePoint|
|EventSource|Identifica que un evento se produjo en SharePoint. Los valores posibles son **SharePoint** y **ObjectModel**.|SharePoint|
|ExternalAccess|Para la actividad de administración de Exchange, especifica si un usuario de la organización ejecutó el cmdlet, el personal del centro de administración de Microsoft o una cuenta de servicio de centro de recursos, o un administrador delegado. El valor **False** indica que el cmdlet lo ejecutó algún usuario de su organización. El valor **True** indica que el cmdlet lo ejecutó el personal del centros de datos, una cuenta de servicio del centro de datos o un administrador delegado.  <br/> Para la actividad de buzón de correo de Exchange, especifica si un usuario de fuera de la organización obtuvo acceso a un buzón.|Exchange|
|ExtendedProperties|Las propiedades extendidas de un evento de Azure Active Directory.|Azure Active Directory|
|ID|IDENTIFICADOR de la entrada de informe. El identificador identifica de forma única la entrada del informe.|Todo|
|InternalLogonType|Reservado para uso interno.|Exchange (actividad de buzón de correo)|
|ItemType|El tipo de objeto al que se obtuvo acceso o que se modificó. Los valores posibles son **File**, **Folder**, **Web**, **site**, **tenant**y **DocumentLibrary**.|SharePoint|
|LoginStatus|Identifica los errores de inicio de sesión que pueden haberse producido.|Azure Active Directory|
|LogonType|Tipo de acceso al buzón. Los siguientes valores indican el tipo de usuario que ha tenido acceso al buzón.  <br/><br/> **0** -indica un propietario del buzón.<br/> **1** -indica un administrador.<br/> **2** -indica un delegado. <br/>**3** -indica el servicio de transporte en el centro de servicios de Microsoft.<br/> **4** : indica una cuenta de servicio en el centro de recursos de Microsoft. <br/>**6** -indica un administrador delegado.|Exchange (actividad de buzón de correo)|
|MailboxGuid|El GUID de Exchange del buzón al que se obtuvo acceso.|Exchange (actividad de buzón de correo)|
|MailboxOwnerUPN|La dirección de correo electrónico del propietario del buzón al que se obtuvo acceso.|Exchange (actividad de buzón de correo)|
|Members|Enumera los usuarios que se han agregado o quitado de un equipo. Los siguientes valores indican el tipo de rol asignado al usuario.  <br/><br/> **1** : indica el rol de propietario.<br/> **2** -indica el rol del miembro.<br/> **3** -indica el rol invitado. <br/><br/>La propiedad Members también incluye el nombre de su organización y la dirección de correo electrónico del miembro.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|La propiedad se incluye para los eventos de administración, como agregar un usuario como miembro de un sitio o un grupo de administradores de colección de sitios. La propiedad incluye el nombre de la propiedad que se modificó (por ejemplo, el grupo de administradores del sitio) el nuevo valor de la propiedad Modified (el usuario que se agregó como administrador del sitio y el valor anterior del objeto modificado.|All (actividad de administración)|
|ObjectID|Para el registro de auditoría de Exchange, el nombre del objeto modificado por el cmdlet.  <br/> Para la actividad de SharePoint, el nombre completo de la ruta de acceso de la dirección URL del archivo o la carpeta a los que ha tenido acceso un usuario.  <br/> Para actividad de Azure AD, el nombre de la cuenta de usuario que se modificó.|Todo|
|Operación|El nombre de la actividad de usuario o administrador. El valor de esta propiedad corresponde al valor que se seleccionó en la lista desplegable de **actividades** . Si se ha seleccionado **Mostrar resultados para todas las actividades** , el informe incluirá entradas para todas las actividades de usuario y de administrador para todos los servicios. Para obtener una descripción de las operaciones o actividades que se registran en el registro de auditoría de Office 365, consulte la ficha **actividades auditadas** en [Buscar en el registro de auditoría de la Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> Esta propiedad identifica el nombre del cmdlet ejecutado para la actividad de administración de Exchange.|Todo|
|OrganizationID|El GUID de la organización de Office 365.|Todo|
|Path|El nombre de la carpeta del buzón donde se encuentra el mensaje al que se obtuvo acceso. Esta propiedad también identifica la carpeta a donde se crea o se copia o se mueve un mensaje.|Exchange (actividad de buzón de correo)|
|Parameters|Para la actividad de administración de Exchange, el nombre y el valor de todos los parámetros que se usaron con el cmdlet que se identifica en la propiedad Operation.|Exchange (actividad de administración)|
|RecordType|El tipo de operación indicado por el registro. Los siguientes valores indican el tipo de registro.  <br/><br/> **1** -indica un registro del registro de auditoría de administración de Exchange. <br/>**2** -indica un registro del registro de auditoría de buzoNes de Exchange para una operación realizada en un elemento de buzón de correo único. <br/>**3** : también indica un registro del registro de auditoría de buzones de Exchange. Este tipo de registro indica que la operación se realizó en varios elementos en el buzón de origen (como mover varios elementos a la carpeta elementos eliminados o eliminar de forma permanente varios elementos). <br/>**4** : indica una operación de administrador del sitio en SharePoint, como un administrador o un usuario que asigna permisos a un sitio. <br/>**6** -indica una operación relacionada con un archivo o una carpeta en SharePoint, como un usuario que visualiza o modifica un archivo. <br/>**8** : indica una operación de administración realizada en Azure Active Directory. <br/>**9** : indica eventos de inicio de sesión de OrgId en Azure Active Directory. Este tipo de registro está en desuso. <br/>**10** : indica eventos de cmdlet de seguridad realizados por el personal de Microsoft en el centro de datos. <br/>**11** : indica eventos de protección contra la pérdida de datos (DLP) en SharePoint.<br/> **12** : indica los eventos de Sway. <br/>**13** : indica los eventos DLP en Exchange, cuando se configura con una directiva DLP unificada. No se admiten eventos DLP basados en reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).<br>**14** : indica los eventos de uso compartido en SharePoint.<br/> **15** -indica eventos de inicio de sesión del servicio de token seguro (STS) en Azure Active Directory. <br/>**18** : indica los eventos del centro de cumplimiento de _AMP_ de seguridad. <br/>**20** : indica eventos de Power BI. <br/>**21**: indica los eventos de Dynamics 365.<br/>**22** : indica eventos de Yammer. <br/>**23** : indica eventos de Skype empresarial. <br/>**24** : indica eventos de eDiscovery. Este tipo de registro indica actividades que se llevaron a cabo al ejecutar búsquedas de contenido y administrar casos de eDiscovery en el centro de seguridad y cumplimiento. Para obtener más información, vea [buscar actividades de eDiscovery en el registro de auditoría de Office 365](search-for-ediscovery-activities-in-the-audit-log.md).<br/>**25, 26 o 27** -indica eventos de Microsoft Teams. <br/>**28** : indica eventos de suplantación de identidad y malware de eventos de Exchange Online Protection y Office 365 Advanced Threat Protection.<br/> **30** : indica los eventos de flujo de Microsoft.<br/> **32** : eventos de Microsoft Stream indicados.<br/> **35** : indica los eventos de Microsoft Project. <br/> **36** : indica los eventos de la lista de SharePoint.<br/> **38** : indica eventos relacionados con las directivas de retención y las etiquetas de retención en el centro de seguridad y cumplimiento.  <br/>**40** : indica los eventos que se producen a partir de las señales de alerta de seguridad y cumplimiento.<br/> **41** : indica los eventos de bloqueo seguro de tiempo de bloqueo y de invalidación de bloqueo en Office 365 protección contra amenazas avanzada.<br/>**44** : indica los eventos del análisis de área de trabajo. <br/>**45** : indica los eventos de la aplicación PowerApps. <br/> **47** : indica eventos de suplantación de identidad y malware de la protección contra amenazas avanzada de Office 365 para archivos en SharePoint, OneDrive y Microsoft Teams.|Todo|
|ResultStatus|Indica si la acción (especificada en la propiedad **Operation** ) se ha realizado correctamente o no.  <br/> Para la actividad de administración de Exchange, el valor puede ser **true** (correcto) o **false** (error).|Todo  <br/>|
|SecurityComplianceCenterEventType|Indica que la actividad fue un evento del centro de cumplimiento de & de seguridad. Todas las actividades del centro de seguridad & cumplimiento tendrán un valor de **0** para esta propiedad.|Centro de seguridad y cumplimiento|
|SharingType|El tipo de permisos de uso compartido que se asignó al usuario con el que se compartió el recurso. Este usuario se identifica en la propiedad **UserSharedWith** .|SharePoint|
|Sitio|El GUID del sitio donde se encuentra el archivo o la carpeta a la que obtuvo acceso el usuario.|SharePoint|
|SiteUrl|La dirección URL del sitio donde se encuentra el archivo o la carpeta a la que obtuvo acceso el usuario.|SharePoint|
|SourceFileExtension|La extensión del archivo al que obtuvo acceso el usuario. Esta propiedad está en blanco si el objeto al que se obtuvo acceso es una carpeta.|SharePoint|
|SourceFileName|El nombre del archivo o carpeta al que obtuvo acceso el usuario.|SharePoint|
|SourceRelativeUrl|La dirección URL de la carpeta que contiene el archivo al que obtuvo acceso el usuario. La combinación de los valores de las propiedades **SiteURL**, **SourceRelativeURL**y **SourceFileName** es la misma que el valor de la propiedad **objectId** , que es el nombre de ruta completo del archivo al que ha tenido acceso el usuario.|SharePoint|
|Subject|La línea de asunto del mensaje al que se obtuvo acceso.|Exchange (actividad de buzón de correo)|
|TabType| Tipo de ficha agregada, eliminada o actualizada en un equipo. Los valores posibles de esta propiedad son:  <br/><br/> **Excelpin** : una pestaña de Excel.  <br/> **Extensión** : todas las aplicaciones de origen y de terceros; como Planner, VSTS y Forms.  <br/> **Notas** : pestaña OneNote.  <br/> **Pdfpin** : una ficha PDF.  <br/> **Powerbi** -una pestaña de powerbi.  <br/> **Powerpointpin** : una pestaña de PowerPoint.  <br/> **Sharepointfiles** : una pestaña de SharePoint.  <br/> **Página Web** : ficha de un sitio web anclado.  <br/> **Wiki: pestaña** : ficha wiki.  <br/> **Wordpin** : una pestaña de Word.|Microsoft Teams|
|Target|El usuario en el que se realizó la acción (identificada en la propiedad **Operation** ) en. Por ejemplo, si se agrega un usuario Guest a SharePoint o a un equipo de Microsoft, dicho usuario aparecerá en esta propiedad.|Azure Active Directory|
|TeamGuid|El identificador de un equipo en Microsoft Teams.|Microsoft Teams|
|TeamName|El nombre de un equipo en Microsoft Teams.|Microsoft Teams|
|UserAgent|Información sobre el explorador del usuario. Esta información la proporciona el explorador.|SharePoint|
|UserDomain|Información de identidad sobre la organización del espacio empresarial del usuario (actor) que realizó la acción.|Azure Active Directory|
|Identificado|El usuario que realizó la acción (especificado en la propiedad **Operation** ) que resultó en el registro que se está registrando. Tenga en cuenta que los registros de la actividad realizada por las cuentas del sistema (como SHAREPOINT\system o NT AUTHORITY\SYSTEM) también se incluyen en el registro de auditoría.|Todo|
|UserKey|Un identificador alternativo para el usuario identificado en la propiedad **userid** . Por ejemplo, esta propiedad se rellena con el identificador único de Passport (PUID) para los eventos realizados por los usuarios en SharePoint. Esta propiedad también puede especificar el mismo valor que la propiedad **userid** para los eventos que se producen en otros servicios y eventos que realizan las cuentas del sistema.|Todo|
|UserSharedWith|El usuario con el que se compartió un recurso. Esta propiedad se incluye si el valor de la propiedad **Operation** es **SharingSet**. Este usuario también aparece en la columna **compartido con** en el informe.|SharePoint|
|UserType|El tipo de usuario que llevó a cabo la operación. Los siguientes valores indican el tipo de usuario. <br/> <br/> **0** : un usuario normal. <br/>**2** -un administrador de la organización de Office 365. <br/>**3** -una cuenta de administrador o de centro de recursos de Microsoft Datacenter. <br/>**4** : una cuenta del sistema. <br/>**5** : una aplicación. <br/>**6** : una entidad de servicio.<br/>**7** : una directiva personalizada.<br/>**8** : una directiva del sistema.|Todo|
|Versión|Indica el número de versión de la actividad (identificado por la propiedad **Operation** ) que se registra.|Todo|
|Carga de trabajo|El servicio de Office 365 donde se produjo la actividad. Los valores posibles de esta propiedad son:  <br/> <br/>**SharePoint<br/>de<br/>Exchange<br/>AzureActiveDirectory<br/>de<br/>DataCenterSecurity<br/>de<br/>OneDrive para Skype<br/>empresarial<br/>SecurityComplianceCenter<br/>de PowerBI CRM<br/>Yammer<br/>Microsoft Teams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>Project<br/>PowerApps<br/>análisis de espacio de trabajo**|Todo|
||||
   
Tenga en cuenta que las propiedades descritas anteriormente también se muestran al hacer clic en **más información** al ver los detalles de un evento específico. 
  
![Haga clic en más información para ver las propiedades detalladas del registro de sucesos del registro de auditoría](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

