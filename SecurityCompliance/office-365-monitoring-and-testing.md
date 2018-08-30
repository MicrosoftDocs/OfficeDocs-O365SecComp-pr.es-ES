---
title: Supervisión de Office 365 y comprobación de los límites del inquilino
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
description: 'Resumen: Una explicación de cómo Microsoft supervisa y pruebas de inquilinos límites para Office 365.'
ms.openlocfilehash: 4d57c7497bfe8bf9939f3ae785ab9fbc670bd0ae
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535930"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Supervisar y probar los límites de inquilinos
Microsoft supervisa de forma continua y comprueba explícitamente para los puntos débiles y las vulnerabilidades de seguridad en los límites del inquilino, incluida la supervisión de intrusiones, los intentos de infracción de permiso y agotamiento de recursos. También se utilizan varios sistemas internos para supervisar continuamente la utilización de recursos incorrectos, lo que si detecta, desencadena la limitación integradas.

Office 365 tiene sistemas internos de supervisión que supervisión para los errores de forma continua y unidad recuperación automática cuando se detecta el error. Sistemas de Office 365 analizar las desviaciones en el comportamiento de servicio e inician procesos de recuperación automática que están integrados en el sistema. Office 365 también usa fuera de supervisión en el que realizar la supervisión desde varias ubicaciones tanto de servicios de terceros de confianza (para la comprobación de SLA independiente) y nuestros propios centros de datos para generar alertas. Para realizar diagnósticos, tenemos extensiva de registro, auditoría y seguimiento. Análisis de causa de seguimiento detallado y ayuda a nosotros aislar problemas y llevar a cabo raíz rápida y eficaz de supervisión.

Mientras Office 365 tiene automatizados acciones de recuperación que sea posible, los ingenieros de Microsoft en llamada están disponibles 24 x 7 para investigar todas las extensiones de seguridad de gravedad 1 y revisan el análisis detallado de todos los incidentes servicio contribuyen a aprendizaje continuo y mejora. Este equipo incluye ingenieros de soporte técnico, los desarrolladores de productos, administradores de programas, los directores de producto y liderazgo senior. Nuestros profesionales en llamada oportuna de reserva y a menudo pueden automatizar las acciones de recuperación, para que la próxima vez que se produce un evento, puede ser Self-cicatrizada.

Microsoft lleva a cabo una revisión exhaustiva posteriores a los incidentes cada vez que se produce un incidente de seguridad de Office 365, independientemente de la magnitud del impacto. Una revisión posteriores a los incidentes consta de un análisis de ¿qué sucedió con, cómo se respondió y cómo se evitar incidentes similares en el futuro. Por razones de transparencia y control, compartimos incidente posteriores a la revisión de los incidentes de los servicios principales con los clientes afectados. Para obtener información detallada, vea [Administración de incidentes de seguridad de Office 365](http://aka.ms/Office365SIM).

## <a name="assume-breach-methodology"></a>Se supone la metodología de incumplimiento
En función de un análisis detallado de las tendencias de seguridad, Microsoft abogados y destaca la necesidad de las inversiones adicionales en los procesos de seguridad reactiva y tecnologías que se centran en detección y respuesta a las amenazas emergentes, en lugar de únicamente la prevención de esas amenazas. Debido a los cambios en el panorama de amenazas y el análisis en profundidad, Microsoft refinado su estrategia de seguridad más allá de simplemente evitar infracciones de seguridad a una mejor equipado para abordar los problemas con las infracciones cuando se producen: una estrategia que considere principales eventos de seguridad no como una cuestión de if, pero cuándo.

Mientras se han recomendados [Se supone incumplimiento](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) de Microsoft en su lugar durante muchos años, muchos clientes son conscientes del trabajo que se realiza en segundo plano para reforzar la nube de Microsoft. Se supone que incumplimiento es un modo de pensar que guía las inversiones en seguridad, las decisiones de diseño y prácticas de seguridad operativa. Límites de incumplimiento la confianza realizada en las aplicaciones, servicios, identidades y redes por tratar todas ellas se supone: internos y externos — como no seguro y ya está en riesgo. Aunque la estrategia se supone incumplimiento no se transmiten de un incumplimiento real de los servicios de empresa o en la nube de Microsoft, era un reconocimiento que muchas organizaciones, en toda la industria, se han se pueda infringir a pesar de todos los intentos para evitarlo. Mientras impidiendo que las infracciones es una parte fundamental de las operaciones de cualquier organización, esas prácticas deben ser continuamente probadas y aumenta para enfrentar con efectividad adversarios modernos y avanzadas amenazas persistentes. Para cualquier organización preparar un incumplimiento, debe crear y mantener los procedimientos de respuesta de seguridad eficaz, repetible y probado exhaustivamente.

Mientras que los procesos de seguridad impedir incumplimiento, como modelo de amenazas, revisiones de código y las pruebas de seguridad son muy útiles como parte del [Ciclo de vida de desarrollo de seguridad](http://www.microsoft.com/security/sdl/default.aspx)de, se supone incumplimiento proporciona numerosas ventajas que ayudan a la cuenta de la seguridad general por ejercicio y medición capacidades reactivas en caso de infracción.

En Microsoft, establecemos out para hacerlo a través de curso war-games ejercicios y pruebas de penetración sitio activo de nuestros planes de respuesta de seguridad con el fin de mejorar nuestra capacidad de detección y respuesta. Microsoft con regularidad simula las infracciones para el mundo real, lleva a cabo seguridad continua supervisión y administración de incidentes de seguridad recomendados para validar y mejorar la seguridad de Office 365, Azure y otros servicios de nube de Microsoft.

Microsoft ejecuta su estrategia de seguridad suponen incumplimiento con dos grupos principales:
- Equipos de rojo (los atacantes)
- Equipos azules (defensores)

Personal de Microsoft Azure y Office 365 separa los equipos de color rojos a tiempo completo y los equipos azules.

Conoce como "[Rojo formación](http://go.microsoft.com/fwlink/?linkid=518599)", el enfoque consiste en probar sistemas de Azure y Office 365 y operaciones con las mismas tácticas, técnicas y procedimientos como adversarios reales, frente a la infraestructura de producción en directo, sin el conocimiento previo de la Ingeniería o los equipos de operaciones. Esto realiza una prueba de Microsoft seguridad capacidades de detección y respuesta, y ayuda a identifica las vulnerabilidades de seguridad de producción, errores de configuración, suposiciones válidas y otros problemas de seguridad de una manera controlada. Incumplimiento de cada equipo rojo seguido de divulgación completa entre ambos equipos para identificar vacíos, conclusiones de direcciones y mejorar la respuesta de incumplimiento.

**Nota**: ningún dato del cliente está dirigido deliberadamente durante la formación de equipos de Red o las pruebas de penetración sitio activo. Las pruebas son contra la infraestructura de Office 365 y Azure y plataformas, así como los inquilinos de Microsoft, las aplicaciones y datos. Los inquilinos de atención al cliente, aplicaciones y contenido hospedado en Office 365 o Azure nunca el destino.

## <a name="red-teams"></a>Equipos de color rojos
El equipo de color rojo es un grupo de personal a tiempo completo dentro de Microsoft que se centra en la infraestructura de Microsoft violación, plataforma y los inquilinos de Microsoft y aplicaciones. Son el adversario dedicado (un grupo de protección de datos confidenciales intrusos) realiza dirigidos y persistentes de los ataques contra los servicios en línea (infraestructura de Microsoft, plataformas y las aplicaciones, pero no los clientes finales aplicaciones o contenido).

La función del equipo de color rojo es para atacar y entrar en entornos con los mismos pasos como un adversario:
 
![Etapas de incumplimiento](media/office-365-isolation-breach-stages.png)

Entre otras funciones, los equipos de color rojos intentan infringir los límites de aislamiento de inquilinos para buscar errores o carencias en nuestro diseño de aislamiento.

## <a name="blue-teams"></a>Equipos azules
El equipo de azul se compone de un conjunto dedicado de Respondedores de seguridad o los miembros de a través de la respuesta de incidente de seguridad, ingeniería y operaciones de las organizaciones. Independientemente de su composición, son independientes y funcionan por separado desde el equipo de color rojo. El siguiente equipo azul estableció seguridad procesa y utiliza las herramientas y tecnologías más recientes para detectar y responder a ataques y penetración. Al igual que los ataques para el mundo real, el equipo de azul no sabe cómo o cuándo se producirán los ataques del equipo de color rojo o qué métodos se pueden utilizar. Su trabajo, ya sea un ataque de color rojo del equipo o un ataque real, es detectar y responder a todos los incidentes de seguridad. Por este motivo, el equipo de azul es continuamente en llamada y debe reaccionar a las infracciones de color rojo del equipo del mismo modo que lo haría con cualquier otra infracción.

Cuando un adversario, como un equipo de color rojo, infringe un entorno, el equipo de azul debe:
- Recopilar evidencia el adversario a la izquierda
- Detectar la evidencia como una indicación de peligro
- Los equipos de ingeniería y el funcionamiento adecuados de la alerta
- Clasifique las alertas para determinar si merece una mayor investigación
- Recopilar el contexto del entorno para delimitar el incumplimiento de
- Un plan de corrección para contener o expulsar al adversario de formulario
- Ejecutar el plan de corrección y recuperarse incumplimiento

Estos pasos de formulario la respuesta de incidente de seguridad que se ejecuta en paralela para el adversario, tal y como se muestra a continuación:
 
![Etapas de la respuesta de incumplimiento](media/office-365-isolation-breach-response-stages.png)

Las infracciones de equipo rojo permiten para el ejercicio de la azul capacidad del equipo para detectar y responder a ataques para el mundo real end-to-end. Lo más importante, permite respuesta a incidentes prácticas de seguridad antes de una infracción de la original. Además, debido a las infracciones de color rojo del equipo, el equipo de azul mejora sus conocimientos de la situación que pueden ser útil cuando trabaja con futuras infracciones (ya sea desde el equipo de color rojo o adversario otra). A lo largo de la detección y el proceso de respuesta, el equipo de azul genera inteligencia y obtiene visibilidad en las condiciones reales de los entornos que intentan defenderse. Con frecuencia, esto se logra a través de análisis de datos y argumentación, realizado por el equipo de azul, al responder a los ataques de equipo rojo y mediante el establecimiento de indicadores de amenaza, como indicadores de compromiso. Mucho como cómo el equipo de color rojo identifica diferencias en la historia de la seguridad, los equipos azules identifican vacíos en su capacidad para detectar y responder. Además, dado que los equipos de color rojos modelar los ataques para el mundo real, el equipo de azul se puede evaluar con precisión en su capacidad o incapacidad para abordar los problemas con determinados y persistentes adversarios. Por último, las infracciones de equipo rojo medir preparación y el impacto de nuestra respuesta incumplimiento.
