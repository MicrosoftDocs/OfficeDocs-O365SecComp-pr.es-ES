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
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="37a5a-103">Revocación de correo electrónico de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="37a5a-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="37a5a-p101">En este artículo es parte de una serie de artículos sobre [Office 365 Message Encryption](ome.md)más grande. Revocación de correo electrónico cifrados, derecho ahora está en vista previa. Esperan que las actualizaciones y los cambios realizados en la característica y el contenido se continúa mejorando nuestra oferta.</span><span class="sxs-lookup"><span data-stu-id="37a5a-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="37a5a-p102">Es posible que encuentre necesario revocar un correo electrónico que ya se ha enviado. Si el correo electrónico se cifró mediante el cifrado de mensajes de Office 365, y es un administrador de Office 365, puede hacerlo para el correo electrónico en determinadas condiciones. En este artículo se describe en qué circunstancias esto es posible y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="37a5a-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="37a5a-110">Mensajes de correo electrónico cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="37a5a-110">Encrypted emails that you can revoke</span></span>
<span data-ttu-id="37a5a-p103">Mensajes de correo electrónico cifrados se pueden revocar si el destinatario recibe un vínculo basada en correo electrónico cifrado con la marca. Si el destinatario recibe una experiencia en línea nativo en un cliente de Outlook compatible, esos mensajes de correo electrónico no pueden ser revocados.</span><span class="sxs-lookup"><span data-stu-id="37a5a-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="37a5a-113">Si un destinatario recibe una experiencia basada en un vínculo o una experiencia en línea depende del tipo de destinatario de identidad: Office 365 y Microsoft Account destinatarios (por ejemplo, los usuarios de outlook.com) obtener una experiencia en línea en los clientes de Outlook compatibles.</span><span class="sxs-lookup"><span data-stu-id="37a5a-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span>  
<span data-ttu-id="37a5a-114">Todos los otros tipos de destinatario, como destinatarios de Gmail, obtener una experiencia basada en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="37a5a-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span> 

<span data-ttu-id="37a5a-p104">Próximamente, las organizaciones tendrán la capacidad para forzar una experiencia basada en el vínculo, independientemente de la identidad del destinatario. De este modo, todos los destinatarios obtendrá un correo electrónico con marca con un vínculo al portal de cifrado de mensajes de Office 365 donde puedan leer y responder a mensajes de correo electrónico cifrados. Todas esos correos electrónicos cifrados será revocable.</span><span class="sxs-lookup"><span data-stu-id="37a5a-p104">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span> 
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="37a5a-118">Experiencia de destinatario para mensajes de correo electrónico cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="37a5a-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="37a5a-119">Una vez que se ha revocado un correo electrónico, el destinatario producirá un error al intentar tener acceso el correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el mensaje se ha revocado por el remitente".</span><span class="sxs-lookup"><span data-stu-id="37a5a-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)
    
## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="37a5a-121">Procedimiento para revocar un correo electrónico cifrado</span><span class="sxs-lookup"><span data-stu-id="37a5a-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="37a5a-p105">Paso 1. Obtener el identificador de mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="37a5a-p105">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="37a5a-p106">Antes de que se puede revocar un correo cifrado necesita recopilar el identificador de mensaje de correo electrónico. El identificador del mensaje normalmente tiene el formato:</span><span class="sxs-lookup"><span data-stu-id="37a5a-p106">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="37a5a-p107">Hay varias maneras de averiguar el identificador de mensaje de correo electrónico que se va a revocar. En esta sección se describe un par de opciones, pero se puede usar cualquier método que proporciona el identificador.</span><span class="sxs-lookup"><span data-stu-id="37a5a-p107">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="37a5a-128">Para identificar el identificador de mensaje de correo electrónico que desea revocar mediante el uso de seguimiento de mensajes en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="37a5a-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="37a5a-129">Búsqueda para el correo electrónico por remitente o destinatario que usa el [Nuevo seguimiento de mensajes en el centro de cumplimiento y seguridad de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="37a5a-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="37a5a-p108">Una vez que haya ubicado el correo electrónico selecciónelo para que aparezcan en el panel de **Detalles de seguimiento de mensajes** . Expanda **Más información** para encontrar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="37a5a-p108">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="37a5a-132">Para identificar el identificador de mensaje de correo electrónico que desea revocar mediante el uso de informes de cifrado de mensajes de Office en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="37a5a-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>
1. <span data-ttu-id="37a5a-133">En la seguridad &amp; centro de cumplimiento, desplácese hasta el **Informe de cifrado de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="37a5a-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="37a5a-134">Elija la tabla de **Detalles de la vista** e identificar el mensaje que se va a revocar.</span><span class="sxs-lookup"><span data-stu-id="37a5a-134">Choose the **View details** table and identify the message that you want to revoke.</span></span> 
3. <span data-ttu-id="37a5a-135">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="37a5a-135">Double-click the message to view details that include the Message ID.</span></span> 

### <a name="step-2-revoke-the-mail"></a><span data-ttu-id="37a5a-p109">Paso 2. Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="37a5a-p109">Step 2. Revoke the mail</span></span>  

<span data-ttu-id="37a5a-138">Una vez que sepa el identificador de mensaje de correo electrónico que desea revocar, puede revocar el correo electrónico mediante el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="37a5a-138">Once you know the Message ID of the email you want to revoke, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span> 

1. <span data-ttu-id="37a5a-139">[Conectarse a Exchange Online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="37a5a-139">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="37a5a-140">Ejecute el cmdlet Set-OMEMessageRevocation como sigue:</span><span class="sxs-lookup"><span data-stu-id="37a5a-140">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>
    
    ```
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. <span data-ttu-id="37a5a-141">Para comprobar si se ha revocado el correo electrónico, ejecute el cmdlet Get-OMEMessageStatus como sigue:</span><span class="sxs-lookup"><span data-stu-id="37a5a-141">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>
    
    ```
    Get-OMEMessageStatus -MessageId "<messageId>"
    ```  
    <span data-ttu-id="37a5a-142">Si revocación se realizó correctamente, el cmdlet devuelve el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="37a5a-142">If revocation was successful, the cmdlet returns the following result:</span></span>  

    ```The encrypted email with the subject "<subject>" and Message ID "<messageId>" was successfully revoked.```
