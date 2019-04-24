---
title: Buscar datos en una investigación
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
ms.openlocfilehash: 5f52f26c4443addd0e108794e1d3635a9b8efb98
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258058"
---
# <a name="search-for-data-in-an-investigation"></a>Buscar datos en una investigación

En la ficha **Buscar** de una investigación de datos, puede buscar datos confidenciales en ubicación incorrecta, confidenciales o confidenciales en ubicaciones de contenido en Office 365 con palabras clave y condiciones. 

Después de ejecutar una búsqueda, puede ver las estadísticas de los elementos devueltos por la búsqueda, como las ubicaciones de contenido que tienen la mayoría de los elementos que coinciden con la consulta de búsqueda. También puede obtener una vista previa de un subconjunto de los resultados. Una vez que haya identificado el conjunto de documentos que desea investigar, puede Agregar los resultados de la búsqueda a un conjunto de evidencias para procesarlos y analizarlos.

## <a name="create-a-search"></a>Create a search

1. En una investigación, haga clic en la ficha **búsquedas** y, a continuación, haga clic en **nueva búsqueda**. 

    Se muestra un asistente que le guiará por el proceso de creación de una búsqueda.

2. Escriba un nombre de búsqueda y una descripción opcional para la búsqueda.

3. Definir los criterios de búsqueda. Puede agregar condiciones para la búsqueda con las tarjetas de condición predefinidas o mediante el uso de nombres de propiedades de búsqueda en la consulta de palabras clave. Para obtener más información, vea [crear consultas de búsqueda](build-search-queries.md).

4. Elija las ubicaciones de contenido (orígenes de datos) para buscar. Puede limitar la búsqueda seleccionando las ubicaciones de contenido de personas de interés específicas (si agregó cualquiera a la investigación). Si ha agregado personas de interés a la investigación, puede agregarlas siguiendo los pasos descritos en [Manage People of Interest](manage-people-of-interest.md#add-people-of-interest).
 
    En algunos casos, es posible que primero necesite buscar en todas las ubicaciones de contenido de su organización; como alternativa, puede que necesite buscar ubicaciones que no pertenezcan a una persona específica. En estos escenarios, puede elegir buscar en toda la organización o en todas las ubicaciones de los servicios específicos de Office 365 (como Exchange, SharePoint, OneDrive de la empresa o Teams).

5. Guarde y ejecute la búsqueda.

Una vez creada la búsqueda, se muestra una página de control flotante con detalles sobre la búsqueda. Tenga en cuenta que los botones **estadísticas** y **vista previa** aparecen inicialmente atenuados porque la búsqueda no se ha completado. Puede realizar un seguimiento del progreso mediante la supervisión de la columna **Estado** en la ficha **búsquedas** .

## <a name="view-statistics-and-search-results"></a>Ver estadísticas y resultados de la búsqueda

Después de crear e iniciar una búsqueda de investigación de datos, la herramienta usa los criterios de búsqueda (la consulta de búsqueda y las ubicaciones de contenido) que ha definido y busca en un índice en el servicio activo los elementos que coinciden con los criterios de búsqueda. Hay tres componentes de una búsqueda que se devuelven cuando finaliza la búsqueda: 

- **Estimate** : dado que la búsqueda solo busca en un índice (en lugar de en las ubicaciones de contenido reales), los resultados de una búsqueda son una estimación (en función de lo que se haya encontrado en el índice que coincide con los resultados de la búsqueda). Se muestra un resumen de la estimación en la página desplegable de búsqueda en **Estado**. Tenga en cuenta que el estado del proceso de estimación para una búsqueda se muestra en la ficha **búsquedas** de la columna **Estado de estimación** . Una vez finalizada la estimación de la búsqueda, este estado se establece en **correcto**.

- **Estadísticas** : estadísticas proporcionan información más detallada sobre los resultados de la búsqueda. Esto incluye lo siguiente:

    - Resumen: estadísticas similares a los resultados de la estimación de búsqueda que se muestran en la página de control flotante.
    - Ubicaciones principales: estadísticas sobre el número de elementos que coinciden con la consulta de búsqueda en cada ubicación de contenido en la que se ha buscado. 
    - Consultas: estadísticas detalladas sobre la consulta de búsqueda, incluido el número de elementos que coinciden con cada condición en una consulta de búsqueda.

    Haga clic en **estadísticas** en la página de control flotante para ver estas estadísticas. Tenga en cuenta que este botón está inactivo hasta que el valor del **Estado Estimado** en la ficha **búsquedas** está establecido en **correcto**. Para obtener más información acerca de las estadísticas de búsqueda, vea [estadísticas de búsqueda](search-statistics.md).

- **Vista previa** : una vez completada la búsqueda, puede ver los elementos reales de un subconjunto de muestra de los resultados de la búsqueda que devuelve la búsqueda. Puede ver en la vista nativa del tipo de elemento, también puede ver los metadatos del elemento. Esta es una buena forma de determinar rápidamente si los resultados de la búsqueda son lo que esperaba o si necesita editar la búsqueda y volver a ejecutarla. Haga clic en **vista previa** en la página de control flotante para ver los elementos de los resultados de la búsqueda. Tenga en cuenta que este botón está inactivo hasta que el valor del **Estado de vista previa** en la ficha **búsquedas** está establecido en **correcto**.
 
> [!NOTE]
> Los valores de estado de las columnas **Estado de estimación** y **Estado de vista previa** en la ficha **búsquedas** se han **enviado**, **en curso**y **correctos**. Si hay un error con la búsqueda, se muestra el estado de **error** .

## <a name="add-search-results-to-evidence"></a>Agregar resultados de búsqueda a la evidencia

Cuando esté satisfecho con los resultados de una búsqueda y esté listo para analizar y corregir los resultados de la búsqueda, puede agregarlos a un conjunto de evidencias de la investigación. Cuando se agregan elementos a un conjunto de evidencias en la ficha **evidencia** , se producen las dos siguientes cosas:

- Todos los elementos de los resultados de la búsqueda se copian del origen de datos en el servicio activo y se copian en una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

- Todos los elementos (incluido el contenido y los metadatos) se vuelven a indizar para que todos los datos del conjunto de evidencias se puedan buscar durante la investigación. Volver a indizar los datos da como resultado búsquedas exhaustivas y muy rápidas cuando busca los datos en el conjunto de evidencias durante la investigación.

Una de las ventajas de copiar los datos activos en un conjunto de evidencias en Azure es que, para incidentes críticos o sensibles al tiempo, puede contener rápidamente el daño al eliminar inmediatamente contenido sospechoso en el origen de datos original en el servicio en directo y, a continuación, investigar el incidente mediante el análisis de la evidencia que se ha copiado en el entorno en cuarentena de la ubicación de almacenamiento de Azure. 

Copiar los datos originales en el conjunto de evidencias también facilita la investigación al proporcionarle herramientas de análisis avanzadas, como detección de temas, detección de casi duplicados y identificación de subprocesos de correo electrónico.

Si es necesario, también puede agregar datos de orígenes de datos que no sean de Office 365 a un conjunto de evidencias para que se almacenen junto con los datos recopilados de Office 365.

Para agregar datos a un conjunto con evidencia, seleccione una búsqueda en la ficha **búsquedas** y, a continuación, haga clic en **Agregar resultados a evidencias** en la página de flotante. Tenga en cuenta que puede agregar datos a un conjunto de evidencias existente o crear un nuevo conjunto de evidencias al instante.

### <a name="tracking-the-progress-of-adding-search-results-to-evidence"></a>Seguimiento del progreso de agregar resultados de búsqueda a la evidencia

Agregar datos a un conjunto de evidencias es un proceso de ejecución prolongada. El proceso incluye la recopilación de elementos del origen de datos original de Office 365 (por ejemplo, de buzones y sitios), copiándolos en la ubicación de almacenamiento de Azure (este proceso de ** copia también se denomina ingesta) y, a continuación, vuelva a indizar los elementos. Puede realizar el seguimiento del progreso en la pestaña **trabajos** o en la pestaña **búsquedas** de la columna **datos agregados a evidencias** . Una vez finalizado el procesamiento del procesamiento de pruebas, puede ir a la pestaña **evidencia** , hacer clic en el conjunto de evidencias y, a continuación, iniciar la investigación buscando, revisando, etiquetando y exportando los datos relevantes según sea necesario.