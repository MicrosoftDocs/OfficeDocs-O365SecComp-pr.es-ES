---
title: Defensa contra los ataques de denegación de servicio en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una descripción general de los ataques de denegación de servicio (DoS).
ms.openlocfilehash: b5a51ae332b32142d9ab993a29763b2160c3ce97
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535589"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="689a2-103">Defensa contra los ataques de denegación de servicio en Office 365</span><span class="sxs-lookup"><span data-stu-id="689a2-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="689a2-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="689a2-104">Introduction</span></span>
<span data-ttu-id="689a2-105">Microsoft ofrece una infraestructura confiable para más de 200 servicios de nube, incluidos Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype y Xbox Live que se hospedan en nuestra nube global infraestructura de centros de datos de más de 100.</span><span class="sxs-lookup"><span data-stu-id="689a2-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="689a2-p101">Como una organización global con una importante presencia en Internet y muchas propiedades destacadas de Internet que proporcionan los servicios de nube, Microsoft es un destino de gran tamaño, comunes para los intrusos y otras personas malintencionadas. La red--la capa de comunicación entre los clientes y el Cloud Microsoft--es uno de los objetivos principales de ataques malintencionados. De hecho, durante muchos años, Microsoft ha sido continuamente y persistentemente en alguna forma de cyberattack basada en la red. En casi todas las ocasiones, al menos una de las propiedades de Internet de Microsoft está experimentando algún tipo de ataque. Sin sistemas de mitigación confiable y persistente que pueden defenderse de estos ataques, servicios de nube de Microsoft sería sin conexión y no está disponible para los clientes.</span><span class="sxs-lookup"><span data-stu-id="689a2-p101">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="689a2-111">Microsoft utiliza principios de seguridad de defensa en profundidad para proteger sus redes y servicios de nube.</span><span class="sxs-lookup"><span data-stu-id="689a2-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="689a2-112">Definición y síntomas de ataques de denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="689a2-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="689a2-p102">Es una manera de atacar los servicios de red crear muchas solicitudes frente a los hosts de un servicio saturar la red y los servidores para denegar el servicio a los usuarios legítimos. Esto se conoce como un ataque de denegación de servicio (DoS). Cuando se realiza el ataque por múltiples actores, extremos o vectores, se conoce como ataque por denegación de servicio (DDoS) distribuido. Aunque pueden variar los medios, motivos y objetivos, los ataques de denegación de servicio y DDoS suelen estar formados por los esfuerzos de una persona o personas para impedir que un sitio de Internet o el servicio funciona correctamente o en absoluto, temporalmente o indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="689a2-p102">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="689a2-117">[Estados Unidos Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) define los síntomas de ataques de denegación de servicio para incluir:</span><span class="sxs-lookup"><span data-stu-id="689a2-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="689a2-118">Inusualmente lento rendimiento de la red (al abrir archivos o tengan acceso a sitios de Internet)</span><span class="sxs-lookup"><span data-stu-id="689a2-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="689a2-119">Falta de disponibilidad de un sitio Web</span><span class="sxs-lookup"><span data-stu-id="689a2-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="689a2-120">Incapacidad para tener acceso a un sitio Web</span><span class="sxs-lookup"><span data-stu-id="689a2-120">Inability to access a Web site</span></span>
- <span data-ttu-id="689a2-121">Aumento considerable en correo no deseado recibido</span><span class="sxs-lookup"><span data-stu-id="689a2-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="689a2-122">Desconexión de una conexión a Internet inalámbrica o por cable</span><span class="sxs-lookup"><span data-stu-id="689a2-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="689a2-123">Pérdida a largo plazo de acceso a la Web o los servicios de Internet</span><span class="sxs-lookup"><span data-stu-id="689a2-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="689a2-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="689a2-124">Related Topics</span></span>
- [<span data-ttu-id="689a2-125">Principios básicos de la defensa contra ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="689a2-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="689a2-126">Estrategia de defensa de denegación de servicio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="689a2-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="689a2-127">Defensa de servicios de nube de Microsoft contra los ataques de denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="689a2-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
