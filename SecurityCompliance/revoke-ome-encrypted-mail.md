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
ms.openlocfilehash: 098ce50791152c8bbb4e4692d6fb85e4c2c7cb58
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156792"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="f7893-103">Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="f7893-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="f7893-104">La revocación de correo electrónico se ofrece como parte de un cifrado de mensajes avanzado de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7893-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="f7893-105">Office 365 Advanced Message Encryption está disponible sobre el cifrado de mensajes de Office 365 en determinadas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="f7893-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="f7893-106">El cifrado de mensajes avanzado se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 y Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="f7893-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="f7893-107">Si su organización tiene una suscripción de Office 365 que no incluye el cifrado avanzado de mensajes de Office 365, puede comprar el cifrado de mensajes avanzado como complemento con la compatibilidad con E5 del SKU de compatibilidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="f7893-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="f7893-108">Este artículo forma parte de una amplia serie de artículos sobre el cifrado de [mensajes de Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="f7893-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="f7893-109">Es posible que necesite revocar un correo electrónico que ya se ha enviado.</span><span class="sxs-lookup"><span data-stu-id="f7893-109">You may find it necessary to revoke an email that has already been sent.</span></span> <span data-ttu-id="f7893-110">Si el correo electrónico se cifró mediante el cifrado de mensajes avanzado de Office 365 y es administrador de Office 365, puede hacerlo para el correo electrónico en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="f7893-110">If the email was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions.</span></span> <span data-ttu-id="f7893-111">En este artículo se describen las circunstancias en las que esto es posible y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f7893-111">This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="f7893-112">Mensajes de correo electrónico cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="f7893-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="f7893-113">Puede revocar los correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos con marcas.</span><span class="sxs-lookup"><span data-stu-id="f7893-113">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="f7893-114">Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, dichos mensajes no se pueden revocar.</span><span class="sxs-lookup"><span data-stu-id="f7893-114">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="f7893-115">El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles.</span><span class="sxs-lookup"><span data-stu-id="f7893-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="f7893-116">Todos los demás tipos de destinatarios, como los destinatarios de gmail, obtienen una experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="f7893-116">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="f7893-117">Experiencia del destinatario para correos electrónicos cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="f7893-117">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="f7893-118">Una vez que se haya revocado un correo electrónico, el destinatario recibirá un error al intentar obtener acceso al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".</span><span class="sxs-lookup"><span data-stu-id="f7893-118">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="f7893-120">Cómo revocar un correo electrónico cifrado</span><span class="sxs-lookup"><span data-stu-id="f7893-120">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="f7893-121">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="f7893-121">Step 1.</span></span> <span data-ttu-id="f7893-122">Obtener el identificador del mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f7893-122">Obtain the Message ID of the email</span></span>

<span data-ttu-id="f7893-123">Para poder revocar un correo cifrado, debe recopilar el identificador de mensaje del correo.</span><span class="sxs-lookup"><span data-stu-id="f7893-123">Before you can revoke an encrypted mail you need to gather the Message ID of the mail.</span></span> <span data-ttu-id="f7893-124">El MessageId suele tener el formato:</span><span class="sxs-lookup"><span data-stu-id="f7893-124">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="f7893-125">Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="f7893-125">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="f7893-126">En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.</span><span class="sxs-lookup"><span data-stu-id="f7893-126">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="f7893-127">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en &amp; el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f7893-127">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="f7893-128">Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevo en el centro de seguridad _AMP_ cumplimiento de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="f7893-128">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="f7893-129">Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** .</span><span class="sxs-lookup"><span data-stu-id="f7893-129">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="f7893-130">Expanda **más información** para buscar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7893-130">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="f7893-131">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes &amp; de Office en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f7893-131">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="f7893-132">En el centro &amp; de seguridad y cumplimiento, navegue hasta el informe de cifrado de **mensajes**.</span><span class="sxs-lookup"><span data-stu-id="f7893-132">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>

2. <span data-ttu-id="f7893-133">Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="f7893-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="f7893-134">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7893-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="f7893-135">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="f7893-135">Step 2.</span></span> <span data-ttu-id="f7893-136">Comprobar que el correo es revocable</span><span class="sxs-lookup"><span data-stu-id="f7893-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="f7893-137">Para comprobar si puede revocar un mensaje de correo electrónico determinado, compruebe si el campo Estado de revocación está \*\*\*\* visible en la tabla detalles &amp; del centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f7893-137">To verify whether you can revoke a particular email message, check whether the Revocation Status field is visible in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="f7893-138">Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f7893-138">To verify whether or not you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="f7893-139">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7893-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f7893-140">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f7893-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f7893-141">Ejecute el cmdlet Set-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f7893-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="f7893-142">Esto devuelve el asunto del mensaje y si el mensaje es revocable.</span><span class="sxs-lookup"><span data-stu-id="f7893-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="f7893-143">For example,</span><span class="sxs-lookup"><span data-stu-id="f7893-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="f7893-144">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="f7893-144">Step 3.</span></span> <span data-ttu-id="f7893-145">Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="f7893-145">Revoke the mail</span></span>  

<span data-ttu-id="f7893-146">Una vez que conozca el identificador del mensaje de correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f7893-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email.</span></span>

<span data-ttu-id="f7893-147">Para revocar el correo electrónico en &amp; el centro de seguridad y cumplimiento, en la tabla de **detalles** , elija **revocar**.</span><span class="sxs-lookup"><span data-stu-id="f7893-147">To revoke the email in the Security &amp; Compliance Center, in the **Details** table, choose **Revoke**.</span></span>

<span data-ttu-id="f7893-148">Puede revocar un correo electrónico mediante Windows PowerShell con el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="f7893-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="f7893-149">[Conexión al PowerShell de Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f7893-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f7893-150">Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f7893-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="f7893-151">Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f7893-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="f7893-152">Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f7893-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="f7893-153">Más información sobre el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="f7893-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="f7893-154">Cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="f7893-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="f7893-155">Office 365 Advanced Message Encryption-expiración del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f7893-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="f7893-156">Descripción de la Directiva de mensajes y el servicio de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f7893-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)