---
title: Información heredada para el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
description: Si aún no se ha desplazado la organización de Office 365 para las nuevas capacidades OME, pero ya ha implementado OME, a continuación, la información de este artículo se aplica a la organización. Microsoft recomienda que realice un plan para mover a las nuevas capacidades OME tan pronto como es razonable para la organización. Para obtener instrucciones, vea Set up nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure. Si desea obtener más información acerca de cómo funcionan en primer lugar las nuevas capacidades, consulte cifrado de mensajes de Office 365. El resto de este artículo hace referencia al comportamiento OME antes del lanzamiento de las nuevas capacidades OME.
ms.openlocfilehash: d5b21cbe0004ca7bda38085bd5d8ef5f2a22b04e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536282"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Información heredada para el cifrado de mensajes de Office 365

Si aún no se ha desplazado la organización de Office 365 para las nuevas capacidades OME, pero ya ha implementado OME, a continuación, la información de este artículo se aplica a la organización. Microsoft recomienda que realice un plan para mover a las nuevas capacidades OME tan pronto como es razonable para la organización. Para obtener instrucciones, vea [Configurar nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure](set-up-new-message-encryption-capabilities.md). Si desea obtener más información acerca de cómo funcionan en primer lugar las nuevas capacidades, consulte [Cifrado de mensajes de Office 365](ome.md). El resto de este artículo hace referencia al comportamiento OME antes del lanzamiento de las nuevas capacidades OME.
  
Con el cifrado de mensajes de Office 365, la organización puede enviar y recibir mensajes de correo electrónico cifrado entre las personas dentro y fuera de su organización. Office 365 cifrado de mensajes funciona con Outlook.com, Yahoo, Gmail y otros servicios de correo electrónico. Cifrado de mensajes de correo electrónico ayuda a garantiza que sólo los destinatarios puede ver el contenido del mensaje.
  
Estos son algunos ejemplos:
  
- Un empleado bancario envía la tarjeta de crédito a los clientes
    
- Un representante de la compañía de seguros proporciona detalles de la directiva a los clientes
    
- Un corredor de hipotecas solicita información financiera de un cliente para una aplicación de préstamos
    
- Proveedor de atención médica envía información médica a los pacientes
    
- Un abogado que envía información confidencial a un cliente o a otro abogado
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Cómo funciona el cifrado de mensajes de Office 365 sin las nuevas capacidades

Cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (RMS Azure). Con Azure RMS, los administradores pueden definir reglas de flujo de correo para determinar las condiciones para el cifrado. Por ejemplo, una regla puede requerir el cifrado de todos los mensajes dirigidos a un destinatario concreto.
  
Vea este vídeo corto para ver cómo funciona el cifrado de mensajes de Office 365 sin las nuevas capacidades.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
Cuando alguien le envía un mensaje de correo electrónico en Exchange Online coincide con una regla de cifrado, el mensaje se envía con datos adjuntos HTML. El destinatario abre los datos adjuntos HTML y sigue las instrucciones para ver el mensaje cifrado en el portal de cifrado de mensajes de Office 365. El destinatario puede elegir ver el mensaje de inicio de sesión de una cuenta de Microsoft o un trabajo o escuela asociado con Office 365, o mediante un código de acceso única. Ambas opciones ayudan a garantizar que sólo el destinatario puede ver el mensaje cifrado. Este proceso es muy diferente para las nuevas capacidades OME.
  
En el siguiente diagrama se resume el paso de un mensaje de correo electrónico a través del proceso de cifrado y descrifrado.
  
![Diagrama que muestra la ruta de acceso de un correo electrónico cifrado](media/O365-Office365MessageEncryption-Concept.png)
  
Para obtener más información, vea [información de servicio de cifrado de mensajes de Office 365 heredado antes del lanzamiento de las nuevas capacidades OME](legacy-information-for-message-encryption.md#LegacyServiceInfo).
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definición de reglas de flujo de correo para Office 365 Message Encryption que no utilicen las nuevas capacidades OME

Para habilitar el cifrado de mensajes de Office 365 sin las nuevas capacidades, los administradores de Exchange Online y Exchange Online Protection definir reglas de flujo de correo de Exchange. Estas reglas determinan en qué correo electrónico de condiciones deben cifrarse los mensajes, así como las condiciones para quitar el cifrado de mensajes. Cuando se establece una acción de cifrado para una regla, todos los mensajes que coincidan con las condiciones de regla se cifran antes de que se envían.
  
Reglas de flujo de correo son flexibles, lo que le permite combinar las condiciones para que pueda cumplir los requisitos de seguridad específica en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contienen palabras clave especificadas y dirigidos a destinatarios externos. Cifrado de mensajes de Office 365 También cifra las respuestas de los destinatarios de correo electrónico cifrado, y puede crear una regla que descifra las respuestas como una comodidad para los usuarios de correo electrónico. De esta forma, los usuarios de su organización no tendrán que iniciar sesión en el portal de cifrado para ver las respuestas.
  
Para obtener más información acerca de cómo crear reglas de flujo de correo de Exchange, consulte [Definir reglas para el cifrado de mensajes de Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, ver y responder mensajes de correo electrónico cifrado

Con el cifrado de mensajes de Office 365, mensajes de correo electrónico se cifran automáticamente, en función de las reglas definidas por el administrador. Un correo electrónico que lleve un mensaje cifrado llega en la Bandeja de entrada del destinatario con un archivo HTML adjunto.
  
Destinatarios siga las instrucciones que aparecen en el mensaje para abrir los datos adjuntos y autenticar mediante el uso de una cuenta de Microsoft o un trabajo o escuela asociado a Office 365. Si los destinatarios no tienen una de estas cuentas, está dirigidos a la creación de una cuenta que les permiten iniciar sesión para ver el mensaje cifrado de Microsoft. Como alternativa, pueden elegir los destinatarios obtener un código de acceso única para ver el mensaje. Después de iniciar sesión en o mediante un código de acceso única, los destinatarios pueden ver el mensaje descifrado y enviar una respuesta cifrada.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalizar los mensajes cifrados con cifrado de mensajes de Office 365

Como administrador de Exchange Online y Exchange Online Protection, puede personalizar los mensajes cifrados. Por ejemplo, puede agregar marca de su empresa y un logotipo, especifique una introducción y agregar texto de declinación de responsabilidades en los mensajes cifrados y en el portal donde los destinatarios ver los mensajes cifrados. Uso de cmdlets de Windows PowerShell, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de los mensajes de correo electrónico cifrado:
  
- Texto de introducción del correo electrónico que contiene el mensaje cifrado
    
- Texto de aviso de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado
    
- Texto del portal que aparecerá en el portal de visualización de mensajes
    
- Logotipo que aparecerá en el mensaje de correo electrónico y portal de visualización
    
También puede volver a la apariencia predeterminada en cualquier momento.
  
En el ejemplo siguiente se muestra un logotipo personalizado para ContosoPharma en los datos adjuntos del correo electrónico:
  
![Ejemplo de la página de visualización del mensaje cifrado](media/TA-OME-3attachment2.jpg)
  
 **Para personalizar los mensajes de correo electrónico de cifrado y el portal de cifrado con la marca de la organización**
  
1. Conectarse a Exchange Online mediante PowerShell remoto, tal como se describe en [conectarse a Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated).
    
2. Use el cmdlet Set-OMEConfiguration tal como se describe aquí: [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) o utilice la siguiente tabla para obtener instrucciones. 
    
   **Opciones de personalización de cifrado**

|**Para personalizar esta característica de la experiencia de cifrado**|**Use estos comandos de Windows PowerShell**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrado  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Ejemplo:**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Ejemplo:**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|Texto que aparece en la parte superior del portal de visualización de correo cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Ejemplo:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Ejemplo:**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff  <br/> Tamaño óptimo del archivo de logotipo: inferior a 40 KB  <br/> Tamaño óptimo de la imagen de logotipo: 170 x 70 píxeles  <br/> |
   
 **Para quitar las personalizaciones de marca de los mensajes de correo electrónico de cifrado y el portal de cifrado**
  
1. Conectarse a Exchange Online mediante PowerShell remoto, tal como se describe en [conectarse a Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).
    
2. Use el cmdlet Set-OMEConfiguration tal como se describe aquí: [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). Para quitar la organización de las personalizaciones de la DisclaimerText, EmailText, con marca y los valores de PortalText, establezca el valor en una cadena vacía, `""`. Para todos los valores, como el logotipo, de imagen, establezca el valor en `"$null"`.
    
   **Opciones de personalización de cifrado**

|**Para hacer que esta característica de la experiencia de cifrado vuelva a los valores de texto e imagen predeterminados**|**Use estos comandos de Windows PowerShell**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrado  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Ejemplo:**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Ejemplo:**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|Texto que aparece en la parte superior del portal de visualización de correo cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Ejemplo revertir a valor predeterminado:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Ejemplo revertir a valor predeterminado:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Información de servicio para cifrado de mensajes de Office 365 heredado antes del lanzamiento de las nuevas capacidades OME
<a name="LegacyServiceInfo"> </a>

En la siguiente tabla proporciona detalles técnicos para el servicio de cifrado de mensajes de Office 365 antes del lanzamiento de las nuevas capacidades OME.
  
|**Detalles del servicio**|**Descripción**|
|:-----|:-----|
|Requisitos de dispositivo de cliente  <br/> |Los mensajes cifrados se pueden ver en cualquier dispositivo de cliente, siempre y cuando los datos adjuntos HTML puedan abrirse en un explorador moderno que admita el envío de formularios.  <br/> |
|Algoritmo de cifrado y compatibilidad con FIPS (Estándar federal de procesamiento de información)  <br/> |Cifrado de mensajes de Office 365 usa las mismas claves de cifrado como Windows Azure Information Rights Management (IRM) y es compatible con cifrado en modo 2 (2K clave para RSA) y 256 bits para los sistemas de SHA-1. Para obtener más información acerca de los modos criptográficos subyacentes de IRM, consulte [Modos criptográficos de AD RMS](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).<br/> |
|Tipos de mensaje admitidos  <br/> |Sólo se admite el cifrado de mensajes de Office 365 para los elementos que tienen un identificador de clase de mensaje de **IPM. Nota**. Para obtener más información, vea [tipos de elementos y clases de mensajes](https://msdn.microsoft.com/library/office/ff861573.aspx).<br/> |
|Límites de tamaño de mensaje  <br/> |Cifrado de mensajes de Office 365 puede cifrar mensajes de hasta 25 megabytes. Para obtener más información acerca de los límites de tamaño de mensaje, consulte [Límites de Exchange Online](http://technet.microsoft.com/library/exchange-online-limits.aspx).<br/> |
|Directivas de retención de correo electrónico Exchange Online  <br/> |Exchange Online no almacena los mensajes cifrados.  <br/> |
|Compatibilidad de idiomas en el cifrado de mensajes de Office 365  <br/> | El cifrado de mensajes de Office 365 admite los idiomas de Office 365 de la siguiente manera:  <br/>  Los mensajes de correo electrónico entrantes y archivos HTML adjuntos están localizados en función de la configuración de idioma de la dirección del remitente.  <br/>  El portal de visualización se localiza en función de la configuración del explorador del destinatario.  <br/>  El cuerpo (contenido) del mensaje cifrado no se localiza.  <br/> |
|Información de privacidad del Portal OME y la aplicación Visor OME  <br/> |El vínculo [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) proporciona más información sobre el uso de su información privada por parte de Microsoft.  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>Preguntas más frecuentes acerca de OME heredado
<a name="LegacyServiceInfo"> </a>

¿Tiene alguna pregunta acerca del cifrado de mensajes de Office 365? A continuación presentamos algunas respuestas. Si no puede encontrar lo que necesita, compruebe los foros de la Comunidad de Office 365 en [la Comunidad de Office 365](http://community.office365.com/en-us/forums/default.aspx).
  
 **P. Mis a los usuarios envían mensajes de correo electrónico cifrado a destinatarios fuera de nuestra organización. ¿Hay algo que los destinatarios externos tienen que hacer para leer y responder a mensajes de correo electrónico que se cifran con el cifrado de mensajes de Office 365?**
  
Los destinatarios externos pueden leer los correos electrónicos que reciban cifrados con el cifrado de Office 365 de dos maneras:
  
- Iniciando sesión con una cuenta de Microsoft o una cuenta de trabajo o escuela asociado a Office 365.
    
- Código de acceso mediante el uso de una sola vez.
    
 **P. ¿Se almacenan los mensajes cifrados de Office 365 en la nube o en los servidores de Microsoft?**
  
No, los mensajes cifrados se conservan en el sistema de correo electrónico del destinatario y, cuando el destinatario abre el mensaje, se registra temporalmente para su visualización en los servidores de Office 365. Los mensajes no se almacenan allí.
  
 **P. ¿Puedo personalizar los mensajes de correo electrónico cifrado con mi marca?**
  
Sí. Puede usar cmdlets de Windows PowerShell para personalizar el texto predeterminado que aparece en la parte superior de los mensajes de correo electrónico cifrados, el texto de aviso de declinación de responsabilidades y el logotipo que quiera usar para el mensaje de correo electrónico y el portal de cifrado. Para más información, consulte [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **P. ¿Requiere el servicio una licencia para cada usuario de la organización?**
  
Se requiere una licencia para cada usuario de la organización que envíe correo electrónico cifrado.
  
 **P. ¿Requieren los destinatarios externos suscripciones?**
  
No, los destinatarios externos no requieren una suscripción para leer o responder los mensajes cifrados. 
  
 **P. ¿cómo es el cifrado de mensajes de Office 365 diferentes de Rights Management Services (RMS)?**
  
RMS proporciona capacidades de protección de derechos de información para los correos electrónicos internos de la organización al proporcionar plantillas integradas, tales como: no reenviar y confidencial de la compañía. Cifrado de mensajes de correo electrónico Office 365 cifrado de mensajes es compatible con los mensajes que se envían a destinatarios externos, así como los destinatarios internos.
  
 **P. ¿cómo es el cifrado de mensajes de Office 365 diferente de S/MIME?**
  
S/MIME es básicamente una tecnología de cifrado del lado cliente y requiere la administración de certificados complicados y la publicación de infraestructura. El cifrado de mensajes Office 365 usa reglas de transporte y no depende de la publicación de certificados.
  
 **P. ¿Puedo leer los mensajes cifrados en dispositivos móviles?**
  
Sí, puede ver los mensajes en Android y iOS mediante la descarga de las aplicaciones de Visor de OME desde el [almacén de Google reproducir](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409) y el [almacén de aplicación de Apple](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409). Abra los datos adjuntos HTML en la aplicación de Visor de OME y, a continuación, siga las instrucciones para abrir el mensaje cifrado. Para otros dispositivos móviles, puede abrir los datos adjuntos HTML como su cliente de correo es compatible con el envío de formularios.
  
 **P. ¿Se cifran las respuestas y los mensajes reenviados?**
  
Sí. Las respuestas se siguen cifrando durante todo el período de la conversación.
  
 **P. ¿Proporciona localización el cifrado de mensajes de Office 365?**
  
El correo electrónico entrante y el contenido HTML se localiza según la configuración de correo electrónico del remitente. El portal de visualización se localiza según la configuración del explorador del destinatario. Sin embargo, el cuerpo (contenido) del mensaje cifrado no se localiza.
  
 **P. ¿Qué método de cifrado se usa para el cifrado de mensajes de Office 365?**
  
El cifrado de mensajes de Office 365 usa Rights Management Services (RMS) como infraestructura de cifrado. El método de cifrado utilizado depende de dónde obtiene las claves de RMS utilizadas para cifrar y descifrar mensajes.
  
- Si utiliza Microsoft Azure RMS para obtener las claves, se usa 2 de modo de cifrado. 2 de modo de cifrado es una implementación criptográfica de AD RMS actualizada y mejorada. Admite RSA 2048 para firma y cifrado y admite SHA-256 para la firma.
    
- Si usa Active Directory (AD) RMS para obtener las claves, se utiliza el modo criptográfico 1 o el modo criptográfico 2. El método empleado depende de la implementación local de AD RMS. El modo criptográfico 1 es la implementación criptográfica original de AD RMS. Es compatible con RSA 1024 para firma y cifrado, y admite SHA-1 para firma. Este modo sigue siendo compatible con todas las versiones actuales de RMS.
    
Para obtener más información, consulte [Modos criptográficos de AD RMS](http://go.microsoft.com/fwlink/p/?LinkId=398616).
  
 **P. ¿Por qué algunos mensajes cifrados dicen proceder de Office365@messaging.microsoft.com?**
  
Cuando se envía una respuesta cifrada desde el portal de cifrado o a través de la aplicación del Visor de OME, la dirección de correo electrónico de envío se establece en Office365@messaging.microsoft.com porque el mensaje cifrado se envía a través de un extremo de Microsoft. Esto ayuda a evitar que los mensajes cifrados se marquen como correo no deseado. El nombre mostrado en el correo electrónico y la dirección del portal de cifrado no se modifican a causa de este etiquetado. Además, este etiquetado solo se aplica a los mensajes enviados a través del portal, no a través de cualquier otro cliente de correo electrónico.
  
 **P. soy un suscriptor de Exchange Hosted Encryption (EHE). ¿Dónde puedo obtener más información acerca de la actualización a Office 365 Message Encryption?**
  
Se han actualizado todos los clientes EHE al cifrado de mensajes de Office 365. Para obtener más información, visite el [Centro de actualización de cifrado de Exchange hospedado](http://go.microsoft.com/fwlink/p/?LinkID=511077).
  
 **P. ¿necesitan para abrir cualquier direcciones URL, direcciones IP o los puertos de firewall de la organización para admitir el cifrado de mensajes de Office 365?**
  
Sí. Debe agregar direcciones URL para Exchange Online para que la lista de permitidos de la organización habilite la autenticación de los mensajes cifrados por el servicio de cifrado de mensajes de Office 365. Para ver una lista de direcciones URL de Exchange Online, consulte [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx).
  
 **P. ¿A cuántos destinatarios puedo enviar un mensaje cifrado de Office 365?**
  
El límite de destinatarios para un mensaje cifrado se basa en el número de caracteres en el campo **para** del mensaje. Cuando se combina (después de la expansión de la lista de distribución), las direcciones de destinatario en el campo **para** no deben superar los 11,980 caracteres. Debido a que las direcciones de correo electrónico pueden variar en longitud de caracteres, no hay un límite de destinatarios estándar para un único mensaje cifrado. 
  
 **P. ¿Es posible revocar un mensaje enviado a un destinatario concreto?**
  
No. No se puede revocar un mensaje a una persona en particular después de enviarlo.
  
 **P. ¿Puedo ver un informe de los mensajes cifrados que se han recibido y leído?**
  
No hay un informe que muestra si se ha visto un mensaje cifrado, pero hay disponibles que pueden aprovechar para determinar el número de mensajes que coincide con una regla de transporte específica, por ejemplo informes de Office 365.
  
 **P. ¿Qué hace Microsoft con la información que proporciono a través del Portal OME y la aplicación Visor OME?**
  
La [declaración de privacidad de Portal de cifrado de mensajería de Office 365](protected-message-viewer-portal-privacy-statement.md) proporciona información detallada sobre lo que Microsoft hace y no hace con su información privada. 
  

