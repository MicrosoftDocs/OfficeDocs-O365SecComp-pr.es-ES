---
title: Trabajar con un partner para archivar datos de terceros en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Su organización puede trabajar con un socio de Microsoft para configurar un conector personalizado para importar datos de terceros desde orígenes de datos como Salesforce chatter, Yahoo Messenger o Yammer. Esto le permite archivar datos de orígenes de datos de terceros en Office 365 para poder usar las características de cumplimiento de Office 365, como directivas de retención, búsqueda de contenido y retención legal para administrar el gobierno de los datos de terceros de la organización.
ms.openlocfilehash: 99596953ce0f18c0cd7220f0955d251dbccb0e37
ms.sourcegitcommit: 372691a3a886e5cc299961032ee334aef26fb904
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464703"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a>Trabajar con un partner para archivar datos de terceros en Office 365

Puede trabajar con un socio de Microsoft para importar y archivar datos desde un origen de datos de terceros a Office 365. Un asociado puede proporcionarle un conector personalizado que está configurado para extraer elementos del origen de datos de terceros (de forma periódica) y, a continuación, importar dichos elementos a Office 365. El conector de asociados convierte el contenido de un elemento del origen de datos en un formato de mensaje de correo electrónico y, a continuación, almacena los elementos en los buzones de Office 365. Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Office 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría y las directivas de retención de Office 365 a estos datos.
  
A continuación, se presenta una introducción al proceso y los pasos necesarios para trabajar con un socio de Microsoft para importar datos de terceros a Office 365.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Step 2: Create and configure a third-party data mailbox in Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[Paso 4: Proporcionar información al asociado](#step-4-provide-your-partner-with-information)

[Paso 5: registrar el conector de datos de terceros en Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Cómo funciona el proceso de importación de datos de terceros

En la siguiente ilustración y descripción se explica cómo funciona el proceso de importación de datos de terceros al trabajar con un partner.
  
![Cómo funciona el proceso de importación de datos de terceros](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. El cliente trabaja con su compañero de elección para configurar un conector que extraerá elementos del origen de datos de terceros y, a continuación, importará dichos elementos a Office 365.
    
2. El conector del asociado se conecta a orígenes de datos de terceros a través de una API de terceros (en una base programada o configurada) y extrae elementos del origen de datos. El conector asociado convierte el contenido de un elemento en un formato de mensaje de correo electrónico. Consulte la sección [More Information](#more-information) para obtener una descripción del esquema de formato de mensaje. 
    
3. El conector del asociado se conecta al servicio de Azure en Office 365 mediante el servicio Web Exchange (EWS) a través de un punto final conocido.
    
4. Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:
    
    a. **Elementos que tienen un identificador de usuario correspondiente a una cuenta de usuario de Office 365:** Si el conector del asociado puede asignar el identificador de usuario del elemento del origen de datos de terceros a un identificador de usuario específico en Office 365, el elemento se copia en **** la carpeta depuraciones de la carpeta elementos recuperables del usuario. Los usuarios no pueden acceder a los elementos de esta carpeta. Sin embargo, puede usar las herramientas de Office 365 eDiscovery para buscar elementos en la carpeta depuraciones.
    
    b. **Elementos que no tienen un identificador de usuario correspondiente a una cuenta de usuario de Office 365:** Si el conector del asociado no puede asignar el identificador de usuario de un elemento a un identificador de usuario específico en Office 365, el elemento se copia en la carpeta **bandeja de entrada** del buzón de datos de terceros. La importación de elementos a la Bandeja de entrada permite que usted u otra persona de la organización inicie sesión en el buzón de correo de terceros para ver y administrar estos elementos, y ver si es necesario realizar ajustes en la configuración del conector asociado.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Paso 1: Buscar un asociado de datos de terceros

Un componente clave para archivar datos de terceros en Office 365 es encontrar y trabajar con un socio de Microsoft que se especializa en capturar datos de un origen de datos de terceros e importarlos a Office 365. Una vez importados los datos, se pueden archivar y conservar junto con los otros datos de Microsoft de la organización, como el correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa. Un asociado crea un conector que extrae datos de los orígenes de datos de terceros de la organización (como BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa los datos a una API de Office 365 que importa elementos a buzones de Exchange como mensajes de correo electrónico. 
  
En las secciones siguientes se enumeran los socios de Microsoft (y los orígenes de datos de terceros que admiten) que participan en el programa para archivar datos de terceros en Office 365.

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verboa](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

17a-4 LLC admite los siguientes orígenes de datos de terceros:
  
- BlackBerry
    
- Secuencias de datos de Bloomberg
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- Secuencias de datos de MessageLabs
    
- OpenText
    
- Ayuda de Hacer clic para llamar de Oracle/ATG Live
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype Empresarial (Lync/OCS)
    
- Skype Empresarial Online (Lync Online)
    
- Bases de datos SQL
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com) admite los siguientes orígenes de datos de terceros: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com) admite los siguientes orígenes de datos de terceros: 
  
- AOL con cliente Pivot 
    
- Registros de llamadas de BlackBerry (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Chat
    
- Bloomberg Mail
    
- Cuadro
    
- CipherCloud para Salesforce Chatter
    
- Servidor de &amp; presencia de mensajería instantánea de Cisco (V10, v 10.5.1 SU1, v 11.0, v 11,5 SU2)

- Equipos Cisco WebEx

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- Archivos de texto delimitados personalizados
    
- Archivos XML personalizados
    
- Facebook (páginas)
    
- Factset
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive para la Empresa

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter

- Skype Empresarial Online
    
- Skype Empresarial, versiones 2007 R2 - 2016 (local)
    
- Slack Enterprise Grid
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- Twitter
    
- UBS Chat
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) admite los siguientes orígenes de datos de terceros: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) admite los siguientes orígenes de datos de terceros: 
  
- APUNTA
    
- American Idol
    
- Apple Juice
    
- AOL con cliente Pivot
    
- Áreas
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- Registros de llamadas de BlackBerry (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Mail
    
- CellTrust
    
- Importación de chat
    
- Directiva y registro en tiempo real de chat
    
- Flanco
    
- Servidor de &amp; presencia de mensajería instantánea de Cisco (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)
    
- Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)
    
- Importación de colaboración
    
- Registro de colaboración en tiempo real
    
- Conexión directa
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google +
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/YellowJacket
    
- Importación de mensajería instantánea
    
- Directiva y registro de mensajería instantánea en tiempo real
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 Real Time Logging (v6, v7)
    
- Jive Import
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010, 2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010, 2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- Fotos
    
- My Space
    
- Subred
    
- Office 365 Lync Dedicated
    
- Mensajería instantánea compartida de Office 365
    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype Empresarial 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Términos
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Toolbar
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verboa

[Verboa](https://www.verba.com) admite los siguientes orígenes de datos de terceros: 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Cisco Jabber IM
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Vídeo de Cisco UCCX/UCCE
    
- Cisco UCCX/UCCE de voz
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Centro de contacto de Luware LUCS
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Vídeo de controlador de borde de sesión de paquete Oracle/Acme
    
- Voz de controlador de borde de sesión de paquete Oracle/Acme
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- Skype Empresarial/MI de Lync
    
- Skype Empresarial/Vídeo de Lync
    
- Skype Empresarial/Voz de Lync
    
- Speakerbus Voice
    
- Standard SIP/H.323 Video
    
- Standard SIP/H.323 Voice
    
- Truphone Voice
    
- TwistedPair Radio
    
- Pantalla de equipo de escritorio de Windows
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>Paso 2: Crear y configurar un buzón de datos de terceros en Office 365

Estos son los pasos para crear y configurar un buzón de datos de terceros para importar datos a Office 365. Como se explicó anteriormente, los elementos se importan a este buzón si el conector del asociado no puede asignar el identificador de usuario del elemento a una cuenta de usuario de Office 365.
  
 **Complete estas tareas en el centro de administración de 365 de Microsoft**
  
1. Cree una cuenta de usuario en Office 365 y asígnela una licencia de Exchange Online plan 2; vea [Agregar usuarios a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Se necesita una licencia de plan 2 para poner el buzón en retención por juicio o habilitar un buzón de archivo que tenga una cuota de almacenamiento ilimitada.
    
2. Agregue la cuenta de usuario para el buzón de datos de terceros a la función de administrador de **Administrador de Exchange** en Office 365; consulte [asignar roles de administrador en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).
    
    > [!TIP]
    > Escriba las credenciales para esta cuenta de usuario. Necesitará proporcionárselas a su socio, tal como se describe en el paso 4. 
  
 **Completar estas tareas en el centro de administración de Exchange**
  
1. Ocultar el buzón de datos de terceros de la libreta de direcciones y de otras listas de direcciones de la organización; consulte [Manage User mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Como alternativa, puede ejecutar el siguiente comando de PowerShell:
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Asignar el permiso **FullAccess** al buzón de datos de terceros para que los administradores o responsables de cumplimiento puedan abrir el buzón de datos de terceros en el cliente de escritorio de Outlook; consulte [administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Habilite las siguientes características de Office 365 relacionadas con el cumplimiento para el buzón de datos de terceros:
    
    - Habilitar el buzón de archivo; consulte [Habilitar](enable-archive-mailboxes.md) el archivado de buzones de archivo y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md). Esto le permite liberar espacio de almacenamiento en el buzón de correo principal mediante la configuración de una directiva de archivo que mueva los elementos de datos de terceros al buzón de archivo. Esto proporciona un almacenamiento ilimitado para los datos de terceros.
    
    - Coloque el buzón de datos de la tercera persona en retención por juicio. También puede aplicar una directiva de retención de Office 365 en el centro de seguridad y cumplimiento. Colocar este buzón de correo en retención retiene los elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evita que se purguen del buzón. Consulte uno de los siguientes temas:
    
      - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Introducción a las directivas de retención en Office 365](retention-policies.md)
    
       
    
    - Habilite el registro de auditoría del buzón para el acceso como propietario, delegado y administrador al buzón de datos de terceros; consulte [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). Esto le permite auditar todas las actividades realizadas por cualquier usuario que tenga acceso al buzón de datos de terceros.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Paso 3: Configurar los buzones de usuario para los datos de terceros

El paso siguiente es configurar los buzones de usuario para que admitan los datos de terceros. Complete estas tareas con el centro de administración de Exchange o con los cmdlets de Windows PowerShell correspondientes.
  
1. Habilitar el buzón de archivo para cada usuario; consulte [Habilitar](enable-archive-mailboxes.md) el archivado de buzones de archivo y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md).
    
2. Coloque los buzones de usuario en retención por juicio o aplique una directiva de retención de Office 365; Consulte uno de los siguientes temas: 
    
    - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Introducción a las directivas de retención en Office 365](retention-policies.md)
    
    Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.

## <a name="step-4-provide-your-partner-with-information"></a>Paso 4: Proporcionar información al asociado

El último paso es proporcionar a su asociado la información siguiente para que pueda configurar el conector y conectarse a su organización de Office 365 con el fin de importar datos a los buzones de usuario y al buzón de datos de terceros. 
  
- El extremo que se usa para conectarse al servicio de Azure en Office 365:

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Las credenciales de inicio de sesión (identificador de usuario y contraseña de Office 365) del buzón de datos de terceros que ha creado en el paso 2. Estas credenciales son necesarias para que el conector asociado pueda tener acceso e importar elementos a los buzones de usuario y al buzón de datos de un tercero.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Paso 5: registrar el conector de datos de terceros en Azure Active Directory

A partir del 30 de septiembre de 2018, el servicio de Azure en Office 365 empezará a usar la autenticación moderna en Exchange Online para autenticar conectores de datos de terceros que intenten conectarse a su organización de Office 365 para importar datos. El motivo de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se basaba en conectores de terceros de la lista blanca que usan el punto de conexión descrito anteriormente para conectarse al servicio de Azure.

Para permitir que un conector de datos de terceros se conecte a Office 365 mediante el nuevo método de autenticación moderna, un administrador de la organización de Office 365 debe dar su consentimiento para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory. Esto se realiza al aceptar una solicitud de permiso para permitir que el conector tenga acceso a los datos de la organización en Azure Active Directory. Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa a Azure Active Directory y se representa como una entidad de servicio. Para obtener más información sobre el proceso de consentimiento, consulte [consentimiento de administrador](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)de inquilinos.

Estos son los pasos para acceder y aceptar la solicitud para registrar el conector:

1. Vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e inicie sesión con las credenciales de un administrador global de Office 365.<br/><br/>Se muestra el siguiente cuadro de diálogo. Puede expandir los Cares para revisar los permisos que se asignarán al conector.<br/><br/>![Se muestra el cuadro de diálogo de solicitud de permisos](media/O365-ThirdPartyDataConnector-OptIn1.png)
2. Haga clic en **Aceptar**.

Después de aceptar la solicitud, se muestra el [portal de Azure](https://portal.azure.com) . Para ver la lista de aplicaciones de su organización, haga clic en**aplicaciones empresariales**de **Azure Active Directory** > . El conector de datos de terceros de Office 365 aparece en la hoja **aplicaciones empresariales** .

> [!IMPORTANT]
> Después del 30 de septiembre de 2018, los datos de terceros ya no se importarán en los buzones de la organización si no registra un conector de datos de terceros en Azure Active Directory. Nota los conectores de datos de terceros existentes (los creados antes del 30 de septiembre de 2018) también deben registrarse en Azure Active Directory siguiendo el procedimiento que se indica en el paso 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Revocar el consentimiento de un conector de datos de terceros

Una vez que la organización ha Condado permiso a la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar ese consentimiento en cualquier momento. Sin embargo, la revocación del consentimiento de un conector significa que los datos del origen de datos de terceros ya no se importarán en Office 365.

Para revocar el consentimiento de un conector de datos de terceros, puede eliminar la aplicación (eliminando la entidad de servicio correspondiente) de Azure Active Directory mediante la hoja **aplicaciones empresariales** en el portal de Azure o mediante el [ Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) en PowerShell de Office 365. También puede usar el cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) en PowerShell de Azure Active Directory.
  
## <a name="more-information"></a>Más información

- Tal como se ha explicado, los elementos de orígenes de datos de terceros se importan a los buzones de Exchange como mensajes de correo electrónico. El conector del asociado importa el elemento mediante un esquema requerido por la API 365 de Office. En la tabla siguiente se describen las propiedades del mensaje de un elemento de un origen de datos de terceros después de que este se importe a un buzón de Exchange como un mensaje de correo electrónico. La tabla también indica si la propiedad del mensaje es obligatoria. Las propiedades obligatorias deben rellenarse. Si a un elemento le falta una propiedad obligatoria, no se importará a Office 365. El proceso de importación devuelve un mensaje de error que explica por qué no se ha importado un elemento y qué propiedad falta.
    
    |**Propiedad del mensaje**|**¿Es obligatoria?**|**Descripción**|**Valor de ejemplo**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Sí  <br/> |El usuario que originalmente ha creado o enviado el elemento en el origen de datos de terceros. El conector del asociado intenta asignar el identificador de usuario del elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario de Office 365 para todos los participantes (usuarios de los campos de y a). Una copia del mensaje se importará al buzón de cada participante. Si ninguno de los participantes del elemento se puede asignar a una cuenta de usuario de Office 365, el elemento se importará al buzón de archivado de otro fabricante en Office 365.  <br/> <br/> El participante que se identifica como remitente del elemento debe tener un buzón activo en la organización de Office 365 a la que se va a importar el elemento. Si el remitente no tiene un buzón activo, se devolverá el siguiente error:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Sí  <br/> |El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.  <br/> | `bob@contoso.com` <br/> |
    |**Asunto** <br/> |No  <br/> |El asunto del elemento de origen.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**OBSOLET** <br/> |Sí  <br/> |La fecha en que el elemento se creó o publicó originalmente en el origen de datos del cliente. Por ejemplo, la fecha en la que se ha enviado un mensaje a Twitter.  <br/> | `01 NOV 2015` <br/> |
    |**CUERPO** <br/> |No  <br/> |El contenido del mensaje o la publicación. En el caso de algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT**. Durante el proceso de importación, el conector del asociado intenta mantener la fidelidad total del origen de contenido como sea posible. Si es posible, los archivos, los gráficos u otro contenido del cuerpo del elemento de origen se incluyen en esta propiedad. Si no es así, el contenido del elemento de origen se incluye en la propiedad **ATTACHMENT**. El contenido de esta propiedad depende del conector del asociado y de la capacidad de la plataforma de origen.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**DATOS adjuntos** <br/> |No  <br/> |Si un elemento del origen de datos (como un Tweet en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluye imágenes, la conexión del asociado intentará primero incluir datos adjuntos en la propiedad **Body** . Si esto no es posible, se agrega a la propiedad * * ATTACHMENT * *. Otros ejemplos de datos adjuntos son los "Me gusta" de Facebook, los metadatos del origen del contenido y las respuestas a un mensaje o una publicación.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Sí  <br/> | Se trata de una propiedad de varios valores, que se crea y rellena con el conector de asociado. El formato de esta propiedad es `IPM.NOTE.Source.Event`. (Esta propiedad debe comenzar con `IPM.NOTE`. Este formato es similar al de la `IPM.NOTE.X` clase de mensaje. Esta propiedad incluye la siguiente información:  <br/><br/>`Source`: Indica el origen de datos de terceros; por ejemplo, Twitter, Facebook o BlackBerry.  <br/> <br/>  `Event`: Indica el tipo de actividad que se realizó en el origen de datos de terceros que generó los elementos; por ejemplo, un Tweet en Twitter o un post en Facebook. Los eventos son específicos del origen de datos.  <br/> <br/>  Un objetivo de esta propiedad es filtrar elementos específicos en función del origen de datos en el que un elemento se originó o basó, o bien en función del tipo de evento. Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para encontrar todos los tweets publicados por un usuario concreto.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Cuando los elementos se importan correctamente a los buzones de Office 365, un identificador único se devuelve al autor de la llamada como parte de la respuesta HTTP. Este identificador, llamado `x-IngestionCorrelationID`, se puede usar para solucionar problemas posteriores de los asociados para el seguimiento de elementos de un extremo a otro. Se recomienda que los asociados capturen esta información y la registren según corresponda en su extremo. A continuación se incluye un ejemplo de una respuesta HTTP que muestra este identificador:

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- Puede usar la herramienta de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar elementos que se importaron a los buzones en Office 365 desde un origen de datos de terceros. Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valores y propiedades de mensaje en el cuadro palabra clave para una búsqueda de contenido.
    
  - **`kind:externaldata`**: Use este par Property-Value para buscar todos los tipos de datos de terceros. Por ejemplo, para buscar elementos que se importaron de un origen de datos de terceros y contenían la palabra "Contoso" en la propiedad Subject del elemento importado, usaría la palabra `kind:externaldata AND subject:contoso`clave Query.
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**: Use este par Property-Value solo para buscar un tipo de datos de terceros. Por ejemplo, para buscar únicamente datos de Facebook que contengan la palabra "Contoso" en la propiedad Subject, usaría la `itemclass:ipm.externaldata.Facebook* AND subject:contoso`consulta de palabra clave. 

  Para obtener una lista completa de los valores que se van a usar para los tipos `itemclass` de datos de terceros para la propiedad, consulte [use Content Search to Search a data de terceros importado a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:
    
  - [Búsqueda de contenido en Office 365](content-search.md)
    
  - [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
 
