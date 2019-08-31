---
title: Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Puede crear una regla de flujo de correo de Exchange para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.
ms.openlocfilehash: d423cc7f85609563acf80ea8efffa8935a2537d3
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699012"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="4527a-103">Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4527a-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="4527a-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span><span class="sxs-lookup"><span data-stu-id="4527a-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="4527a-105">Como administrador, puede usar reglas de flujo de correo para ver lo que los usuarios notifican a Microsoft como correo no deseado, fraudes de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="4527a-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="4527a-106">Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="4527a-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="4527a-107">Por el contrario, puede crear una regla de flujo de correo de Exchange (también denominada regla de transporte) para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4527a-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4527a-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="4527a-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="4527a-109">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="4527a-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="4527a-110">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos.</span><span class="sxs-lookup"><span data-stu-id="4527a-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="4527a-111">Para ver qué permisos necesita, consulte el entrada "reglas de flujo de correo" en el tema [permisos de directivas de mensajería y conformidad](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) y la entrada "directivas de buzón de Outlook en la web" en el tema [clients and Mobile](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) Devices Permissions.</span><span class="sxs-lookup"><span data-stu-id="4527a-111">To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="4527a-112">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4527a-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="4527a-113">Usar el EAC para crear una regla de flujo de correo para ver los informes de correo no deseado manuales de los usuarios, suplantación de identidad (phishing) y no</span><span class="sxs-lookup"><span data-stu-id="4527a-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="4527a-114">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="4527a-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="4527a-115">Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span><span class="sxs-lookup"><span data-stu-id="4527a-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="4527a-116">Give the rule a name and then click **More options**.</span><span class="sxs-lookup"><span data-stu-id="4527a-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="4527a-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span><span class="sxs-lookup"><span data-stu-id="4527a-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="4527a-118">In the **specify words or phrases** box, do the following:</span><span class="sxs-lookup"><span data-stu-id="4527a-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="4527a-119">Escriba `abuse@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono.</span><span class="sxs-lookup"><span data-stu-id="4527a-119">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="4527a-120">These email addresses are used to submit false negative messages to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4527a-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="4527a-121">Escriba `phish@office365.microsoft.com` y, a ![continuación,](media/ITPro-EAC-AddIcon.gif)haga clic en agregar icono.</span><span class="sxs-lookup"><span data-stu-id="4527a-121">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="4527a-122">Esta dirección de correo electrónico se usa para enviar mensajes de suplantación de identidad perdidos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4527a-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="4527a-123">Escriba `false_positive@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `not_junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono.</span><span class="sxs-lookup"><span data-stu-id="4527a-123">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="4527a-124">These email addresses are used to submit false positive messages to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4527a-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="4527a-125">Click **ok**.</span><span class="sxs-lookup"><span data-stu-id="4527a-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="4527a-126">En **hacer lo siguiente**, seleccione **CCO el mensaje a...** y, a continuación, seleccione los buzones donde quiera recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4527a-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="4527a-127">Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones.</span><span class="sxs-lookup"><span data-stu-id="4527a-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="4527a-128">Recomendamos probar la regla durante un tiempo antes de aplicarla.</span><span class="sxs-lookup"><span data-stu-id="4527a-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="4527a-129">Consulte [procedimientos para reglas de flujo de correo](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="4527a-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="4527a-130">Haga clic en el botón **Guardar** para guardar la regla.</span><span class="sxs-lookup"><span data-stu-id="4527a-130">Click the **save** button to save the rule.</span></span> <span data-ttu-id="4527a-131">Aparecerá en la lista de reglas.</span><span class="sxs-lookup"><span data-stu-id="4527a-131">It appears in your list of rules.</span></span> 
    
<span data-ttu-id="4527a-132">Después de crear y aplicar la regla, todos los mensajes que se envíen desde la organización a las direcciones de correo electrónico especificadas se copiarán en el buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="4527a-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

