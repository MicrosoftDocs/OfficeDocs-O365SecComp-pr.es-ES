---
title: Información heredada para el cifrado de mensajes de Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
description: Si todavía no ha movido su organización de Office 365 a las nuevas capacidades de OME, pero ya ha implementado OME, la información de este artículo se aplica a su organización. Microsoft recomienda que cree un plan para cambiar a las nuevas funciones de OME en cuanto sea razonable para su organización. Para obtener instrucciones, vea configurar las nuevas funciones de cifrado de mensajes de Office 365 basadas en Azure Information Protection. Si desea obtener más información sobre cómo funcionan las nuevas funciones en primer lugar, consulte Office 365 Message Encryption. En el resto de este artículo se hace referencia al comportamiento OME antes de la publicación de las nuevas capacidades de OME.
ms.openlocfilehash: 03e2cb9c1f7d447f2fcf222382fcc2366faf0658
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252088"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Información heredada para el cifrado de mensajes de Office 365

Si todavía no ha movido su organización de Office 365 a las nuevas capacidades de OME, pero ya ha implementado OME, la información de este artículo se aplica a su organización. Microsoft recomienda que cree un plan para cambiar a las nuevas funciones de OME en cuanto sea razonable para su organización. Para obtener instrucciones, vea [configurar las nuevas funciones de cifrado de mensajes de Office 365 basadas en Azure Information Protection](set-up-new-message-encryption-capabilities.md). Si desea obtener más información sobre cómo funcionan las nuevas funciones en primer lugar, consulte [Office 365 Message Encryption](ome.md). En el resto de este artículo se hace referencia al comportamiento OME antes de la publicación de las nuevas capacidades de OME.
  
Con el cifrado de mensajes de Office 365, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre usuarios de dentro y fuera de la organización. El cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo, gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios deseados puedan ver el contenido de los mensajes.
  
Aquí le mostramos otros ejemplos:
  
- Un empleado del Banco envía extractos de tarjeta de crédito a los clientes
    
- Un representante de la compañía de seguros proporciona detalles de directivas a los clientes
    
- Un intermediario de hipoteca solicita información financiera a un cliente para una solicitud de préstamo
    
- Un proveedor de asistencia sanitaria envía información sobre el cuidado de la salud a los pacientes
    
- Un abogado envía información confidencial a un cliente o a otro abogado
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Cómo funciona el cifrado de mensajes de Office 365 sin las nuevas funciones

El cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS). Con Azure RMS, los administradores pueden definir reglas de flujo de correo para determinar las condiciones de cifrado. Por ejemplo, una regla puede requerir el cifrado de todos los mensajes dirigidos a un destinatario específico.
  
Vea este breve vídeo para ver cómo funciona el cifrado de mensajes de Office 365 sin las nuevas funciones.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
Cuando alguien envía un mensaje de correo electrónico en Exchange online que coincide con una regla de cifrado, el mensaje se envía con un archivo adjunto HTML. El destinatario abre los datos adjuntos HTML y sigue las instrucciones para ver el mensaje cifrado en el portal de cifrado de mensajes de Office 365. El destinatario puede elegir ver el mensaje iniciando sesión con una cuenta Microsoft o una escuela o un trabajo asociado con Office 365, o mediante un código de acceso único. El proceso de inicio de sesión ayuda a garantizar que solo los destinatarios previstos puedan ver los mensajes cifrados. Este proceso es muy diferente para las nuevas capacidades de OME.
  
En el siguiente diagrama se resume el paso de un mensaje de correo electrónico a través del proceso de cifrado y descrifrado.
  
![Diagrama que muestra la ruta de acceso de un correo electrónico cifrado](media/O365-Office365MessageEncryption-Concept.png)
  
Para obtener más información, vea [información de servicio para el cifrado de mensajes de Office 365 heredado antes de la publicación de las nuevas capacidades de OME](legacy-information-for-message-encryption.md#LegacyServiceInfo).
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definición de reglas de flujo de correo para el cifrado de mensajes de Office 365 que no usan las nuevas funciones de OME

Para habilitar el cifrado de mensajes de Office 365 sin las nuevas funciones, los administradores de Exchange Online y Exchange Online Protection definen las reglas de flujo de correo de Exchange. Estas reglas determinan en qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar el cifrado de mensajes. Cuando se establece una acción de cifrado para una regla, los mensajes que coinciden con las condiciones de la regla se cifran antes de enviarse.
  
Las reglas de flujo de correo son flexibles, lo que permite combinar condiciones para que pueda cumplir requisitos de seguridad específicos en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contengan palabras clave especificadas y que estén dirigidos a destinatarios externos. El cifrado de mensajes de Office 365 también cifra las respuestas de destinatarios de correo electrónico cifrado y puede crear una regla que descifre esas respuestas como comodidad para los usuarios de correo electrónico. De este modo, los usuarios de la organización no tendrán que iniciar sesión en el portal de cifrado para ver las respuestas.
  
Para obtener más información acerca de cómo crear reglas de flujo de correo de Exchange, vea [definir reglas para el cifrado de mensajes de Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, ver y responder mensajes de correo electrónico cifrado

Con el cifrado de mensajes de Office 365, los mensajes de correo electrónico se cifran automáticamente en función de las reglas definidas por el administrador. Un correo electrónico que lleva un mensaje cifrado llega a la bandeja de entrada del destinatario con un archivo HTML adjunto.
  
Los destinatarios siguen las instrucciones del mensaje para abrir los datos adjuntos y autenticarse con una cuenta de Microsoft o una escuela o trabajo asociado con Office 365. Si los destinatarios no tienen ninguna cuenta, se les conducirá a crear una cuenta de Microsoft que les permitirá iniciar sesión para ver el mensaje cifrado. Como alternativa, los destinatarios pueden elegir obtener un código de acceso único para ver el mensaje. Después de iniciar sesión o usar un código de acceso único, los destinatarios pueden ver el mensaje descifrado y enviar una respuesta cifrada.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalizar mensajes cifrados con el cifrado de mensajes de Office 365

Como administrador de Exchange Online y Exchange Online Protection, puede personalizar los mensajes cifrados. Por ejemplo, puede Agregar la marca y el logotipo de su compañía, especificar una introducción y agregar texto de declinación de responsabilidades en los mensajes cifrados y en el portal donde los destinatarios ven los mensajes cifrados. Con los cmdlets de Windows PowerShell, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de los mensajes de correo electrónico cifrados:
  
- Texto de introducción del correo electrónico que contiene el mensaje cifrado
    
- Texto de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado
    
- Texto del portal que aparecerá en el portal de visualización de mensajes
    
- Logotipo que aparecerá en el mensaje de correo electrónico y en el portal de visualización
    
También puede volver a la apariencia predeterminada en cualquier momento.
  
El siguiente ejemplo muestra un logotipo personalizado para ContosoPharma en los datos adjuntos de correo electrónico:
  
![Ejemplo de la página de visualización del mensaje cifrado](media/TA-OME-3attachment2.jpg)
  
 **Para personalizar los mensajes de correo electrónico de cifrado y el portal de cifrado con la marca de la organización**
  
1. Conéctese a Exchange online mediante PowerShell remoto, tal como se describe en [Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated).
    
2. Use el cmdlet Set-OMEConfiguration como se describe aquí: [set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) o use la siguiente tabla para obtener instrucciones. 
    
   **Opciones de personalización de cifrado**

|**Para personalizar esta característica de la experiencia de cifrado**|**Usar estos comandos de Windows PowerShell**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrados  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|Texto que aparece en la parte superior del portal de visualización de correo cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff  <br/> Tamaño óptimo del archivo de logotipo: menos de 40 KB  <br/> Tamaño óptimo de la imagen de logotipo: 170 píxeles  <br/> |
   
 **Para quitar personalizaciones de marca de los mensajes de correo electrónico de cifrado y el portal de cifrado**
  
1. Conéctese a Exchange online mediante PowerShell remoto, tal como se describe en [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).
    
2. Use el cmdlet Set-OMEConfiguration tal y como se describe aquí: [set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). Para quitar las personalizaciones de marca de la organización de los valores de DisclaimerText, EmailText y PortalText, establezca el valor en una cadena vacía `""`. Para todos los valores de imagen, como el logotipo, establezca el `"$null"`valor en.
    
   **Opciones de personalización de cifrado**

|**Para revertir esta característica de la experiencia de cifrado de nuevo a la imagen y el texto predeterminados**|**Usar estos comandos de Windows PowerShell**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrados  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|Texto que aparece en la parte superior del portal de visualización de correo cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Ejemplo de volver a su valor predeterminado:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Ejemplo de volver a su valor predeterminado:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Información de servicio para el cifrado de mensajes de Office 365 heredado antes de la publicación de las nuevas capacidades de OME
<a name="LegacyServiceInfo"> </a>

En la siguiente tabla se proporcionan detalles técnicos para el servicio de cifrado de mensajes de Office 365 antes de la publicación de las nuevas capacidades de OME.
  
|**Detalles del servicio**|**Descripción**|
|:-----|:-----|
|Requisitos de dispositivo de cliente  <br/> |Los mensajes cifrados se pueden ver en cualquier dispositivo de cliente, siempre y cuando los datos adjuntos HTML puedan abrirse en un explorador moderno que admita el envío de formularios.  <br/> |
|Algoritmo de cifrado y compatibilidad con FIPS (Estándar federal de procesamiento de información)  <br/> |El Cifrado de mensajes de Office 365 emplea las mismas claves de cifrado que Microsoft Azure Information Rights Management (IRM) y admite el modo criptográfico 2 (clave de 2048 bits para RSA y de 256 bits para sistemas SHA-1). Para obtener más información acerca de los modos criptográficos de IRM subyacentes, consulte [modos criptográficos de AD RMS](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).  <br/> |
|Tipos de mensaje admitidos  <br/> |Solo se admite el cifrado de mensajes de Office 365 para los elementos que tienen un identificador de clase de mensaje de **IPM.Note**. Para obtener más información, vea [tipos de elementos y clases de mensajes](https://msdn.microsoft.com/library/office/ff861573.aspx).  <br/> |
|Límites de tamaño de mensaje  <br/> |El Cifrado de mensajes de Office 365 es capaz de cifrar mensajes de hasta 25 megabytes. Para obtener más información sobre los límites de tamaño de los mensajes, vea [límites de Exchange Online](http://technet.microsoft.com/library/exchange-online-limits.aspx).  <br/> |
|Directivas de retención de correo electrónico de Exchange Online  <br/> |Exchange online no almacena los mensajes cifrados.  <br/> |
|Compatibilidad de idiomas en el cifrado de mensajes de Office 365  <br/> | El cifrado de mensajes de Office 365 admite los idiomas de Office 365 de la siguiente manera:  <br/>  Los mensajes de correo electrónico entrantes y los archivos HTML adjuntos se localizan según la configuración de idioma del remitente.  <br/>  El portal de visualización se localiza en función de la configuración del explorador del destinatario.  <br/>  El cuerpo (contenido) del mensaje cifrado no se localiza.  <br/> |
|Información de privacidad del Portal OME y la aplicación Visor OME  <br/> |El vínculo [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) proporciona más información sobre el uso de su información privada por parte de Microsoft.  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>Preguntas más frecuentes acerca de OME heredados
<a name="LegacyServiceInfo"> </a>

¿Tiene alguna pregunta sobre el cifrado de mensajes de Office 365? Aquí encontrará algunas respuestas. Si no encuentra lo que necesita, consulte los foros de la comunidad de Office 365 en la [comunidad de office 365](http://community.office365.com/en-us/forums/default.aspx).
  
 **P. mis usuarios envían mensajes de correo electrónico cifrados a destinatarios fuera de la organización. ¿Hay algo que los destinatarios externos tengan que hacer para leer y responder a los mensajes de correo electrónico cifrados con el cifrado de mensajes de Office 365?**
  
Los destinatarios externos pueden leer los correos electrónicos que reciban cifrados con el cifrado de Office 365 de dos maneras:
  
- Iniciando sesión con una cuenta de Microsoft o una cuenta profesional o educativa asociada con Office 365.
    
- Mediante un código de paso único.
    
 **P. ¿Se almacenan los mensajes cifrados de Office 365 en la nube o en los servidores de Microsoft?**
  
No, los mensajes cifrados se conservan en el sistema de correo electrónico del destinatario y, cuando el destinatario abre el mensaje, se publica temporalmente para verlo en los servidores de Office 365. Pero los mensajes no se almacenan ahí.
  
 **P. ¿Puedo personalizar los mensajes de correo electrónico cifrado con mi marca?**
  
Sí. Puede usar cmdlets de Windows PowerShell para personalizar el texto predeterminado que aparece en la parte superior de los mensajes de correo electrónico cifrados, el texto de aviso de declinación de responsabilidades y el logotipo que quiera usar para el mensaje de correo electrónico y el portal de cifrado. Para más información, consulte [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **P. ¿Requiere el servicio una licencia para cada usuario de la organización?**
  
Se requiere una licencia para cada usuario de la organización que envíe correo electrónico cifrado.
  
 **P. ¿Requieren los destinatarios externos suscripciones?**
  
No, los destinatarios externos no requieren una suscripción para leer o responder los mensajes cifrados. 
  
 **P. ¿en qué se diferencia el cifrado de mensajes de Office 365 de Rights Management Services (RMS)?**
  
RMS proporciona funciones de protección de derechos de la información para los correos electrónicos internos de una organización al proporcionar plantillas integradas, como: no reenviar y confidencial de la empresa. El cifrado de mensajes de Office 365 es compatible con el cifrado para los mensajes de correo electrónico que se envían a destinatarios externos, así como destinatarios internos.
  
 **P. ¿en qué se diferencia el cifrado de mensajes de Office 365 de S/MIME?**
  
S/MIME es básicamente una tecnología de cifrado del lado cliente y requiere la administración de certificados complicados y la publicación de infraestructura. El cifrado de mensajes de Office 365 usa reglas de flujo de correo (también conocidas como reglas de transporte) y no depende de la publicación de certificados.
  
 **P. ¿Puedo leer los mensajes cifrados en dispositivos móviles?**
  
Sí, puede ver los mensajes en Android y iOS descargando las aplicaciones del visor de OME de [Google Play Store](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409) y de la [App Store de Apple](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409). Abra los datos adjuntos en formato HTML en la aplicación del Visor de OME y, a continuación, siga las instrucciones para abrir el mensaje cifrado. Para otros dispositivos móviles, puede abrir los datos adjuntos en formato HTML siempre que el cliente de correo permita la publicación de formularios.
  
 **P. ¿Se cifran las respuestas y los mensajes reenviados?**
  
Sí. Las respuestas se siguen cifrando durante todo el período de la conversación.
  
 **P. ¿el cifrado de mensajes de Office 365 proporciona localización?**
  
El correo electrónico entrante y el contenido HTML se localiza según la configuración de correo electrónico del remitente. El portal de visualización se localiza según la configuración del explorador del destinatario. Sin embargo, el cuerpo (contenido) del mensaje cifrado no se localiza.
  
 **P. ¿Qué método de cifrado se usa para el cifrado de mensajes de Office 365?**
  
El cifrado de mensajes de Office 365 usa Rights Management Services (RMS) como infraestructura de cifrado. El método de cifrado utilizado depende de dónde obtiene las claves de RMS utilizadas para cifrar y descifrar mensajes.
  
- Si usa Microsoft Azure RMS para obtener las claves, se usa el modo criptográfico 2. El modo criptográfico 2 es una implementación criptográfica de AD RMS actualizada y mejorada. Es compatible con RSA 2048 para firma y cifrado, y admite SHA-256 para firma.
    
- Si usa Active Directory (AD) RMS para obtener las claves, se utiliza el modo criptográfico 1 o el modo criptográfico 2. El método empleado depende de la implementación local de AD RMS. El modo criptográfico 1 es la implementación criptográfica original de AD RMS. Es compatible con RSA 1024 para firma y cifrado, y admite SHA-1 para firma. Este modo sigue siendo compatible con todas las versiones actuales de RMS.
    
Para obtener más información, consulte [modos criptográficos de AD RMS](http://go.microsoft.com/fwlink/p/?LinkId=398616).
  
 **P. ¿Por qué algunos mensajes cifrados dicen proceder de Office365@messaging.microsoft.com?**
  
Cuando se envía una respuesta cifrada desde el portal de cifrado o a través de la aplicación del Visor de OME, la dirección de correo electrónico de envío se establece en Office365@messaging.microsoft.com porque el mensaje cifrado se envía a través de un extremo de Microsoft. Esto ayuda a evitar que los mensajes cifrados se marquen como correo no deseado. El nombre mostrado en el correo electrónico y la dirección del portal de cifrado no se modifican a causa de este etiquetado. Además, este etiquetado solo se aplica a los mensajes enviados a través del portal, no a través de cualquier otro cliente de correo electrónico.
  
 **P. soy un suscriptor de Exchange Hosted Encryption (EHE). ¿Dónde puedo obtener más información sobre la actualización al cifrado de mensajes de Office 365?**
  
Todos los clientes de EHE se han actualizado a Cifrado de mensajes de Office 365. Para obtener más información, visite el [centro de actualización de Exchange hostEd Encryption](http://go.microsoft.com/fwlink/p/?LinkID=511077).
  
 **P. ¿es necesario que abra las direcciones URL, las direcciones IP o los puertos del firewall de mi organización para que admitan el cifrado de mensajes de Office 365?**
  
Sí. Debe agregar direcciones URL para Exchange Online para que la lista de permitidos de la organización habilite la autenticación de los mensajes cifrados por parte del servicio de cifrado de mensajes de Office 365. Para ver una lista de direcciones URL de Exchange Online, consulte [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx).
  
 **P. ¿A cuántos destinatarios puedo enviar un mensaje cifrado de Office 365?**
  
El límite de destinatarios de un mensaje cifrado se basa en el número de caracteres del campo **para** del mensaje. Cuando se combinan (tras expandir la lista de distribución), las direcciones de los destinatarios en el campo **Para** no deben superar los 11.980 caracteres. Como las direcciones de correo electrónico pueden variar en longitud de caracteres, no hay un límite de destinatarios estándar para un solo mensaje cifrado. 
  
 **P. ¿Es posible revocar un mensaje enviado a un destinatario concreto?**
  
No. No puede revocar un mensaje a una persona determinada después de enviarlo.
  
 **P. ¿Puedo ver un informe de los mensajes cifrados que se han recibido y leído?**
  
No hay un informe que muestre si se ha visto un mensaje cifrado, pero hay disponible Office 365 Reports que puede aprovechar para determinar el número de mensajes que coincidieron con una regla de flujo de correo específica (también denominada regla de transporte), por ejemplo.
  
 **P. ¿Qué hace Microsoft con la información que proporciono a través del Portal OME y la aplicación Visor OME?**
  
La [declaración de privacidad del portal de cifraDo de Office 365 Messaging](protected-message-viewer-portal-privacy-statement.md) proporciona información detallada sobre lo que Microsoft hace y qué no hace con la información privada. 
  

