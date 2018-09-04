---
title: Archivado de datos de terceros en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Los administradores pueden importar datos de otros proveedores de plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a buzones de correo en la organización de Office 365. Esto le permite archivar datos de orígenes de datos, Twitter y Facebook en Office 365. A continuación, puede appply las características de cumplimiento de normas de Office 365 (por ejemplo, retención legal, búsqueda de contenido y las directivas de retención) a los datos de otro fabricante.
ms.openlocfilehash: 7af88338333e90bd208d693fbfd5bb691d44b538
ms.sourcegitcommit: 4c6c937ec51e8b754332e4c1c8d286e73e197e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "23827094"
---
# <a name="archiving-third-party-data-in-office-365"></a>Archivado de datos de terceros en Office 365

Permite a los administradores importan y archivar datos de terceros desde plataformas de medios sociales, plataformas y plataformas de colaboración de documentos, a los buzones de correo en la organización de Office 365 de mensajería instantánea de Office 365. Ejemplos de orígenes de datos de terceros que se pueden importar a Office 365 incluyen lo siguiente: 
  
- **Social** - Twitter, Facebook, Yammer y LinkedIn 
    
- **Mensajería instantánea** - Yahoo Messenger, GoogleTalk y Cisco Jabber 
    
- **Colaboración en documentos** - cuadro y lista desplegable 
    
- **Industrias verticales** - administración de relaciones de cliente (por ejemplo, la cháchara de fuerza de ventas) y Financials (por ejemplo, Reuters Thomson y Bloomberg) 
    
- **Mensajería de texto SMS /** - BlackBerry 
    
Después de importan datos de otro fabricante, puede aplicar las características de cumplimiento de normas de Office 365, como las directivas de retención de la suspensión por litigio, búsqueda de contenido, en lugar de archivado, auditoría y Office 365 — a estos datos. Por ejemplo, cuando un buzón de correo se coloca en suspensión por litigio, se conservarán los datos de otro fabricante. Puede buscar datos de terceros mediante el uso de búsqueda de contenido. O puede aplicar el archivado y las políticas de retención a los datos de terceros, al igual que puede utilizar para datos de Microsoft. En resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización mantenga la compatibilidad con el gobierno y las directivas de las normativas.
  
Aquí es información general sobre el proceso y los pasos necesarios para importar datos de otros fabricantes a Office 365.

[Paso 1: Buscar un asociado de datos de terceros](#step-1-find-a-third-party-data-partner)

[Paso 2: Crear y configurar un buzón de datos de terceros en Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Paso 3: Configurar los buzones de usuario para los datos de terceros](#step-3-configure-user-mailboxes-for-third-party-data)

[Paso 4: Proporcionar información al asociado](#step-4-provide-your-partner-with-information)

[Paso 5: Registrar el conector de datos de terceros en Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Proceso de importación de los datos de otros fabricantes de cómo funciona >

En la ilustración y la descripción siguientes se explica cómo funciona el proceso de importación de datos de terceros.
  
![Cómo funciona el proceso de importación de datos de terceros](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Cliente funciona con su socio de elección para configurar un conector que se va a extraer los elementos del origen de datos de terceros y, a continuación, importar esos elementos a Office 365.
    
2. El conector de socio se conecta a orígenes de datos de terceros mediante una API de terceros (de forma programada o configurado como) y extrae los elementos del origen de datos. El conector de socio convierte el contenido de un elemento en un formato de mensaje de correo electrónico. Vea la sección [obtener más información](#more-information) para obtener una descripción del esquema de formato de mensaje. 
    
3. Conector de socio se conecta al servicio de Azure en Office 365 mediante el uso de servicio de Web Exchange (EWS) a través de un punto final conocido.
    
4. Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:
    
    r. **los elementos que tienen un identificador de usuario que corresponde a una cuenta de usuario de Office 365** - si el conector de socio puede asignar el identificador de usuario del elemento en el origen de datos de terceros a un usuario determinado que identificador en Office 365, el elemento se copia a la carpeta de **purga** en el usuario Carpeta elementos recuperables. Los usuarios no pueden tener acceso a los elementos de la carpeta de purga. Sin embargo, puede usar herramientas de exhibición de documentos electrónicos de Office 365 para buscar elementos en la carpeta de purga.
    
    b. **los elementos que no tienen un identificador de usuario que corresponde a una cuenta de usuario de Office 365** - si el conector de socio no puede asignar el identificador de usuario de un elemento a un usuario determinado que identificador en Office 365, el elemento se copia en la carpeta **Bandeja de entrada** del buzón de datos de terceros. Importación de elementos a la Bandeja de entrada permite usted o alguien de su organización para iniciar sesión en el buzón de correo de terceros para ver y administrar estos elementos y vea si los ajustes deben realizarse en la configuración del conector de socio.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Paso 1: Buscar un asociado de datos de terceros

Un componente clave para el archivado de datos de terceros en Office 365 es buscar y trabajar con un socio de Microsoft que está especializado en capturar los datos de un origen de datos de terceros y se importa a Office 365. Una vez que se importan los datos, puede archivar y conserva junto con la organización de otros datos de Microsoft, como correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa. Un socio crea un conector que extrae datos de orígenes de datos de terceros de su organización (por ejemplo, BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa los datos a una API de Office 365 que importa los elementos a los buzones de Exchange como mensajes de correo electrónico. 
  
Las secciones siguientes enumeran los socios de Microsoft y los orígenes de datos de terceros que admiten — que participan en el programa para el archivado de datos de terceros en Office 365.

[17a-4 LLC](#17a-4-llc)
  
[Actiance](#actiance)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

17a-4 LLC admite los siguientes orígenes de datos de terceros:
  
- BlackBerry
    
- Secuencias de datos de Bloomberg
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- 
Secuencias de datos de MessageLabs

    
- OpenText
    
- Ayuda de Hacer clic para llamar de Oracle/ATG Live

    
- Pivot IMTRADER

    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- 
Skype Empresarial (Lync/OCS)
    
- 
Skype Empresarial Online (Lync Online)

    
- Bases de datos SQL
    
- 
Squawker

    
- Thomson Reuters Eikon Messenger

  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com) es compatible con los siguientes orígenes de datos de terceros: 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- 
AOL con cliente Pivot

    
- Ares
    
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

    
- Chatter

    
- Mensajería instantánea Cisco &amp; servidor de presencia (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)
    
- Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)

    
- Importación de colaboración

    
- Registro de colaboración en tiempo real

    
- Conexión directa
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+

    
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

    
- HIELO/YellowJacket
    
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
    
- 
Microsoft Lync (2010, 2013)

    
- MFTP
    
- Microsoft Lync 2013 Voice

    
- Microsoft SharePoint (2010, 2013)

    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
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

    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo

    
- Yammer
    
- YouTube
    
  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com) es compatible con los siguientes orígenes de datos de terceros: 
  
- Facebook
    
- Flickr

    
- Instagram

    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com) es compatible con los siguientes orígenes de datos de terceros: 
  
- AOL con cliente Pivot 
    
- Registros de llamadas de BlackBerry (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Chat

    
- Bloomberg Mail

    
- Box

    
- CipherCloud para Salesforce Chatter
    
- Mensajería instantánea Cisco &amp; servidor de presencia (v10, v10.5.1 SU1, v11.0, v11.5 Do2)

- Equipos de Cisco Webex

- Área de trabajo de Citrix &amp; ShareFile

- CrowdCompass

- Archivos de texto delimitados por tabulaciones personalizadas

    
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

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) es compatible con los siguientes orígenes de datos de terceros: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[Verba](https://www.verba.com) es compatible con los siguientes orígenes de datos de terceros: 
  
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
    
- Cisco UCCX/UCCE voz
    
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

Estos son los pasos para crear y configurar un buzón de correo de datos de terceros para la importación de datos a Office 365. Como anterior se explica, los elementos se importan a este buzón de correo si el conector de socio no puede asignar el identificador de usuario del elemento a una cuenta de usuario de Office 365.
  
 **Completar estas tareas en el centro de administración de Office 365**
  
1. Crear una nueva cuenta de usuario en Office 365 y asignar una licencia de Exchange Online Plan 2; vea [Agregar usuarios a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Se requiere una licencia de Plan 2 para colocar el buzón de correo en juicio o habilitar un buzón de archivo que tiene una cuota de almacenamiento de información ilimitado.
    
2. Agregar la cuenta de usuario para el buzón de correo de terceros datos al rol de administrador de **Administrador de Exchange** en Office 365; vea [asignar roles de administrador en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).
    
    > [!TIP]
    > Escriba las credenciales para esta cuenta de usuario. Necesitará proporcionárselas a su socio, tal como se describe en el paso 4. 
  
 **Completar estas tareas en el centro de administración de Exchange**
  
1. Ocultar el buzón de correo de terceros datos desde la libreta de direcciones y otras listas de direcciones de su organización; vea [administrar buzones de usuario](https://go.microsoft.com/fwlink/p/?LinkId=616058). Como alternativa, puede ejecutar el siguiente comando de PowerShell:
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Asignar **contar** con permiso para el buzón de correo de datos de terceros para que los administradores o responsables del cumplimiento normativo pueden abrir el buzón de correo de datos de terceros en el cliente de escritorio de Outlook; vea [Administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Habilitar las siguientes características de Office 365 relacionados con el cumplimiento de normas para el buzón de datos de terceros:
    
    - Habilitar el buzón de archivo; vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md). Esto le permitirá libere espacio en el buzón principal mediante la configuración de una directiva de archivo que mueve los elementos de datos de terceros para el buzón de archivo. Esto le proporcionará almacenamiento ilimitado de datos de terceros.
    
    - Colocar el buzón de correo de datos de terceros en juicio. También puede aplicar una directiva de retención de Office 365 en la seguridad de Office 365 &amp; centro de cumplimiento. Colocar este buzón de correo en espera va a conservar los elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evitar que se purgarán desde el buzón de correo. Vea uno de los siguientes temas:
    
      - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Introducción a las directivas de retención en Office 365](retention-policies.md)
    
       
    
    - Habilitar el registro para el acceso al buzón de otro fabricante datos; propietario, delegado y administración de auditoría de buzón de correo vea la sección [Habilitar auditoría en Office 365 de buzón de correo](enable-mailbox-auditing.md). Esto le permitirá auditar la actividad de todos los realizado por cualquier usuario que tenga acceso al buzón de datos de terceros.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Paso 3: Configurar los buzones de usuario para los datos de terceros

El siguiente paso es configurar los buzones de usuario para admitir los datos de otro fabricante. Completar estas tareas mediante el centro de administración de Exchange o mediante el uso de los cmdlets de Windows PowerShell correspondientes.
  
1. Habilitar el buzón de archivo para cada usuario; vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).
    
2. Colocar buzones de usuario en juicio o aplicar una directiva de retención Office 365; vea uno de los siguientes temas: 
    
    - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Introducción a las directivas de retención en Office 365](retention-policies.md)
    
    Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.

## <a name="step-4-provide-your-partner-with-information"></a>Paso 4: Proporcionar información al asociado

El último paso es proporcionar a su asociado la información siguiente para que pueda configurar el conector y conectarse a su organización de Office 365 con el fin de importar datos a los buzones de usuario y al buzón de datos de terceros. 
  
- El extremo que se usa para conectarse al servicio de Azure en Office 365:

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- El inicio de sesión credenciales (identificador de usuario de Office 365 y la contraseña) del buzón de datos de terceros que creó en el paso 2. Estas credenciales son necesarias para que el conector de socio puede tener acceso e importar elementos a los buzones de usuario y el buzón de correo de datos de terceros.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Paso 5: Registrar el conector de datos de terceros en Azure Active Directory

Iniciar el 30 de septiembre de 2018, el servicio de Azure en Office 365 comenzará con autenticación moderna en Exchange Online para autenticar los conectores de datos de terceros que intenten conectarse a la organización de Office 365 para importar datos. La razón de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se ha basado en la lista blanca los conectores de terceros que usan el extremo descrito anteriormente para conectarse al servicio de Azure.

Para habilitar un conector de datos de terceros para conectarse a Office 365 con el nuevo método de autenticación moderno, debe consentimiento de un administrador de la organización de Office 365 para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory. Esto se realiza mediante la aceptación de una solicitud de permisos para permitir que el conector de acceso a datos de la organización de Azure Active Directory. Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa para Azure Active Directory y representado como una entidad de seguridad de servicio. Para el proceso de consentimiento de obtener más información, vea [Administración de inquilinos da su consentimiento](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).

Estos son los pasos para tener acceso y aceptar la solicitud para registrar el conector:

1. Vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de un administrador global de Office 365.<br/><br/>Se muestra el cuadro de diálogo siguiente. Puede expandir los corchetes angulares para revisar los permisos que se asignará al conector.<br/><br/>![Se muestra el cuadro de diálogo de solicitud de permisos](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. Haga clic en **Aceptar**.

Después de aceptar la solicitud, se muestra el [portal de Azure](https://portal.azure.com) . Para ver la lista de aplicaciones para su organización, haga clic en **Azure Active Directory** > **aplicaciones empresariales**. El conector de datos de terceros para Office 365 se muestra en el servidor blade de **aplicaciones de empresa** .

> [!IMPORTANT]
> Después de 30 de septiembre de 2018, datos de otro fabricante ya no se importará en buzones de la organización si no registrar un conector de datos de terceros en Azure Active Directory. Tenga en cuenta los existentes conectores de datos de terceros (los que se crean antes del 30 de septiembre de 2018) también debe estar registrada en Azure Active Directory mediante el procedimiento descrito en el paso 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Revocar el consentimiento para un conector de datos de terceros

Después de la organización da su consentimiento a la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar dicho consentimiento en cualquier momento. Sin embargo, revocar el consentimiento para un conector significa que ya no se importará los datos desde el origen de datos de terceros en Office 365.

Para revocar el consentimiento para un conector de datos de terceros, puede eliminar la aplicación (mediante la eliminación de la entidad de seguridad de servicio correspondiente) de Azure Active Directory con el servidor blade de **aplicaciones empresariales** en el portal de Azure, o mediante el uso de la [ Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) en PowerShell de Office 365. También puede usar el cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) en Azure Active Directory PowerShell.
  
## <a name="more-information"></a>Más información

- Explica lo anterior, los elementos de datos de terceros orígenes se importan a los buzones de Exchange como mensajes de correo electrónico. El conector de socio importa el elemento mediante un esquema requerido por la API de Office 365. En la siguiente tabla se describe las propiedades de mensaje de un elemento de un origen de datos de terceros después de que se importa a un buzón de Exchange como un mensaje de correo electrónico. En la tabla también se indica si la propiedad message es obligatoria. Deben rellenarse propiedades obligatorias. Si un elemento no tiene una propiedad obligatoria, no se importan a Office 365. El proceso de importación devolverá un mensaje de error que explica por qué un elemento no se ha importado y qué propiedad es que faltan.
    
    |**Propiedad del mensaje**|**¿Obligatorio?**|**Descripción**|**Valor de ejemplo**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Sí  <br/> |El usuario que creó originalmente o envía el elemento en el origen de datos de terceros. El conector de socio se intentará asignar el identificador de usuario desde el elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario de Office 365 para todos los participantes (los usuarios de los campos FROM y TO). Se va a importar una copia del mensaje al buzón de todos los participantes. Si ninguno de los participantes del elemento se pueden asignar a una cuenta de usuario de Office 365, el elemento se importará para el buzón de correo archivado de terceros en Office 365.<br/> <br/> El participante que se identificó como el remitente del elemento debe tener un buzón en la organización de Office 365 que el elemento se importa a activo. Si el remitente no tiene un buzón de correo activo, se devuelve el siguiente error:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Sí  <br/> |El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.  <br/> | `bob@contoso.com` <br/> |
    |**SUBJECT** <br/> |No  <br/> |El asunto del elemento de origen.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**FECHA** <br/> |Sí  <br/> |La fecha en la que el elemento originalmente se ha creado o publicado en el origen de datos del cliente; por ejemplo, la fecha en la que se ha publicado un mensaje en Twitter.  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |No  <br/> |El contenido del mensaje o post. Para algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT** . Durante el proceso de importación, el conector de socio se intentará mantener fidelidad completa desde el origen de contenido como sea posible. Si es posible archivos, gráficos u otro contenido desde el cuerpo del elemento de origen se incluye en esta propiedad. De lo contrario, el contenido desde el elemento de origen se incluye en la propiedad **datos adjuntos** . El contenido de esta propiedad dependerán del conector de socio y en la capacidad de la plataforma de origen.<br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |No  <br/> |Si un elemento en el origen de datos (por ejemplo, un mensajes en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluir imágenes, el socio conectar será el primer intento para incluir datos adjuntos en la propiedad **BODY** . Si eso no es posible, a continuación, se agrega a la ** datos adjuntos ** (propiedad). Otros ejemplos de los datos adjuntos son "Me gusta" en Facebook, metadatos desde el origen de contenido y las respuestas a un mensaje o post.<br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Sí  <br/> | Se trata de una propiedad multivalor, que se crea y se rellena por el conector de socio. El formato de esta propiedad es `IPM.NOTE.Source.Event`. (Esta propiedad debe comenzar con `IPM.NOTE`; este formato es similar a la de la `IPM.NOTE.X` clase de mensaje.) Esta propiedad incluye la siguiente información:<br/><br/>`Source`-Indica el origen de datos de terceros; Por ejemplo, Twitter, Facebook o BlackBerry.  <br/> <br/>  `Event`-Indica el tipo de actividad que se llevó a cabo en el origen de datos de otros fabricantes que producen los elementos; Por ejemplo, un mensajes en Twitter o una entrada en Facebook. Eventos son específicos para el origen de datos.<br/> <br/>  Uno de los objetivos de esta propiedad es filtrar elementos específicos según el origen de datos donde un elemento se originó o en función del tipo de evento. Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para buscar todos los tweets a la que se contabilizaron por un usuario específico.<br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Cuando los elementos se importan correctamente a los buzones de correo en Office 365, se devuelve un identificador único al autor de la llamada como parte de la respuesta HTTP. Este identificador, denominado `x-IngestionCorrelationID`— puede usarse para fines de solución de problemas posteriores por los socios para realizar un seguimiento de los elementos de extremo a otro. Se recomienda que los socios capturan esta información y registrarla según corresponda en su extremo. Este es un ejemplo de una respuesta HTTP que muestra este identificador:

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- Puede usar la herramienta de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar los elementos que se han importado a buzones de correo en Office 365 desde un origen de datos de terceros. Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valor de la propiedad de mensaje en el cuadro de palabra clave para una búsqueda de contenido. . 
    
  - **`kind:externaldata`**-Use este par de valor de la propiedad para buscar todos los tipos de datos de terceros. Por ejemplo, para buscar los elementos que se importaron desde un origen de datos de terceros y contiene la palabra "contoso" en la propiedad Subject del elemento importado, usaría la consulta de palabra clave `kind:externaldata AND subject:contoso`.
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-Usar este par de valor de la propiedad a la búsqueda sólo un tipo de especificar de datos de terceros. Por ejemplo, para buscar sólo los datos de Facebook que contiene la palabra "contoso" en la propiedad Subject, usaría la consulta de palabra clave `itemclass:ipm.externaldata.Facebook* AND subject:contoso`. 

  Para obtener una lista completa de los valores que se usará para tipos de datos de terceros para la `itemclass` (propiedad), consulte [Usar la búsqueda de contenido para buscar datos de terceros que se importaron a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:
    
  - [Búsqueda de contenido en Office 365](content-search.md)
    
  - [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
 
