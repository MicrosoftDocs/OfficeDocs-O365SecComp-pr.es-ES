---
title: Notas de la versión para eDiscovery avanzado (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Este artículo contiene las notas de la versión para eDiscovery avanzado (versión preliminar).
ms.openlocfilehash: 32a02c16fd30e740fcc6e1c99b46775b97590a28
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240945"
---
# <a name="release-notes-for-advanced-ediscovery-preview"></a>Notas de la versión para eDiscovery avanzado (versión preliminar)

El programa de vista previa pública para eDiscovery avanzado es la forma de obtener acceso anticipado a la próxima funcionalidad y actualizaciones. Para obtener acceso anticipado a las características más recientes, simplemente cree y use un caso de exhibición avanzada de documentos electrónicos (versión preliminar) en el centro de seguridad & cumplimiento de Office 365. Consulte [Create a New Case](create-new-ediscovery-case.md).

## <a name="known-issues"></a>Problemas conocidos

**Microsoft Forms**

- Los datos correspondientes a un formulario creado antes del 31 de enero de 2019 no se podrán buscar al usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos (versión preliminar) para buscar buzones de custodios. Los formularios creados después de esta fecha estarán disponibles para su búsqueda.

- Un formulario creado por un usuario puede seguir recibiendo respuestas incluso después de que se elimine el usuario que creó el formulario. Sin embargo, los datos correspondientes para las respuestas (que se produjeron después de que se eliminó el buzón de custodio) no se podrán buscar cuando se use la herramienta de búsqueda en eDiscovery avanzado (versión preliminar) para buscar buzones de correo de custodios.
 
**Microsoft Sway**

- Si un usuario edita un Sway justo antes de eliminar la cuenta de usuario para el propietario de ese Sway, es posible que los cambios no se puedan buscar al usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos (versión preliminar) para buscar buzones de correo de custodios. Sway bloquea los cambios en un Sway tan pronto como recibe una señal de que la cuenta se eliminó. Sin embargo, hay una pequeña posibilidad de que se pueda editar un Sway antes de que se reciba esta señal.

## <a name="issues-fixed-in-this-release"></a>Problemas corregidos en esta versión

- DCR: control de excepciones para elementos sin indexar y elementos huérfanos
- DCR: mantener notificaciones
- DCR: custodios en eDiscovery

## <a name="whats-new"></a>Novedades

- **La navegación rediseñada en el centro de seguridad _AMP_ cumplimiento del** -Advanced EDiscovery (versión preliminar) tiene un aspecto nuevo. Use la exhibición avanzada de documentos electrónicos (versión preliminar) para administrar más el flujo de trabajo de casos.

- **Administración de casos** : hay compatibilidad adicional para nuevos tipos de casos. También puede seleccionar y guardar sus casos de reciente y favoritos. Seguimiento y supervisión de la actividad en y a través de los casos con nuevos paneles.

- **Administración** de custodios – agregue y elimine usuarios como custodios de datos en un caso.

- **Integración de Exchange, onedrive y Teams** : agregue automáticamente el buzón actual de un usuario, la cuenta de onedrive para la empresa y los sitios de Microsoft Teams a un caso. 

- **Comunicaciones** de custodios: Envíe y administre notificaciones de retención legal en nombre de su organización.

- **Portal de custodia** : nuevo portal para los custodios para acceder a sus avisos de espera activos.

- **IndizaCión profunda** : vuelva a rastrear los elementos indexados parcialmente a petición.

- **Corrección** de errores: corregir o descargar errores de procesamiento; Esto incluye compatibilidad con la corrección para tipos de archivo grandes, archivos protegidos con contraseña y mucho más. 

- **Mejoras en la búsqueda** : cree una búsqueda identificando los custodios o las ubicaciones.

- **Conjuntos de trabajo** : administre, realice un seguimiento y audite conjuntos de documentos estáticos.

- **Revisión** : Use una vista nativa, de texto y casi nativa para revisar los documentos agregados al conjunto de trabajo.

- **Censurar, etiquetar y anotar** : censurar texto, aplicar etiquetas y crear anotaciones mientras revisa documentos.
  
- **Revisión con tecnología de análisis**: aproveche el análisis de eDiscovery para buscar, buscar y deshacer resultados en un conjunto de trabajo.

- **Trabajos** : seguimiento del estado de los procesos de ejecución prolongada.

- **Nuevas actividades de auditoría** : realizar un seguimiento y ver una nueva actividad de auditoría para la exhibición avanzada de documentos electrónicos.
