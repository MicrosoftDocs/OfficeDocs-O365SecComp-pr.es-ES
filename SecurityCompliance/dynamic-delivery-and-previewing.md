---
title: Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: Al configurar las directivas de los datos adjuntos seguros ATP, elija entrega dinámica para evitar retrasos de mensaje y permiten a los usuarios obtener una vista previa de datos adjuntos que se están analizando.
ms.openlocfilehash: 23ef316ed35b89ef1fad5e9639dd10e76036a4f3
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965247"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="0481d-103">Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="0481d-103">Dynamic delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="0481d-p101">Entrega dinámica es una opción que puede seleccionar para. Lea este artículo para obtener más información acerca de la entrega dinámica y las capacidades de vista previa de datos adjuntos en [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="0481d-p101">Dynamic delivery is an option that can be selected for . Read this article to learn about dynamic delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="0481d-106">Dinámico cómo funciona la entrega</span><span class="sxs-lookup"><span data-stu-id="0481d-106">How dynamic delivery works</span></span>

<span data-ttu-id="0481d-p102">Al [configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md), puede elegir entre varias opciones, como **bloque**, **Reemplazar**y **Entrega dinámica**. Dependiendo de cómo se configuran las directivas, los destinatarios de correo electrónico pueden experimentar un retraso en la entrega de correo electrónico secundario mientras se examinan los datos adjuntos. Para evitar retrasos de mensaje, elija **Entrega dinámica**.</span><span class="sxs-lookup"><span data-stu-id="0481d-p102">When you [set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md), you can choose from several options, such as **Block**, **Replace**, and **Dynamic Delivery**. Depending on how your policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
<span data-ttu-id="0481d-p103">La opción de entrega dinámica elimina los retrasos de correo electrónico mediante el envío el cuerpo de un mensaje de correo electrónico a través de con un marcador de posición para cada dato adjunto de correo electrónico. El marcador de posición permanece hasta que los datos adjuntos se examinan por [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md). Destinatarios de correo electrónico pueden leer y responder a sus mensajes de correo electrónico inmediatamente, sabiendo que se están analizando sus datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="0481d-p103">The dynamic delivery option eliminates email delays by sending the body of an email message through with a placeholder for each email attachment. The placeholder remains until the attachment is scanned by [ATP Safe Attachments in Office 365](atp-safe-attachments.md). Email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.</span></span>
  
<span data-ttu-id="0481d-p104">La mayoría de los archivos PDF y Office documentos pueden ser una vista previa en modo seguro mientras ATP análisis está en curso. Si un archivo adjunto no es compatible con el controlador de vista previa dinámica de entrega, los destinatarios de correo electrónico ven el marcador de posición de datos adjuntos hasta que se complete el análisis de los datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="0481d-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the dynamic delivery previewer, email recipients see the attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>
  
<span data-ttu-id="0481d-p105">Como cada dato adjunto está desactivada, automáticamente se a adjuntar al mensaje de correo electrónico original. Si un archivo adjunto se determina como malintencionado, se envía a cuarentena, donde una persona en el equipo de seguridad de su organización (por ejemplo, un administrador global de Office 365 o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="0481d-p105">As each attachment is cleared, it is automatically reattached to the original email message. If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="0481d-117">¿Qué sucede cuando alguien envía un correo electrónico que contiene datos adjuntos?</span><span class="sxs-lookup"><span data-stu-id="0481d-117">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="0481d-p106">Suponga que una organización utiliza la entrega dinámica para sus [datos adjuntos seguros de ATP directiva](set-up-atp-safe-attachments-policies.md), y que alguien recibe un correo electrónico que contiene datos adjuntos. Ahora suponga que esa persona está a punto de reenviar el mensaje de correo electrónico a otra persona. ¿Qué sucede? Depende de si los destinatarios adicionales se incluyen en las directivas de los datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="0481d-p106">Suppose that an organization is using dynamic delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="0481d-122">Si un destinatario está cubierto por una directiva de datos adjuntos seguros de ATP mediante la opción de entrega dinámica, el destinatario ve el marcador de posición, con la posibilidad de obtener una vista previa de archivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="0481d-122">If a recipient is covered by an ATP Safe Attachments policy using the dynamic delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="0481d-123">Si un destinatario no está cubierto por una directiva de datos adjuntos seguros de ATP, a continuación, el correo electrónico y datos adjuntos se realizarán a través de, sin datos adjuntos seguros de ATP examen o marcadores de posición de datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="0481d-123">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="0481d-124">¿Qué se necesita para que funcione la entrega dinámica?</span><span class="sxs-lookup"><span data-stu-id="0481d-124">What's required for dynamic delivery to work?</span></span>

- <span data-ttu-id="0481d-125">Su organización debe tener [La protección de amenaza avanzada de Office 365](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="0481d-125">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="0481d-126">Se deben definir directivas para datos adjuntos seguros de ATP mediante la opción de entrega dinámico (vea [configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="0481d-126">Policies must be defined for ATP Safe Attachments using the dynamic delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="0481d-127">Correo electrónico de su organización debe estar hospedado en Office 365</span><span class="sxs-lookup"><span data-stu-id="0481d-127">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="0481d-128">¿Hay escenarios para la que no está disponible la entrega dinámica?</span><span class="sxs-lookup"><span data-stu-id="0481d-128">Are there scenarios for which dynamic delivery is not available?</span></span>

<span data-ttu-id="0481d-p107">Hay determinados escenarios en los que no se admite la entrega dinámica. Estos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0481d-p107">There are certain scenarios in which dynamic delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="0481d-131">Mensajes de correo electrónico que se encuentran en las carpetas públicas</span><span class="sxs-lookup"><span data-stu-id="0481d-131">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="0481d-132">Mensajes de correo electrónico que se enrutan fuera de y, a continuación, realizar una copia en el buzón del usuario mediante las reglas personalizadas</span><span class="sxs-lookup"><span data-stu-id="0481d-132">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="0481d-133">Mensajes que se mueven (automático o manual) fuera del buzón hospedado y en otras ubicaciones, incluidas carpetas archivadas</span><span class="sxs-lookup"><span data-stu-id="0481d-133">Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="0481d-134">Mensajes que se eliminan</span><span class="sxs-lookup"><span data-stu-id="0481d-134">Messages that are deleted</span></span>
    
- <span data-ttu-id="0481d-135">Carpeta de búsqueda de buzón de correo de un usuario que se encuentra en un estado de error</span><span class="sxs-lookup"><span data-stu-id="0481d-135">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="0481d-p108">Entornos en los que un administrador de Exchange Online ha habilitado Exclaimer. (Vea [los mensajes con datos adjuntos no se entregan cuando se usan entrega dinámica ATP y Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span><span class="sxs-lookup"><span data-stu-id="0481d-p108">Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span></span>

- <span data-ttu-id="0481d-138">Mensajes cifrados con extensiones seguras multipropósito de correo Internet ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="0481d-138">Messages encrypted with Secure/Multipurpose Internet Mail Extensions ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0481d-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0481d-139">Related topics</span></span>

[<span data-ttu-id="0481d-140">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="0481d-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="0481d-141">Datos adjuntos seguros de ATP en Office 365</span><span class="sxs-lookup"><span data-stu-id="0481d-141">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="0481d-142">Configurar las directivas de los datos adjuntos seguros de ATP en Office 365</span><span class="sxs-lookup"><span data-stu-id="0481d-142">Set up ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="0481d-143">Vínculos de ATP seguros en Office 365</span><span class="sxs-lookup"><span data-stu-id="0481d-143">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)

[<span data-ttu-id="0481d-144">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="0481d-144">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

