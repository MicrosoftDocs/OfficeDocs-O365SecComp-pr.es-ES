---
title: Office 365 principales principios de defensa contra ataques por denegación de servicio
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Modo en que Microsoft usa los principios principales de absorción, detección y mitigación en su defensa contra ataques por denegación de servicio (DoS).
ms.openlocfilehash: dfe179924f7414b0120697023f3daf7e6b6661b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216010"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="af574-103">Principios básicos de la defensa contra ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="af574-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="af574-p101">Los tres principios básicos para defenderse contra los ataques DoS basados en la red son la absorción, la detección y la mitigación. La absorción se produce antes de la detección y la detección se produce antes de la mitigación. La absorción es la mejor protección contra un ataque DoS. Si el ataque no se puede detectar, no se puede mitigar. Pero, incluso si no se puede absorber el ataque a DoS más pequeño, los servicios no se mantendrán durante el tiempo suficiente para que se detecte el ataque.</span><span class="sxs-lookup"><span data-stu-id="af574-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="af574-p102">Por supuesto, por lo general no es viable económicamente para la mayoría de las organizaciones comprar la capacidad sobrante necesaria para absorber ataques de DoS, ya que esto requiere una gran inversión en tecnología y conocimientos técnicos. Esto destaca una de las ventajas de seguridad de usar los servicios en la nube de Microsoft; la gran escala de nuestros servicios nos permite proporcionar una protección de red sólida a los clientes de la nube de manera rentable. Pero incluso en nuestra escala, sin embargo, debe haber un equilibrio entre la absorción, la detección y la mitigación. Para encontrar ese equilibrio, estudiaremos la tasa de crecimiento de un ataque para calcular cuánto es necesario absorber.</span><span class="sxs-lookup"><span data-stu-id="af574-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="af574-p103">La detección es un juego de gato y de mouse. Debe buscar constantemente las nuevas formas en las que los usuarios atacan o intentan derrotar a sus sistemas. Detect-> mitigate-> detecte-> mitigate, etc., es un estado persistente, permanente y que continuará indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="af574-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="af574-116">Defensa contra ataques DoS</span><span class="sxs-lookup"><span data-stu-id="af574-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="af574-p104">Para defenderse correctamente contra un ataque DoS, la detección temprana es esencial. Al detectar un ataque antes de que el sistema esté saturado, los defensores pueden ejecutar un plan de respuesta.</span><span class="sxs-lookup"><span data-stu-id="af574-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="af574-119">La siguiente fórmula le ayudará a aproximarse al tiempo de impacto de un ataque DoS:</span><span class="sxs-lookup"><span data-stu-id="af574-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="af574-120">**Capacidad máxima (en bytes/s)/velocidad de crecimiento (en bytes/s) = tiempo de impacto (en bytes/s)**</span><span class="sxs-lookup"><span data-stu-id="af574-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="af574-p105">Si el tiempo de detección se produce después del tiempo de impacto, es probable que el ataque de DoS se realice correctamente. Si el tiempo de detección se produce antes del tiempo de impacto, los servicios que sean atacados deben permanecer en línea y ser accesibles, si se usan estrategias de mitigación. Por lo tanto, solo se pueden hacer dos cosas para defenderse contra ataques DoS:</span><span class="sxs-lookup"><span data-stu-id="af574-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="af574-124">Aumente la capacidad para aumentar el límite máximo de capacidad (lo que, a su vez, proporciona más tiempo para detectar un ataque); o</span><span class="sxs-lookup"><span data-stu-id="af574-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="af574-125">Reducir el tiempo de detección.</span><span class="sxs-lookup"><span data-stu-id="af574-125">Decrease the time to detect.</span></span>

<span data-ttu-id="af574-p106">El aumento de la capacidad tiene un impacto fiscal directo. Microsoft recomienda que los clientes desarrollen una capacidad de absorción básica mínima, para garantizar que pueden sobrevivir a algún ataque de DoS niveles. La capacidad de absorción real variará de un cliente a un cliente, ya que cada cliente tiene sus propios umbrales para la exposición, el riesgo y la inversión financiera. En última instancia, por razones económicas, las inversiones de investigación y tiempo en formas de reducir el tiempo de detección suelen ser la defensa más rentable.</span><span class="sxs-lookup"><span data-stu-id="af574-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
