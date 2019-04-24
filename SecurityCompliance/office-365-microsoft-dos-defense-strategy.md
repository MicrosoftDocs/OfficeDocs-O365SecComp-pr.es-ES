---
title: Office 365 estrategia de defensa para DoS de Microsoft
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
description: Información general sobre la estrategia de defensa de Microsoft para tratar con ataques por denegación de servicio (DoS).
ms.openlocfilehash: acc0c74ae9ed434d4718d7b8b3bd9429b3245d46
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262552"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a>Estrategia de la defensa de denegación de servicio de Microsoft

La estrategia de Microsoft para defenderse contra los ataques de denegación de servicio (DoS) basados en red es un tanto única debido a nuestra escalabilidad y a su espacio global. Esta escala permite que Microsoft use estrategias y técnicas que puedan coincidir con pocas organizaciones (proveedores o organizaciones del cliente). La piedra angular de nuestra estrategia de DoS está aprovechando nuestra presencia global. Microsoft se compromete con los proveedores de Internet, los proveedores de emparejamiento (públicos y privados) y las corporaciones privadas de todo el mundo, lo que nos da una importante presencia en Internet (que, en esta redacción, se duplica cada 18 meses). La presencia de una gran cantidad de presencia permite a Microsoft absorber ataques en una superficie muy grande.

Dada nuestra exclusiva naturaleza, Microsoft usa procesos de detección y mitigación que difieren de los usados por grandes empresas. Nuestra estrategia se basa en una separación de detección y mitigación, así como en la mitigación global y distribuida a través de muchos límites. Muchas empresas usan soluciones de terceros que detectan y mitigan los ataques en el perímetro. A medida que nuestra capacidad de vanguardia aumentó, resultó evidente que la importancia de cualquier ataque contra contornos individuales o concretos era muy bajo. Debido a nuestra configuración única, hemos separado los componentes de detección y mitigación. Hemos implementado la detección en varios niveles que nos permite detectar ataques más cercanos a sus puntos de saturación, a la vez que se mantienen atenuaciones globales en el perímetro. Esta estrategia garantiza que se puedan controlar varios ataques simultáneos.

Una de las defensas más eficaces y de bajo costo utilizadas por Microsoft contra ataques DoS es reducir la superficie de ataque. Al hacerlo, nos permite eliminar el tráfico no deseado en el perímetro, en lugar de analizar, procesar y depurar los datos en línea.

En la interfaz con la red pública, Microsoft usa dispositivos de seguridad de propósito especial para el firewall, la traducción de direcciones de red y las funciones de filtrado IP. También usamos el enrutamiento global de igualdad de costos (ECMP). El enrutamiento de ECMP global es un marco de red que garantiza que hay varias rutas globales para llegar a un servicio. Gracias a estas varias rutas de acceso, un ataque contra el servicio debe limitarse a la región desde la que se origina el ataque; otras regiones no deberían verse afectadas por este ataque, ya que los usuarios finales usarían otras rutas para llegar al servicio en esas regiones. También hemos desarrollado nuestro propio sistema interno de correlación y detección de DoS que usa datos de flujo, métricas de rendimiento e información adicional. Se trata de un servicio en la nube de hiperescala que se ejecuta en Microsoft Azure y que analiza los datos recopilados de varios puntos en las redes y servicios de Microsoft. Un equipo de respuesta ante incidentes entre cargas de trabajo en DoS identifica los roles y las responsabilidades en Teams, los criterios de escalabilidad y los protocolos para la contratación de varios equipos y el tratamiento de incidentes. Estas soluciones proporcionan protección basada en red contra ataques DoS.

Por último, las cargas de trabajo basadas en la nube se configuran con umbrales optimizados basados en su Protocolo y el uso de ancho de banda debe proteger la carga de trabajo de manera exclusiva.
