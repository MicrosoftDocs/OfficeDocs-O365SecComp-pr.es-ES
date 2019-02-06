---
title: Principios básicos de Office 365 de defensa frente a ataques de denegación de servicio
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Cómo Microsoft utiliza los principios básicos de absorción, detección y mitigación en su defensa contra los ataques de denegación de servicio (DoS).
ms.openlocfilehash: e313d5514e9bc493db78bebffca24a0fae4cbca7
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741103"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="c40e3-103">Principios básicos de la defensa contra ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="c40e3-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="c40e3-p101">Los tres principales principios cuando defensa contra los ataques de denegación de servicio basados en red es absorción, detección y mitigación. Absorción sucede antes de detección y detección lleva a cabo antes de mitigación. Absorción es la mejor defensa contra los ataques de denegación de servicio. Si no se puede detectar el ataque, no se pueden mitigar. Pero si no se pueden absorber incluso el ataque DoS más pequeño, a continuación, no se van a servicios sobrevivir tiempo suficiente para que el ataque se detectó.</span><span class="sxs-lookup"><span data-stu-id="c40e3-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="c40e3-p102">Por supuesto, por lo general no resulta económica viable para la mayoría de las organizaciones comprar el exceso de capacidad necesario para absorber los ataques de denegación de servicio, ya que exige una considerable inversión en tecnología y conocimientos técnicos. Esto destaca una de las ventajas de seguridad del uso de servicios de nube de Microsoft; la escala ingente de nuestros servicios nos permite proporcionar protección de la red segura a nuestros clientes en la nube de manera rentable. Pero incluso en nuestra escala, sin embargo, debe haber un equilibrio entre la absorción, detección y mitigación. Para encontrar ese equilibrio, nos estudiar la tasa de crecimiento de un ataque para calcular cuánto necesitamos absorber.</span><span class="sxs-lookup"><span data-stu-id="c40e3-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="c40e3-p103">Detección es un juego de ratón y el gato. Debe buscar constantemente para las personas de formas nuevas se atacar se o intentar para defenderse de los sistemas. Detectar - > mitigar - detectar > - > mitigar, etc., es un estado perpetuo, persistente que seguirá indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="c40e3-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="c40e3-116">Defensa contra los ataques de denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="c40e3-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="c40e3-p104">Para defenderse correctamente un ataque DoS, detección temprana es esencial. Mediante la detección de un ataque antes de que el sistema está sobrecargado, defensores pueden ejecutar un plan de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c40e3-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="c40e3-119">La fórmula siguiente le ayudará a aproximar el tiempo a un impacto de un ataque de denegación de servicio:</span><span class="sxs-lookup"><span data-stu-id="c40e3-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="c40e3-120">**Capacidad máxima (en bytes/seg.) / tasa de crecimiento (en bytes/seg.) = tiempo de impacto (en bytes/seg.)**</span><span class="sxs-lookup"><span data-stu-id="c40e3-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="c40e3-p105">Si el tiempo de detección se produce después de la hora de impacto, a continuación, es probable que el ataque de denegación de servicio se completará correctamente. Si el tiempo de detección se produce antes de impacto de tiempo, los servicios de sufrir un ataque deben permanecer en línea y accesibles, si se usan las estrategias de mitigación. Por lo tanto, hay sólo dos cosas que pueden hacer para defenderse de los ataques de denegación de servicio:</span><span class="sxs-lookup"><span data-stu-id="c40e3-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="c40e3-124">Aumentar la capacidad para elevar el límite máximo de capacidad máxima (que a su vez proporciona más tiempo para detectar un ataque); o</span><span class="sxs-lookup"><span data-stu-id="c40e3-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="c40e3-125">Reducir el tiempo para detectar.</span><span class="sxs-lookup"><span data-stu-id="c40e3-125">Decrease the time to detect.</span></span>

<span data-ttu-id="c40e3-p106">Aumento de la capacidad tiene una repercusión directa fiscal. Microsoft recomienda que los clientes desarrollan absorción básica al menos capacidad, para asegurarse de que pueden sobrevivir cierto nivel de ataque de denegación de servicio. La capacidad de absorción real varían de un cliente a otro, como cada cliente tiene sus propios umbrales de exposición, los riesgos y gastos financieros. En última instancia, las inversiones de investigación y tiempo en formas de reducir el tiempo de detección por motivos económicos, son normalmente la defensa más rentable.</span><span class="sxs-lookup"><span data-stu-id="c40e3-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
