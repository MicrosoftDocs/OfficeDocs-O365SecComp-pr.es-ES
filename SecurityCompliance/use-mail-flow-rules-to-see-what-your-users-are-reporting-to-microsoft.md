---
title: Use reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: Puede crear una regla de transporte de Exchange para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.
ms.openlocfilehash: 7ee8fb2bca1071ccd4080379485c1670a5e66a73
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206413"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="54e14-103">Use reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft</span><span class="sxs-lookup"><span data-stu-id="54e14-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="54e14-p101">Hay varias formas de enviar mensajes falsos positivos y falsos negativos a Microsoft para su análisis. Como administrador, puede usar reglas de flujo de correo para ver lo que los usuarios notifican a Microsoft como correo no deseado, fraudes de suplantación de identidad (phishing). Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Por el contrario, puede crear una regla de transporte de Exchange para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="54e14-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="54e14-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="54e14-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="54e14-109">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="54e14-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="54e14-p102">Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "reglas de transporte" en el tema [permisos de directivas de mensajería y conformidad](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) y la entrada "directivas de buzón de Outlook en la web" en el tema [clients and Mobile](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) Devices Permissions.</span><span class="sxs-lookup"><span data-stu-id="54e14-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="54e14-112">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="54e14-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="54e14-113">Usar el EAC para crear una regla de flujo de correo para ver los informes de correo no deseado manuales de los usuarios, suplantación de identidad (phishing) y no</span><span class="sxs-lookup"><span data-stu-id="54e14-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="54e14-114">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="54e14-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="54e14-115">Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span><span class="sxs-lookup"><span data-stu-id="54e14-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="54e14-116">Give the rule a name and then click **More options**.</span><span class="sxs-lookup"><span data-stu-id="54e14-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="54e14-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span><span class="sxs-lookup"><span data-stu-id="54e14-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="54e14-118">In the **specify words or phrases** box, do the following:</span><span class="sxs-lookup"><span data-stu-id="54e14-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="54e14-p103">Escriba `abuse@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono. Estas direcciones de correo electrónico se usan para enviar mensajes falsos negativos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54e14-p103">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="54e14-p104">Escriba `phish@office365.microsoft.com` y, a ![continuación,](media/ITPro-EAC-AddIcon.gif)haga clic en agregar icono. Esta dirección de correo electrónico se usa para enviar mensajes de suplantación de identidad perdidos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54e14-p104">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="54e14-p105">Escriba `false_positive@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `not_junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono. Estas direcciones de correo electrónico se usan para enviar mensajes de falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54e14-p105">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="54e14-125">Click **ok**.</span><span class="sxs-lookup"><span data-stu-id="54e14-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="54e14-126">En **hacer lo siguiente**, seleccione **CCO el mensaje a...** y, a continuación, seleccione los buzones donde quiera recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="54e14-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="54e14-p106">Si lo desea, puede realizar selecciones para auditar la regla, probarla, activar la regla durante un período de tiempo específico y otras selecciones. Se recomienda probar la regla durante un período antes de aplicarla. Consulte [procedimientos para reglas de flujo de correo](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="54e14-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="54e14-p107">Haga clic en el botón **Guardar** para guardar la regla. Aparecerá en la lista de reglas.</span><span class="sxs-lookup"><span data-stu-id="54e14-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="54e14-132">Después de crear y aplicar la regla, todos los mensajes que se envíen desde la organización a las direcciones de correo electrónico especificadas se copiarán en el buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="54e14-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

