---
title: Entrega dinámica y vista previa con datos adJuntos seguros de Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Cuando configure las directivas de datos adjuntos seguros de ATP, elija la entrega dinámica para evitar retrasos en los mensajes y permitir a los usuarios obtener una vista previa de los datos adjuntos que se están analizando.
ms.openlocfilehash: 1fb221d28a4089db8a4278903107c610d6825f5e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218400"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="1aed9-103">Entrega dinámica y vista previa con datos adJuntos seguros de Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1aed9-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="1aed9-p101">**Resumen**: la entrega dinámica es una opción que se puede seleccionar para los [datos adjuntos seguros de ATP](atp-safe-attachments.md). Lea este artículo para obtener información sobre las capacidades de entrega y vista previa de datos adjuntos de ATP en los [datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="1aed9-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="1aed9-p102">Cuando [se configuran directivas de datos adjuntos seguros ATP](set-up-atp-safe-attachments-policies.md) para la organización, hay varias opciones sobre cómo se administran los datos adjuntos de correo electrónico. Entre estos se incluyen **bloquear**, **reemplazar**y **entrega dinámica**. En función de cómo estén configuradas las directivas de datos adJuntos seguros de ATP, los destinatarios de correo electrónico podrían experimentar un retraso menor en la entrega de correo electrónico mientras se examinan los datos adjuntos. Para evitar retrasos en los mensajes, elija **entrega dinámica**.</span><span class="sxs-lookup"><span data-stu-id="1aed9-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="1aed9-110">Cómo funciona la entrega dinámica</span><span class="sxs-lookup"><span data-stu-id="1aed9-110">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="1aed9-p103">La entrega dinámica elimina los retrasos del correo electrónico enviando el cuerpo de un mensaje de correo electrónico al destinatario con un marcador de posición para cada adjunto de correo electrónico. El marcador de posición permanece hasta que una copia de los datos adjuntos se analiza y se determina que está protegido por [datos adjuntos seguros ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="1aed9-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="1aed9-113">A medida que se borren los datos adjuntos, estará disponible para abrirlos o descargarlos.</span><span class="sxs-lookup"><span data-stu-id="1aed9-113">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="1aed9-114">Si los datos adjuntos se determinan como malintencionados, se envían a cuarentena, donde alguien del equipo de seguridad de su organización (como un administrador global de Office 365 o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1aed9-114">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="1aed9-p104">La mayoría de los PDF y los documentos de Office se pueden mostrar como una vista previa en modo seguro mientras se está realizando el análisis de ATP. Si los datos adjuntos no son compatibles con el previsor de entrega dinámica, los destinatarios de correo electrónico ven un marcador de posición de datos adjuntos hasta que se complete el análisis de datos adJuntos seguros ATP.</span><span class="sxs-lookup"><span data-stu-id="1aed9-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="1aed9-117">Si está usando un dispositivo móvil y los PDF no se representan en primer lugar en el previsualizador de entrega dinámico, intente iniciar sesión en Office 365 con el explorador móvil.</span><span class="sxs-lookup"><span data-stu-id="1aed9-117">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="1aed9-118">Con la entrega dinámica, los usuarios pueden leer y responder a sus mensajes de correo electrónico inmediatamente, mientras se analizan los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="1aed9-118">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="1aed9-p105">El análisis de datos adJuntos seguros de ATP tiene lugar en la misma región en la que residen los datos de Office 365. Para obtener más información acerca de la geografía del centro de datos, consulte [¿dónde están los datos ubicados?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="1aed9-p105">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="1aed9-121">¿Qué sucede cuando alguien reenvía un correo electrónico que contiene datos adjuntos?</span><span class="sxs-lookup"><span data-stu-id="1aed9-121">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="1aed9-p106">Suponga que una organización está usando la entrega dinámica para la [Directiva de datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md)y alguien recibe un correo electrónico que contiene datos adjuntos. Ahora, supongamos que la persona reenvía el mensaje de correo electrónico a otro usuario. ¿Qué sucede? Depende de si los destinatarios adicionales se incluyen en las directivas de datos adJuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="1aed9-p106">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person forwards the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="1aed9-126">Si un destinatario está cubierto por una directiva de datos adJuntos seguros de ATP mediante la opción de entrega dinámica, el destinatario verá el marcador de posición, con la capacidad de obtener una vista previa de los archivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="1aed9-126">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="1aed9-127">Si un destinatario no está cubierto por una directiva de datos adJuntos seguros de ATP, el correo electrónico y los datos adjuntos pasarán, sin el análisis de datos adjuntos seguros de ATP o los marcadores de posición de datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="1aed9-127">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="1aed9-128">¿Qué se necesita para que funcione la entrega dinámica?</span><span class="sxs-lookup"><span data-stu-id="1aed9-128">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="1aed9-129">Su organización debe tener la [protección contra amenazas avanzada de Office 365](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="1aed9-129">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="1aed9-130">Las directivas deben definirse para los datos adJuntos seguros de ATP que usen la opción de entrega dinámica (consulte [configurar las directivas de datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="1aed9-130">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="1aed9-131">El correo electrónico de su organización debe estar hospedado en Office 365</span><span class="sxs-lookup"><span data-stu-id="1aed9-131">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="1aed9-132">¿Hay algún escenario para el que no esté disponible la entrega dinámica?</span><span class="sxs-lookup"><span data-stu-id="1aed9-132">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="1aed9-p107">Hay algunos escenarios en los que no se admite la entrega dinámica. Entre ellas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1aed9-p107">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="1aed9-135">Mensajes de correo electrónico que están en carpetas públicas</span><span class="sxs-lookup"><span data-stu-id="1aed9-135">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="1aed9-136">Mensajes de correo electrónico que se redirigen del y después al buzón del usuario mediante reglas personalizadas</span><span class="sxs-lookup"><span data-stu-id="1aed9-136">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="1aed9-137">Mensajes de correo electrónico que se mueven (de forma automática o manual) del buzón de correo hospedado y a otras ubicaciones, incluidas las carpetas de archivo</span><span class="sxs-lookup"><span data-stu-id="1aed9-137">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="1aed9-138">Mensajes de correo electrónico que se eliminan</span><span class="sxs-lookup"><span data-stu-id="1aed9-138">Email messages that are deleted</span></span>
    
- <span data-ttu-id="1aed9-139">Carpeta de búsqueda del buzón de un usuario que se encuentra en estado de error</span><span class="sxs-lookup"><span data-stu-id="1aed9-139">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="1aed9-p108">Entornos en los que un administrador de Exchange Online ha habilitado exclaimer. Para resolver esto, vea [no se entregan los mensajes con datos adjuntos cuando se usan la entrega y](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery) exClaims dinámicas de ATP</span><span class="sxs-lookup"><span data-stu-id="1aed9-p108">Environments in which an Exchange Online admin has enabled Exclaimer. To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="1aed9-142">Mensajes cifrados con [extensiones seguras multipropósito al correo de Internet (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="1aed9-142">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

