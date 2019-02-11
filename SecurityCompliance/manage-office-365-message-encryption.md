---
title: Administrar el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: Una vez que haya terminado la configuración de seguridad de Office 365 Message Encryption (OME), puede personalizar la configuración de la implementación en un número de formas. Por ejemplo, puede configurar si se debe habilitar códigos de acceso única, mostrar el botón Proteger en Outlook en el web y mucho más. Las tareas en este artículo se describen cómo.
ms.openlocfilehash: 6a9eddae2d3d166d96979d88b15845c3b7379bd9
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696234"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="40b3b-105">Administrar el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="40b3b-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="40b3b-p102">Una vez que haya terminado la configuración de seguridad de Office 365 Message Encryption (OME), puede personalizar la configuración de la implementación en un número de formas. Por ejemplo, puede configurar si se debe habilitar códigos de acceso única, mostrar el botón **proteger** en Outlook en el web y mucho más. Las tareas en este artículo se describen cómo.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="40b3b-p103">En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. En este artículo está destinada a los administradores y profesionales de TI. Si sólo está buscando información en enviar o recibir un mensaje cifrado, vea la lista de los artículos de [Office 365 Message Encryption (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="40b3b-112">Administración de si los destinatarios de Google, Yahoo y Account de Microsoft pueden utilizar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="40b3b-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="40b3b-p104">De forma predeterminada, al configurar las nuevas capacidades de cifrado de mensajes de Office 365, los usuarios de su organización pueden enviar mensajes a los destinatarios que están fuera de su organización de Office 365. Si el destinatario usa un *identificador sociales* como una cuenta de Google, Yahoo cuenta o cuenta de Microsoft, el destinatario puede iniciar sesión en el portal de OME con el identificador sociales. Si lo desea, puede elegir no permitir a los destinatarios usar los identificadores de sociales para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="40b3b-116">Para administrar si o no permitir a los destinatarios usar los identificadores de sociales para iniciar sesión en el portal de OME</span><span class="sxs-lookup"><span data-stu-id="40b3b-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="40b3b-117">[Conectarse a Exchange Online mediante PowerShell remoto](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="40b3b-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="40b3b-118">Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn como sigue:</span><span class="sxs-lookup"><span data-stu-id="40b3b-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="40b3b-119">Por ejemplo, para deshabilitar los identificadores sociales:</span><span class="sxs-lookup"><span data-stu-id="40b3b-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="40b3b-120">Para habilitar los identificadores sociales:</span><span class="sxs-lookup"><span data-stu-id="40b3b-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="40b3b-121">Administrar el uso de códigos de acceso única para iniciar sesión en el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="40b3b-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="40b3b-p105">De forma predeterminada, si el destinatario de un mensaje cifrado por OME no utiliza Outlook, independientemente de la cuenta utilizada por el destinatario, el destinatario recibe un vínculo de la vista web de tiempo limitado que les permite leer el mensaje. Esto incluye un código de acceso única. Como administrador, puede administrar independientemente de si o no códigos de acceso única pueden usarse para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="40b3b-125">Para administrar o si no se generan códigos de acceso única para OME</span><span class="sxs-lookup"><span data-stu-id="40b3b-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="40b3b-p106">Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="40b3b-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="40b3b-128">Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="40b3b-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="40b3b-129">Por ejemplo, para deshabilitar los códigos de acceso única:</span><span class="sxs-lookup"><span data-stu-id="40b3b-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="40b3b-130">Para habilitar códigos de acceso única:</span><span class="sxs-lookup"><span data-stu-id="40b3b-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="40b3b-131">Administración de la visualización del botón Protect en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="40b3b-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="40b3b-p107">De forma predeterminada, no está habilitado el botón **proteger** en Outlook en el web al configurar OME. Como administrador, puede administrar si se deben mostrar en este botón para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p107">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="40b3b-134">Para administrar si aparece o no el botón Proteger en Outlook en el web</span><span class="sxs-lookup"><span data-stu-id="40b3b-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="40b3b-p108">Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="40b3b-p108">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="40b3b-137">Ejecute el cmdlet Set-IRMConfiguration con el parámetro - SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="40b3b-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="40b3b-138">Por ejemplo, para deshabilitar el botón **proteger** :</span><span class="sxs-lookup"><span data-stu-id="40b3b-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="40b3b-139">Para habilitar el botón **proteger** :</span><span class="sxs-lookup"><span data-stu-id="40b3b-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="40b3b-140">Habilitar el descifrado del servicio de mensajes de correo electrónico para los usuarios de aplicación de correo de iOS</span><span class="sxs-lookup"><span data-stu-id="40b3b-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="40b3b-p109">La aplicación de correo de iOS no puede descifrar mensajes protegidos con cifrado de mensajes de Office 365. Como administrador de Office 365, puede aplicar el descifrado del servicio para los mensajes entregados a la aplicación de correo de iOS. Cuando se decide hacer esto, el servicio envía una copia del mensaje descifrada al dispositivo iOS. El mensaje se almacena descifrar en el dispositivo de cliente. El mensaje también conserva información acerca de los derechos de uso, aunque la aplicación de correo de iOS no aplica los derechos de uso de lado cliente para el usuario. Esto significa que el usuario puede copiar o imprimir el mensaje incluso si originalmente no tiene los derechos necesarios para hacerlo. Sin embargo, si el usuario intenta para llevar a cabo una acción que requiere el servidor de correo de Office 365, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo. Sin embargo, los usuarios finales pueden evitar restricción de uso no reenviar por reenviar el mensaje desde una cuenta diferente en su aplicación de correo de iOS independientemente de si configurado la descifrado del servicio de correo, los datos adjuntos para cifrar y derechos de correo protegido no pueden verse en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p109">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="40b3b-p110">Si decide no permitir que los mensajes descifrados se envíen a usuarios de la aplicación de correo de iOS, los usuarios reciben un mensaje que indica que no tienen derechos para ver el mensaje. De forma predeterminada, no está habilitado el descifrado del servicio de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p110">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="40b3b-152">Para obtener más información y para una vista de la experiencia del cliente, vea [vista cifra los mensajes en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="40b3b-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="40b3b-153">Para administrar usuarios de la aplicación de correo de iOS o no puede ver los mensajes protegidos por el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="40b3b-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="40b3b-p111">Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="40b3b-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="40b3b-156">Ejecute el cmdlet Set-ActiveSyncOrganizations con el parámetro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="40b3b-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="40b3b-157">Por ejemplo, para configurar el servicio para descifrar los mensajes antes de que se envíen a las aplicaciones unenlightened como iOS aplicación de correo:</span><span class="sxs-lookup"><span data-stu-id="40b3b-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="40b3b-158">O bien, para configurar el servicio para que no envíe mensajes descifrados a las aplicaciones unenlightened:</span><span class="sxs-lookup"><span data-stu-id="40b3b-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="40b3b-159">Habilitar descifrado del servicio de datos adjuntos de correo electrónico para los clientes de correo de explorador web</span><span class="sxs-lookup"><span data-stu-id="40b3b-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="40b3b-p112">Normalmente, cuando se usa el cifrado de mensajes de Office 365, automáticamente se cifran los datos adjuntos. Como administrador de Office 365, puede aplicar el descifrado del servicio para los datos adjuntos de correo electrónico que los usuarios descargar desde un explorador web.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p112">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="40b3b-p113">Si opta por hacer esto, el servicio envía una copia descifrada del archivo en el dispositivo. El mensaje aún está cifrado. Los datos adjuntos de correo electrónico también conserva información acerca de los derechos de uso, aunque el explorador no se aplican los derechos de uso de lado cliente para el usuario. Esto significa que el usuario puede copiar o imprimir los datos adjuntos de correo electrónico incluso si originalmente no tiene los derechos necesarios para hacerlo. Sin embargo, si el usuario intenta para llevar a cabo una acción que requiere que el servidor de correo de Office 365, como la transferencia de los datos adjuntos, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p113">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="40b3b-167">Independientemente de si configurado descifrado del servicio de datos adjuntos, los datos adjuntos al cifran y correo protegido con derechos no pueden verse en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="40b3b-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="40b3b-168">Si decide no permitir datos adjuntos de correo electrónico descifrado, que es el valor predeterminado, los usuarios reciben un mensaje que indica que no tienen derechos para ver los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="40b3b-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="40b3b-169">Para obtener más información acerca de cómo Office 365 implementa el cifrado de mensajes de correo electrónico y datos adjuntos de correo electrónico con la opción sólo cifrar, vea [opción sólo cifrar para los correos electrónicos.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="40b3b-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="40b3b-170">Para administrar o no los datos adjuntos de correo electrónico se descifran al descargarlos desde un explorador web</span><span class="sxs-lookup"><span data-stu-id="40b3b-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="40b3b-p114">Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="40b3b-p114">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="40b3b-173">Ejecute el cmdlet Set-IRMConfiguration con el parámetro DecryptAttachmentFromPortal:</span><span class="sxs-lookup"><span data-stu-id="40b3b-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="40b3b-174">Por ejemplo configurar el servicio para descifrar los datos adjuntos de correo electrónico cuando un usuario para descargarlas desde un explorador web:</span><span class="sxs-lookup"><span data-stu-id="40b3b-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="40b3b-175">Para configurar el servicio para dejar los datos adjuntos de correo electrónico cifrado, tal y como están al descargar:</span><span class="sxs-lookup"><span data-stu-id="40b3b-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="40b3b-176">Personalizar la apariencia de los mensajes de correo electrónico y el portal de OME</span><span class="sxs-lookup"><span data-stu-id="40b3b-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="40b3b-177">Para obtener información detallada acerca de cómo se puede personalizar OME para su organización, vea [Agregar marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="40b3b-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="40b3b-178">Deshabilitación de las nuevas capacidades para OME</span><span class="sxs-lookup"><span data-stu-id="40b3b-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="40b3b-p115">Esperamos que no se incluyen a ella, pero si es necesario, deshabilitar las nuevas capacidades para OME es muy sencillo. En primer lugar, necesitará quitar las reglas de flujo de correo se ha creado que utilice las nuevas capacidades OME. Para obtener información sobre cómo quitar las reglas de flujo de correo, vea [Administrar reglas de flujo de correo](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). A continuación, siga estos pasos en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p115">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="40b3b-183">Para deshabilitar las nuevas capacidades para OME</span><span class="sxs-lookup"><span data-stu-id="40b3b-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="40b3b-p116">Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="40b3b-p116">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="40b3b-p117">Si se habilita el botón **proteger** de Outlook en la web, deshabilitar, ejecute el cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled. De lo contrario, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="40b3b-p117">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter. Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="40b3b-188">Deshabilitar las nuevas capacidades para OME, ejecute el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:</span><span class="sxs-lookup"><span data-stu-id="40b3b-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
