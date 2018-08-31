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
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a>Defensa contra los ataques de denegación de servicio en Office 365

## <a name="introduction"></a>Introducción
Microsoft ofrece una infraestructura confiable para más de 200 servicios de nube, incluidos Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype y Xbox Live que se hospedan en nuestra nube global infraestructura de centros de datos de más de 100.

Como una organización global con una importante presencia en Internet y muchas propiedades destacadas de Internet que proporcionan los servicios de nube, Microsoft es un destino de gran tamaño, comunes para los intrusos y otras personas malintencionadas. La red--la capa de comunicación entre los clientes y el Cloud Microsoft--es uno de los objetivos principales de ataques malintencionados. De hecho, durante muchos años, Microsoft ha sido continuamente y persistentemente en alguna forma de cyberattack basada en la red. En casi todas las ocasiones, al menos una de las propiedades de Internet de Microsoft está experimentando algún tipo de ataque. Sin sistemas de mitigación confiable y persistente que pueden defenderse de estos ataques, servicios de nube de Microsoft sería sin conexión y no está disponible para los clientes.

Microsoft utiliza principios de seguridad de defensa en profundidad para proteger sus redes y servicios de nube. 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>Definición y síntomas de ataques de denegación de servicio
Es una manera de atacar los servicios de red crear muchas solicitudes frente a los hosts de un servicio saturar la red y los servidores para denegar el servicio a los usuarios legítimos. Esto se conoce como un ataque de denegación de servicio (DoS). Cuando se realiza el ataque por múltiples actores, extremos o vectores, se conoce como ataque por denegación de servicio (DDoS) distribuido. Aunque pueden variar los medios, motivos y objetivos, los ataques de denegación de servicio y DDoS suelen estar formados por los esfuerzos de una persona o personas para impedir que un sitio de Internet o el servicio funciona correctamente o en absoluto, temporalmente o indefinidamente.

[Estados Unidos Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) define los síntomas de ataques de denegación de servicio para incluir:
- Inusualmente lento rendimiento de la red (al abrir archivos o tengan acceso a sitios de Internet)
- Falta de disponibilidad de un sitio Web
- Incapacidad para tener acceso a un sitio Web
- Aumento considerable en correo no deseado recibido
- Desconexión de una conexión a Internet inalámbrica o por cable
- Pérdida a largo plazo de acceso a la Web o los servicios de Internet

## <a name="related-topics"></a>Temas relacionados
- [Principios básicos de la defensa contra ataques por denegación de servicio](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Estrategia de defensa de denegación de servicio de Microsoft](office-365-microsoft-dos-defense-strategy.md)
- [Defensa de servicios de nube de Microsoft contra los ataques de denegación de servicio](office-365-defending-cloud-services-against-dos-attacks.md)
