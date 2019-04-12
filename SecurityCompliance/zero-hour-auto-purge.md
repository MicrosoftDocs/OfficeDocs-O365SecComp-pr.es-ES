---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/11/2019
ms.audience: Admin
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
ms.openlocfilehash: 507cd6af5320a3b925841786136d518c996e4d29
ms.sourcegitcommit: 86ff2eba1d57b9d5288840788529e69ad9d836b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31818607"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="8c6a9-104">Purga automática cero horas: protección contra correo no deseado y malware</span><span class="sxs-lookup"><span data-stu-id="8c6a9-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="8c6a9-105">Información general</span><span class="sxs-lookup"><span data-stu-id="8c6a9-105">Overview</span></span>

<span data-ttu-id="8c6a9-106">La purga automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con phish, correo no deseado o malware que ya se han entregado a los buzones de los usuarios y, a continuación, inofensivos en el contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="8c6a9-107">Cómo hace ZAP esto depende del tipo de contenido malintencionado detectado; el correo se puede zapped debido al contenido de correo, las direcciones URL o los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="8c6a9-108">ZAP está disponible con la protección de Exchange Online predeterminada que se incluye con cualquier suscripción a Office 365 que contenga buzones de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="8c6a9-109">ZAP está activado de forma predeterminada, pero deben cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="8c6a9-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="8c6a9-110">La **acción de correo no deseado** está configurada para **mover el mensaje a la carpeta correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="8c6a9-111">También puede crear una nueva Directiva de filtro de correo no deseado que se aplique sólo a un grupo de usuarios si no desea que ZAP pueda filtrar todos los buzones.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="8c6a9-112">Los usuarios han mantenido su configuración predeterminada de correo no deseado y no han desactivado la protección contra correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="8c6a9-113">(Consulte [cambiar el nivel de protección en el filtro de correo no deseado](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) para obtener más información acerca de las opciones de usuario en Outlook).</span><span class="sxs-lookup"><span data-stu-id="8c6a9-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-zap-works"></a><span data-ttu-id="8c6a9-114">Cómo funciona el ZAP</span><span class="sxs-lookup"><span data-stu-id="8c6a9-114">How ZAP works</span></span>

<span data-ttu-id="8c6a9-115">Office 365 actualiza las firmas de malware y del motor de correo no deseado en tiempo real de manera diaria.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="8c6a9-116">Sin embargo, es posible que los usuarios sigan teniendo mensajes malintencionados entregados a sus bandejas de correo por diversos motivos, incluso si el contenido se ha armado después de que se entregue a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="8c6a9-117">ZAP soluciona el control continuado de las actualizaciones de las firmas de correo no deseado y malware de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="8c6a9-118">ZAP puede buscar y quitar los mensajes previamente entregados que ya se encuentran en las bandejas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

- <span data-ttu-id="8c6a9-119">En el caso del correo identificado como correo no deseado, ZAP mueve los mensajes no leídos a la carpeta de correo no deseado de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span>

- <span data-ttu-id="8c6a9-120">En el caso del correo identificado como phish, ZAP mueve los mensajes a la carpeta de correo no deseado de los usuarios, independientemente de si el correo electrónico se ha leído.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-120">For mail that is identified as phish, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="8c6a9-121">Para el malware recién detectado, ZAP quita los datos adjuntos de los mensajes de correo electrónico, independientemente de si el correo electrónico se ha leído.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span>
  
<span data-ttu-id="8c6a9-122">La acción ZAP es fluida para el usuario del buzón de correo; no se notifica si se mueve un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="8c6a9-123">El mensaje no debe tener más de 2 días.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-123">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="8c6a9-124">Las listas de permitidos, [las reglas de flujo de correo](https://go.microsoft.com/fwlink/p/?LinkId=722755)y las reglas de usuario final o los filtros adicionales tienen prioridad sobre Zap.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-124">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="8c6a9-125">Para revisar o configurar una directiva de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="8c6a9-125">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="8c6a9-126">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-126">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="8c6a9-127">En **Administración de amenazas**, elija **anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-127">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="8c6a9-128">Revise la configuración estándar.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-128">Review the standard settings.</span></span>

4. <span data-ttu-id="8c6a9-129">Si desea personalizar la configuración, seleccione la pestaña **personalizado** y active la **Configuración personalizada**.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-129">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**.</span></span> <span data-ttu-id="8c6a9-130">Modifique la configuración y, si quiere, elija **+ crear una directiva** para agregar una nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-130">Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span>

## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="8c6a9-131">Para ver si ZAP movió el mensaje</span><span class="sxs-lookup"><span data-stu-id="8c6a9-131">To see if ZAP moved your message</span></span>

<span data-ttu-id="8c6a9-132">Si desea ver si el mensaje se movió a un ZAP, puede usar el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) (o el [Explorador de amenazas](use-explorer-in-security-and-compliance.md)).</span><span class="sxs-lookup"><span data-stu-id="8c6a9-132">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>

## <a name="to-disable-zap"></a><span data-ttu-id="8c6a9-133">Para deshabilitar ZAP</span><span class="sxs-lookup"><span data-stu-id="8c6a9-133">To disable ZAP</span></span>
  
<span data-ttu-id="8c6a9-134">Si desea deshabilitar ZAP para el inquilino de Office 365 o un conjunto de usuarios, use el parámetro **ZapEnabled** de [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet de EOP.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-134">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

<span data-ttu-id="8c6a9-135">En el siguiente ejemplo, se deshabilita ZAP para una directiva de filtro de contenido denominada "Test".</span><span class="sxs-lookup"><span data-stu-id="8c6a9-135">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>

```Powershell
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="8c6a9-136">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="8c6a9-136">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="8c6a9-137">¿Qué sucede si un mensaje legítimo se mueve a la carpeta correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="8c6a9-137">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="8c6a9-138">Debe seguir el proceso normal de informes para [falsos positivos](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="8c6a9-138">You should follow the normal reporting process for [false-positives](prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="8c6a9-139">La única razón por la que el mensaje se movería de la bandeja de entrada a la carpeta correo no deseado sería porque el servicio determinó que el mensaje era correo no deseado o malintencionado.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-139">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="8c6a9-140">¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="8c6a9-140">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="8c6a9-141">ZAP no mueve los mensajes a cuarentena de la bandeja de entrada en este momento.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-141">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="8c6a9-142">¿Qué ocurre si tengo una regla de flujo de correo personalizada (regla de bloqueo/permiso)?</span><span class="sxs-lookup"><span data-stu-id="8c6a9-142">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="8c6a9-143">Las reglas creadas por los administradores (reglas de flujo de correo) o las reglas de bloqueo y permiso tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-143">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="8c6a9-144">Estos mensajes se excluyen de los criterios de la característica, por lo que el flujo de correo seguirá la acción de regla (bloquear/permitir regla).</span><span class="sxs-lookup"><span data-stu-id="8c6a9-144">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="8c6a9-145">¿Qué ocurre si un mensaje se mueve a otra carpeta (por ejemplo, una regla de bandeja de entrada)?</span><span class="sxs-lookup"><span data-stu-id="8c6a9-145">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>
<span data-ttu-id="8c6a9-146">ZAP sigue funcionando en este caso, a menos que el mensaje se haya eliminado o esté en correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-146">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c6a9-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8c6a9-147">Related Topics</span></span>

[<span data-ttu-id="8c6a9-148">Protección contra correo no deseado en Office 365</span><span class="sxs-lookup"><span data-stu-id="8c6a9-148">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="8c6a9-149">Bloquear el correo no deseado con el filtro contra correo no deseado de Office 365 para evitar problemas de falsos negativos</span><span class="sxs-lookup"><span data-stu-id="8c6a9-149">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
