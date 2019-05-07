---
title: Administrar trabajos en la exhibición avanzada de documentos electrónicos
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
ms.openlocfilehash: 4d306f6f1a37fad0aa5e3f92cafdb29b1ea37d1c
ms.sourcegitcommit: 25595bc8fae96bc23b7b6d7102a22f37878987c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33641616"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Administrar trabajos en la exhibición avanzada de documentos electrónicos

Esta es una lista de los trabajos (que suelen ser procesos de larga duración) cuyo seguimiento se realiza en la ficha **trabajos** de un caso en eDiscovery avanzado. Estas tareas se desencadenan por acciones del usuario al usar y administrar casos.

| Tipo de trabajo           | Descripción     |
| :----------------- | :----------     |
|Adición de datos a un conjunto de revisión | Un usuario agrega los resultados de una búsqueda a un conjunto de revisión. Este trabajo consta de dos trabajos secundarios: </br> </br>• **GatheringItems** : se genera una lista de elementos que coinciden con la consulta de búsqueda (y el origen de datos de Office 365 en el que se encuentran). </br>• **Indización de &** de ingesta: los elementos que coinciden con la consulta de búsqueda se copian en una ubicación de almacenamiento de Azure (en un proceso denominado ingesta) y, a continuación, se vuelven a indizar los elementos en la ubicación de almacenamiento de Azure. ** Este nuevo índice se usa al consultar y analizar elementos en el conjunto de datos. </br></br>Para obtener más información, vea [Agregar resultados de búsqueda a un conjunto de revisión](add-data-to-review-set.md). |
|Adición de datos a otro conjunto de revisión | Un usuario agrega documentos de un conjunto de revisión a un conjunto de revisión diferente en el mismo caso. Para obtener más información, vea [Agregar datos a un conjunto de revisión desde otro conjunto de revisión](add-data-to-review-set-from-another-review-set.md).|
|Adición de datos que no son de Office 365 a un conjunto de revisión | Un usuario carga datos que no son de Office 365 a un conjunto de revisión. Los datos también se indizan durante este proceso. Por ejemplo, los archivos de un servidor de archivos local o un equipo cliente se cargan en un conjunto de revisión. Para obtener más información, vea [cargar datos que no son de Office 365 en un conjunto de revisión](load-non-office365-data.md).| 
|Adición de datos corregidos a un conjunto de revisión | Los datos con errores de procesamiento se corrigen y se cargan de nuevo en un conjunto de revisión. Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md). | 
|Comparar conjuntos de carga | Un usuario examina las diferencias entre los distintos conjuntos de carga en un conjunto de revisión. Un conjunto de carga es una instancia de adición de datos a un conjunto de revisión. Por ejemplo, si agrega los resultados de dos búsquedas distintas al mismo conjunto de revisión, cada una de ellas representará un conjunto de carga. Para obtener más información, consulte [Manage Load sets](manage-load-sets.md). |
|Conversión de documentos censurados a PDF|Una vez que un usuario anota un documento en un conjunto de revisiones y censura una parte del mismo, puede optar por convertir el documento censurado en un archivo PDF. Esto garantiza que la parte censurada no será visible si el documento se exporta para su presentación. Para obtener más información, vea [ver documentos en un conjunto de revisión](annotating-and-redacting-documents.md). |
|Estimar los resultados de la búsqueda | Una vez que un usuario crea y ejecuta una nueva búsqueda (o vuelve a ejecutar una búsqueda existente), la herramienta de búsqueda busca en el índice los elementos que coinciden con la consulta de búsqueda y prepara una estimación que incluye el número y el tamaño total de todos los elementos en la búsqueda, así como el número de orígenes de datos Sear ched.  Para obtener más información, vea [recopilar datos para un caso](collecting-data-for-ediscovery.md). | 
|Preparación de datos para la exportación | Un usuario exporta documentos desde un conjunto de revisión. Una vez finalizado el proceso de exportación, pueden descargar los datos exportados en un equipo local. Para obtener más información, vea [exportar datos de casos](exporting-data-ediscover20.md). | 
|Preparación para la resolución de errores |Cuando un usuario selecciona un archivo y crea un nuevo corrección de errores en la vista de error en la ficha **procesamiento** de un caso, el primer paso del proceso es cargar el archivo que tiene el error de procesamiento en una ubicación de almacenamiento de Azure en la nube de Microsoft. Este trabajo realiza un seguimiento del progreso del proceso de carga. Para obtener más información acerca del flujo de trabajo de corrección de errores, vea [corrección de errores al procesar datos](error-remediation.md). | 
|Preparación de la vista previa de búsqueda | Una vez que un usuario crea y ejecuta una nueva búsqueda (o vuelve a ejecutar una búsqueda existente), la herramienta de búsqueda prepara un subconjunto de elementos de muestra (que coinciden con la consulta de búsqueda) en los que se puede obtener una vista previa. La vista previa de los resultados de búsqueda ayuda a determinar la eficacia de la búsqueda.  Para obtener más información, vea [recopilar datos para un caso](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Volver a indizar los datos del custodio | Cuando agrega un custodio a un caso, todos los elementos parcialmente indizados de los orígenes de datos seleccionados del custodio se vuelven a indexar mediante un proceso denominado *indización avanzada*. Este trabajo también se desencadena cuando se hace clic en **Actualizar índice** en la vista índice en la ficha **procesamiento** de un caso. Para obtener más información, consulte [indización avanzada de los datos de custodios](indexing-custodian-data.md).
|Ejecución de análisis | Un usuario analiza los datos en un conjunto de revisión mediante la ejecución de herramientas avanzadas de análisis de exhibición de documentos electrónicos, como detección de duplicados, análisis de subprocesos de correo electrónico y análisis de temas. Para obtener más información, consulte [analizar datos en un conjunto de revisión](analyzing-data-in-review-set.md). | 
|Etiquetando documentos | Este trabajo se desencadena cuando un usuario hace clic en **iniciar trabajo de etiquetado** en el **Panel etiquetado** al revisar los documentos de un conjunto de revisión. Un usuario puede iniciar este trabajo después de etiquetar los documentos en un conjunto de revisión y, a continuación, seleccionarlos de forma masiva en el panel ver documento. Para obtener más información, vea [etiquetar documentos en un conjunto de revisión](tagging-documents.md). | 
|||


## <a name="job-status"></a>Estado del trabajo

En la tabla siguiente se describen los distintos Estados de los trabajos.

| Estado           | Descripción     |
| :----------------- | :----------     |
| Submitted | Se ha creado un nuevo trabajo.  La fecha y la hora en las que se envió el trabajo se muestran en la columna **creado** de la ficha **trabajos** . |
| Error de envío | Error en el envío del trabajo.  Intente volver a ejecutar la acción que desencadenó el trabajo. |
| En curso | El trabajo está en curso, puede supervisar el progreso del trabajo en la pestaña **trabajos** . |
| Se ejecuta correctamente | El trabajo se ha completado correctamente. La fecha y la hora en que se completó el trabajo se muestran en la columna **completado** de la ficha **trabajos** . |
| Parcialmente correcta | El trabajo se ha realizado parcialmente correctamente. |
| Failed | Error en el trabajo.  Intente volver a ejecutar la acción que desencadenó el trabajo. Si se produce un error en el trabajo por segunda vez, le recomendamos que se ponga en contacto con el soporte técnico de Microsoft y proporcione la información de soporte técnico del trabajo. |
