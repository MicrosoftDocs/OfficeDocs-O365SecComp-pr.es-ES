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
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214900"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="394a8-103">Revocación del correo electrónico de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="394a8-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="394a8-p101">Este artículo forma parte de una amplia serie de artículos sobre el cifrado de [mensajes de Office 365](ome.md). Ahora, la revocación del correo electrónico cifrado está en versión preliminar. Espere actualizaciones y cambios en la característica y el contenido a medida que continuamos mejorando nuestra oferta.</span><span class="sxs-lookup"><span data-stu-id="394a8-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="394a8-p102">Es posible que necesite revocar un correo electrónico que ya se ha enviado. Si el correo electrónico se cifró mediante el cifrado de mensajes de Office 365 y es administrador de Office 365, puede hacerlo para el correo electrónico en determinadas condiciones. En este artículo se describen las circunstancias en las que esto es posible y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="394a8-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="394a8-110">Mensajes de correo electrónico cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="394a8-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="394a8-p103">Puede revocar los correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos con marcas. Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, dichos mensajes no se pueden revocar.</span><span class="sxs-lookup"><span data-stu-id="394a8-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="394a8-p104">El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles. Todos los demás tipos de destinatarios, como los destinatarios de gmail, obtienen una experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="394a8-p104">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients. All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

<span data-ttu-id="394a8-p105">Próximamente, las organizaciones tendrán la posibilidad de forzar una experiencia basada en vínculos independientemente de la identidad del destinatario. De esta forma, todos los destinatarios recibirán un correo electrónico con marca con un vínculo al portal de cifrado de mensajes de Office 365 donde podrán leer y responder a los correos electrónicos cifrados. Todos los mensajes de correo electrónico cifrados serán revocables.</span><span class="sxs-lookup"><span data-stu-id="394a8-p105">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span>
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="394a8-118">Experiencia del destinatario para correos electrónicos cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="394a8-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="394a8-119">Una vez que se haya revocado un correo electrónico, el destinatario recibirá un error al intentar obtener acceso al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".</span><span class="sxs-lookup"><span data-stu-id="394a8-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="394a8-121">Cómo revocar un correo electrónico cifrado</span><span class="sxs-lookup"><span data-stu-id="394a8-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="394a8-p106">Paso 1. Obtener el identificador del mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="394a8-p106">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="394a8-p107">Para poder revocar un correo cifrado, debe recopilar el identificador de mensaje del correo. El MessageId suele tener el formato:</span><span class="sxs-lookup"><span data-stu-id="394a8-p107">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="394a8-p108">Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar. En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.</span><span class="sxs-lookup"><span data-stu-id="394a8-p108">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="394a8-128">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en &amp; el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="394a8-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="394a8-129">Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevo en el centro de seguridad _AMP_ cumplimiento de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="394a8-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="394a8-p109">Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** . ExPanda **más información** para buscar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="394a8-p109">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="394a8-132">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes &amp; de Office en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="394a8-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="394a8-133">En el centro &amp; de seguridad y cumplimiento, navegue hasta el informe de cifraDo de **mensajes**.</span><span class="sxs-lookup"><span data-stu-id="394a8-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="394a8-134">Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="394a8-134">Choose the **View details** table and identify the message that you want to revoke.</span></span>
3. <span data-ttu-id="394a8-135">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.</span><span class="sxs-lookup"><span data-stu-id="394a8-135">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="394a8-p110">Paso 2. Comprobar que el correo es revocable</span><span class="sxs-lookup"><span data-stu-id="394a8-p110">Step 2. Verify that the mail is revocable</span></span>

<span data-ttu-id="394a8-138">Para comprobar si puede revocar un mensaje de correo electrónico determinado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="394a8-138">To verify whether or not you can revoke a particular email message, complete these steps.</span></span>

1. <span data-ttu-id="394a8-p111">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="394a8-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="394a8-141">Ejecute el cmdlet Set-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="394a8-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="394a8-p112">Esto devuelve el asunto del mensaje y si el mensaje es revocable. Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="394a8-p112">This returns the subject of the message and whether the message is revocable. For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="394a8-p113">Paso 3. Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="394a8-p113">Step 3. Revoke the mail</span></span>  

<span data-ttu-id="394a8-146">Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico con el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="394a8-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="394a8-147">[Conexión a PowerShell de Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="394a8-147">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="394a8-148">Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="394a8-148">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="394a8-149">Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="394a8-149">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    <span data-ttu-id="394a8-150">Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="394a8-150">If revocation was successful, the cmdlet returns the following result:</span></span>  

    `Revoked: True`
