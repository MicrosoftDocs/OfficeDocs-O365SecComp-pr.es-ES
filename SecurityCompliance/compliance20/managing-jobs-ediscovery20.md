---
title: Administrar trabajos en la exhibición avanzada de documentos electrónicos (versión preliminar)
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
ms.openlocfilehash: e5f7c6d0f0932041ef92591afcb59ad836cae0e4
ms.sourcegitcommit: 19d27ff836ee7fa1f8a4e761e04d928f13f4bfd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "31745292"
---
# <a name="manage-jobs-in-advanced-ediscovery-preview"></a>Administrar trabajos en la exhibición avanzada de documentos electrónicos (versión preliminar)

Esta es una lista de los trabajos (que suelen ser procesos de larga ejecución) cuyo seguimiento se realiza en la ficha **trabajos** de un caso en eDiscovery avanzado (versión preliminar). Estas tareas se desencadenan por acciones del usuario al usar y administrar casos.

| Tipo de trabajo           | Description     |
| :----------------- | :----------     |
|Adición de datos a un conjunto de trabajo | Un usuario agrega los resultados de una búsqueda a un conjunto de trabajo.  Para obtener más información, vea [Agregar resultados de búsqueda a un conjunto de trabajo](add-data-to-working-set.md). |
|Adición de datos a otro conjunto de trabajo | Un usuario agrega documentos de un conjunto de trabajo a un conjunto de trabajo diferente en el mismo caso.|
|Adición de datos que no son de Office 365 a un conjunto de trabajo | Un usuario carga datos que no son de Office 365 a un conjunto de trabajo. Los datos también se indizan durante este proceso. Por ejemplo, los archivos de un servidor de archivos local o un equipo cliente se cargan en un conjunto de trabajo. Para obtener más información, vea [cargar datos que no son de Office 365 en un conjunto de trabajo](load-non-office365-data.md).| 
|Adición de datos corregidos a un conjunto de trabajo | Los datos con errores de procesamiento se corrigen y se cargan de nuevo en un conjunto de trabajo. Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md). | 
|Comparar conjuntos de carga | Un usuario examina las diferencias entre los distintos conjuntos de carga en un conjunto de trabajo. Un conjunto de carga es una instancia de agregar datos a un conjunto de trabajo. Por ejemplo, si agrega los resultados de dos búsquedas distintas al mismo conjunto de trabajo, cada una de ellas representará un conjunto de carga. Para obtener más información, consulte [Manage Load sets](manage-load-sets.md). |
|Conversión de documentos censurados a PDF|Una vez que un usuario anota un documento en un conjunto de trabajo y censura una parte del mismo, puede optar por convertir el documento censurado en un archivo PDF. Esto garantiza que la parte censurada no será visible si el documento se exporta para su presentación. Para obtener más información, vea [ver documentos en un conjunto de trabajo](annotating-and-redacting-documents.md). |
|Estimar los resultados de la búsqueda | Una vez que un usuario crea y ejecuta una nueva búsqueda (o vuelve a ejecutar una búsqueda existente), la herramienta de búsqueda busca en el índice los elementos que coinciden con la consulta de búsqueda y prepara una estimación que incluye el número y el tamaño total de todos los elementos en la búsqueda, así como el número de orígenes de datos Sear Ched.  Para obtener más información, vea [recopilar datos para un caso](collecting-data-for-ediscovery.md). | 
|Preparación de datos para la exportación | Un usuario exporta documentos desde un conjunto de trabajo. Una vez finalizado el proceso de exportación, pueden descargar los datos exportados en un equipo local. Para obtener más información, vea [exportar datos de casos](exporting-data-ediscover20.md). | 
|Preparación para la resolución de errores |Cuando un usuario selecciona un archivo y crea un nuevo corrección de errores en la vista de error en la ficha **procesamiento** de un caso, el primer paso del proceso es cargar el archivo que tiene el error de procesamiento en una ubicación de almacenamiento de Azure en la nube de Microsoft. Este trabajo realiza un seguimiento del progreso del proceso de carga. Para obtener más información acerca del flujo de trabajo de corrección de errores, vea [corrección de errores al procesar datos](error-remediation.md). | 
|Preparación de la vista previa de búsqueda | Una vez que un usuario crea y ejecuta una nueva búsqueda (o vuelve a ejecutar una búsqueda existente), la herramienta de búsqueda prepara un subconjunto de elementos de muestra (que coinciden con la consulta de búsqueda) en los que se puede obtener una vista previa. La vista previa de los resultados de búsqueda ayuda a determinar la eficacia de la búsqueda.  Para obtener más información, vea [recopilar datos para un caso](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Volver a indizar los datos del custodio | Cuando agrega un custodio a un caso, todos los elementos parcialmente indizados de los orígenes de datos seleccionados del custodio se vuelven a indexar mediante un proceso denominado *indizaCión avanzada*. Este trabajo también se desencadena cuando se hace clic en **Actualizar índice** en la vista índice en la ficha **procesamiento** de un caso. Para obtener más información, consulte [indizaCión avanzada de los datos de custodios](indexing-custodian-data.md).
|Ejecución de análisis | Un usuario analiza los datos de un conjunto de trabajo mediante la ejecución de herramientas avanzadas de análisis de exhibición de documentos electrónicos, como detección de duplicados, análisis de subprocesos de correo electrónico y análisis de temas. Para obtener más información, vea [analizar datos en un conjunto de trabajo](analyzing-data-in-working-set.md). | 
|Etiquetando documentos | Este trabajo se desencadena cuando un usuario hace clic en **iniciar trabajo de etiquetado** en el **Panel etiquetado** al revisar los documentos de un conjunto de trabajo. Un usuario puede iniciar este trabajo después de etiquetar los documentos en un conjunto de trabajo y, a continuación, seleccionarlos de forma masiva en el panel ver documento. Para obtener más información, vea [etiquetar documentos en un conjunto de trabajo](tagging-documents.md). | 
|||
