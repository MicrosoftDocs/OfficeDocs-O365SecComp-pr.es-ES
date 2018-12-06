---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: Purgar cero horas automático (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con el correo no deseado o malware que ya se han entregado a las bandejas de entrada de los usuarios y, a continuación, representa el contenido malintencionado inocua. ZAP ¿cómo esto depende del tipo de contenido malintencionado detectado.
ms.openlocfilehash: 1cf14051e91801a74a0d739c69900bb3f825b318
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180850"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="dc1b3-104">Purga automática cero horas: protección contra correo no deseado y malware</span><span class="sxs-lookup"><span data-stu-id="dc1b3-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="dc1b3-105">Información general</span><span class="sxs-lookup"><span data-stu-id="dc1b3-105">Overview</span></span>

<span data-ttu-id="dc1b3-p102">Purgar cero horas automático (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con phishing, spam o malware que ya se han entregado a las bandejas de entrada de los usuarios y, a continuación, representa el contenido malintencionado inocua. ¿Cómo ZAP hace esto depende del tipo de contenido malintencionado detectado; Puede que haya que hacerlo correo debido a contenido de correo, las direcciones URL o los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="dc1b3-108">ZAP está disponible con el valor predeterminado de Exchange Online Protection que se incluye con cualquier suscripción de Office 365 que contiene los buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="dc1b3-109">ZAP está activado de forma predeterminada, pero se deben cumplir las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc1b3-109">ZAP is turned on by default, but the folowing conditions must be met:</span></span>
  
- <span data-ttu-id="dc1b3-110">**Acción de spam** se establece para **mover el mensaje a la carpeta correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="dc1b3-111">También puede crear una nueva directiva de filtro de spam que sólo se aplica a un conjunto de usuarios si no desea que todos los buzones que se filtran por ZAP.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="dc1b3-p103">Los usuarios conservan su valor predeterminado configuración del correo electrónico no deseado y no han desactivado de protección de correo electrónico no deseado. (Para obtener información detallada acerca de las opciones de usuario en Outlook, vea [cambiar el nivel de protección en el filtro de correo electrónico no deseado](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) ).</span><span class="sxs-lookup"><span data-stu-id="dc1b3-p103">Users have kept their default junk mail settings, and have not turned off junk email protection. (See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="dc1b3-114">¿Cómo funciona ZAP?</span><span class="sxs-lookup"><span data-stu-id="dc1b3-114">How does ZAP work?</span></span>

<span data-ttu-id="dc1b3-p104">Las firmas de motor y malware contra correo no deseadas en las actualizaciones de Office 365 en tiempo real de manera diaria. Sin embargo, los usuarios aún es posible que obtenga malintencionados mensajes entregados a sus bandejas de entrada para una variedad de motivos, incluido si el contenido se weaponized después de que se envía a los usuarios. ZAP soluciona este problema mediante la supervisión de forma continua las actualizaciones de las firmas de correo no deseado y malware de Office 365. ZAP puede buscar y quitar mensajes entregados que ya están en las bandejas de entrada de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-p104">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures. ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 

- <span data-ttu-id="dc1b3-119">Para el correo que se identifica como correo no deseado, ZAP mueve mensajes no leídos a la carpeta de correo electrónico no deseado de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 

- <span data-ttu-id="dc1b3-120">Para el correo que se identifica como correo no deseado, ZAP mueve los mensajes a la carpeta de correo electrónico no deseado de los usuarios, independientemente de si se ha leído el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-120">For mail that is identified as spam, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="dc1b3-121">Para recién detectado malware, ZAP quita los datos adjuntos de mensajes de correo electrónico, independientemente de si se ha leído el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="dc1b3-122">La acción ZAP es transparente para el usuario del buzón; no se notifica sobre esto si se mueve un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="dc1b3-123">Permitir listas, [reglas de flujo de correo](https://go.microsoft.com/fwlink/p/?LinkId=722755)y las reglas de usuario final o filtros adicionales tienen prioridad sobre ZAP.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-123">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="dc1b3-124">Para revisar o configurar una directiva de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="dc1b3-124">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="dc1b3-125">Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="dc1b3-126">En **administración de amenaza**, elija **contra correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-126">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="dc1b3-127">Revise la configuración estándar.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-127">Review the standard settings.</span></span> 

4. <span data-ttu-id="dc1b3-p105">Si desea personalizar la configuración, seleccione la ficha **personalizado** y activar la **configuración personalizada**. Editar la configuración y si lo desea, elija **+ crear una directiva** para agregar una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-p105">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**. Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="dc1b3-130">Para ver si ZAP mueve el mensaje</span><span class="sxs-lookup"><span data-stu-id="dc1b3-130">To see if ZAP moved your message</span></span>

<span data-ttu-id="dc1b3-131">Si desea ver si ZAP mueve el mensaje, puede utilizar ya sea el [informe de estado de protección de amenaza](view-email-security-reports.md#threat-protection-status-report-new) (o [El Explorador de amenaza](use-explorer-in-security-and-compliance.md)).</span><span class="sxs-lookup"><span data-stu-id="dc1b3-131">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report-new) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="dc1b3-132">Para deshabilitar ZAP</span><span class="sxs-lookup"><span data-stu-id="dc1b3-132">To disable ZAP</span></span>
  
<span data-ttu-id="dc1b3-133">Si desea deshabilitar eliminar para el inquilino de Office 365, o un conjunto de usuarios, use el parámetro **ZapEnabled** de [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet de elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-133">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="dc1b3-134">En el siguiente ejemplo, ZAP está deshabilitado para una directiva de filtro de contenido denominada "Prueba".</span><span class="sxs-lookup"><span data-stu-id="dc1b3-134">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="dc1b3-135">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="dc1b3-135">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="dc1b3-136">¿Qué ocurre si un mensaje legítimo se mueve a la carpeta correo electrónico no deseado?</span><span class="sxs-lookup"><span data-stu-id="dc1b3-136">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="dc1b3-p106">Debe seguir el proceso de generación de informes normal de falsos positivos. La única razón se pasaría el mensaje de la Bandeja de entrada a la carpeta correo electrónico no deseado sería debido a que el servicio ha determinado que el mensaje es correo no deseado o malintencionado.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="dc1b3-139">¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo electrónico no deseado?</span><span class="sxs-lookup"><span data-stu-id="dc1b3-139">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="dc1b3-140">ZAP no mover los mensajes en cuarentena desde la Bandeja de entrada en este momento.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-140">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="dc1b3-141">¿Qué ocurre si tiene una regla de flujo de correo personalizado (bloquear o permitir regla)?</span><span class="sxs-lookup"><span data-stu-id="dc1b3-141">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="dc1b3-p107">Las reglas creadas por administradores (reglas de flujo de correo) o las reglas de bloqueo y permitir tiene prioridad. Este tipo de mensajes se excluye de los criterios de la característica.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dc1b3-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dc1b3-144">Related Topics</span></span>

[<span data-ttu-id="dc1b3-145">Protección contra correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="dc1b3-145">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="dc1b3-146">Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos</span><span class="sxs-lookup"><span data-stu-id="dc1b3-146">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

