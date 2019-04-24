---
title: Revocar el correo electrónico cifrado por el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Como administrador de Office 365, puede revocar determinados mensajes de correo electrónico cifrados con el cifrado de mensajes de Office 365.
ms.openlocfilehash: 75b5e46e25f447ddac0de5a7911d0df8385da6b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264832"
---
# <a name="office-365-message-encryption-email-revocation"></a>Revocación del correo electrónico de cifrado de mensajes de Office 365

Este artículo forma parte de una amplia serie de artículos sobre el cifrado de [mensajes de Office 365](ome.md). Ahora, la revocación del correo electrónico cifrado está en versión preliminar. Espere actualizaciones y cambios en la característica y el contenido a medida que continuamos mejorando nuestra oferta.

Es posible que necesite revocar un correo electrónico que ya se ha enviado. Si el correo electrónico se cifró mediante el cifrado de mensajes de Office 365 y es administrador de Office 365, puede hacerlo para el correo electrónico en determinadas condiciones. En este artículo se describen las circunstancias en las que esto es posible y cómo hacerlo.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Mensajes de correo electrónico cifrados que puede revocar

Puede revocar los correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos con marcas. Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, dichos mensajes no se pueden revocar.

El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles. Todos los demás tipos de destinatarios, como los destinatarios de gmail, obtienen una experiencia basada en vínculos.

Próximamente, las organizaciones tendrán la posibilidad de forzar una experiencia basada en vínculos independientemente de la identidad del destinatario. De esta forma, todos los destinatarios recibirán un correo electrónico con marca con un vínculo al portal de cifrado de mensajes de Office 365 donde podrán leer y responder a los correos electrónicos cifrados. Todos los mensajes de correo electrónico cifrados serán revocables.
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiencia del destinatario para correos electrónicos cifrados revocados

Una vez que se haya revocado un correo electrónico, el destinatario recibirá un error al intentar obtener acceso al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>Cómo revocar un correo electrónico cifrado

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Paso 1. Obtener el identificador del mensaje de correo electrónico

Para poder revocar un correo cifrado, debe recopilar el identificador de mensaje del correo. El MessageId suele tener el formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar. En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en &amp; el centro de seguridad y cumplimiento

1. Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevo en el centro de seguridad _AMP_ cumplimiento de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).
2. Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** . ExPanda **más información** para buscar el identificador de mensaje.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes &amp; de Office en el centro de seguridad y cumplimiento

1. En el centro &amp; de seguridad y cumplimiento, navegue hasta el informe de cifraDo de **mensajes**.
2. Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.
3. Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Paso 2. Comprobar que el correo es revocable

Para comprobar si puede revocar un mensaje de correo electrónico determinado, siga estos pasos.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-OMEMessageStatus de la siguiente manera:
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   Esto devuelve el asunto del mensaje y si el mensaje es revocable. For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>Paso 3. Revocar el correo  

Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico con el cmdlet Set-OMEMessageRevocation.

1. [Conexión al PowerShell de Exchange Online](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:  

    `Revoked: True`
