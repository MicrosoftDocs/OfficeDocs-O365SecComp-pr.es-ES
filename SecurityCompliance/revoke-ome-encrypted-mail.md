---
title: Revocar el correo electrónico cifrado con cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Como administrador de Office 365, puede revocar determinados mensajes de correo electrónico cifrados con cifrado de mensajes de Office 365.
ms.openlocfilehash: 19eb874fa15a21c29a9eb2823829e81ff244a555
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011826"
---
# <a name="office-365-message-encryption-email-revocation"></a>Revocación de correo electrónico de cifrado de mensajes de Office 365

En este artículo es parte de una serie de artículos sobre [Office 365 Message Encryption](ome.md)más grande. Revocación de correo electrónico cifrados, derecho ahora está en vista previa. Esperan que las actualizaciones y los cambios realizados en la característica y el contenido se continúa mejorando nuestra oferta.

Es posible que encuentre necesario revocar un correo electrónico que ya se ha enviado. Si el correo electrónico se cifró mediante el cifrado de mensajes de Office 365, y es un administrador de Office 365, puede hacerlo para el correo electrónico en determinadas condiciones. En este artículo se describe en qué circunstancias esto es posible y cómo hacerlo.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Mensajes de correo electrónico cifrados que puede revocar
Mensajes de correo electrónico cifrados se pueden revocar si el destinatario recibe un vínculo basada en correo electrónico cifrado con la marca. Si el destinatario recibe una experiencia en línea nativo en un cliente de Outlook compatible, esos mensajes de correo electrónico no pueden ser revocados.

Si un destinatario recibe una experiencia basada en un vínculo o una experiencia en línea depende del tipo de destinatario de identidad: Office 365 y Microsoft Account destinatarios (por ejemplo, los usuarios de outlook.com) obtener una experiencia en línea en los clientes de Outlook compatibles.  
Todos los otros tipos de destinatario, como destinatarios de Gmail, obtener una experiencia basada en el vínculo. 

Próximamente, las organizaciones tendrán la capacidad para forzar una experiencia basada en el vínculo, independientemente de la identidad del destinatario. De este modo, todos los destinatarios obtendrá un correo electrónico con marca con un vínculo al portal de cifrado de mensajes de Office 365 donde puedan leer y responder a mensajes de correo electrónico cifrados. Todas esos correos electrónicos cifrados será revocable. 
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiencia de destinatario para mensajes de correo electrónico cifrados revocados

Una vez que se ha revocado un correo electrónico, el destinatario producirá un error al intentar tener acceso el correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el mensaje se ha revocado por el remitente".

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)
    
## <a name="how-to-revoke-an-encrypted-email"></a>Procedimiento para revocar un correo electrónico cifrado

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Paso 1. Obtener el identificador de mensaje de correo electrónico

Antes de que se puede revocar un correo cifrado necesita recopilar el identificador de mensaje de correo electrónico. El identificador del mensaje normalmente tiene el formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Hay varias maneras de averiguar el identificador de mensaje de correo electrónico que se va a revocar. En esta sección se describe un par de opciones, pero se puede usar cualquier método que proporciona el identificador.

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje de correo electrónico que desea revocar mediante el uso de seguimiento de mensajes en la seguridad &amp; centro de cumplimiento

1. Búsqueda para el correo electrónico por remitente o destinatario que usa el [Nuevo seguimiento de mensajes en el centro de cumplimiento y seguridad de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).
2. Una vez que haya ubicado el correo electrónico selecciónelo para que aparezcan en el panel de **Detalles de seguimiento de mensajes** . Expanda **Más información** para encontrar el identificador de mensaje.

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje de correo electrónico que desea revocar mediante el uso de informes de cifrado de mensajes de Office en la seguridad &amp; centro de cumplimiento
1. En la seguridad &amp; centro de cumplimiento, desplácese hasta el **Informe de cifrado de mensajes**.
2. Elija la tabla de **Detalles de la vista** e identificar el mensaje que se va a revocar. 
3. Haga doble clic en el mensaje para ver los detalles que incluyen el identificador de mensaje. 

### <a name="step-2-revoke-the-mail"></a>Paso 2. Revocar el correo  

Una vez que sepa el identificador de mensaje de correo electrónico que desea revocar, puede revocar el correo electrónico mediante el cmdlet Set-OMEMessageRevocation. 

1. [Conectarse a Exchange Online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Ejecute el cmdlet Set-OMEMessageRevocation como sigue:
    
    ```
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. Para comprobar si se ha revocado el correo electrónico, ejecute el cmdlet Get-OMEMessageStatus como sigue:
    
    ```
    Get-OMEMessageStatus -MessageId "<messageId>"
    ```  
    Si revocación se realizó correctamente, el cmdlet devuelve el resultado siguiente:  

    ```The encrypted email with the subject "<subject>" and Message ID "<messageId>" was successfully revoked.```
