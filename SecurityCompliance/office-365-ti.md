---
title: Respuesta y investigación de amenazas de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/09/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Descubra cómo las capacidades de inteligencia sobre amenazas de la protección contra amenazas avanzada pueden ayudarle a investigar las amenazas contra su organización, responder a malware, suplantación de identidad (phishing) y otros ataques que Office 365 ha detectado en su nombre y buscar indicadores de amenazas.
ms.openlocfilehash: 1d076ed6ca48b8423ad92d5ea71bd87167b8519a
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524004"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="1f1aa-103">Respuesta y investigación de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="1f1aa-103">Office 365 Threat Investigation and Response</span></span>

<span data-ttu-id="1f1aa-104">Las capacidades de investigación y respuesta de amenazas de Office 365 Advanced Threat Protection ayudan a los analistas de seguridad y los administradores a proteger a los usuarios de Office 365 de su organización:</span><span class="sxs-lookup"><span data-stu-id="1f1aa-104">Threat investigation and response capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="1f1aa-105">Facilitar la identificación, la supervisión y la comprensión de los ataques</span><span class="sxs-lookup"><span data-stu-id="1f1aa-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="1f1aa-106">Ayuda para solucionar rápidamente amenazas en Exchange Online, SharePoint Online, una unidad para empresas y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f1aa-106">Helping to quickly address threats in Exchange Online, SharePoint Online, One Drive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="1f1aa-107">Proporciona información y conocimientos para ayudar a evitar ataques contra su organización</span><span class="sxs-lookup"><span data-stu-id="1f1aa-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="1f1aa-108">Investigación y respuesta automatizadas para amenazas críticas basadas en correo electrónico</span><span class="sxs-lookup"><span data-stu-id="1f1aa-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1f1aa-109">La **investigación y respuestas de amenazas de office 365 (anteriormente conocido como office 365 Threat Intelligence) ahora forma parte de office 365 Advanced Threats plan 2**, que se incluye en ciertas suscripciones, como [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. Si su organización tiene una suscripción que no incluye Office 365 ATP, puede comprar ATP como complemento.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-109">**Office 365 THreat Investigation and Responses (previously known as Office 365 Threat Intelligence) is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="1f1aa-110">Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span><span class="sxs-lookup"><span data-stu-id="1f1aa-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="1f1aa-111">¿Qué está cambiando?</span><span class="sxs-lookup"><span data-stu-id="1f1aa-111">What's changing?</span></span>

<span data-ttu-id="1f1aa-112">Anteriormente, las capacidades de investigación y respuestas de respuesta de Office 365 se incluyeron en suscripciones, como Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-112">Formerly, Office 365 Threat investigation and responses capabilities were included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="1f1aa-113">Este es el caso, pero ahora estas características forman parte de Office 365 Advanced Threat Protection Plan 2 (y esto se incluye en Office 365 Enterprise E5).</span><span class="sxs-lookup"><span data-stu-id="1f1aa-113">This is still the case, and now these features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="1f1aa-114">Además, la investigación de amenazas y la capbailities de respuesta de Office 365 anteriormente estaban disponibles para su compra como un complemento para Office 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-114">In addition, Office 365 Threat investigation and response capbailities were formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="1f1aa-115">Ahora, estas funciones se incluyen en el plan 2 de la protección contra amenazas avanzada de Office 365 (que también incluye Office 365 el plan de protección contra amenazas avanzada 1).</span><span class="sxs-lookup"><span data-stu-id="1f1aa-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (which also includes Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="1f1aa-116">Para obtener más información, consulte [planes y precios de la protección contra amenazas avanzada de Office 365](https://products.office.com/exchange/advance-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="1f1aa-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="1f1aa-117">Esto es lo que significa todo esto:</span><span class="sxs-lookup"><span data-stu-id="1f1aa-117">Here's what all this means:</span></span>

- <span data-ttu-id="1f1aa-118">**Si su organización ya tiene Office 365 Enterprise E5**, ya tiene el plan 2 de la protección contra amenazas avanzada y esto incluye capacidades de investigación y respuesta de amenazas.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat investigation and response capabilities.</span></span>

- <span data-ttu-id="1f1aa-119">**Si su organización tenía anteriormente inteligencia sobre amenazas de office 365 (pero no la protección contra amenazas avanzada de office 365) como complemento** a otra suscripción de Office 365, tendrá Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="1f1aa-120">Esto incluye las capacidades del plan 1 de protección contra amenazas avanzada y la investigación de amenazas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-120">This includes Advanced Threat Protection Plan 1 and Threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="1f1aa-121">**Si su organización tenía previamente la protección contra amenazas avanzada de office 365 (pero no la inteligencia de amenazas de office 365) como un complemento** para otra suscripción de Office 365, tendrá Office 365 Advanced Threat Protection Plan 1.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-121">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="1f1aa-122">Esto incluye la protección contra amenazas avanzada (pero no las capacidades de investigaiton y respuesta de amenazas).</span><span class="sxs-lookup"><span data-stu-id="1f1aa-122">This includes Advanced Threat Protection (but not Threat investigaiton and response capabilities).</span></span>

<span data-ttu-id="1f1aa-123">Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="1f1aa-123">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigaiton-and-response-capabilities"></a><span data-ttu-id="1f1aa-124">Introducción a las capacidades de investigaiton y respuesta de amenazas</span><span class="sxs-lookup"><span data-stu-id="1f1aa-124">Get started with threat investigaiton and response capabilities</span></span>

<span data-ttu-id="1f1aa-125">Use los siguientes recursos para obtener más información acerca de las capacidades de investigación y respuesta de amenazas en Office 365 y cómo puede usarla para mantener a los usuarios de la organización más seguros.</span><span class="sxs-lookup"><span data-stu-id="1f1aa-125">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="1f1aa-126">[Introducción a la investigación y respuesta de amenazas](get-started-with-ti.md) (incluye información sobre las funciones necesarias)</span><span class="sxs-lookup"><span data-stu-id="1f1aa-126">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="1f1aa-127">Obtenga información sobre los rastreadores de amenazas: nuevos y dignos</span><span class="sxs-lookup"><span data-stu-id="1f1aa-127">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="1f1aa-128">Buscar e investigar correo electrónico malintencionado que se entregó</span><span class="sxs-lookup"><span data-stu-id="1f1aa-128">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="1f1aa-129">Usar el simulador de ataques</span><span class="sxs-lookup"><span data-stu-id="1f1aa-129">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="1f1aa-130">Integración de la investigación de amenazas y respuesta con la protección contra amenazas avanzada de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="1f1aa-130">Integrate Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="1f1aa-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1f1aa-131">Related topics</span></span>

[<span data-ttu-id="1f1aa-132">Protección contra amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="1f1aa-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="1f1aa-133">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="1f1aa-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1f1aa-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1f1aa-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 