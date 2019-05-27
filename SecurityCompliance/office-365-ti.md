---
title: Investigación y respuesta de amenazas de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Descubra cómo las capacidades de inteligencia sobre amenazas de Office 365 Advanced Threat Protection pueden ayudarle a investigar amenazas contra su organización, responder a malware, phishing y otros ataques que Office 365 ha detectado en su nombre y buscar amenazas indicadores.
ms.openlocfilehash: 3a1ccc3d3e37b9b1433e8e339709d09ba56970b0
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408365"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="f98a0-103">Investigación y respuesta de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="f98a0-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="f98a0-104">Las capacidades de investigación y respuesta de amenazas de [Office 365 Advanced Threat Protection](office-365-atp.md) ayudan a los analistas de seguridad y los administradores a proteger a los usuarios de Office 365 de su organización:</span><span class="sxs-lookup"><span data-stu-id="f98a0-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="f98a0-105">Facilitar la identificación, la supervisión y la comprensión de los ataques</span><span class="sxs-lookup"><span data-stu-id="f98a0-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="f98a0-106">Ayuda para solucionar rápidamente amenazas en Exchange Online, SharePoint Online, OneDrive para la empresa y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f98a0-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="f98a0-107">Proporciona información y conocimientos para ayudar a evitar ataques contra su organización</span><span class="sxs-lookup"><span data-stu-id="f98a0-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="f98a0-108">Investigación y respuesta automatizadas para amenazas críticas basadas en correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f98a0-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="f98a0-109">La protección contra amenazas **avanzada de office 365 y la investigación y respuesta de amenazas (anteriormente conocida como office 365 Threat Intelligence) ahora son office 365 Advanced Threat Protection Plan 2**, junto con otras capacidades de protección contra amenazas incluidas en Algunas suscripciones, como [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education A5, etc. Si su organización tiene una suscripción que no incluye Office 365 ATP, puede comprar ATP como complemento.</span><span class="sxs-lookup"><span data-stu-id="f98a0-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (previously known as Office 365 Threat Intelligence) are now Office 365 Advanced Threat Protection Plan 2**, along with additional threat protection capabilities included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="f98a0-110">Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span><span class="sxs-lookup"><span data-stu-id="f98a0-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="f98a0-111">¿Qué está cambiando?</span><span class="sxs-lookup"><span data-stu-id="f98a0-111">What's changing?</span></span>

<span data-ttu-id="f98a0-112">Anteriormente, la inteligencia sobre amenazas de Office 365 se incluyó en las suscripciones, como Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="f98a0-112">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="f98a0-113">Este es el caso, ya que la investigación de amenazas y las capacidades de respuesta ahora forman parte del plan 2 de la protección contra amenazas avanzada de Office 365 (y se incluye en Office 365 Enterprise E5).</span><span class="sxs-lookup"><span data-stu-id="f98a0-113">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="f98a0-114">Además, la inteligencia sobre amenazas de Office 365 anteriormente estuvo disponible para la compra como un complemento para los clientes de Office 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="f98a0-114">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="f98a0-115">Ahora, estas funciones se incluyen en Office 365 Advanced Threat Protection Plan 2 (junto con todas las características de Office 365 el plan de protección contra amenazas avanzada 1).</span><span class="sxs-lookup"><span data-stu-id="f98a0-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="f98a0-116">Para obtener más información, consulte [planes y precios de la protección contra amenazas avanzada de Office 365](https://products.office.com/exchange/advance-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="f98a0-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="f98a0-117">Esto es lo que significa todo esto:</span><span class="sxs-lookup"><span data-stu-id="f98a0-117">Here's what all this means:</span></span>

- <span data-ttu-id="f98a0-118">**Si su organización ya tiene Office 365 Enterprise E5**, ya tiene el plan 2 de la protección contra amenazas avanzada y esto incluye capacidades de investigación y respuesta de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f98a0-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="f98a0-119">**Si su organización tenía previamente la inteligencia sobre amenazas de office 365 (pero no la protección contra amenazas avanzada de office 365) como un complemento** a otra suscripción de Office 365, ahora tendrá Office 365 Advanced Threat Protection Plan 2 y esto incluye capacidades de investigación y respuesta de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f98a0-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="f98a0-120">**Si su organización tenía previamente la protección contra amenazas avanzada de office 365 (pero no la inteligencia de amenazas de office 365) como un complemento** a otra suscripción de Office 365, ahora tendrá Office 365 Advanced Threat Protection Plan 1.</span><span class="sxs-lookup"><span data-stu-id="f98a0-120">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="f98a0-121">Esto incluye el plan 1 de la protección contra amenazas avanzada de Office 365 (pero no la investigación de amenazas y las capacidades de respuesta).</span><span class="sxs-lookup"><span data-stu-id="f98a0-121">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="f98a0-122">Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="f98a0-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="f98a0-123">Introducción a las capacidades de investigación y respuesta de amenazas</span><span class="sxs-lookup"><span data-stu-id="f98a0-123">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="f98a0-124">Use los siguientes recursos para obtener más información acerca de las capacidades de investigación y respuesta de amenazas en Office 365 y cómo puede usarla para mantener a los usuarios de la organización más seguros.</span><span class="sxs-lookup"><span data-stu-id="f98a0-124">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="f98a0-125">[Introducción a la investigación y respuesta de amenazas](get-started-with-ti.md) (incluye información sobre las funciones necesarias)</span><span class="sxs-lookup"><span data-stu-id="f98a0-125">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="f98a0-126">Obtenga información sobre los rastreadores de amenazas: nuevos y dignos</span><span class="sxs-lookup"><span data-stu-id="f98a0-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="f98a0-127">Ahorrar tiempo y esfuerzo con capacidades automatizadas de investigación y respuesta (AIR)</span><span class="sxs-lookup"><span data-stu-id="f98a0-127">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="f98a0-128">Usar el explorador de amenazas (o detecciones en tiempo real) para identificar y investigar el contenido malintencionado en el correo electrónico y los archivos</span><span class="sxs-lookup"><span data-stu-id="f98a0-128">Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files</span></span>](threat-explorer.md)
    
- [<span data-ttu-id="f98a0-129">Buscar e investigar el correo electrónico malintencionado que se ha entregado</span><span class="sxs-lookup"><span data-stu-id="f98a0-129">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="f98a0-130">Usar el simulador de ataques para simular ataques y aumentar el conocimiento de los usuarios</span><span class="sxs-lookup"><span data-stu-id="f98a0-130">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="f98a0-131">Integración de capacidades de investigación y respuesta de amenazas con la protección contra amenazas avanzada de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="f98a0-131">Integrate Threat Investigation and Response capabilities with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="f98a0-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f98a0-132">Related topics</span></span>

[<span data-ttu-id="f98a0-133">Vistas del explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="f98a0-133">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="f98a0-134">Protección contra amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="f98a0-134">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="f98a0-135">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="f98a0-135">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="f98a0-136">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f98a0-136">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
