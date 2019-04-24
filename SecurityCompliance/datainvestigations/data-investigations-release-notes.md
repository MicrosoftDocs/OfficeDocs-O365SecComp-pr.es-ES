---
title: Notas de la versión para investigaciones de datos (versión preliminar) en Microsoft 365
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
description: En este artículo se describe la herramienta nueva investigación de datos (versión preliminar) en Microsoft 365.
ms.openlocfilehash: 648f223c136007e88a3beb6b58e692b758b5d27f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258988"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Notas de la versión para investigaciones de datos (versión preliminar) en Microsoft 365

Puede usar la nueva herramienta de investigaciones de datos (vista previa) en en Microsoft 365 para clasificar, investigar y corregir incidentes relacionados con los datos, como un incidente de derrame de datos o una investigación interna. La versión preliminar pública de las investigaciones de datos proporciona acceso anticipado a la próxima funcionalidad y actualizaciones. Para obtener acceso anticipado a las características más recientes, cree una nueva investigación en investigaciones de datos (versión preliminar) en el centro de seguridad & cumplimiento. Para obtener información sobre cómo hacerlo, consulte [administrar un incidente de derrame de datos en Microsoft 365](manage-data-spillage-incidents.md).

## <a name="whats-new"></a>Novedades 

- **Investigaciones** : puede agrupar búsquedas e incidentes mediante la creación de una investigación. Administrar quién puede tener acceso a la investigación agregando o quitando miembros.  También puede seleccionar y marcar sus investigaciones favoritas. Realice un seguimiento y monitoree la actividad dentro y a través de las investigaciones mediante nuevos paneles. Una vez completada la investigación, puede cerrarla o eliminarla.

- **Personas de interés** : al agregar usuarios a las investigaciones como personas de interés, puede ver su buzón de correo, la cuenta de OneDrive para la empresa y los sitios de Microsoft Teams. Puede usarlos para el ámbito de las búsquedas de contenido de investigación. Para investigar mejor a una persona de interés, también puede ver los registros de auditoría relacionados con sus actividades en Office 365 y otros servicios de Microsoft.

- **Búsquedas** : cree una búsqueda en toda la organización con varias condiciones de búsqueda. Si conoce los usuarios o sitios que desea buscar, puede hacerlo si agrega esos usuarios como personas de interés o especifica ubicaciones de sitios en el Asistente para crear una búsqueda. 

- **Evidence** : cree un nuevo conjunto de evidencias y agregue resultados de búsqueda que desee revisar. Puede revisar documentos individuales, anotar para dejar notas de investigación y exportar resultados para moverlos a un entorno diferente. 

- **Revisión** : Use una vista nativa, de texto y cercana a la nativa para revisar los documentos agregados a un incidente. También puede aplicar análisis a los documentos para agrupar elementos por duplicados, subprocesos de correo electrónico y temas, lo que puede ayudar a revisar el incidente. 

- **Censurar, etiquetar y anotar** : censurar texto, aplicar etiquetas y crear anotaciones mientras revisa documentos.
  
- **IndizaCión avanzada** : si hay elementos parcialmente indizados, se volverán a indexar a petición para que todos los datos estén disponibles para la búsqueda.

- **Corrección** de errores: corregir o descargar errores de procesamiento. Esto incluye compatibilidad con la corrección para tipos de archivo grandes, archivos protegidos con contraseña y otros problemas relacionados con los errores de indización. 

- **Trabajos** : seguimiento del estado de los procesos de ejecución prolongada.

- Eliminar de forma permanente **los elementos del buzón de correo** -en situaciones urgentes, es posible que deba eliminar los elementos mal colocados de forma permanente. Para ello, puede ejecutar el comando **New-ComplianceSearchAction-Purge-PurgeType HardDelete** en Security _AMP_ Compliance Center PowerShell para eliminar de forma permanente los elementos de los buzones de correo. Para obtener más información, vea [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).
