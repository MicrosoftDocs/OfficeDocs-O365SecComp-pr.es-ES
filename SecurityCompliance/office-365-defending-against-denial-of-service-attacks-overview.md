---
title: Defensa contra ataques por denegación de servicio en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Información general sobre los ataques de denegación de servicio (DoS).
ms.openlocfilehash: 246704bff18c07d9b76281ae3c7071cd0d747630
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220510"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="18940-103">Defensa contra ataques por denegación de servicio en Office 365</span><span class="sxs-lookup"><span data-stu-id="18940-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="18940-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="18940-104">Introduction</span></span>
<span data-ttu-id="18940-105">Microsoft ofrece una infraestructura de confianza para más de 200 servicios en la nube, incluidos Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype y Xbox Live hospedados en nuestra nube global infraestructura de más de 100 centros de recursos.</span><span class="sxs-lookup"><span data-stu-id="18940-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="18940-p101">Como organización global con una presencia importante en Internet y muchas propiedades de Internet destacadas que proporcionan servicios en la nube, Microsoft es un objetivo común y amplio para los hackers y otras personas malintencionadas. La red (la capa de comunicación entre clientes y la nube de Microsoft) es uno de los principales objetivos de ataques malintencionados. De hecho, durante muchos años, Microsoft ha estado continuamente y de manera persistente bajo alguna forma de ciberataque basada en la red. En casi todas las ocasiones, al menos una de las propiedades de Internet de Microsoft experimenta algún tipo de ataque. Sin sistemas de mitigación confiable y persistente que puedan defenderse contra estos ataques, los servicios en la nube de Microsoft estarán sin conexión y no estarán disponibles para los clientes.</span><span class="sxs-lookup"><span data-stu-id="18940-p101">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="18940-111">Microsoft usa los principios de seguridad de defensa en profundidad para proteger sus redes y servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="18940-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="18940-112">Definición y síntomas de ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="18940-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="18940-p102">Una forma de atacar los servicios de red es crear muchas solicitudes en los hosts de un servicio para saturar la red y los servidores para denegar el servicio a los usuarios legítimos. Esto se conoce como un ataque de denegación de servicio (DoS). Cuando varios actores, extremos o vectores realizan el ataque, se hace referencia a él como un ataque de denegación de servicio (DDoS) distribuido. Aunque los medios, motivos y objetivos varían, los ataques entre DoS y DDoS suelen estar formados por los esfuerzos de una persona o personas para evitar que un sitio o servicio de Internet funcione correctamente o en absoluto, ya sea de manera temporal o indefinida.</span><span class="sxs-lookup"><span data-stu-id="18940-p102">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="18940-117">El equipo de [preparación de emergencia para equipos de Estados Unidos](https://www.us-cert.gov/) (US-CERT) define los síntomas de ataques dos para incluir:</span><span class="sxs-lookup"><span data-stu-id="18940-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="18940-118">Rendimiento de red inusualmente lento (al abrir archivos o acceder a sitios de Internet)</span><span class="sxs-lookup"><span data-stu-id="18940-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="18940-119">No disponibilidad de un sitio web</span><span class="sxs-lookup"><span data-stu-id="18940-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="18940-120">Incapacidad para obtener acceso a un sitio web</span><span class="sxs-lookup"><span data-stu-id="18940-120">Inability to access a Web site</span></span>
- <span data-ttu-id="18940-121">Aumento espectacular en el correo no deseado recibido</span><span class="sxs-lookup"><span data-stu-id="18940-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="18940-122">Desconexión de una conexión a Internet inalámbrica o cableada</span><span class="sxs-lookup"><span data-stu-id="18940-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="18940-123">Pérdida a largo plazo de acceso a la web o a cualquier servicio de Internet</span><span class="sxs-lookup"><span data-stu-id="18940-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="18940-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="18940-124">Related Topics</span></span>
- [<span data-ttu-id="18940-125">Principios básicos de la defensa contra ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="18940-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="18940-126">Estrategia de la defensa de denegación de servicio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="18940-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="18940-127">Defensa de los servicios en la nube de Microsoft contra ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="18940-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
