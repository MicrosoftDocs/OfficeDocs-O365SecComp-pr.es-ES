---
title: Administrar el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: Una vez que haya terminado de configurar el cifrado de mensajes de Office 365 (OME), puede personalizar la configuración de la implementación de varias maneras. Por ejemplo, puede configurar si desea habilitar códigos de paso de una sola vez, mostrar el botón proteger en Outlook en la web y más. Las tareas de este artículo describen cómo hacerlo.
ms.openlocfilehash: 8b044898efb1ef86790773cd3f8e8061523b0ec0
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213760"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="36a6e-105">Administrar el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="36a6e-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="36a6e-p102">Una vez que haya terminado de configurar el cifrado de mensajes de Office 365 (OME), puede personalizar la configuración de la implementación de varias maneras. Por ejemplo, puede configurar si desea habilitar códigos de paso de una sola vez, mostrar el botón **proteger** en Outlook en la web y más. Las tareas de este artículo describen cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="36a6e-p103">Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="36a6e-112">Administrar si los destinatarios de cuentas de Google, Yahoo y Microsoft pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="36a6e-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="36a6e-p104">De forma predeterminada, al configurar las nuevas capacidades de cifrado de mensajes de Office 365, los usuarios de la organización pueden enviar mensajes a destinatarios que están fuera de la organización de Office 365. Si el destinatario usa un *identificador social* , como una cuenta de Google, una cuenta de Yahoo o una cuenta de Microsoft, el destinatario puede iniciar sesión en el portal de OME mediante el ID social. Si lo desea, puede optar por no permitir que los destinatarios usen identificadores sociales para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="36a6e-116">Para administrar si desea permitir que los destinatarios usen identificadores sociales para iniciar sesión en el portal de OME</span><span class="sxs-lookup"><span data-stu-id="36a6e-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="36a6e-117">[Conéctese a Exchange online mediante PowerShell remoto](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="36a6e-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="36a6e-118">Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="36a6e-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="36a6e-119">Por ejemplo, para deshabilitar los identificadores sociales:</span><span class="sxs-lookup"><span data-stu-id="36a6e-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="36a6e-120">Para habilitar los identificadores sociales:</span><span class="sxs-lookup"><span data-stu-id="36a6e-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="36a6e-121">Administración del uso de códigos de paso de una sola vez para iniciar sesión en el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="36a6e-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="36a6e-p105">De forma predeterminada, si el destinatario de un mensaje cifrado por OME no usa Outlook, independientemente de la cuenta usada por el destinatario, el destinatario recibe un vínculo de vista Web limitado que les permite leer el mensaje. Esto incluye un código de paso único. Como administrador, puede administrar si se pueden usar códigos de paso de un solo uso para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="36a6e-125">Para administrar si se generan o no códigos de paso de un solo tiempo para OME</span><span class="sxs-lookup"><span data-stu-id="36a6e-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="36a6e-p106">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="36a6e-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="36a6e-128">Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="36a6e-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="36a6e-129">Por ejemplo, para deshabilitar los códigos de paso de una sola vez:</span><span class="sxs-lookup"><span data-stu-id="36a6e-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="36a6e-130">Para habilitar los códigos de paso de una sola vez:</span><span class="sxs-lookup"><span data-stu-id="36a6e-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="36a6e-131">Administrar la presentación del botón proteger en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="36a6e-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="36a6e-p107">De forma predeterminada, el botón **proteger** de Outlook en la web no está habilitado al configurar OME. Como administrador, puede administrar si desea que se muestre este botón a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p107">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="36a6e-134">Para administrar si el botón proteger aparece o no en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="36a6e-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="36a6e-p108">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="36a6e-p108">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="36a6e-137">Ejecute el cmdlet Set-IRMConfiguration con el parámetro-SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="36a6e-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="36a6e-138">Por ejemplo, para deshabilitar el botón **proteger** :</span><span class="sxs-lookup"><span data-stu-id="36a6e-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="36a6e-139">Para habilitar el botón **proteger** :</span><span class="sxs-lookup"><span data-stu-id="36a6e-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="36a6e-140">Habilitar el descifrado del servicio de mensajes de correo electrónico para los usuarios de la aplicación de correo de iOS</span><span class="sxs-lookup"><span data-stu-id="36a6e-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="36a6e-p109">La aplicación de correo de iOS no puede descifrar mensajes protegidos con el cifrado de mensajes de Office 365. Como administrador de Office 365, puede aplicar el descifrado del servicio para los mensajes que se entregan a la aplicación de correo de iOS. Cuando elige hacerlo, el servicio envía una copia descifrada del mensaje al dispositivo iOS. El mensaje se almacena descifrado en el dispositivo cliente. El mensaje también retiene información sobre los derechos de uso, aunque la aplicación de correo de iOS no aplica derechos de uso del lado cliente al usuario. Esto significa que el usuario puede copiar o imprimir el mensaje incluso si no tenía originalmente los derechos necesarios. Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Office 365, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tuvo originalmente el permiso de uso. Sin embargo, los usuarios finales pueden solucionar la restricción de uso no reEnviar el mensaje a partir de una cuenta distinta en su aplicación de correo de iOS. independientemente de si se configura el descifrado del servicio de correo, los datos adjuntos al correo cifrado y con derechos protegidos no se puede ver en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p109">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="36a6e-p110">Si opta por no permitir que se envíen mensajes descifrados a los usuarios de la aplicación de correo de iOS, los usuarios recibirán un mensaje que indica que no tienen derechos para ver el mensaje. De forma predeterminada, el descifrado del servicio de mensajes de correo electrónico no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p110">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="36a6e-152">Para obtener más información y para obtener una vista de la experiencia del cliente, consulte [Ver mensajes cifrados en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="36a6e-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="36a6e-153">Para administrar si los usuarios de la aplicación de correo de iOS pueden ver los mensajes protegidos por el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="36a6e-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="36a6e-p111">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="36a6e-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="36a6e-156">Ejecute el cmdlet Set-ActiveSyncOrganizations con el parámetro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="36a6e-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="36a6e-157">Por ejemplo, para configurar el servicio para descifrar mensajes antes de que se envíen a aplicaciones no habilitadas, como la aplicación de correo de iOS:</span><span class="sxs-lookup"><span data-stu-id="36a6e-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="36a6e-158">O bien, para configurar el servicio para que no envíe mensajes descifrados a aplicaciones no habilitadas:</span><span class="sxs-lookup"><span data-stu-id="36a6e-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="36a6e-159">Habilitar el descifrado del servicio de datos adjuntos de correo electrónico para clientes de correo del explorador Web</span><span class="sxs-lookup"><span data-stu-id="36a6e-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="36a6e-p112">Normalmente, cuando se usa el cifrado de mensajes de Office 365, los datos adjuntos se cifran automáticamente. Como administrador de Office 365, puede aplicar el descifrado del servicio para los datos adjuntos de correo electrónico que los usuarios descarguen desde un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p112">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="36a6e-p113">Cuando elige hacerlo, el servicio envía una copia descifrada del archivo al dispositivo. El mensaje sigue cifrado. Los datos adjuntos de correo electrónico también retienen información sobre los derechos de uso, aunque el explorador no aplica al usuario los derechos de uso del lado cliente. Esto significa que el usuario puede copiar o imprimir los datos adjuntos de correo electrónico, incluso si no tienen los derechos para hacerlo originalmente. Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Office 365, como reenviar los datos adjuntos, el servidor no permitirá la acción si el usuario no tuvo originalmente el permiso de uso.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p113">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="36a6e-167">Independientemente de si configura el descifrado del lado del servicio de datos adjuntos, los datos adjuntos a correo cifrado y protegido con derechos no se pueden ver en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="36a6e-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="36a6e-168">Si opta por no permitir datos adjuntos de correo electrónico descifrados, que es la opción predeterminada, los usuarios reciben un mensaje que indica que no tienen derechos para ver los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="36a6e-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="36a6e-169">Para obtener más información acerca de cómo Office 365 implementa el cifrado de mensajes de correo electrónico y datos adjuntos con la opción de solo cifrado, vea la [opción de solo cifrado para los correos electrónicos.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="36a6e-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="36a6e-170">Para administrar si los datos adjuntos de correo electrónico se descifran en un explorador Web o no en descargarlos</span><span class="sxs-lookup"><span data-stu-id="36a6e-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="36a6e-p114">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="36a6e-p114">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="36a6e-173">Ejecute el cmdlet Set-IRMConfiguration con el parámetro DecryptAttachmentFromPortal:</span><span class="sxs-lookup"><span data-stu-id="36a6e-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="36a6e-174">Por ejemplo, para configurar el servicio para descifrar los datos adjuntos de correo electrónico cuando un usuario los descarga desde un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="36a6e-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="36a6e-175">Para configurar el servicio para dejar datos adjuntos de correo electrónico cifrados tal como están al descargarlos:</span><span class="sxs-lookup"><span data-stu-id="36a6e-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="36a6e-176">Personalización de la apariencia de los mensajes de correo electrónico y del portal de OME</span><span class="sxs-lookup"><span data-stu-id="36a6e-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="36a6e-177">Para obtener información detallada acerca de cómo puede personalizar OME para su organización, vea [Agregar la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="36a6e-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="36a6e-178">DesHabilitar las nuevas funciones para OME</span><span class="sxs-lookup"><span data-stu-id="36a6e-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="36a6e-p115">Esperamos que no se encuentre, pero, si es necesario, deshabilitar las nuevas capacidades de OME es muy sencilla. En primer lugar, debe quitar todas las reglas de flujo de correo que haya creado y que usen las nuevas funciones de OME. Para obtener información sobre cómo eliminar reglas de flujo de correo, consulte [Manage mail Flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). A continuación, complete estos pasos en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p115">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="36a6e-183">Para deshabilitar las nuevas funciones de OME</span><span class="sxs-lookup"><span data-stu-id="36a6e-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="36a6e-p116">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="36a6e-p116">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="36a6e-p117">Si ha habilitado el botón **proteger** en Outlook en la web, deshabilítelo mediante la ejecución del cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled. De lo contrario, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="36a6e-p117">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter. Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="36a6e-188">DesHabilite las nuevas funciones para OME ejecutando el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:</span><span class="sxs-lookup"><span data-stu-id="36a6e-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
