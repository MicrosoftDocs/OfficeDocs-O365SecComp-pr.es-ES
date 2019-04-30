---
title: Notas de la versión de Microsoft Compliance Manager
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
ms.openlocfilehash: 5e18445e3f9ad2848f18174788ec6dd40bc4a178
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473220"
---
# <a name="release-notes-for-compliance-manager-preview"></a>Notas de la versión del administrador de cumplimiento (versión preliminar)

La versión preliminar pública del administrador de cumplimiento le proporciona acceso anticipado a las actualizaciones y funciones futuras.

Puede usar la herramienta actualizada del [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) en el portal de confianza de [servicios](https://servicetrust.microsoft.com) para realizar un seguimiento, asignar y comprobar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.

## <a name="whats-new-in-compliance-manager-preview"></a>Novedades del administrador de cumplimiento (versión preliminar)

- **Integración con la puntuación segura de Microsoft:** El administrador de cumplimiento admite la integración con la [puntuación segura de Microsoft](microsoft-secure-score.md) mediante la asignación de acciones administradas por el cliente a más de 50 acciones de calificación seguras. Al completar una acción asignada en calificación segura, la acción correspondiente del administrador de cumplimiento se actualiza automáticamente.

- **Importar evaluaciones personalizadas:** Además de las evaluaciones integradas, el administrador de cumplimiento ahora admite la importación de plantillas personalizadas, lo que le permite crear evaluaciones personalizadas para cualquier producto o servicio y cualquier estándar o regla.

- **Elementos de acciones:** Los elementos de acción son ahora elementos individuales y muchos incluyen la colección de telemetría de la API de Microsoft Secure score Graph. Siempre que sea posible, las recomendaciones de acciones técnicas ahora tienen vínculos a la página de configuración correspondiente en el servicio de Office 365.

- **Administración de inquilinos:** Nueva interfaz para la administración de elementos de datos nuevos en el administrador de cumplimiento (versión preliminar):
    - **Dimensiones:** Permite ver, agregar y personalizar metadatos para plantillas, evaluaciones y elementos de acción que permiten crear tablas dinámicas personalizadas para los filtros.
    - **Propietarios:** Especifique un propietario para cada elemento de acción.
    - **Acciones del cliente:** Administrar la lista completa de elementos de acciones incluidos en el administrador de cumplimiento (versión preliminar) y habilitar o deshabilitar la supervisión de la puntuación segura para los elementos de acción integrados con calificación segura.

- **Puntuación de cumplimiento actualizada**: la metodología ha cambiado para admitir la sincronización con calificación segura de Microsoft. El sistema de puntuación quita los créditos de los controles administrados por Microsoft y se centra únicamente en la finalización de los controles administrados por el cliente.

## <a name="known-issues-in-compliance-manager-preview"></a>Problemas conocidos en el administrador de cumplimiento (versión preliminar)

En las siguientes secciones se abordan los problemas conocidos que deben resolverse en próximas versiones del administrador de cumplimiento.

### <a name="compliance-score"></a>Puntuación de cumplimiento

- Cuando los elementos de acción se marcan como **no en ámbito**, la puntuación asignada al elemento de acción no se excluye del cálculo de puntuación de cumplimiento. Los elementos de acción marcados **sin ámbito** no deben aumentar la puntuación de cumplimiento.

### <a name="microsoft-managed-controls"></a>Controles administrados por Microsoft

- La fecha de prueba de los controles administrados por Microsoft no aparece en la interfaz de usuario, incluso cuando se incluye en la evaluación. Para ver la información de fecha de prueba, debe exportar la evaluación.

### <a name="customization"></a>Personalización

- Agregar controles personalizados permite agregar un control nuevo a una familia de controles existente, pero no permite agregar una nueva familia de controles.
- Esta versión no admite la vinculación de elementos de acción ni la adición de elementos o controles de acciones a una evaluación.
- Si crea una acción personalizada, no podrá editarla ni eliminarla.

### <a name="control-families-not-shown-in-assessments"></a>Familias de control que no se muestran en las evaluaciones

- Al importar una plantilla, todas las evaluaciones basadas en dicha plantilla reflejarán todas las familias de controles que forman parte de la plantilla. Pero si agrega nuevas familias de controles a la plantilla, las evaluaciones existentes no reflejarán los cambios. Solo las nuevas evaluaciones que se creen en la plantilla actualizada reflejarán los cambios.

### <a name="filters"></a>Filtros

- El filtrado de los elementos de acción o los controles no produce de forma coherente resultados correctos.

### <a name="templates"></a>Plantillas

- Las plantillas archivadas son editables y no se pueden editar.
- Las plantillas bloqueadas permiten la creación de evaluaciones cuando no deberían. Bloquear una plantilla tiene como objetivo evitar que se use para crear evaluaciones.

### <a name="export"></a>Exportar

- Se produce un error en la exportación de plantillas a JSON cuando **** el estado de la plantilla está establecido en importado o **pendiente de aprobación**.

### <a name="supported-browsers"></a>Exploradores compatibles

- Se admiten las versiones más recientes de Microsoft Edge, Chrome y Safari.
- Puede haber casos en los que los datos actualizados no aparezcan hasta que se actualice el explorador.
- La versión preliminar de Microsoft Edge no es compatible, pero no tiene problemas conocidos.
- Internet Explorer no es compatible.

### <a name="session-timeout"></a>Tiempo de espera de sesión

- Cuando se agota el tiempo de espera de una sesión, puede aparecer un error "se ha producido un problema". Para solucionarlo, vaya al [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) e inicie sesión de nuevo.