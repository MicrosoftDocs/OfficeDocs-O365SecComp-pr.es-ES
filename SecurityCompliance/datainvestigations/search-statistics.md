---
title: Estadísticas de búsqueda
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
ms.openlocfilehash: 986c3f3cbb19cd0f66b18db274e68a3bf8414952
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030508"
---
# <a name="search-statistics"></a>Estadísticas de búsqueda

Una manera eficaz de validar los resultados de la búsqueda cuando la investigación es un incidente de datos es ver las estadísticas de los resultados de la búsqueda para asegurarse de que se ajustan a sus expectativas. Cuando una búsqueda termina de ejecutarse, se muestran las siguientes estadísticas de alto nivel bajo **Estado** en la página flotante de búsqueda de detalles:

![Página flotante de búsqueda en detalles de statisics de búsqueda](../media/SearchDetailsFlyout.png)

- Número estimado y tamaño de los elementos que coinciden con los criterios de búsqueda.

- El número y el tamaño de los elementos parcialmente indizados (también denominados *elementos*sin indexar) que no se pueden buscar pero que se encontraron en las ubicaciones de contenido incluidas en la búsqueda.

- El número de buzones y sitios en los que se realizó la búsqueda.

Para ver estadísticas más detalladas, haga clic en **estadísticas** en la página flotante de detalles de búsqueda. En la página **estadísticas de búsqueda** , puede ver el Resumen de la búsqueda, la ubicación superior que contenía los elementos que coincidían con los resultados de la búsqueda, y estadísticas detalladas sobre la consulta de búsqueda.

![Lista desplegable de estadísticas de búsqueda](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a>Resumen

En la vista de **Resumen** , puede ver los resultados de la búsqueda desglosados por tipo de ubicación (por ejemplo, las ubicaciones incluyen los buzones de Exchange y los sitios de SharePoint). Se muestra la siguiente información para cada tipo de Ubicación:

- El número de ubicaciones que tenían elementos que coinciden con los criterios de búsqueda.

- El número total de elementos de cada tipo de ubicación que coinciden con los criterios de búsqueda.

- El tamaño total de los elementos de cada tipo de ubicación que coinciden con los criterios de búsqueda.

## <a name="top-locations"></a>Principales ubicaciones

En la vista de **ubicaciones superiores** , verá las ubicaciones de contenido individuales con la mayoría de los elementos que coinciden con los criterios de búsqueda. Para cada ubicación de contenido, se muestra la siguiente información:

- Nombre de la ubicación; la dirección de correo electrónico de los buzones y la dirección URL de los sitios de SharePoint

- El tipo de ubicación

- Número de elementos que coincidieron con los criterios de búsqueda

- Tamaño total de todos los elementos que coinciden con los criterios de búsqueda.

## <a name="queries"></a>Queries

En la vista **consultas** , puede ver estadísticas detalladas para cada componente de la consulta de búsqueda. Si usó la lista de palabras clave en la consulta de búsqueda, puede ver estadísticas mejoradas en la vista **consultas** que muestran cuántos elementos coinciden con cada palabra clave o frase de palabras clave. Esto puede ayudarle a identificar rápidamente qué partes de la consulta son las más eficaces (y menos) efectivas. 

La siguiente información se muestra en la vista **consultas** :

 - **Tipo de ubicación** : tipo de ubicación de contenido para las estadísticas que se muestran en la fila.

- **Elemento** : esta columna mostrará uno de los siguientes valores: **Primary** o **Keyword**. **Principal** significa que la fila presenta estadísticas sobre toda la consulta; **Palabra clave** significa que las estadísticas de la fila son para uno de los componentes de consulta.

- **Condición** : el componente de consulta real de la consulta de búsqueda a la que hace referencia la fila. Si el valor de la columna **Part** es **principal**, se muestran las estadísticas de toda la consulta de búsqueda; Si el valor es **Keyword**, se muestran las estadísticas del componente de la consulta que se muestra en la columna **consulta** . Por ejemplo, si se usó la lista de palabras clave, se muestran las estadísticas de una de las palabras clave.

  Estas son algunas de las cosas que debe saber sobre las estadísticas que se muestran en la columna **consultas** :
  
  - Cuando busca todo el contenido de los buzones (sin especificar ninguna palabra clave), la consulta real es **(Size > = 0)** para que se devuelvan todos los elementos.
  
  - Al buscar sitios de SharePoint y OneDrive, los dos componentes siguientes se agregan a la consulta de búsqueda:
    
    **No IsExternalContent: 1** : Esto excluye el contenido de una organización de SharePoint local.
    
    **No isOneNotePage: 1** : excluye todos los archivos de OneNote porque serían duplicados de cualquier documento que coincida con la consulta de búsqueda.

- **Ubicaciones en la búsqueda** Número de ubicaciones de contenido con elementos que coinciden con la consulta de búsqueda para el elemento o la condición mostrados en la fila. Tenga en cuenta que los buzones de archivo se cuentan como una ubicación independiente si contienen elementos que coinciden con los criterios de búsqueda.

- **Items** : número total de elementos que coinciden con los criterios de búsqueda de la parte/condición mostrada en la fila.

- **Size** : número total de elementos que coinciden con los criterios de búsqueda de la parte/condición que se muestra en la fila.