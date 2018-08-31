---
title: Cómo funciona la DLP entre la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en la seguridad &amp; centro de cumplimiento funciona con DLP y reglas de transporte en el centro de administración de Exchange.
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536473"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="b1096-103">Cómo funciona la DLP entre la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="b1096-103">How DLP works between the Security &amp; Compliance Center and Exchange Admin Center</span></span>

<span data-ttu-id="b1096-104">En Office 365, puede crear una directiva de (DLP) de prevención de pérdida de datos en dos centros de administración diferentes:</span><span class="sxs-lookup"><span data-stu-id="b1096-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="b1096-p101">En la **seguridad &amp; centro de cumplimiento**, puede crear una sola directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive y Exchange. Cuando sea posible, se recomienda que cree una directiva de DLP aquí. Para obtener más información, vea [DLP en la seguridad &amp; centro de cumplimiento](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b1096-p101">In the **Security &amp; Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security &amp; Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="b1096-p102">En el **Centro de administración de Exchange**, puede crear una directiva DLP para ayudar a proteger el contenido sólo en Exchange. Esta directiva puede usar las reglas de transporte de Exchange, por lo que tiene más opciones específicas a la gestión de correo electrónico. Para obtener más información, vea [DLP en el centro de administración de Exchange](https://go.microsoft.com/fwlink/?linkid=852311).</span><span class="sxs-lookup"><span data-stu-id="b1096-p102">In the **Exchange Admin Center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange transport rules, so it has more options specific to handling email. For more information, see [DLP in the Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="b1096-111">Las directivas de DLP creado en estos admin centros de trabajan en paralelo - en este tema se explica cómo.</span><span class="sxs-lookup"><span data-stu-id="b1096-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Páginas DLP en seguridad y el centro de cumplimiento y el centro de administración de Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a><span data-ttu-id="b1096-113">¿Cómo DLP en la seguridad &amp; centro de cumplimiento funciona con DLP y reglas de transporte en el centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="b1096-113">How DLP in the Security &amp; Compliance Center works with DLP and transport rules in the Exchange Admin Center</span></span>

<span data-ttu-id="b1096-p103">Después de crear una directiva de DLP en la seguridad &amp; centro de cumplimiento, la directiva se implementa en todas las ubicaciones que se incluyen en la directiva. Si la directiva incluye Exchange Online, la directiva sincronizado existe y se aplica en exactamente de la misma manera que una directiva de DLP creada en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b1096-p103">After you create a DLP policy in the Security &amp; Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="b1096-p104">Si ya ha creado las directivas de DLP en el centro de administración de Exchange, esas directivas seguirán funcionando codo con codo con las directivas de correo electrónico que se crea en la seguridad &amp; centro de cumplimiento. Pero tenga en cuenta que las reglas creadas en el centro de administración de Exchange tiene prioridad. Todas las reglas de transporte de Exchange se procesan en primer lugar y, a continuación, reglas de DLP desde la seguridad &amp; se procesan centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1096-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security &amp; Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange transport rules are processed first, and then the DLP rules from the Security &amp; Compliance Center are processed.</span></span>
  
<span data-ttu-id="b1096-119">Esto significa:</span><span class="sxs-lookup"><span data-stu-id="b1096-119">This means that:</span></span>
  
- <span data-ttu-id="b1096-120">Los mensajes que están bloqueados por las reglas de transporte de Exchange no obtener examinados por las reglas DLP creadas en la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1096-120">Messages that are blocked by Exchange transport rules won't get scanned by DLP rules created in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="b1096-121">Si una regla de transporte de Exchange modifica un mensaje de una manera que hace que coinciden con una directiva de DLP en la seguridad &amp; centro de cumplimiento - como la adición de usuarios externos -, a continuación, las reglas DLP detectará esto y aplicar la directiva según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b1096-121">If an Exchange transport rule modifies a message in a way that causes it to match a DLP policy in the Security &amp; Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="b1096-122">También tenga en cuenta que las reglas de transporte de Exchange que use la acción "detener el procesamiento de" no influyen en el procesamiento de DLP de reglas en la seguridad &amp; centro de cumplimiento - éstas se procesarán aún.</span><span class="sxs-lookup"><span data-stu-id="b1096-122">Also note that Exchange transport rules that use the "stop processing" action don't affect the processing of DLP rules in the Security &amp; Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="b1096-123">Sugerencias de directiva en la seguridad &amp; centro de cumplimiento de normas frente el centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="b1096-123">Policy tips in the Security &amp; Compliance Center vs. the Exchange Admin Center</span></span>

<span data-ttu-id="b1096-p105">Sugerencias de directiva pueden trabajar con directivas de DLP y creadas en el centro de administración de Exchange, o con las directivas DLP creadas en la seguridad de las reglas de flujo de correo &amp; centro de cumplimiento, pero no ambos. Esto es debido a que estas directivas se almacenan en distintas ubicaciones, pero pueden dibujar sugerencias de directiva sólo desde una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="b1096-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="b1096-p106">Si ha configurado sugerencias de directivas en el centro de administración de Exchange, las sugerencias de directiva que configurar en la seguridad &amp; centro de cumplimiento no se mostrará a los usuarios de Outlook en la web y Outlook 2013 y versiones posteriores hasta que desactivar las sugerencias en el centro de administración de Exchange. Esto garantiza que las reglas de transporte de Exchange actuales continuará funcionando hasta que se elija Cambiar a la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1096-p106">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="b1096-128">Tenga en cuenta que las notificaciones de correo electrónico mientras sugerencias de directiva pueden dibujar sólo desde una única ubicación, siempre se envían, incluso si está usando las directivas de DLP en tanto la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b1096-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  

