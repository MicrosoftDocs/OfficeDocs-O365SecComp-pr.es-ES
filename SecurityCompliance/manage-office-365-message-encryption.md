---
title: Administrar el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Una vez que haya terminado de configurar el cifrado de mensajes de Office 365 (OME), puede personalizar la configuración de la implementación de varias maneras. Por ejemplo, puede configurar si desea habilitar códigos de paso de una sola vez, mostrar el botón proteger en Outlook en la web y más. Las tareas de este artículo describen cómo hacerlo.
ms.openlocfilehash: 9b59e352131121978ae6a523cc07ea40196e8038
ms.sourcegitcommit: bc25ea19c0b6d318751eadc4f27902b0054d5e2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054702"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="11ed3-105">Administrar el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="11ed3-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="11ed3-106">Una vez que haya terminado de configurar el cifrado de mensajes de Office 365 (OME), puede personalizar la configuración de la implementación de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="11ed3-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="11ed3-107">Por ejemplo, puede configurar si desea habilitar códigos de paso de una sola vez, Mostrar \*\*\*\* el botón cifrar en Outlook en la web y más.</span><span class="sxs-lookup"><span data-stu-id="11ed3-107">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="11ed3-108">Las tareas de este artículo describen cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="11ed3-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="11ed3-109">Administrar si los destinatarios de cuentas de Google, Yahoo y Microsoft pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="11ed3-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="11ed3-110">Cuando se configuran las nuevas capacidades de cifrado de mensajes de Office 365, los usuarios de la organización pueden enviar mensajes a destinatarios que están fuera de la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="11ed3-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="11ed3-111">Si el destinatario usa un *identificador social* , como una cuenta de Google, una cuenta de Yahoo o una cuenta de Microsoft, el destinatario puede iniciar sesión en el portal de OME con un identificador social.</span><span class="sxs-lookup"><span data-stu-id="11ed3-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="11ed3-112">Si lo desea, puede optar por no permitir que los destinatarios usen identificadores sociales para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="11ed3-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="11ed3-113">Para administrar si los destinatarios pueden usar identificadores sociales para iniciar sesión en el portal de OME</span><span class="sxs-lookup"><span data-stu-id="11ed3-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="11ed3-114">[Conéctese a Exchange online mediante PowerShell remoto](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="11ed3-114">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="11ed3-115">Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="11ed3-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="11ed3-116">Por ejemplo, para deshabilitar los identificadores sociales:</span><span class="sxs-lookup"><span data-stu-id="11ed3-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="11ed3-117">Para habilitar los identificadores sociales:</span><span class="sxs-lookup"><span data-stu-id="11ed3-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="11ed3-118">Administrar el uso de códigos de paso de una sola vez para el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="11ed3-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="11ed3-119">Si el destinatario de un mensaje cifrado por OME no usa Outlook, independientemente de la cuenta usada por el destinatario, el destinatario recibe un vínculo de vista Web limitado que les permite leer el mensaje.</span><span class="sxs-lookup"><span data-stu-id="11ed3-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="11ed3-120">Este vínculo incluye un código de paso único.</span><span class="sxs-lookup"><span data-stu-id="11ed3-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="11ed3-121">Como administrador, puede decidir si los destinatarios pueden usar códigos de paso único para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="11ed3-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="11ed3-122">Para administrar si OME genera códigos de paso de un solo tiempo</span><span class="sxs-lookup"><span data-stu-id="11ed3-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="11ed3-123">Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11ed3-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="11ed3-124">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="11ed3-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="11ed3-125">Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="11ed3-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="11ed3-126">Por ejemplo, para deshabilitar los códigos de paso de una sola vez:</span><span class="sxs-lookup"><span data-stu-id="11ed3-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="11ed3-127">Para habilitar los códigos de paso de una sola vez:</span><span class="sxs-lookup"><span data-stu-id="11ed3-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="11ed3-128">Administrar la presentación del botón cifrar en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="11ed3-128">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="11ed3-129">Como administrador, puede administrar si se muestra este botón a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="11ed3-129">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="11ed3-130">Para administrar si el botón cifrar aparece en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="11ed3-130">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="11ed3-131">Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11ed3-131">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="11ed3-132">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="11ed3-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="11ed3-133">Ejecute el cmdlet Set-IRMConfiguration con el parámetro-SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="11ed3-133">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="11ed3-134">Por ejemplo, para deshabilitar \*\*\*\* el botón cifrar:</span><span class="sxs-lookup"><span data-stu-id="11ed3-134">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="11ed3-135">Para habilitar el \*\*\*\* botón cifrar:</span><span class="sxs-lookup"><span data-stu-id="11ed3-135">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="11ed3-136">Habilitar el descifrado del servicio de mensajes de correo electrónico para los usuarios de la aplicación de correo de iOS</span><span class="sxs-lookup"><span data-stu-id="11ed3-136">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="11ed3-137">La aplicación de correo de iOS no puede descifrar mensajes protegidos con el cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="11ed3-137">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="11ed3-138">Como administrador de Office 365, puede aplicar el descifrado del servicio para los mensajes que se entregan a la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="11ed3-138">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="11ed3-139">Cuando elige usar el descifrado del lado del servicio, el servicio envía una copia descifrada del mensaje al dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="11ed3-139">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="11ed3-140">El dispositivo cliente almacena una copia descifrada del mensaje.</span><span class="sxs-lookup"><span data-stu-id="11ed3-140">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="11ed3-141">El mensaje también retiene información sobre los derechos de uso, aunque la aplicación de correo de iOS no aplica derechos de uso del lado cliente al usuario.</span><span class="sxs-lookup"><span data-stu-id="11ed3-141">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="11ed3-142">El usuario puede copiar o imprimir el mensaje incluso si originalmente no tenía los derechos necesarios.</span><span class="sxs-lookup"><span data-stu-id="11ed3-142">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="11ed3-143">Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Office 365, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tuvo originalmente el permiso de uso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="11ed3-143">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="11ed3-144">Sin embargo, los usuarios finales pueden evitar la restricción de uso "no reenviar" reenviando el mensaje desde una cuenta diferente dentro de la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="11ed3-144">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="11ed3-145">Independientemente de si configura el descifrado del lado del servicio del correo, los datos adjuntos a correo cifrado y protegido con derechos no se pueden ver en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="11ed3-145">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="11ed3-146">Si opta por no permitir que se envíen mensajes descifrados a los usuarios de la aplicación de correo de iOS, los usuarios recibirán un mensaje que indica que no tienen derechos para ver el mensaje.</span><span class="sxs-lookup"><span data-stu-id="11ed3-146">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="11ed3-147">De forma predeterminada, el descifrado del servicio de mensajes de correo electrónico no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="11ed3-147">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="11ed3-148">Para obtener más información y para obtener una vista de la experiencia del cliente, consulte [Ver mensajes cifrados en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="11ed3-148">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="11ed3-149">Para administrar si los usuarios de la aplicación de correo de iOS pueden ver los mensajes protegidos por el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="11ed3-149">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="11ed3-150">Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11ed3-150">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="11ed3-151">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="11ed3-151">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="11ed3-152">Ejecute el cmdlet Set-ActiveSyncOrganizations con el parámetro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="11ed3-152">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="11ed3-153">Por ejemplo, para configurar el servicio para descifrar mensajes antes de que se envíen a aplicaciones no habilitadas, como la aplicación de correo de iOS:</span><span class="sxs-lookup"><span data-stu-id="11ed3-153">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="11ed3-154">O bien, para configurar el servicio para que no envíe mensajes descifrados a aplicaciones no habilitadas:</span><span class="sxs-lookup"><span data-stu-id="11ed3-154">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```
> [!NOTE]

> <span data-ttu-id="11ed3-155">Las directivas de buzón de correo individuales (OWA/ActiveSync) invalidan esta configuración (es decir, si se establece-IRMEnabled en false dentro de la Directiva de buzón de OWA respectiva o la Directiva de buzones de ActiveSync, no se aplicarán estas configuraciones).</span><span class="sxs-lookup"><span data-stu-id="11ed3-155">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="11ed3-156">Habilitar el descifrado del servicio de datos adjuntos de correo electrónico para clientes de correo del explorador Web</span><span class="sxs-lookup"><span data-stu-id="11ed3-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="11ed3-157">Normalmente, cuando se usa el cifrado de mensajes de Office 365, los datos adjuntos se cifran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="11ed3-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="11ed3-158">Como administrador de Office 365, puede aplicar el descifrado del servicio para los datos adjuntos de correo electrónico que los usuarios descarguen desde un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="11ed3-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="11ed3-159">Cuando se usa el descifrado del servicio, el servicio envía una copia descifrada del archivo al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11ed3-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="11ed3-160">El mensaje sigue cifrado.</span><span class="sxs-lookup"><span data-stu-id="11ed3-160">The message is still encrypted.</span></span> <span data-ttu-id="11ed3-161">Los datos adjuntos de correo electrónico también conservan información sobre los derechos de uso, aunque el explorador no aplica al usuario los derechos de uso del lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="11ed3-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="11ed3-162">El usuario puede copiar o imprimir los datos adjuntos de correo electrónico incluso si no tienen los derechos necesarios.</span><span class="sxs-lookup"><span data-stu-id="11ed3-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="11ed3-163">Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Office 365, como reenviar los datos adjuntos, el servidor no permitirá la acción si el usuario no tuvo originalmente el permiso de uso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="11ed3-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="11ed3-164">Independientemente de si se configura el descifrado del lado del servicio de los datos adjuntos, los usuarios no pueden ver los datos adjuntos en mensajes cifrados y protegidos por derechos en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="11ed3-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="11ed3-165">Si opta por no permitir datos adjuntos de correo electrónico descifrados, que es la opción predeterminada, los usuarios reciben un mensaje que indica que no tienen derechos para ver los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="11ed3-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="11ed3-166">Para obtener más información acerca de cómo Office 365 implementa el cifrado de mensajes de correo electrónico y datos adjuntos con la opción de solo cifrado, vea la [opción de solo cifrado para los correos electrónicos.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="11ed3-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="11ed3-167">Para administrar si los datos adjuntos de correo electrónico se descifran al descargarlos desde un explorador Web</span><span class="sxs-lookup"><span data-stu-id="11ed3-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="11ed3-168">Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11ed3-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="11ed3-169">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="11ed3-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="11ed3-170">Ejecute el cmdlet Set-IRMConfiguration con el parámetro DecryptAttachmentFromPortal:</span><span class="sxs-lookup"><span data-stu-id="11ed3-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="11ed3-171">Por ejemplo, para configurar el servicio para descifrar los datos adjuntos de correo electrónico cuando un usuario los descarga desde un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="11ed3-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="11ed3-172">Para configurar el servicio para dejar datos adjuntos de correo electrónico cifrados tal como están al descargarlos:</span><span class="sxs-lookup"><span data-stu-id="11ed3-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a><span data-ttu-id="11ed3-173">Asegurarse de que todos los destinatarios externos usan el portal OME para leer el correo cifrado: solo el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="11ed3-173">Ensure all external recipients use the OME Portal to read encrypted mail — Office 365 Advanced Message Encryption only</span></span>

<span data-ttu-id="11ed3-174">Si tiene el cifrado de mensajes avanzado de Office 365, puede usar plantillas de personalización de marca personalizadas para obligar a los destinatarios a recibir un correo de contenedor que les dirija a leer el correo electrónico cifrado en el portal de OME en lugar de usar Outlook o Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="11ed3-174">If you have Office 365 Advanced Message Encryption, you can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="11ed3-175">Es posible que desee hacer esto si usa un mayor control sobre la forma en que los destinatarios usan el correo que reciben.</span><span class="sxs-lookup"><span data-stu-id="11ed3-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="11ed3-176">Por ejemplo, si los destinatarios externos ven el correo electrónico en el portal web, puede establecer una fecha de expiración para el correo electrónico, y puede revocar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="11ed3-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="11ed3-177">Estas características solo se admiten a través del portal OME.</span><span class="sxs-lookup"><span data-stu-id="11ed3-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="11ed3-178">Puede usar la opción cifrar y la opción no reenviar al crear reglas de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="11ed3-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a><span data-ttu-id="11ed3-179">Cree una plantilla personalizada para forzar que todos los destinatarios externos usen el portal OME y el correo electrónico cifrado sea revocable y expire en 7 días.</span><span class="sxs-lookup"><span data-stu-id="11ed3-179">Create a custom template to force all external recipients to use the OME Portal and for encrypted email to be revocable and expire in 7 days</span></span>

1. <span data-ttu-id="11ed3-180">Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11ed3-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="11ed3-181">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="11ed3-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="11ed3-182">Ejecute el cmdlet New-OMEConfiguration:</span><span class="sxs-lookup"><span data-stu-id="11ed3-182">Run the New-OMEConfiguration cmdlet:</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   <span data-ttu-id="11ed3-183">donde `template name` es el nombre que desea usar para la plantilla de personalización de marca personalizada de cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="11ed3-183">where `template name` is the name you want to use for the Office 365 Message Encryption custom branding template.</span></span> <span data-ttu-id="11ed3-184">For example,</span><span class="sxs-lookup"><span data-stu-id="11ed3-184">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. <span data-ttu-id="11ed3-185">Ejecute el cmdlet New-TransportRule:</span><span class="sxs-lookup"><span data-stu-id="11ed3-185">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="11ed3-186">donde:</span><span class="sxs-lookup"><span data-stu-id="11ed3-186">where:</span></span>

   - <span data-ttu-id="11ed3-187">`mail flow rule name`es el nombre que desea usar para la nueva regla de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="11ed3-187">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="11ed3-188">`option name`es `Encrypt` o `Do Not Forward`.</span><span class="sxs-lookup"><span data-stu-id="11ed3-188">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="11ed3-189">`template name`es el nombre que dio a la plantilla de personalización de marca `One week expiration`personalizada, por ejemplo,.</span><span class="sxs-lookup"><span data-stu-id="11ed3-189">`template name` is the name you gave the custom branding template, for example `One week expiration`.</span></span>

   <span data-ttu-id="11ed3-190">Para cifrar todo el correo electrónico externo con la plantilla "expiración de una semana" y aplicar la opción de solo cifrado:</span><span class="sxs-lookup"><span data-stu-id="11ed3-190">To encrypt all external email with the "One week expiration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   <span data-ttu-id="11ed3-191">Para cifrar todo el correo electrónico externo con la plantilla "expiración de una semana" y aplicar la opción no reenviar:</span><span class="sxs-lookup"><span data-stu-id="11ed3-191">To encrypt all external email with the "One week expiration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="11ed3-192">Personalizar la apariencia de los mensajes de correo electrónico y del portal de OME</span><span class="sxs-lookup"><span data-stu-id="11ed3-192">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="11ed3-193">Para obtener información detallada acerca de cómo puede personalizar OME para su organización, vea [Agregar la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="11ed3-193">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="11ed3-194">Deshabilitar las nuevas funciones para OME</span><span class="sxs-lookup"><span data-stu-id="11ed3-194">Disable the new capabilities for OME</span></span>

<span data-ttu-id="11ed3-195">Esperamos que no se encuentre, pero, si es necesario, deshabilitar las nuevas capacidades de OME es muy sencilla.</span><span class="sxs-lookup"><span data-stu-id="11ed3-195">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="11ed3-196">En primer lugar, debe quitar todas las reglas de flujo de correo que haya creado y que usen las nuevas funciones de OME.</span><span class="sxs-lookup"><span data-stu-id="11ed3-196">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="11ed3-197">Para obtener información sobre cómo eliminar reglas de flujo de correo, consulte [Manage mail Flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="11ed3-197">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="11ed3-198">A continuación, complete estos pasos en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ed3-198">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="11ed3-199">Para deshabilitar las nuevas funciones de OME</span><span class="sxs-lookup"><span data-stu-id="11ed3-199">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="11ed3-200">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11ed3-200">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="11ed3-201">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="11ed3-201">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="11ed3-202">Si ha habilitado \*\*\*\* el botón cifrar en Outlook en la web, deshabilítelo mediante la ejecución del cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="11ed3-202">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="11ed3-203">De lo contrario, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="11ed3-203">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="11ed3-204">Deshabilite las nuevas funciones para OME ejecutando el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:</span><span class="sxs-lookup"><span data-stu-id="11ed3-204">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
