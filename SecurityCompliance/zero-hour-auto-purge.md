---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2018
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
ms.openlocfilehash: dc8901dc7c1db5b323ccbeee610647b8a302fcb3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535800"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="4dec8-104">Purga automática cero horas: protección contra correo no deseado y malware</span><span class="sxs-lookup"><span data-stu-id="4dec8-104">Zero-hour auto purge - protection against spam and malware</span></span>

<span data-ttu-id="4dec8-p102">Purgar cero horas automático (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con el correo no deseado o malware que ya se han entregado a las bandejas de entrada de los usuarios y, a continuación, representa el contenido malintencionado inocua. ZAP ¿cómo esto depende del tipo de contenido malintencionado detectado.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with spam or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected.</span></span>
  
<span data-ttu-id="4dec8-107">ZAP está disponible con el valor predeterminado de Exchange Online Protection que se incluye con cualquier suscripción de Office 365 que contiene los buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4dec8-107">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>
  
## <a name="how-does-zap-work"></a><span data-ttu-id="4dec8-108">¿Cómo funciona ZAP?</span><span class="sxs-lookup"><span data-stu-id="4dec8-108">How does ZAP work?</span></span>

<span data-ttu-id="4dec8-p103">Las firmas de motor y malware contra correo no deseadas en las actualizaciones de Office 365 en tiempo real de manera diaria. Sin embargo, los usuarios aún es posible que obtenga malintencionados mensajes entregados a sus bandejas de entrada para una variedad de motivos, incluso cuando el contenido se weaponized en un momento después de que se ha entregado primero a los usuarios. ELIMINAR direcciones esto mediante la supervisión de forma continua las actualizaciones a las firmas de correo no deseado y malware de Office 365, y puede, por tanto, buscar y quitar mensajes entregados ya en las bandejas de entrada. Para el correo que ya se ha identificado como correo no deseado, ZAP mueve los mensajes no leídos a la carpeta de correo electrónico no deseado del usuario. Para recién detectado malware, ZAP quita los datos adjuntos de mensaje de correo electrónico, independientemente de si el correo se ha leído o no. Es true para los mensajes que se han clasificado incorrectamente como malintencionados al revés.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p103">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including when the content was weaponized at a time after it was first delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures, and can therefore find and remove previously delivered messages already in inboxes. For mail that was already identified as spam, ZAP moves unread messages to the user's Junk mail folder. For newly detected malware, ZAP removes the attachments from the email message, regardless of whether the mail was read or not. The reverse is true for messages that were incorrectly classified as malicious.</span></span>
  
<span data-ttu-id="4dec8-115">La acción ZAP es transparente para el usuario del buzón, navegará no se notifica que el correo se ha movido.</span><span class="sxs-lookup"><span data-stu-id="4dec8-115">The ZAP action is seamless for the mailbox user, he or she is not notified the mail has been moved.</span></span>
  
<span data-ttu-id="4dec8-116">Permitir listas, [reglas de flujo de correo](https://go.microsoft.com/fwlink/p/?LinkId=722755)y las reglas de usuario final o filtros adicionales tienen prioridad sobre ZAP.</span><span class="sxs-lookup"><span data-stu-id="4dec8-116">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
 <span data-ttu-id="4dec8-117">**En este artículo:**</span><span class="sxs-lookup"><span data-stu-id="4dec8-117">**In this article:**</span></span>
  
> [<span data-ttu-id="4dec8-118">Establecer la directiva de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="4dec8-118">Set spam filter policy</span></span>](zero-hour-auto-purge.md#BK_SetSpam)
    
> [<span data-ttu-id="4dec8-119">Vea si ZAP mueve el mensaje</span><span class="sxs-lookup"><span data-stu-id="4dec8-119">See if ZAP moved your message</span></span>](zero-hour-auto-purge.md#BK_DidZAPMove)
    
> [<span data-ttu-id="4dec8-120">Deshabilitar ZAP</span><span class="sxs-lookup"><span data-stu-id="4dec8-120">Disable ZAP</span></span>](zero-hour-auto-purge.md#BK_Posh)
    
> [<span data-ttu-id="4dec8-121">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="4dec8-121">FAQ</span></span>](zero-hour-auto-purge.md#BK_FAQ)
    
## <a name="working-with-zap"></a><span data-ttu-id="4dec8-122">Trabajar con ZAP</span><span class="sxs-lookup"><span data-stu-id="4dec8-122">Working with ZAP</span></span>

<span data-ttu-id="4dec8-123">ZAP está activado de forma predeterminada, pero es necesario para asegurarse de que un par de condiciones se cumplen:</span><span class="sxs-lookup"><span data-stu-id="4dec8-123">ZAP is turned on by default, but you do have to make sure a couple of conditions are met:</span></span>
  
- <span data-ttu-id="4dec8-124">Directiva de filtro de spam se establece para [mover el mensaje a la carpeta correo no deseado](zero-hour-auto-purge.md#BK_SetSpam).</span><span class="sxs-lookup"><span data-stu-id="4dec8-124">Spam filter policy is set to [Move message to Junk Email folder](zero-hour-auto-purge.md#BK_SetSpam).</span></span>
    
    <span data-ttu-id="4dec8-125">También puede crear una nueva directiva de filtro de spam que sólo se aplica a un conjunto de usuarios si no desea que todos los buzones que se filtran por ZAP.</span><span class="sxs-lookup"><span data-stu-id="4dec8-125">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>
    
- <span data-ttu-id="4dec8-126">El usuario [opciones \> correo electrónico no deseado](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F).</span><span class="sxs-lookup"><span data-stu-id="4dec8-126">The user's [Options \> Junk Email](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F).</span></span>
    
<span data-ttu-id="4dec8-127">Si desea [ver si ZAP mueve el mensaje](zero-hour-auto-purge.md#BK_DidZAPMove), puede usar la herramienta de seguimiento de mensaje de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4dec8-127">If you want [to see if ZAP moved your message](zero-hour-auto-purge.md#BK_DidZAPMove), you can use the Exchange Online message trace tool.</span></span>
  
<span data-ttu-id="4dec8-128">Los administradores también pueden [Deshabilitar ZAP](zero-hour-auto-purge.md#BK_Posh) mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dec8-128">Admins can also [disable ZAP](zero-hour-auto-purge.md#BK_Posh) by using PowerShell.</span></span> 
  
 <span data-ttu-id="4dec8-129">**Para establecer la directiva de filtro de spam**</span><span class="sxs-lookup"><span data-stu-id="4dec8-129">**To set spam filter policy**</span></span>
  
1. <span data-ttu-id="4dec8-130">Inicie sesión en el [Where iniciar sesión en Office 365 para profesionales](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) y elija **protección** \> **filtro de spam**.</span><span class="sxs-lookup"><span data-stu-id="4dec8-130">Sign in to the [Where to sign in to Office 365 for business](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) and choose **protection** \> **spam filter**.</span></span> 
    
    ![En el EAC, elija protección y, a continuación, filtro de correo no deseado](media/0463c879-63fa-4a6c-9b03-e980d5ef3954.PNG)
  
2. <span data-ttu-id="4dec8-132">Elegir la directiva de filtro que desea ajustar, o bien seleccionar **Agregar**![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) para crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="4dec8-132">Either choose the filter policy you want to adjust, or choose **add**![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) to create a new one.</span></span> 
    
    <span data-ttu-id="4dec8-p104">En la captura de pantalla anterior, la directiva se denomina "Predeterminado", pero si crea directivas de filtro de correo no deseado adicional puede proporcionar un nombre diferente. También puede aplicar la directiva a sólo un conjunto limitado de usuarios.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p104">In the previous screen shot, the policy is named "Default", but if you create additional spam filter policies you can give them a different name. You can also apply the policy to only a limited set of users.</span></span>
    
3. <span data-ttu-id="4dec8-135">En la ventana Directiva, elija **acciones de correo no deseado y masiva**y asegúrese de que el **Spam** se establece en **Mover mensaje a la carpeta correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="4dec8-135">In the policy window, choose **spam and bulk actions**, and make sure that **Spam** is set to **Move message to Junk Email folder**.</span></span> 
    
    <span data-ttu-id="4dec8-136">Si decide **Guardar** en este momento, la directiva se aplica a su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4dec8-136">If you choose **Save** at this point, the policy applies to your Office 365 tenant.</span></span> 
    
    ![Conjunto de acciones de correo no deseado y masiva a Mpve mensaje a la carpeta correo no deseado](media/4332cfb3-89e1-48ba-8da8-9286f2fa1089.PNG)
  
4. <span data-ttu-id="4dec8-p105">Si ha creado una nueva directiva, y que desea aplicar la directiva a sólo un conjunto de usuarios, desplácese hasta la sección **Aplicada a** en la ventana de filtro de la directiva y en los controles de menú elegir los **destinatarios**, **dominio**o **las pertenencias a grupos** ¿desea aplicar la directiva. También puede establecer excepciones y condiciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p105">If you created a new policy, and you want to apply the policy to only a set of users, scroll to the **Applied To** section in the policy filter window, and in the menu controls choose the **recipients**, **domain**, or **group memberships** you want to apply the policy to. You can also set additional conditions and exceptions.</span></span> 
    
    ![En la sección aplicado a elegir los destinatarios](media/19ca10db-c0f4-432c-b3de-ad4101a23de6.PNG)
  
    <span data-ttu-id="4dec8-141">Elija **Guardar** para aplicar la directiva a los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="4dec8-141">Choose **Save** to apply the policy to the selected users.</span></span> 
    
 <span data-ttu-id="4dec8-142">**Para ver si ZAP mueve el mensaje**</span><span class="sxs-lookup"><span data-stu-id="4dec8-142">**To see if ZAP moved your message**</span></span>
  
- <span data-ttu-id="4dec8-143">Puede usar [Buscar y corregir problemas de entrega de correo electrónico como un Office 365 para profesionales admin](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) para determinar si el mensaje se ha movido por ZAP:</span><span class="sxs-lookup"><span data-stu-id="4dec8-143">You can use the [Find and fix email delivery issues as an Office 365 for business admin](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) to determine if the message was moved by ZAP:</span></span> 
    
    <span data-ttu-id="4dec8-144">Busque el texto "cero horas automático purgar (ZAP)" en los detalles de seguimiento para identificar un mensaje que se ha movido por ZAP.</span><span class="sxs-lookup"><span data-stu-id="4dec8-144">Look for the text "Zero-Hour Auto Purge (ZAP)" in your trace details to identify a message that was moved by ZAP.</span></span>
    
 <span data-ttu-id="4dec8-145">**Para deshabilitar ZAP**</span><span class="sxs-lookup"><span data-stu-id="4dec8-145">**To disable ZAP**</span></span>
  
- <span data-ttu-id="4dec8-146">Si desea deshabilitar eliminar para el inquilino de Office 365, o un conjunto de usuarios, use el parámetro **ZapEnabled** de [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet de elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="4dec8-146">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
    <span data-ttu-id="4dec8-147">En el siguiente ejemplo, ZAP está deshabilitado para una directiva de filtro de contenido denominada "Prueba".</span><span class="sxs-lookup"><span data-stu-id="4dec8-147">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
||
|:-----|
|
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

|
   
## <a name="faq"></a><span data-ttu-id="4dec8-148">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="4dec8-148">FAQ</span></span>
<span data-ttu-id="4dec8-149"><a name="BK_FAQ"> </a></span><span class="sxs-lookup"><span data-stu-id="4dec8-149"></span></span>

 <span data-ttu-id="4dec8-150">**¿Qué ocurre si un mensaje legítimo se mueve a la carpeta correo electrónico no deseado?**</span><span class="sxs-lookup"><span data-stu-id="4dec8-150">**What happens if a legitimate message is moved to the junk mail folder?**</span></span>
  
<span data-ttu-id="4dec8-p106">Debe seguir el proceso de generación de informes normal de falsos positivos. La única razón se pasaría el mensaje de la Bandeja de entrada a la carpeta correo electrónico no deseado sería debido a que el servicio ha determinado que el mensaje es correo no deseado o malintencionado.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
 <span data-ttu-id="4dec8-153">**¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo electrónico no deseado?**</span><span class="sxs-lookup"><span data-stu-id="4dec8-153">**What if I use the Office 365 quarantine instead of the junk mail folder?**</span></span>
  
<span data-ttu-id="4dec8-154">ZAP no mover los mensajes en cuarentena desde la Bandeja de entrada en este momento.</span><span class="sxs-lookup"><span data-stu-id="4dec8-154">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
 <span data-ttu-id="4dec8-155">**¿Qué ocurre si tiene una regla de flujo de correo personalizado (bloquear o permitir regla)?**</span><span class="sxs-lookup"><span data-stu-id="4dec8-155">**What If I have a custom mail flow rule (Block/ Allow Rule)?**</span></span>
  
<span data-ttu-id="4dec8-p107">Las reglas creadas por administradores (reglas de flujo de correo) o las reglas de bloqueo y permitir tiene prioridad. Este tipo de mensajes se excluye de los criterios de la característica.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4dec8-158">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4dec8-158">Related Topics</span></span>
<span data-ttu-id="4dec8-159"><a name="BK_FAQ"> </a></span><span class="sxs-lookup"><span data-stu-id="4dec8-159"></span></span>

[<span data-ttu-id="4dec8-160">Protección contra correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="4dec8-160">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="4dec8-161">Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos</span><span class="sxs-lookup"><span data-stu-id="4dec8-161">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

