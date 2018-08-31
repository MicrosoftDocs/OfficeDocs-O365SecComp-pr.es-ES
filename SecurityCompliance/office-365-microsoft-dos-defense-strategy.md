---
title: Estrategia de defensa de denegación de servicio de Microsoft Office 365
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
description: Información general sobre la estrategia de defensa de Microsoft para tratar los ataques de denegación de servicio (DoS).
ms.openlocfilehash: f172db5080ef73402c7e9bc61720eb0f87e844ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535599"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a>Estrategia de defensa de denegación de servicio de Microsoft

Estrategia de Microsoft para la defensa contra ataques por denegación de servicio (DoS) los ataques de red es algo única debido a nuestra escala y dimensión global. Esta escala permite a Microsoft utilizar las estrategias y técnicas que pueden coinciden con pocas organizaciones (proveedores u organizaciones de atención al cliente). El componente fundamental de nuestra estrategia de denegación de servicio está aprovechando nuestra presencia global. Microsoft contrata con proveedores, proveedores de interconexión (pública y privada) y privada de Internet a las empresas en todo el mundo, lo que nos da un importante presencia en Internet (que a partir de escribir este artículo, se dobla alrededor de cada 18 meses). Tener gran presencia permite a Microsoft a absorber ataques a través de un área de superficie muy grande.

Dada nuestra naturaleza único, Microsoft utiliza los procesos de detección y mitigación que difieren de los utilizados por las grandes empresas. Nuestra estrategia se basa en una separación de detección y mitigación, así como mitigación global, distribuido a través de nuestros muchos bordes. Muchas empresas usar soluciones de terceros que se detectan y mitigan los ataques en el borde. Como ya es nuestra capacidad de borde, resultó evidente que el significado de cualquier ataque contra bordes individuales o determinados fue muy bajo. Debido a nuestro configuración única, hemos separado los componentes de detección y mitigación. Hemos implementado detección de varios niveles que nos permite detectar ataques más cerca de sus puntos de saturación que se mantiene la mitigación global en el borde. Esta estrategia garantiza que se pueden controlar varios ataques simultáneos.

Una de las defensas más eficaces y bajo costo empleadas por Microsoft contra los ataques de denegación de servicio es reducir nuestro superficie expuesta a ataques. Si lo hace, nos permite colocar el tráfico no deseado en el borde, en contraposición a analizar, procesamiento de depuración y los datos en línea.

En la interfaz con la red pública, Microsoft utiliza dispositivos de seguridad de propósito especial para servidor de seguridad, traducción de direcciones de red y funciones de filtrado de IP. También usamos enrutamiento global igual costo Multi-path (ECMP). El enrutamiento ECMP global es un marco de trabajo de la red que garantiza que hay varias rutas de acceso global ponerse en contacto con un servicio. Gracias a estas varias rutas de acceso, un ataque contra el servicio debe limitarse a la región desde la que se origina el ataque – otras regiones deben verse afectados por estos ataques, como los usuarios finales usaría otras rutas de acceso ponerse en contacto con el servicio en esas regiones. También hemos desarrollado nuestra propia DoS correlación y detección de sistema interno que usa los datos de flujo, las métricas de rendimiento y otra información. Esto es un servicio de nube de gran escala que se ejecutan en Microsoft Azure que analiza los datos recopilados desde diversos puntos en redes de Microsoft y servicios. Un equipo de respuesta a incidencias de carga de trabajo entre DoS identifica las funciones y responsabilidades entre los equipos, los criterios para las extensiones y los protocolos para contratar varios equipos y para el control de incidentes. Estas soluciones proporcionan protección basada en la red frente a ataques de denegación de servicio.

Por último, se configuran las cargas de trabajo basados en la nube con umbrales optimizados en función de su protocolo y uso de ancho de banda se necesita proteger esa carga de trabajo de forma exclusiva.
