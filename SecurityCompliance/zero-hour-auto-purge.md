---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: La depuración automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con correo no deseado o malware que ya se han entregado a los buzones de los usuarios y, a continuación, inofensivos en el contenido malintencionado. Cómo hace ZAP esto depende del tipo de contenido malintencionado detectado.
ms.openlocfilehash: 91bb167c988e49a40895f851a518ee255abdbf08
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "36698972"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="ae4c8-104">Purga automática cero horas: protección contra correo no deseado y malware</span><span class="sxs-lookup"><span data-stu-id="ae4c8-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="ae4c8-105">Información general</span><span class="sxs-lookup"><span data-stu-id="ae4c8-105">Overview</span></span>

<span data-ttu-id="ae4c8-106">La purga automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con phish, correo no deseado o malware que ya se han entregado a los buzones de los usuarios y, a continuación, inofensivos en el contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="ae4c8-107">Cómo hace ZAP esto depende del tipo de contenido malintencionado detectado; el correo se puede zapped debido al contenido de correo, las direcciones URL o los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="ae4c8-108">ZAP está disponible con la protección de Exchange Online predeterminada que se incluye con cualquier suscripción a Office 365 que contenga buzones de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="ae4c8-109">ZAP está activado de forma predeterminada, pero deben cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="ae4c8-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="ae4c8-110">La **acción de correo no deseado** está configurada para **mover el mensaje a la carpeta correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="ae4c8-111">También puede crear una nueva Directiva de filtro de correo no deseado que se aplique sólo a un grupo de usuarios si no desea que ZAP pueda filtrar todos los buzones.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="ae4c8-112">Los usuarios han mantenido su configuración predeterminada de correo no deseado y no han desactivado la protección contra correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="ae4c8-113">(Consulte [cambiar el nivel de protección en el filtro de correo no deseado](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) para obtener más información acerca de las opciones de usuario en Outlook).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="ae4c8-114">Cómo funciona el ZAP</span><span class="sxs-lookup"><span data-stu-id="ae4c8-114">How ZAP works</span></span>

<span data-ttu-id="ae4c8-115">Office 365 actualiza las firmas de malware y del motor de correo no deseado en tiempo real de manera diaria.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="ae4c8-116">Sin embargo, es posible que los usuarios sigan teniendo mensajes malintencionados entregados a sus bandejas de correo por diversos motivos, incluso si el contenido se ha armado después de que se entregue a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="ae4c8-117">ZAP soluciona el control continuado de las actualizaciones de las firmas de correo no deseado y malware de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="ae4c8-118">ZAP puede buscar y quitar los mensajes previamente entregados que ya se encuentran en las bandejas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="ae4c8-119">La acción ZAP es fluida para el usuario del buzón de correo; no se notifica si se mueve un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="ae4c8-120">El mensaje no debe tener más de 2 días.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="ae4c8-121">Las listas de permitidos, [las reglas de flujo de correo](https://go.microsoft.com/fwlink/p/?LinkId=722755) (también conocidas como reglas de transporte) y las reglas de usuario final o los filtros adicionales tienen prioridad sobre Zap.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="ae4c8-122">ZAP de malware</span><span class="sxs-lookup"><span data-stu-id="ae4c8-122">Malware ZAP</span></span>

<span data-ttu-id="ae4c8-123">Para el malware recién detectado, ZAP quita los datos adjuntos de los mensajes de correo electrónico y deja el cuerpo del mensaje en el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="ae4c8-124">Los datos adjuntos se quitan independientemente del estado de lectura del correo.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="ae4c8-125">ZAP de malware está habilitado de forma predeterminada en la Directiva de malware.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="ae4c8-126">Puede deshabilitar el servicio ZAP de malware mediante el parámetro *ZapEnabled* en el cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) de PowerShell de Exchange online o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="ae4c8-127">ZAP de phish</span><span class="sxs-lookup"><span data-stu-id="ae4c8-127">Phish ZAP</span></span>

<span data-ttu-id="ae4c8-128">Para el correo que se identifica como phish después de la entrega, ZAP realiza la acción según la Directiva de correo no deseado que el usuario está cubierta.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="ae4c8-129">Si la acción de phish a Directiva está configurada para realizar una acción en un correo (redirigir, eliminar, poner en cuarentena, mover a correo no deseado), ZAP moverá el mensaje a la carpeta correo no deseado de la bandeja de entrada del usuario, independientemente del estado de lectura del correo.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="ae4c8-130">Si la acción de phish a Directiva no está configurada para emprender acciones (agregar encabezado X, modificar asunto, sin acción), ZAP no realizará ninguna acción en el correo.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="ae4c8-131">Obtenga más información sobre cómo [configurar las directivas de filtro de correo no deseado](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) aquí.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="ae4c8-132">La ZAP de phish está habilitada de forma predeterminada en la Directiva de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="ae4c8-133">Puede deshabilitar el servicio ZAP de phish mediante el parámetro *ZapEnabled* en el cmdlet [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) de PowerShell de Exchange online o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-133">You can disable Phish ZAP by using the *ZapEnabled* parameter on the [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="ae4c8-134">ZAP de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="ae4c8-134">Spam ZAP</span></span>

<span data-ttu-id="ae4c8-135">Para el correo identificado como correo no deseado después de la entrega, ZAP realiza la acción según la Directiva de correo no deseado que el usuario está cubierta.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-135">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="ae4c8-136">Si la acción de correo no deseado de la Directiva está configurada para realizar una acción en un correo (redirigir, eliminar, poner en cuarentena, mover a correo no deseado), ZAP moverá el mensaje a la carpeta correo no deseado de la bandeja de entrada del usuario, si el mensaje no está leído.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-136">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="ae4c8-137">Si la acción de la Directiva de correo no deseado no está configurada para emprender acciones (agregar encabezado X, modificar asunto, sin acción), ZAP no realizará ninguna acción en el correo.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-137">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="ae4c8-138">Obtenga más información sobre cómo [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) aquí.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-138">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="ae4c8-139">La ZAP de correo no deseado está habilitada de forma predeterminada en la Directiva de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-139">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="ae4c8-140">Puede deshabilitar el ZAP de correo no deseado mediante el parámetro *ZapEnabled* del cmdlet [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) en PowerShell de Exchange online o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-140">You can disable Spam ZAP by using the *ZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="ae4c8-141">El parámetro *ZapEnabled* del cmdlet **set-HostedContentFilterPolicy** deshabilita o habilita tanto el Zap de phish como el correo no deseado para la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-141">The *ZapEnabled* parameter on the **Set-HostedContentFilterPolicy** cmdlet disables or enables both Phish ZAP and Spam ZAP for the policy.</span></span> <span data-ttu-id="ae4c8-142">No puede habilitar o deshabilitar de forma independiente el ZAP de robo y correo no deseado en la misma directiva.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-142">You can't independently enable or disable Phish ZAP and Spam ZAP within the same policy.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="ae4c8-143">Cómo ver si el ZAP movió el mensaje</span><span class="sxs-lookup"><span data-stu-id="ae4c8-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="ae4c8-144">Para determinar si la ZAP movió el mensaje, puede usar el informe de estado de la [protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) o el [Explorador de amenazas (y detecciones en tiempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="ae4c8-145">Deshabilitar ZAP</span><span class="sxs-lookup"><span data-stu-id="ae4c8-145">Disable ZAP</span></span>

<span data-ttu-id="ae4c8-146">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-146">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="ae4c8-147">Para conectarse a PowerShell de Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-147">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="ae4c8-148">Deshabilitar el ZAP de malware \* \*</span><span class="sxs-lookup"><span data-stu-id="ae4c8-148">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="ae4c8-149">En este ejemplo se deshabilita ZAP en la Directiva de filtro de malware denominada "Test".</span><span class="sxs-lookup"><span data-stu-id="ae4c8-149">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="ae4c8-150">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-150">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="ae4c8-151">Deshabilitar el Zap de robo de phish y correo no deseado</span><span class="sxs-lookup"><span data-stu-id="ae4c8-151">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="ae4c8-152">En este ejemplo se deshabilita el robo de correo no deseado y ZAP de phish en la Directiva de filtro de contenido denominada "Test".</span><span class="sxs-lookup"><span data-stu-id="ae4c8-152">This example disables Phish ZAP and Spam ZAP in the content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="ae4c8-153">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-153">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="ae4c8-154">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="ae4c8-154">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="ae4c8-155">¿Qué sucede si un mensaje legítimo se mueve a la carpeta correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="ae4c8-155">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="ae4c8-156">Debe seguir el proceso normal de informes para [falsos positivos](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-156">You should follow the normal reporting process for [false-positives](prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="ae4c8-157">La única razón por la que el mensaje se movería de la bandeja de entrada a la carpeta correo no deseado sería porque el servicio determinó que el mensaje era correo no deseado o malintencionado.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-157">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="ae4c8-158">¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="ae4c8-158">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="ae4c8-159">ZAP no mueve los mensajes a cuarentena de la bandeja de entrada en este momento.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-159">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="ae4c8-160">¿Qué ocurre si tengo una regla de flujo de correo personalizada (regla de bloqueo/permiso)?</span><span class="sxs-lookup"><span data-stu-id="ae4c8-160">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="ae4c8-161">Las reglas creadas por los administradores (reglas de flujo de correo) o las reglas de bloqueo y permiso tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-161">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="ae4c8-162">Estos mensajes se excluyen de los criterios de la característica, por lo que el flujo de correo seguirá la acción de regla (bloquear/permitir regla).</span><span class="sxs-lookup"><span data-stu-id="ae4c8-162">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="ae4c8-163">¿Qué ocurre si un mensaje se mueve a otra carpeta (por ejemplo, una regla de bandeja de entrada)?</span><span class="sxs-lookup"><span data-stu-id="ae4c8-163">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="ae4c8-164">ZAP sigue funcionando en este caso, a menos que el mensaje se haya eliminado o esté en correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="ae4c8-164">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae4c8-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ae4c8-165">Related Topics</span></span>

[<span data-ttu-id="ae4c8-166">Protección contra correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="ae4c8-166">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="ae4c8-167">Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos</span><span class="sxs-lookup"><span data-stu-id="ae4c8-167">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
