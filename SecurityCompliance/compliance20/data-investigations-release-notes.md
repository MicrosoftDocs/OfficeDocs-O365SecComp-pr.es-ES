---
title: Notas de la versión para datos investigaciones (vista previa) en Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: En este artículo se describe la nueva versión de avanzada exhibición de documentos electrónicos (vista previa) en Microsoft 365.
ms.openlocfilehash: 90bcbd4cae1e410e1544352a776ba4cbbedfa429
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695066"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Notas de la versión para datos investigaciones (vista previa) en Microsoft 365

Puede usar la nueva herramienta de investigaciones de datos (vista previa) en Microsoft 365 para evaluar, investigar y corregir los datos relacionados con incidentes, como un incidente de pérdidas de datos o una investigación interna. Las investigaciones de vista previa de datos públicos le proporciona acceso rápido a la funcionalidad próxima y las actualizaciones. Para obtener acceso rápido a las características más recientes, cree una nueva investigación en investigaciones de datos (vista previa) en el centro de cumplimiento de seguridad de Office 365 &. Para obtener más información, vea [administrar un incidente de pérdidas de datos en Microsoft 365](manage-data-spillage-incidents.md).

## <a name="whats-new"></a>Novedades 

- **Investigaciones** - puede agrupar las búsquedas e incidentes mediante la creación de una investigación. Administrar quién puede tener acceso a la investigación agregando o quitando a miembros.  También puede seleccionar y marcar las favoritas investigaciones. Seguimiento y supervisar la actividad dentro y entre las investigaciones mediante paneles nuevo. Después de completar la investigación, puede cerrar o eliminarla.

- **Personas de interés** : al agregar usuarios a las investigaciones como personas de interés, puede ver su buzón, OneDrive para la cuenta de empresa y los sitios de Microsoft Teams. Puede usarlas para establecer el ámbito de las búsquedas de contenido de investigación. Para investigar una persona de interés, también puede ver sus actividades en Office 365 y otros servicios de Microsoft relacionados con los registros de auditoría.

- Condición de búsqueda de **las búsquedas** : crear una búsqueda de toda la organización con distintos. Si conoce los usuarios o sitios que desea buscar, puede hacerlo mediante la adición de esos usuarios como personas de interés o cómo especificar ubicaciones de sitio en el Asistente para la creación de búsqueda. 

- **Incidentes** : crear una nueva incidencia y agregar los resultados de búsqueda que desee revisar. Puede revisar los documentos individuales, puede incluir anotaciones para dejar notas de investigación y exportar los resultados para mover a un entorno diferente. 

- **Revise** – utilice una nativo, texto y casi nativo vista para revisar los documentos de agregado a un incidente. También puede aplicar análisis a los documentos para agrupar los elementos duplicados, los subprocesos de correo electrónico y temas, que pueden ayudar a su revisión del incidente. 

- **Redact, etiqueta y puede incluir anotaciones en** – censurar texto, aplicar etiquetas y realizar anotaciones como revisar documentos.
  
- **Indización profundo** – si hay elementos indizados parcialmente, pueden volver a indizar a petición para que estén disponibles para la búsqueda de todos los datos.

- **Corrección de error** – Remediate o descargar errores de procesamiento. Esto incluye la compatibilidad de corrección para tipos de archivo grande, protegidos con contraseña los archivos y otros problemas relacionados con la indización de errores. 

- **Trabajos** : seguimiento de estado de los procesos de larga ejecución.

- **Los elementos del buzón duro-delete** - en situaciones urgentes, es posible que necesita eliminar permanentemente los elementos rchivo. Para ello, puede ejecutar el **New-ComplianceSearchAction-purgar - PurgeType HardDelete** command en seguridad & PowerShell de centro de cumplimiento para eliminar permanentemente los elementos de los buzones de correo. Para obtener más información, vea [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).
