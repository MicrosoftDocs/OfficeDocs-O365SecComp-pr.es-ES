---
title: Defenderse contra ataques por denegación de servicio en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Información general sobre los ataques de denegación de servicio (DoS).
ms.openlocfilehash: df3ab233271f02b91f16f8954972a61000bf4d3b
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622480"
---
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a>Defenderse contra ataques por denegación de servicio en Office 365

## <a name="introduction"></a>Introducción

Microsoft ofrece una infraestructura de confianza para más de 200 servicios en la nube hospedados en una infraestructura de nube global de más de 100 centros de recursos. Entre ellos se incluyen:

- Microsoft Azure
- Microsoft Bing
- Microsoft Dynamics 365
- Microsoft Office 365
- Microsoft OneDrive
- Skype
- Xbox Live

Como organización global con una presencia importante en Internet y muchas propiedades de Internet destacadas que proporcionan servicios en la nube, Microsoft es un objetivo común y amplio para los hackers y otras personas malintencionadas. La capa de comunicación de red entre los clientes y la nube de Microsoft es uno de los principales objetivos de ataques malintencionados. De hecho, Microsoft se realiza de forma continua y persistente bajo algún tipo de ataque a través de la red. En línea con esto, Microsoft usa principios de seguridad de defensa en profundidad para proteger sus redes y servicios en la nube. Sin sistemas de mitigación confiable y persistente que defienden contra estos ataques, los servicios en la nube de Microsoft estarán sin conexión y no estarán disponibles para los clientes.

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>Definición y síntomas de ataques por denegación de servicio

Una forma de atacar los servicios de red es crear muchas solicitudes a los hosts de servicio para saturar la red y los servidores para denegar el servicio a los usuarios legítimos. Esto se conoce como un ataque de denegación de servicio (DoS). Cuando varios actores, extremos o vectores realizan el ataque, se hace referencia a él como un ataque de denegación de servicio (DDoS) distribuido. Aunque los medios, motivos y objetivos varían, los ataques entre DoS y DDoS suelen estar formados por los esfuerzos para evitar que un sitio o servicio de Internet funcione correctamente o en su totalidad, ya sea de forma temporal o indefinida.

El equipo de [preparación de emergencia para equipos de Estados Unidos](https://www.us-cert.gov/) (US-CERT) define los síntomas de ataques dos para incluir:

- Rendimiento de red inusualmente lento (al abrir archivos o acceder a sitios de Internet)
- No disponibilidad de un sitio web
- Incapacidad para obtener acceso a un sitio web
- Aumento espectacular en el correo no deseado recibido
- Desconexión de una conexión a Internet inalámbrica o cableada
- Pérdida a largo plazo de acceso a la web o a cualquier servicio de Internet

## <a name="related-topics"></a>Temas relacionados

- [Principios básicos de la defensa contra ataques por denegación de servicio](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Estrategia de la defensa de denegación de servicio de Microsoft](office-365-microsoft-dos-defense-strategy.md)
- [Defensa de los servicios en la nube de Microsoft contra ataques por denegación de servicio](office-365-defending-cloud-services-against-dos-attacks.md)
