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
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="6415d-103">Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="6415d-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="6415d-104">La revocación de correo electrónico se ofrece como parte de un cifrado de mensajes avanzado de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6415d-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="6415d-105">Office 365 Advanced Message Encryption está disponible sobre el cifrado de mensajes de Office 365 en determinadas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="6415d-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="6415d-106">El cifrado de mensajes avanzado se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 y Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="6415d-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="6415d-107">Si su organización tiene una suscripción de Office 365 que no incluye el cifrado avanzado de mensajes de Office 365, puede comprar el cifrado de mensajes avanzado como complemento con la compatibilidad con E5 del SKU de compatibilidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="6415d-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="6415d-108">Este artículo forma parte de una amplia serie de artículos sobre el cifrado de [mensajes de Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="6415d-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="6415d-109">Si un mensaje se cifró mediante el cifrado de mensajes avanzado de Office 365 y usted es administrador de Office 365, puede revocar el mensaje en determinadas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="6415d-109">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="6415d-110">En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6415d-110">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="6415d-111">Mensajes de correo electrónico cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="6415d-111">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="6415d-112">Puede revocar los correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos con marcas.</span><span class="sxs-lookup"><span data-stu-id="6415d-112">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="6415d-113">Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, dichos mensajes no se pueden revocar.</span><span class="sxs-lookup"><span data-stu-id="6415d-113">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="6415d-114">El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles.</span><span class="sxs-lookup"><span data-stu-id="6415d-114">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="6415d-115">Todos los demás tipos de destinatarios, como los destinatarios de gmail, obtienen una experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="6415d-115">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="6415d-116">Experiencia del destinatario para correos electrónicos cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="6415d-116">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="6415d-117">Una vez que se ha revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".</span><span class="sxs-lookup"><span data-stu-id="6415d-117">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="6415d-119">Cómo revocar un correo electrónico cifrado</span><span class="sxs-lookup"><span data-stu-id="6415d-119">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="6415d-120">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="6415d-120">Step 1.</span></span> <span data-ttu-id="6415d-121">Obtener el identificador del mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6415d-121">Obtain the Message ID of the email</span></span>

<span data-ttu-id="6415d-122">Para poder revocar un correo cifrado, debe recopilar el identificador de mensaje del correo.</span><span class="sxs-lookup"><span data-stu-id="6415d-122">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="6415d-123">El MessageId suele tener el formato:</span><span class="sxs-lookup"><span data-stu-id="6415d-123">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="6415d-124">Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="6415d-124">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="6415d-125">En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.</span><span class="sxs-lookup"><span data-stu-id="6415d-125">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="6415d-126">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en &amp; el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6415d-126">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="6415d-127">Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevo en el centro de seguridad & cumplimiento de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="6415d-127">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="6415d-128">Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** .</span><span class="sxs-lookup"><span data-stu-id="6415d-128">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="6415d-129">Expanda **más información** para buscar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="6415d-129">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="6415d-130">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes &amp; de Office en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6415d-130">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="6415d-131">En el centro &amp; de seguridad y cumplimiento, navegue hasta el informe de cifrado de **mensajes**.</span><span class="sxs-lookup"><span data-stu-id="6415d-131">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="6415d-132">Para obtener información sobre este informe, consulte [ver informes de seguridad de correo &amp; electrónico en el centro de seguridad y cumplimiento](view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="6415d-132">For information on this report, see [View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md).</span></span>

2. <span data-ttu-id="6415d-133">Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="6415d-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="6415d-134">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6415d-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="6415d-135">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="6415d-135">Step 2.</span></span> <span data-ttu-id="6415d-136">Comprobar que el correo es revocable</span><span class="sxs-lookup"><span data-stu-id="6415d-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="6415d-137">Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe de cifrado \*\*\*\* , en la tabla de &amp; detalles del centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6415d-137">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="6415d-138">Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6415d-138">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="6415d-139">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6415d-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="6415d-140">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="6415d-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="6415d-141">Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6415d-141">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="6415d-142">Esto devuelve el asunto del mensaje y si el mensaje es revocable.</span><span class="sxs-lookup"><span data-stu-id="6415d-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="6415d-143">For example,</span><span class="sxs-lookup"><span data-stu-id="6415d-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="6415d-144">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="6415d-144">Step 3.</span></span> <span data-ttu-id="6415d-145">Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="6415d-145">Revoke the mail</span></span>

<span data-ttu-id="6415d-146">Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante &amp; el centro de seguridad y cumplimiento o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6415d-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="6415d-147">Para revocar el mensaje mediante el &amp; centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6415d-147">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="6415d-148">Para revocar el correo electrónico en &amp; el centro de seguridad y cumplimiento, en el informe de cifrado, en la tabla de **detalles** del mensaje, elija **revocar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="6415d-148">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="6415d-149">Puede revocar un correo electrónico mediante Windows PowerShell con el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="6415d-149">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="6415d-150">[Conexión al PowerShell de Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="6415d-150">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="6415d-151">Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6415d-151">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="6415d-152">Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6415d-152">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="6415d-153">Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6415d-153">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="6415d-154">Más información sobre el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="6415d-154">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="6415d-155">Cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="6415d-155">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="6415d-156">Office 365 Advanced Message Encryption-expiración del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6415d-156">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="6415d-157">Descripción de la Directiva de mensajes y el servicio de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6415d-157">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
