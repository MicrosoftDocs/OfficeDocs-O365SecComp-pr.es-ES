---
title: Metodología de puntuación de cumplimiento
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft. El administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: 120aede52d67375f60145412f5d210509ac57581
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473221"
---
# <a name="compliance-score-methodology-preview"></a>Metodología de puntuación de cumplimiento (versión preliminar)

> [!NOTE]
> La puntuación de cumplimiento no indica una medida absoluta de cumplimiento organizativo con cualquier norma o reglamento específico. Expresa el alcance hasta el que se adoptaron controles que pueden reducir los riesgos en la privacidad individual y los datos personales. Ningún servicio puede garantizar que cumpla con una norma o reglamento y, además, la puntuación de cumplimiento no puede interpretarse como una garantía en ningún caso.

El panel del administrador de cumplimiento muestra una puntuación total de cumplimiento para las evaluaciones en cada mosaico de evaluación. Esta es la puntuación de cumplimiento general para la evaluación y es la acumulación de puntos recibidos para cada control implementado y probado en la evaluación. Para una nueva evaluación, la puntuación de cumplimiento tiene un valor inicial para los controles administrados por Microsoft que han sido probados por terceros independientes. La puntuación de cumplimiento puede ayudar a priorizar con qué evaluaciones y controles centrarse para mejorar su postura de cumplimiento general.

Los valores de puntuación de cumplimiento que se muestran para el control se aplican *en su totalidad* a la puntuación de cumplimiento total en una base Pass/Fail. Puede implementar el control y pasar la prueba de evaluación posterior o no. No hay crédito parcial para una implementación parcial. Los puntos asignados se agregan a la puntuación de cumplimiento cuando el control tiene:

- El **Estado de implementación** es igual a **implementación alternativa** o **implementada** y,
- El resultado de la **prueba** es **correcto**.

## <a name="compliance-score"></a>Puntuación de cumplimiento
  
En el administrador de cumplimiento, los resultados de línea base se mueven del nivel de control al nivel del elemento de acción. Los resultados se basan en el propósito (detective, preventivo o corrector) y la aplicación (discrecional u obligatorio) del elemento de acción.

Los elementos de acción se asignan a los controles y, cuando un control se asigna a varios elementos de acción, la suma de los resultados del elemento de acción es la puntuación del control. La suma de la puntuación de control para todos los controles de una evaluación determinada es la puntuación de la evaluación. La puntuación media de todas las evaluaciones en un grupo es la puntuación de cumplimiento de ese grupo.
  
### <a name="mandatory-or-discretionary-controls"></a>Controles obligatorios o discrecionales
  
 **Los controles obligatorios** son controles que no se pueden omitir intencionada o accidentalmente. Un ejemplo de un control obligatorio común es una directiva de contraseñas administrada centralmente que establece los requisitos de longitud, complejidad y expiración de la contraseña. Los usuarios deben cumplir con estos requisitos para tener acceso al sistema.
  
 Los **controles discrecionales** dependen de los usuarios para comprender la Directiva y actuar en consecuencia. Por ejemplo, una directiva que requiere que los usuarios bloqueen su equipo cuando lo dejan es un control discrecional porque depende del usuario.
  
### <a name="preventative-detective-or-corrective-controls"></a>Controles preventivos, de detectives o correctivos
  
 **Los controles preventivos** son controles que evitan riesgos específicos. Por ejemplo, la protección de la información en reposo mediante el cifrado es un control preventivo contra ataques, infracciones. La separación de tareas es un control preventivo para administrar los conflictos de intereses y protegerse contra el fraude.
  
 **Los controles** de detectives son controles que supervisan activamente los sistemas para identificar las condiciones o comportamientos anómalos que representan el riesgo o que se pueden usar para detectar intrusiones o determinar si se ha producido una infracción. Auditoría de acceso al sistema auditoría de acciones administrativas con privilegios son tipos de controles de supervisión de detectives. Las auditorías de cumplimiento normativo son un tipo de control de detectives que se usa para encontrar problemas del proceso.
  
**Los controles correctivos** son controles que intentan mantener al mínimo los efectos negativos de un incidente de seguridad, emprenden acciones correctivas para reducir el efecto inmediato y revierten el daño, si es posible. La respuesta de la incidencia de privacidad es un control correctivo para limitar los daños y restaurar los sistemas a un estado operativo después de una infracción.
  
Cada control tiene un valor asignado en el administrador de cumplimiento según el riesgo que representa:

|**Type**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio de prevención | ,27 |
| Discrecional preventivo | 9  |
| Detective obligatorio | 3 |
| Discrecionales de detectives | 1 |
| Obligatorio de corrección | 3 |
| Discrecionales correctivas | 1 |
  
## <a name="action-item-workflow"></a>Flujo de trabajo de elementos de acción

Este es el flujo de trabajo básico para un elemento de acción típico:
  
1. El cumplimiento, el riesgo, la privacidad o el responsable de la protección de datos de una organización asigna una tarea a un usuario de la organización para implementar un control. Esa persona podría ser:

    - Un propietario de la Directiva empresarial.
    - Un implementador de ti.
    - Otra persona de la organización con la responsabilidad de realizar la tarea.

2. Ese individuo realiza las tareas necesarias para implementar el control, carga las pruebas de implementación en el administrador de cumplimiento y marca el control ligado al elemento de acción como implementado. Una vez completadas estas tareas, asignan el elemento de acción a un asesor de validación.

    Los evaluadores pueden:

    - Evaluadores internos que realizan la validación de controles dentro de una organización.
    - Evaluadores externos que examinan, comprueban y certifican el cumplimiento, como las organizaciones independientes de terceros que auditan los servicios en la nube de Microsoft.

3. El asesor valida el control y examina la evidencia y marca el control según se ha evaluado y los resultados de la evaluación.

Una vez que se evalúan todos los controles asociados con una evaluación, se completa la evaluación.