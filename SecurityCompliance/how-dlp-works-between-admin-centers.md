---
title: Funcionamiento de DLP entre el Centro de seguridad y cumplimiento y el Centro de administración de Exchange
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/19/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en el centro de cumplimiento de & de seguridad trabaja con DLP y reglas de flujo de correo (reglas de transporte) en el centro de administración de Exchange.
ms.openlocfilehash: efe8fb733417275a259a472db3444b8f6cad1f92
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362038"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="add70-103">Funcionamiento de DLP entre el Centro de seguridad y cumplimiento y el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="add70-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="add70-104">En Office 365, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:</span><span class="sxs-lookup"><span data-stu-id="add70-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="add70-105">En el **centro de seguridad _AMP_ cumplimiento**, puede crear una única directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive, Exchange y ahora Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="add70-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="add70-106">Siempre que sea posible, se recomienda crear una directiva de DLP aquí.</span><span class="sxs-lookup"><span data-stu-id="add70-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="add70-107">Para obtener más información, consulte [DLP en el centro de seguridad _AMP_ cumplimiento](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="add70-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="add70-108">En el **centro de administración de Exchange**, puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange.</span><span class="sxs-lookup"><span data-stu-id="add70-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="add70-109">Esta Directiva puede usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), por lo que tiene más opciones específicas para administrar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="add70-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="add70-110">Para obtener más información, consulte [DLP en el centro de administración de Exchange](https://go.microsoft.com/fwlink/?linkid=852311).</span><span class="sxs-lookup"><span data-stu-id="add70-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="add70-111">Las directivas de DLP creadas en estos centros de administración trabajan en paralelo: en este tema se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="add70-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Páginas de DLP en el centro de seguridad y cumplimiento y el centro de administración de Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="add70-113">Cómo funciona DLP en el centro de cumplimiento de & de seguridad con DLP y reglas de flujo de correo en el centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="add70-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="add70-114">Después de crear una directiva DLP en el centro de seguridad & cumplimiento, la Directiva se implementa en todas las ubicaciones incluidas en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="add70-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="add70-115">Si la Directiva incluye Exchange Online, la Directiva se sincroniza y se aplica exactamente de la misma manera que una directiva de DLP creada en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="add70-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="add70-116">Si ha creado directivas DLP en el centro de administración de Exchange, estas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="add70-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="add70-117">Pero tenga en cuenta que las reglas creadas en el centro de administración de Exchange tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="add70-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="add70-118">Todas las reglas de flujo de correo de Exchange se procesan en primer lugar y, a continuación, se procesan las reglas de DLP del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="add70-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="add70-119">Esto significa que:</span><span class="sxs-lookup"><span data-stu-id="add70-119">This means that:</span></span>
  
- <span data-ttu-id="add70-120">Los mensajes que están bloqueados por reglas de flujo de correo de Exchange no se examinarán mediante las reglas de DLP creadas en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="add70-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="add70-121">Si una regla de flujo de correo de Exchange modifica un mensaje de forma que hace coincidir una directiva DLP en el centro de seguridad & cumplimiento, como la adición de usuarios externos, las reglas de DLP lo detectarán y aplicarán la Directiva según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="add70-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="add70-122">Además, tenga en cuenta que las reglas de flujo de correo de Exchange que usan la acción "detener el procesamiento" no afectan al procesamiento de las reglas de DLP en el centro de cumplimiento de & de seguridad: se seguirán procesando.</span><span class="sxs-lookup"><span data-stu-id="add70-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="add70-123">Sugerencias de directiva en el centro de seguridad & cumplimiento frente al centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="add70-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="add70-124">Las sugerencias de Directiva pueden funcionar con las directivas de DLP y las reglas de flujo de correo creadas en el centro de administración de Exchange, o con las directivas de DLP creadas en el centro de seguridad & cumplimiento, pero no ambas.</span><span class="sxs-lookup"><span data-stu-id="add70-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="add70-125">Esto se debe a que estas directivas se almacenan en ubicaciones distintas, pero las sugerencias de directiva solo pueden dibujar desde una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="add70-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="add70-126">Si ha configurado sugerencias de directiva en el centro de administración de Exchange, las sugerencias de directiva que configure en el centro de seguridad & cumplimiento no aparecerán para los usuarios en Outlook en la web y Outlook 2013 y versiones posteriores hasta que desactive las sugerencias en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="add70-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="add70-127">Esto garantiza que las reglas actuales de flujo de correo de Exchange seguirán funcionando hasta que decida cambiar al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="add70-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="add70-128">Tenga en cuenta que, aunque las sugerencias de directiva solo pueden dibujar desde una única ubicación, siempre se envían notificaciones de correo electrónico, incluso si está usando directivas de DLP tanto en el centro de administración de seguridad & como en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="add70-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

