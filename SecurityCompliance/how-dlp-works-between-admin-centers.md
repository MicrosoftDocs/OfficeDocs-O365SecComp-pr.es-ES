---
title: Cómo funciona DLP entre el centro de seguridad & cumplimiento y el centro de administración de Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en el centro de cumplimiento de & de seguridad trabaja con DLP y reglas de flujo de correo (reglas de transporte) en el centro de administración de Exchange.
ms.openlocfilehash: c20cf5d4e7b83a726b104a57b89f2d8f765d7f16
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341491"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="879ab-103">Cómo funciona DLP entre el centro de seguridad & cumplimiento y el centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="879ab-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="879ab-104">En Office 365, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:</span><span class="sxs-lookup"><span data-stu-id="879ab-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="879ab-p101">En el **centro de seguridad _AMP_ cumplimiento**, puede crear una única directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive y Exchange. Siempre que sea posible, se recomienda crear una directiva de DLP aquí. Para obtener más información, consulte [DLP en el centro de seguridad _AMP_ cumplimiento](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="879ab-p101">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="879ab-p102">En el **centro de administración de Exchange**, puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange. Esta Directiva puede usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), por lo que tiene más opciones específicas para administrar el correo electrónico. Para obtener más información, consulte [DLP en el centro de administración de Exchange](https://go.microsoft.com/fwlink/?linkid=852311).</span><span class="sxs-lookup"><span data-stu-id="879ab-p102">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email. For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="879ab-111">Las directivas de DLP creadas en estos centros de administración trabajan en paralelo: en este tema se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="879ab-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Páginas de DLP en el centro de seguridad y cumplimiento y el centro de administración de Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="879ab-113">Cómo funciona DLP en el centro de cumplimiento de & de seguridad con DLP y reglas de flujo de correo en el centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="879ab-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="879ab-p103">Después de crear una directiva DLP en el centro de seguridad & cumplimiento, la Directiva se implementa en todas las ubicaciones incluidas en la Directiva. Si la Directiva incluye Exchange Online, la Directiva se sincroniza y se aplica exactamente de la misma manera que una directiva de DLP creada en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="879ab-p103">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="879ab-p104">Si ha creado directivas DLP en el centro de administración de Exchange, estas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el centro de seguridad & cumplimiento. Pero tenga en cuenta que las reglas creadas en el centro de administración de Exchange tienen prioridad. Todas las reglas de flujo de correo de Exchange se procesan en primer lugar y, a continuación, se procesan las reglas de DLP del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="879ab-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="879ab-119">Esto significa que:</span><span class="sxs-lookup"><span data-stu-id="879ab-119">This means that:</span></span>
  
- <span data-ttu-id="879ab-120">Los mensajes que están bloqueados por reglas de flujo de correo de Exchange no se examinarán mediante las reglas de DLP creadas en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="879ab-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="879ab-121">Si una regla de flujo de correo de Exchange modifica un mensaje de forma que hace coincidir una directiva DLP en el centro de seguridad & cumplimiento, como la adición de usuarios externos, las reglas de DLP lo detectarán y aplicarán la Directiva según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="879ab-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="879ab-122">Además, tenga en cuenta que las reglas de flujo de correo de Exchange que usan la acción "detener el procesamiento" no afectan al procesamiento de las reglas de DLP en el centro de cumplimiento de & de seguridad: se seguirán procesando.</span><span class="sxs-lookup"><span data-stu-id="879ab-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="879ab-123">Sugerencias de directiva en el centro de seguridad & cumplimiento frente al centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="879ab-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="879ab-p105">Las sugerencias de Directiva pueden funcionar con las directivas de DLP y las reglas de flujo de correo creadas en el centro de administración de Exchange, o con las directivas de DLP creadas en el centro de seguridad & cumplimiento, pero no ambas. Esto se debe a que estas directivas se almacenan en ubicaciones distintas, pero las sugerencias de directiva solo pueden dibujar desde una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="879ab-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="879ab-p106">Si ha configurado sugerencias de directiva en el centro de administración de Exchange, las sugerencias de directiva que configure en el centro de seguridad & cumplimiento no aparecerán para los usuarios en Outlook en la web y Outlook 2013 y versiones posteriores hasta que desactive las sugerencias en el centro de administración de Exchange. Esto garantiza que las reglas actuales de flujo de correo de Exchange seguirán funcionando hasta que decida cambiar al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="879ab-p106">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center. This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="879ab-128">Tenga en cuenta que, aunque las sugerencias de directiva solo pueden dibujar desde una única ubicación, siempre se envían notificaciones de correo electrónico, incluso si está usando directivas de DLP tanto en el centro de administración de seguridad & como en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="879ab-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

