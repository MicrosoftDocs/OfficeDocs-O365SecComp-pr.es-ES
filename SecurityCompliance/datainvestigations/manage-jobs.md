---
title: Administrar trabajos en investigaciones de datos
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
description: ''
ms.openlocfilehash: 28577d45c44eabcffcff2d98bc89a664f3fba6f5
ms.sourcegitcommit: 19d27ff836ee7fa1f8a4e761e04d928f13f4bfd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "31745302"
---
# <a name="manage-jobs-in-data-investigations-preview"></a>Administrar trabajos en investigaciones de datos (versión preliminar)

Esta es una lista de los trabajos (que suelen ser procesos de larga duración) cuyo seguimiento se realiza en la ficha **trabajos** de una investigación en investigaciones de datos (versión preliminar). Estas tareas las desencadenan acciones del usuario al usar y administrar las investigaciones.

| Tipo de trabajo           | Description     |
| :----------------- | :----------     |
|Adición de datos a un conjunto de evidencias | Un usuario agrega los resultados de una búsqueda a un conjunto de evidencias.  Para obtener más información, vea [buscar datos en una investigación](search-for-data.md). |
|Adición de datos a otro conjunto de evidencias | Un usuario agrega documentos de un conjunto de evidencias a un conjunto de evidencias diferente en el mismo caso.|
|Adición de datos que no son de Office 365 a un conjunto de evidencias | Un usuario carga datos que no son de Office 365 en un conjunto de evidencias. Los datos también se indizan durante este proceso. Por ejemplo, los archivos de un servidor de archivos local o un equipo cliente se cargan en un conjunto de evidencias. Para obtener más información, vea [cargar datos que no son de Office 365 en pruebas](load-non-office365-data.md).| 
|Adición de datos corregidos a un conjunto de evidencias | Los datos con errores de procesamiento se corrigen y se cargan de nuevo en un conjunto de evidencias. Para obtener más información, vea [corrección de errores al procesar datos para una investigación](error-remediation.md). | 
|Comparar conjuntos de carga | Un usuario examina las diferencias entre los distintos conjuntos de carga en un conjunto de evidencias. Un conjunto de carga es una instancia de agregar datos a un conjunto de evidencias. Por ejemplo, si agrega los resultados de dos búsquedas diferentes al mismo conjunto de evidencias, cada una de ellas representará un conjunto de carga. Para obtener más información, consulte [Manage Load sets](manage-load-sets.md). |
|Conversión de documentos censurados a PDF|Una vez que un usuario anota un documento en un conjunto de evidencias y censura una parte del mismo, puede optar por convertir el documento censurado en un archivo PDF. Esto garantiza que la parte censurada no será visible whenf que el documento se exporte para su presentación. Para obtener más información, vea [Review Data in Evidence](review-data-in-evidence.md). |
|Estimar los resultados de la búsqueda | Cuando un usuario crea y ejecuta una nueva búsqueda (o vuelve a ejecutar una búsqueda existente), la herramienta de búsqueda busca en el índice los elementos que coinciden con la consulta de búsqueda y prepara una estimación que incluye el número y el tamaño total de todos los elementos mediante la búsqueda, y el número de orígenes de datos sea el rched.  Para obtener más información, vea [buscar datos en una investigación](search-for-data.md). | 
|Preparación de datos para la exportación | Un usuario exporta documentos de un conjunto de evidencias. Una vez finalizado el proceso de exportación, pueden descargar los datos exportados en un equipo local. Para obtener más información, vea [exportar datos de una investigación](export-data.md). | 
|Preparación para la resolución de errores |Cuando un usuario selecciona un archivo y crea un nuevo corrección de errores en la vista de errores en la ficha **procesamiento** de una investigación, el primer paso del proceso es cargar el archivo que tiene el error de procesamiento en una ubicación de almacenamiento de Azure en la nube de Microsoft. Este trabajo realiza un seguimiento del progreso del proceso de carga. Para obtener más información acerca del flujo de trabajo de corrección de errores, consulte [corrección de errores al procesar datos para una investigación](error-remediation.md).| 
|Preparación de la vista previa de búsqueda | Una vez que un usuario crea y ejecuta una nueva búsqueda (o vuelve a ejecutar una búsqueda existente), la herramienta de búsqueda prepara un subconjunto de elementos de muestra (que coinciden con la consulta de búsqueda) en los que se puede obtener una vista previa. La vista previa de los resultados de búsqueda puede ayudarle a determinar la eficacia de la búsqueda.  Para obtener más información, vea [buscar datos en una investigación](search-for-data.md). | 
|Volver a indizar datos de personas de interés | Cuando se agrega una persona de interés a una investigación, todos los elementos parcialmente indizados de los orígenes de datos seleccionados del interés se vuelven a indizar mediante un proceso denominado *indizaCión avanzada*. Este trabajo también se desencadena cuando se hace clic en **Actualizar índice** en la vista índice en la ficha **procesamiento** de una investigación. Para obtener más información, vea [indizaCión avanzada de datos para una investigación](index-data-people-of-interest.md).
|Ejecución de análisis | Un usuario analiza los datos de un conjunto de evidencias mediante la ejecución de herramientas de análisis, como la detección de duplicados, el análisis de subprocesos de correo electrónico y el análisis de temas. Para obtener más información, vea [ejecutar análisis para investigar con mayor rapidez](run-analytics-to-investigate-faster.md). | 
|Etiquetando documentos | Este trabajo se desencadena cuando un usuario hace clic en **iniciar trabajo de etiquetado** en el **Panel etiquetado** al revisar los documentos de un conjunto de evidencias. Un usuario puede iniciar este trabajo después de etiquetar los documentos en un conjunto de evidencias y, a continuación, seleccionarlos de forma masiva en el panel ver documento. Para obtener más información, vea [etiquetar documentos en evidencia](tag-documents.md). | 
|||