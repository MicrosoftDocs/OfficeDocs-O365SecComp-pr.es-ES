---
title: Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: Al configurar las directivas de los datos adjuntos seguros ATP, elija entrega dinámica para evitar retrasos de mensaje y permiten a los usuarios obtener una vista previa de datos adjuntos que se están analizando.
ms.openlocfilehash: a272253594dda7ea720bb1e8b59e38e870f2f036
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238432"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="a7738-103">Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a7738-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="a7738-p101">**Resumen**: entrega dinámico es una opción que se puede seleccionar los datos adjuntos [seguros](atp-safe-attachments.md)de ATP. Lea este artículo para obtener más información acerca de la entrega dinámica y las capacidades de vista previa de datos adjuntos en [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="a7738-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="a7738-106">Cómo funciona la entrega dinámica</span><span class="sxs-lookup"><span data-stu-id="a7738-106">How Dynamic Delivery works</span></span>

<span data-ttu-id="a7738-p102">Cuando [se configuran las directivas de los datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) para su organización, hay varias opciones sobre cómo se controlan los datos adjuntos de correo electrónico. Éstas incluyen **bloque**, **Reemplazar**y **Entrega dinámica**. Dependiendo de cómo se configuran las directivas de los datos adjuntos seguros de ATP, los destinatarios de correo electrónico pueden experimentar un retraso en la entrega de correo electrónico secundario mientras se examinan los datos adjuntos. Para evitar retrasos de mensaje, elija **Entrega dinámica**.</span><span class="sxs-lookup"><span data-stu-id="a7738-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
<span data-ttu-id="a7738-p103">Entrega dinámica elimina los retrasos de correo electrónico mediante el envío el cuerpo de un mensaje de correo electrónico a través de al destinatario con un marcador de posición para cada dato adjunto de correo electrónico. El marcador de posición permanece hasta que una copia de los datos adjuntos se examinan y determinada como segura por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md). La mayoría de los archivos PDF y Office documentos pueden ser una vista previa en modo seguro mientras ATP análisis está en curso. Si un archivo adjunto no es compatible con el controlador de vista previa dinámica entrega, los destinatarios de correo electrónico ven un marcador de posición de datos adjuntos hasta que se complete el análisis de los datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="a7738-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md). Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

- <span data-ttu-id="a7738-115">Como cada dato adjunto está desactivada, está disponible para abrir o descargar.</span><span class="sxs-lookup"><span data-stu-id="a7738-115">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="a7738-116">Si un archivo adjunto se determina como malintencionado, se envía a cuarentena, donde una persona en el equipo de seguridad de su organización (por ejemplo, un administrador global de Office 365 o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="a7738-116">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="a7738-117">Con entrega dinámico, los destinatarios de correo electrónico pueden leer y responder a sus mensajes de correo electrónico inmediatamente, sabiendo que se están analizando sus datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a7738-117">With Dynamic Delivery, email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.</span></span> 

<span data-ttu-id="a7738-p104">Datos adjuntos seguros de ATP que lleve a cabo el examen se coloque en la misma región donde residen los datos de Office 365. Para obtener más información acerca de la zona geográfica de centro de datos, vea [¿dónde están los datos que se encuentra?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="a7738-p104">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="a7738-120">¿Qué sucede cuando alguien envía un correo electrónico que contiene datos adjuntos?</span><span class="sxs-lookup"><span data-stu-id="a7738-120">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="a7738-p105">Suponga que una organización utiliza la entrega dinámica para sus [datos adjuntos seguros de ATP directiva](set-up-atp-safe-attachments-policies.md), y que alguien recibe un correo electrónico que contiene datos adjuntos. Ahora suponga que esa persona está a punto de reenviar el mensaje de correo electrónico a otra persona. ¿Qué sucede? Depende de si los destinatarios adicionales se incluyen en las directivas de los datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="a7738-p105">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="a7738-125">Si un destinatario está cubierto por una directiva de datos adjuntos seguros de ATP mediante la opción de entrega dinámica, el destinatario ve el marcador de posición, con la posibilidad de obtener una vista previa de archivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="a7738-125">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="a7738-126">Si un destinatario no está cubierto por una directiva de datos adjuntos seguros de ATP, a continuación, el correo electrónico y datos adjuntos se realizarán a través de, sin datos adjuntos seguros de ATP examen o marcadores de posición de datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a7738-126">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="a7738-127">¿Qué se necesita para que funcione la entrega dinámica?</span><span class="sxs-lookup"><span data-stu-id="a7738-127">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="a7738-128">Su organización debe tener [La protección de amenaza avanzada de Office 365](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="a7738-128">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="a7738-129">Se deben definir directivas para datos adjuntos seguros de ATP mediante la opción de entrega dinámico (vea [configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="a7738-129">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="a7738-130">Correo electrónico de su organización debe estar hospedado en Office 365</span><span class="sxs-lookup"><span data-stu-id="a7738-130">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="a7738-131">¿Hay escenarios para la que no está disponible la entrega dinámica?</span><span class="sxs-lookup"><span data-stu-id="a7738-131">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="a7738-p106">Hay determinados escenarios en los que no se admite la entrega dinámica. Estos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7738-p106">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="a7738-134">Mensajes de correo electrónico que se encuentran en las carpetas públicas</span><span class="sxs-lookup"><span data-stu-id="a7738-134">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="a7738-135">Mensajes de correo electrónico que se enrutan fuera de y, a continuación, realizar una copia en el buzón del usuario mediante las reglas personalizadas</span><span class="sxs-lookup"><span data-stu-id="a7738-135">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="a7738-136">Mensajes que se mueven (automático o manual) fuera del buzón hospedado y en otras ubicaciones, incluidas carpetas archivadas</span><span class="sxs-lookup"><span data-stu-id="a7738-136">Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="a7738-137">Mensajes que se eliminan</span><span class="sxs-lookup"><span data-stu-id="a7738-137">Messages that are deleted</span></span>
    
- <span data-ttu-id="a7738-138">Carpeta de búsqueda de buzón de correo de un usuario que se encuentra en un estado de error</span><span class="sxs-lookup"><span data-stu-id="a7738-138">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="a7738-p107">Entornos en los que un administrador de Exchange Online ha habilitado Exclaimer. (Vea [los mensajes con datos adjuntos no se entregan cuando se usan entrega dinámica ATP y Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span><span class="sxs-lookup"><span data-stu-id="a7738-p107">Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span></span>

- <span data-ttu-id="a7738-141">Mensajes cifrados con extensiones seguras multipropósito de correo Internet ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="a7738-141">Messages encrypted with Secure/Multipurpose Internet Mail Extensions ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span></span>
    
