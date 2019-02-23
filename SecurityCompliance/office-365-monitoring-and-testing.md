---
title: Office 365 supervisión y pruebas de los límites de inquilino
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
description: 'Resumen: una explicación de cómo Microsoft supervisa y comprueba los límites de inquilino para Office 365.'
ms.openlocfilehash: fce217bfcb5fec1ba3fb6da70eb6f9da9a2c1d44
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221100"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Supervisar y probar los límites de inquilinos
Microsoft supervisa y comprueba explícitamente los puntos débiles y las vulnerabilidades en los límites de los inquilinos, incluida la supervisión de intrusiones, intentos de infracción de permisos y inanición de recursos. También usamos varios sistemas internos para supervisar continuamente la utilización de recursos inadecuados, que, si se detectan, desencadena una limitación integrada.

Office 365 tiene sistemas de supervisión internos que supervisan continuamente los errores y la recuperación automática cuando se detecta un error. Office 365 sistemas analizan las desviaciones en el comportamiento del servicio e inician procesos de recuperación automática integrados en el sistema. Office 365 también usa una supervisión externa en la que la supervisión se realiza desde varias ubicaciones, desde servicios de terceros de confianza (para la comprobación de SLA independiente) y nuestros propios centros de recursos para generar alertas. Para los diagnósticos, tenemos un registro, una auditoría y un seguimiento extensivos. El seguimiento y la supervisión granular nos ayudan a aislar los problemas y realizar un análisis rápido y eficaz de la causa de origen.

Aunque Office 365 tiene acciones de recuperación automatizadas siempre que sea posible, los ingenieros de llamadas de Microsoft están disponibles 24 horas al día, para investigar todas las escalaciones de seguridad de gravedad 1, y las revisiones post mortem de cada incidente de servicio contribuye a un aprendizaje continuo y desarrollo. Este equipo incluye ingenieros de soporte técnico, desarrolladores de productos, administradores de programas, jefes de producto y liderazgo Senior. Nuestros profesionales de la llamada proporcionan una copia de seguridad oportuna y a menudo pueden automatizar las acciones de recuperación, de modo que la próxima vez que se produzca un evento, se puede solucionar por sí misma.

Microsoft realiza una revisión exhaustiva posterior al incidente cada vez que se produce un incidente de seguridad de Office 365 independientemente de la magnitud del impacto. Una revisión posterior al incidente consiste en un análisis de lo ocurrido, cómo respondemos y cómo evitaría incidentes similares en el futuro. En aras de la transparencia y la responsabilidad, compartimos la revisión posterior al incidente por cualquier incidente importante del servicio con los clientes afectados. Para obtener detalles específicos, consulte [Office 365 Security Incident Management](http://aka.ms/Office365SIM).

## <a name="assume-breach-methodology"></a>Asumir una metodología de inFracciones
Basándose en análisis detallados de tendencias de seguridad, Microsoft defiende y destaca la necesidad de inversiones adicionales en procesos y tecnologías de seguridad reactivos que se centran en la detección y la respuesta a amenazas emergentes, en lugar de en la única prevención de esas amenazas. Debido a los cambios en el panorama de las amenazas y el análisis exhaustivo, Microsoft ha refinado su estrategia de seguridad más allá de sólo evitar infracciones de seguridad a un mejor equipado para enfrentarse a las brechas en caso de que se produzcan (una estrategia que considere eventos de seguridad principales) que no como una cuestión de IF, pero cuando.

Mientras que Microsoft [asume](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) que se han implementado prácticas de violación durante muchos años, muchos clientes no conocen el trabajo que se realiza en segundo plano para reforzar la nube de Microsoft. Asuma un inCumplimiento es una mentalidad que guía las inversiones en seguridad, las decisiones de diseño y las prácticas de seguridad operacional. SuPongamos que la inFracción de seguridad se aplica a las aplicaciones, servicios, identidades y redes al tratarlas todos (internos y externos) como no seguras y ya en peligro. Aunque la estrategia de inFracciones no proviene de una infracción real de cualquier servicio de Microsoft Enterprise o de la nube, fue un reconocimiento que muchas organizaciones, en la industria, se violaban a pesar de todos los intentos de evitarlo. Aunque la prevención de las infracciones es una parte fundamental de las operaciones de la organización, estas prácticas deben probarse y aumentarse continuamente para enfrentarse de manera eficaz a las amenazas modernas adversarios y avanzadas. Para que cualquier organización pueda prepararse para una infracción, primero debe crear y mantener procedimientos de respuesta de seguridad sólidos, repetibles y probados minuciosamente.

Aunque evitar los procesos de seguridad de inCumplimiento, como la modelación de amenazas, las revisiones de código y las pruebas de seguridad son muy útiles como parte del [ciclo de vida de desarrollo de seguridad](http://www.microsoft.com/security/sdl/default.aspx), suponer un incumplimiento ofrece numerosas ventajas que ayudan a la seguridad general por ejercitar y medir las capacidades reactivas en caso de infracción.

En Microsoft, nos hemos pensado en lograrlo a través de ejercicios de guerra en curso y pruebas de penetración en el sitio en directo de nuestros planes de respuesta de seguridad con el objetivo de mejorar nuestra capacidad de detección y respuesta. Microsoft simula periódicamente las infracciones en el mundo real, dirige la supervisión de seguridad continua y practica la administración de incidentes de seguridad para validar y mejorar la seguridad de Office 365, Azure y otros servicios en la nube de Microsoft.

Microsoft ejecuta su estrategia de seguridad de inFracciones con dos grupos principales:
- Equipos de color rojo (atacantes)
- Equipos azules (defensores)

El personal de Microsoft Azure y Office 365 es equipo de equipos rojos y azules independientes a tiempo completo.

Conocido como "[equipo rojo](http://go.microsoft.com/fwlink/?linkid=518599)", el enfoque consiste en probar sistemas y operaciones de Azure y Office 365 con las mismas tácticas, técnicas y procedimientos que los adversarios reales, con la infraestructura de producción activa, sin el foreknowledge del Equipos de ingeniería u operaciones. Esto prueba las capacidades de detección y respuesta de seguridad de Microsoft y ayuda a identificar las vulnerabilidades de producción, los errores de configuración, los supuestos no válidos y otros problemas de seguridad de manera controlada. Cada infracción de equipo en rojo va seguida de una divulgación completa entre los dos equipos para identificar brechas, conclusiones de la dirección y mejora de la respuesta a las infracciones.

**Nota**: los datos de los clientes no se destinan deliberadamente durante la formación de equipos rojos o las pruebas de penetración en sitios activos. Las pruebas están relacionadas con las plataformas y la infraestructura de Office 365 y Azure, así como con los propios espacios empresariales, aplicaciones y datos de Microsoft. Los inquilinos de cliente, las aplicaciones y el contenido hospedados en Office 365 o Azure nunca se dirigen.

## <a name="red-teams"></a>Equipos rojos
El equipo de color rojo es un grupo de personal a tiempo completo dentro de Microsoft que se centra en la infracción de la infraestructura, la plataforma y las aplicaciones y los espacios empresariales de Microsoft. Son los adversarios dedicados (un grupo de hackers éticos) que realizan ataques perSeguidos y persistentes contra los servicios en línea (infraestructura de Microsoft, plataformas y aplicaciones, pero no a las aplicaciones ni al contenido de los clientes finales).

El rol del equipo en rojo es atacar y penetrar en entornos con los mismos pasos que un adversario:
 
![Fases de inFracción](media/office-365-isolation-breach-stages.png)

Entre otras funciones, los equipos rojos intentan específicamente infringir los límites de aislamiento de inquilino para encontrar errores o brechas en nuestro diseño de aislamiento.

## <a name="blue-teams"></a>Equipos azules
El equipo azul se compone de un conjunto dedicado de respondedores o miembros de seguridad a través de las organizaciones de respuesta, ingeniería y operaciones de incidentes de seguridad. Independientemente de su forma de componerla, son independientes y operan por separado del equipo de red. El equipo azul sigue los procesos de seguridad establecidos y usa las últimas herramientas y tecnologías para detectar y responder a los ataques y la penetración. Al igual que con los ataques del mundo real, el equipo azul no sabe cuándo o cómo se producirán los ataques del equipo rojo o qué métodos pueden usarse. Su trabajo, ya sea un ataque de equipo en rojo o un asalto real, es detectar y responder a todos los incidentes de seguridad. Por este motivo, el equipo azul está continuamente activado y debe reaccionar a las infracciones de equipo en rojo de la misma manera que lo harían para cualquier otra infracción.

Cuando un adversario, como un equipo de color rojo, ha infringido un entorno, el equipo azul debe:
- Recopilar evidencia dejada por el adversario
- Detectar la evidencia como una indicación de peligro
- Alertar a los equipos de ingeniería y de funcionamiento apropiados
- Clasifique las alertas para determinar si justifican una mayor investigación
- Recopilar el contexto del entorno para el ámbito de la infracción
- Formar un plan de corrección para contener o expulsar el adversario
- Ejecutar el plan de corrección y recuperarse de una infracción

Estos pasos conforman la respuesta al incidente de seguridad que se ejecuta en paralelo con el del adversario, tal como se muestra a continuación:
 
![Fases de respuesta a las inFracciones](media/office-365-isolation-breach-response-stages.png)

Las infracciones de equipo en rojo permiten ejercitar la capacidad del equipo azul para detectar y responder a ataques en el mundo real de un extremo a otro. Lo más importante es que permite la respuesta al incidente de seguridad antes de una infracción del auténtico. Además, debido a las infracciones de equipo en rojo, el equipo azul mejora su conciencia de situación que puede ser valiosa al tratar con infracciones futuras (ya sea del equipo de color rojo o de otro adversario). Durante el proceso de detección y respuesta, el equipo azul produce una inteligencia que requiere acción y obtiene visibilidad de las condiciones reales del entorno o los entornos que intentan defender. Con frecuencia, esto se logra a través del análisis de datos y de la investigación, realizado por el equipo azul, cuando responde a los ataques de equipo rojos y estableciendo indicadores de amenazas, como indicadores de peligro. De forma similar a cómo el equipo rojo identifica brechas en el caso de seguridad, los equipos azules identifican brechas en su capacidad para detectar y responder. Además, dado que los equipos de color rojo modelan los ataques en el mundo real, el equipo azul puede evaluarse con precisión por su capacidad o incapacidad para tratar con los adversarios determinados y persistentes. Por último, las infracciones de equipo en rojo miden tanto la preparación como el impacto de nuestra respuesta a la infracción.
