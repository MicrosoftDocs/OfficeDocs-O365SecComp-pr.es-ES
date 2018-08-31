---
title: Principios básicos de Office 365 de defensa frente a ataques de denegación de servicio
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
description: Cómo Microsoft utiliza los principios básicos de absorción, detección y mitigación en su defensa contra los ataques de denegación de servicio (DoS).
ms.openlocfilehash: 8355a7897c788241092363a23e198423e81c587a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535591"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>Principios básicos de la defensa contra ataques por denegación de servicio
Los tres principales principios cuando defensa contra los ataques de denegación de servicio basados en red es absorción, detección y mitigación. Absorción sucede antes de detección y detección lleva a cabo antes de mitigación. Absorción es la mejor defensa contra los ataques de denegación de servicio. Si no se puede detectar el ataque, no se pueden mitigar. Pero si no se pueden absorber incluso el ataque DoS más pequeño, a continuación, no se van a servicios sobrevivir tiempo suficiente para que el ataque se detectó.

Por supuesto, por lo general no resulta económica viable para la mayoría de las organizaciones comprar el exceso de capacidad necesario para absorber los ataques de denegación de servicio, ya que exige una considerable inversión en tecnología y conocimientos técnicos. Esto destaca una de las ventajas de seguridad del uso de servicios de nube de Microsoft; la escala ingente de nuestros servicios nos permite proporcionar protección de la red segura a nuestros clientes en la nube de manera rentable. Pero incluso en nuestra escala, sin embargo, debe haber un equilibrio entre la absorción, detección y mitigación. Para encontrar ese equilibrio, nos estudiar la tasa de crecimiento de un ataque para calcular cuánto necesitamos absorber.

Detección es un juego de ratón y el gato. Debe buscar constantemente para las personas de formas nuevas se atacar se o intentar para defenderse de los sistemas. Detectar -> mitigar -> detectar -> mitigar, etc., es un estado perpetuo, persistente que seguirá indefinidamente.

## <a name="defending-against-dos-attacks"></a>Defensa contra los ataques de denegación de servicio
Para defenderse correctamente un ataque DoS, detección temprana es esencial. Mediante la detección de un ataque antes de que el sistema está sobrecargado, defensores pueden ejecutar un plan de respuesta.

La fórmula siguiente le ayudará a aproximar el tiempo a un impacto de un ataque de denegación de servicio:

   **Capacidad máxima / (tasa de crecimiento de capacidad máxima X) = tiempo de impacto**

Si el tiempo de detección se produce después de la hora de impacto, a continuación, es probable que el ataque de denegación de servicio se completará correctamente. Si el tiempo de detección se produce antes de impacto de tiempo, los servicios de sufrir un ataque deben permanecer en línea y accesibles, si se usan las estrategias de mitigación. Por lo tanto, hay sólo dos cosas que pueden hacer para defenderse de los ataques de denegación de servicio:
- Aumentar la capacidad para elevar el límite máximo de capacidad máxima (que a su vez proporciona más tiempo para detectar un ataque); o
- Reducir el tiempo para detectar.

Aumento de la capacidad tiene una repercusión directa fiscal. Microsoft recomienda que los clientes desarrollan absorción básica al menos capacidad, para asegurarse de que pueden sobrevivir cierto nivel de ataque de denegación de servicio. La capacidad de absorción real varían de un cliente a otro, como cada cliente tiene sus propios umbrales de exposición, los riesgos y gastos financieros. En última instancia, las inversiones de investigación y tiempo en formas de reducir el tiempo de detección por motivos económicos, son normalmente la defensa más rentable.
