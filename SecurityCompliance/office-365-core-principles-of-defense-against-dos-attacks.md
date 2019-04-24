---
title: Office 365 principales principios de defensa contra ataques por denegación de servicio
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
description: Modo en que Microsoft usa los principios principales de absorción, detección y mitigación en su defensa contra ataques por denegación de servicio (DoS).
ms.openlocfilehash: bbfffeaeb66fc83e80c274be9550a95dc8bd3f0d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262932"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>Principios básicos de la defensa contra ataques por denegación de servicio

Los tres principios básicos para defenderse contra los ataques DoS basados en la red son la absorción, la detección y la mitigación.
La absorción se produce antes de la detección y la detección se produce antes de la mitigación. La absorción es la mejor protección contra un ataque DoS. Si el ataque no se puede detectar, no se puede mitigar. Pero, incluso si no se puede absorber el ataque a DoS más pequeño, los servicios no se mantendrán durante el tiempo suficiente para que se detecte el ataque.

Por supuesto, por lo general no es viable económicamente para la mayoría de las organizaciones comprar la capacidad sobrante necesaria para absorber ataques de DoS, ya que esto requiere una gran inversión en tecnología y conocimientos técnicos. Esto destaca una de las ventajas de seguridad de usar los servicios en la nube de Microsoft; la gran escala de nuestros servicios nos permite proporcionar una protección de red sólida a los clientes de la nube de manera rentable. Pero incluso en nuestra escala, sin embargo, debe haber un equilibrio entre la absorción, la detección y la mitigación. Para encontrar ese equilibrio, estudiaremos la tasa de crecimiento de un ataque para calcular cuánto es necesario absorber.

La detección es un juego de gato y de mouse. Debe buscar constantemente las nuevas formas en las que los usuarios atacan o intentan derrotar a sus sistemas. Detect-> mitigate-> detecte-> mitigate, etc., es un estado persistente, permanente y que continuará indefinidamente.

## <a name="defending-against-dos-attacks"></a>Defensa contra ataques DoS

Para defenderse correctamente contra un ataque DoS, la detección temprana es esencial. Al detectar un ataque antes de que el sistema esté saturado, los defensores pueden ejecutar un plan de respuesta.

La siguiente fórmula le ayudará a aproximarse al tiempo de impacto de un ataque DoS:

   **Capacidad máxima (en bytes/s)/velocidad de crecimiento (en bytes/s) = tiempo de impacto (en bytes/s)**

Si el tiempo de detección se produce después del tiempo de impacto, es probable que el ataque de DoS se realice correctamente. Si el tiempo de detección se produce antes del tiempo de impacto, los servicios que sean atacados deben permanecer en línea y ser accesibles, si se usan estrategias de mitigación. Por lo tanto, solo se pueden hacer dos cosas para defenderse contra ataques DoS:
- Aumente la capacidad para aumentar el límite máximo de capacidad (lo que, a su vez, proporciona más tiempo para detectar un ataque); o
- Reducir el tiempo de detección.

El aumento de la capacidad tiene un impacto fiscal directo. Microsoft recomienda que los clientes desarrollen una capacidad de absorción básica mínima, para garantizar que pueden sobrevivir a algún ataque de DoS niveles. La capacidad de absorción real variará de un cliente a un cliente, ya que cada cliente tiene sus propios umbrales para la exposición, el riesgo y la inversión financiera. En última instancia, por razones económicas, las inversiones de investigación y tiempo en formas de reducir el tiempo de detección suelen ser la defensa más rentable.
