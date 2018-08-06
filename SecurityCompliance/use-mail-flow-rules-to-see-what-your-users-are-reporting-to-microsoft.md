---
title: Use reglas de flujo de correo para ver lo que los usuarios son informes a Microsoft
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/23/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: Puede crear una regla de transporte de Exchange para impedir que los usuarios enviar mensajes de correo electrónico a Microsoft para su análisis y usarlas en sus propios procesos de seguridad
ms.openlocfilehash: f2376668e2a1a16eba9913178a100fc31763b227
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026777"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="336e0-103">Use reglas de flujo de correo para ver lo que los usuarios son informes a Microsoft</span><span class="sxs-lookup"><span data-stu-id="336e0-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="336e0-p101">Hay varias maneras que puede enviar mensajes negativos falsos positivos y false a Microsoft para su análisis. Como administrador, puede usar las reglas de flujo de correo para ver lo que los usuarios son informes a Microsoft como correo no deseado, que no sean de correo no deseado y las estafas de suplantación de identidad. Para obtener más información, vea [enviar spam, no spam y los mensajes de estafas de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Por el contrario, puede crear una regla de transporte de Exchange para impedir que los usuarios enviar mensajes de correo electrónico a Microsoft para su análisis y usarlas en sus propios procesos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="336e0-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="336e0-108">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="336e0-108">What do you need to know before you begin?</span></span>
<span data-ttu-id="336e0-109"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="336e0-109"></span></span>

<span data-ttu-id="336e0-110">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="336e0-110">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="336e0-p102">Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada "Reglas de transporte" en el tema [permisos de directivas y cumplimiento de normas de mensajería](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) y la entrada "Directivas de buzón de correo de Outlook Web App" en el tema de [los clientes y los permisos de los dispositivos móviles](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) .</span><span class="sxs-lookup"><span data-stu-id="336e0-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook Web App mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="336e0-113">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="336e0-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="336e0-114">Usar el EAC para crear una regla de flujo de correo para ver los usuarios manual correo no deseado, suplantación de identidad y los informes no no deseados</span><span class="sxs-lookup"><span data-stu-id="336e0-114">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>
<span data-ttu-id="336e0-115"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="336e0-115"></span></span>

1. <span data-ttu-id="336e0-116">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="336e0-116">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="336e0-117">Click ![Agregar icono](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span><span class="sxs-lookup"><span data-stu-id="336e0-117">Click ![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="336e0-118">Give the rule a name and then click **More options**.</span><span class="sxs-lookup"><span data-stu-id="336e0-118">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="336e0-119">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span><span class="sxs-lookup"><span data-stu-id="336e0-119">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="336e0-120">In the **specify words or phrases** box, do the following:</span><span class="sxs-lookup"><span data-stu-id="336e0-120">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="336e0-p103">Type **abuse@messaging.microsoft.com** and then click ![Agregar icono](media/ITPro-EAC-AddIcon.png), and then type **junk@office365.microsoft.com** and then click ![Agregar icono](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false negative messages to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="336e0-p103">Type **abuse@messaging.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then type **junk@office365.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="336e0-p104">Escriba **phish@office365.microsoft.com** y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.png). Esta dirección de correo electrónico se usa para enviar mensajes de suplantación de identidad perdidas a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="336e0-p104">Type **phish@office365.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="336e0-p105">Type **false_positive@messaging.microsoft.com** and then click ![Agregar icono](media/ITPro-EAC-AddIcon.png), and then type **not_junk@office365.microsoft.com** and then click ![Agregar icono](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false positive messages to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="336e0-p105">Type **false_positive@messaging.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then type **not_junk@office365.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="336e0-127">Click **ok**.</span><span class="sxs-lookup"><span data-stu-id="336e0-127">Click **ok**.</span></span>
    
6. <span data-ttu-id="336e0-128">Bajo, **siga este procedimiento**, seleccione **CCO del mensaje a...** y, a continuación y, a continuación, seleccione los buzones de correo que desea reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="336e0-128">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="336e0-p106">Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contiene más información acerca de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="336e0-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contains more information about these selections.</span></span> 
    
8. <span data-ttu-id="336e0-p107">Haga clic en el botón **Guardar** para guardar la regla. Aparecerá en la lista de reglas.</span><span class="sxs-lookup"><span data-stu-id="336e0-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="336e0-134">Después de crear y aplicar la regla, se copiarán todos los mensajes que se envían desde la organización a las direcciones de correo electrónico especificada en el buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="336e0-134">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

