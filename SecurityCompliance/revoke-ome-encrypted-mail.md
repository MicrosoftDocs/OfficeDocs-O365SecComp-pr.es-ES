---
title: Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador de Office 365, puede revocar determinados mensajes de correo electrónico cifrados con el cifrado avanzado de mensajes de Office 365.
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857620"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365

La revocación de correo electrónico se ofrece como parte de un cifrado de mensajes avanzado de Office 365. Office 365 Advanced Message Encryption está disponible sobre el cifrado de mensajes de Office 365 en determinadas suscripciones. El cifrado de mensajes avanzado se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 y Office 365 Education A5. Si su organización tiene una suscripción de Office 365 que no incluye el cifrado avanzado de mensajes de Office 365, puede comprar el cifrado de mensajes avanzado como complemento con la compatibilidad con E5 del SKU de compatibilidad avanzada.

Este artículo forma parte de una amplia serie de artículos sobre el cifrado de [mensajes de Office 365](ome.md).

Si un mensaje se cifró mediante el cifrado de mensajes avanzado de Office 365 y usted es administrador de Office 365, puede revocar el mensaje en determinadas circunstancias. En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Mensajes de correo electrónico cifrados que puede revocar

Puede revocar los correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos con marcas. Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, dichos mensajes no se pueden revocar.

El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles. Todos los demás tipos de destinatarios, como los destinatarios de gmail, obtienen una experiencia basada en vínculos.

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiencia del destinatario para correos electrónicos cifrados revocados

Una vez que se ha revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>Cómo revocar un correo electrónico cifrado

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Paso 1. Obtener el identificador del mensaje de correo electrónico

Para poder revocar un correo cifrado, debe recopilar el identificador de mensaje del correo. El MessageId suele tener el formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar. En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en &amp; el centro de seguridad y cumplimiento

1. Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevo en el centro de seguridad & cumplimiento de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** . Expanda **más información** para buscar el identificador de mensaje.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes &amp; de Office en el centro de seguridad y cumplimiento

1. En el centro &amp; de seguridad y cumplimiento, navegue hasta el informe de cifrado de **mensajes**. Para obtener información sobre este informe, consulte [ver informes de seguridad de correo &amp; electrónico en el centro de seguridad y cumplimiento](view-email-security-reports.md).

2. Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.

3. Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Paso 2. Comprobar que el correo es revocable

Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe de cifrado **** , en la tabla de &amp; detalles del centro de seguridad y cumplimiento.

Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Esto devuelve el asunto del mensaje y si el mensaje es revocable. For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>Paso 3. Revocar el correo

Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante &amp; el centro de seguridad y cumplimiento o Windows PowerShell.

Para revocar el mensaje mediante el &amp; centro de seguridad y cumplimiento

Para revocar el correo electrónico en &amp; el centro de seguridad y cumplimiento, en el informe de cifrado, en la tabla de **detalles** del mensaje, elija **revocar mensaje**.

Puede revocar un correo electrónico mediante Windows PowerShell con el cmdlet Set-OMEMessageRevocation.

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

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre el cifrado de mensajes avanzado de Office 365

- [Cifrado avanzado de mensajes de Office 365](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption-expiración del correo electrónico](ome-advanced-expiration.md)

- [Descripción de la Directiva de mensajes y el servicio de cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
