---
title: Ver las estadísticas de palabras clave para resultados de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Use la característica de estadísticas de búsqueda para mostrar y comparar estadísticas para varias búsquedas de contenido en Office 365 seguridad &amp; centro de cumplimiento. También puede configurar la lista de palabras clave al crear o editar una consulta de búsqueda para obtener estadísticas mejoradas que muestran cuántos elementos coincidieron con cada palabra clave o frase de palabras clave.
ms.openlocfilehash: 0f0258f228e296e48def8de16aabc068901dffc7
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "27209811"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Ver las estadísticas de palabras clave para resultados de búsqueda de contenido

Después de crear y ejecutar una búsqueda de contenido, puede ver estadísticas sobre los resultados de búsqueda estimado. Esto incluye un resumen de los resultados de búsqueda (similares al resumen de los resultados de búsqueda estimado que se muestra en el panel de detalles), las estadísticas de consulta, como el número de ubicaciones de contenido con los elementos que coinciden con la consulta de búsqueda y el nombre de las ubicaciones de contenido que dispone de los elementos más coincidentes. Puede mostrar estadísticas para las búsquedas de contenido de uno o más. Esto le permite para comparar los resultados para varias búsquedas de forma rápida y tomar decisiones acerca de la eficacia de las consultas de búsqueda.
  
Además, puede configurar las búsquedas nuevas y existentes para devolver las estadísticas de cada palabra clave en una consulta de búsqueda. Esto le permite comparar el número de resultados para cada palabra clave en una consulta y para comparar las estadísticas de palabra clave de varias búsquedas.
  
También puede descargar las estadísticas de búsqueda y palabras clave a un archivo CSV. Esto le permite usar las características de ordenación y filtradas en Excel para comparar los resultados y preparar informes para los resultados de búsqueda.
  
## <a name="get-statistics-for-content-searches"></a>Obtener las estadísticas de búsquedas de contenido

Para mostrar las estadísticas para las búsquedas de contenido:
  
1. En la seguridad de Office 365 &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> **búsqueda de contenido**.
    
2. En la lista de búsquedas, seleccione uno o más de las búsquedas y, a continuación, haga clic en **estadísticas de búsqueda**![botón estadísticas de búsqueda](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png).
    
    ![Seleccione varias búsquedas y, a continuación, haga clic en estadísticas de búsqueda](media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. En la página de **estadísticas de búsqueda** , haga clic en uno de los siguientes vínculos para mostrar estadísticas sobre las búsquedas seleccionadas. 
    
    **Resumen**
    
    Esta página muestra estadísticas similares a los que se muestra en el panel de detalles en la página de **búsqueda de contenido** . Se muestran las estadísticas de todas las búsquedas seleccionadas. Tenga en cuenta que también puede ejecutar volver a las búsquedas seleccionadas desde esta página para actualizar las estadísticas. 
    
    ![Resumen de las estadísticas para las búsquedas seleccionadas](media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    r. el nombre de la búsqueda de contenido. Como se ha indicado anteriormente, puede mostrar y comparar las estadísticas de varias búsquedas.
    
    b. el tipo de ubicación de contenido que se realizó la búsqueda. Cada fila muestra las estadísticas de buzones de correo, sitios y las carpetas públicas de la búsqueda especificada.
    
    c. el número de ubicaciones de contenido que contiene los elementos que coinciden con la consulta de búsqueda. Para los buzones de correo, esta estadística también incluye el número de buzones de archivo que contienen elementos que coinciden con la consulta de búsqueda.
    
    d. el número total de elementos de especificado todas las ubicaciones de contenido que coinciden con la consulta de búsqueda. Algunos ejemplos de tipos de elemento son mensajes de correo electrónico, los elementos de calendario y documentos. Si un elemento contiene varias instancias de una palabra clave que se busca, se sólo cuenta una vez en el número total de elementos. Por ejemplo, si está buscando las palabras "stock" o "loterías" y un mensaje de correo electrónico contiene tres instancias de la palabra "stock", se sólo cuenta una vez en la columna de **los elementos** . 
    
    e. el tamaño total de todos los elementos que se han encontrado en la ubicación del contenido especificada que coinciden con la consulta de búsqueda. 
    
    **Consultas**
    
    Esta página muestra estadísticas sobre la consulta de búsqueda.
    
    ![Estadísticas de consulta de búsqueda para las búsquedas seleccionadas](media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    r. el nombre de la búsqueda de contenido que la fila contiene las estadísticas de consulta de.
    
    b. el tipo de ubicación de contenido que son aplicables a las estadísticas de consultas.
    
    c. esta columna indica qué parte de la consulta de búsqueda son aplicables a las estadísticas. **Principal** indica la consulta de búsqueda completa. Si utiliza una lista de palabras clave al crear o editar una consulta de búsqueda, las estadísticas de cada componente de la consulta se incluyen en esta tabla. Vea la sección [obtener estadísticas de palabras clave para las búsquedas de contenido](#get-keyword-statistics-for-content-searches) en este artículo para obtener más información. 
    
    d. esta columna contiene la búsqueda real de consultas que se ejecutan mediante la herramienta de búsqueda de contenido. Tenga en cuenta que la herramienta agrega automáticamente algunos componentes adicionales a la consulta que cree. 

    - Cuando se busca para todas las de contenido en los buzones de correo (si no se especifica ninguna palabra clave), la consulta de palabra clave real es `size>=0` para que se devuelvan todos los elementos. 
    
     - Al buscar SharePoint Online y OneDrive para sitios de negocio, se agregan los siguientes dos componentes:
    
          **No IsExternalContent:1** - excluye cualquier contenido de una organización de SharePoint local. 
    
          **No IsOneNotePage:1** - excluye todos los archivos de OneNote debido a que estos sería duplicados de cualquier documento que coincide con la consulta de búsqueda. 

    
    e. el número de las ubicaciones de contenido (especificado por la ** tipo de ubicación ** columna) que contienen elementos que coinciden con la consulta de búsqueda aparece en la columna de la **consulta** . 
    
    f. el número de elementos (desde la ubicación del contenido especificado) que coinciden con la consulta de búsqueda aparece en la columna de la **consulta** . Como se explica anteriormente, si un elemento contiene varias instancias de una palabra clave que se busca, se cuenta como una sola en esta columna. 
    
    g. el tamaño total de todos los elementos que se han encontrado (en la ubicación del contenido especificada) que coinciden con la consulta de búsqueda en la columna de la **consulta** . 
    
    **Ubicaciones principales**
    
    Esta página muestra estadísticas sobre el número de elementos que coinciden con la consulta de búsqueda en cada ubicación del contenido que se realizó la búsqueda. Se muestran las ubicaciones de la parte superior de 1.000. Si ver las estadísticas de varias búsquedas, se muestran las ubicaciones de 1.000 superiores de cada búsqueda. Tenga en cuenta que una ubicación de contenido no está incluida en esta página si no contiene los elementos que coinciden con la consulta de búsqueda.
    
    ![Estadísticas sobre el número de elementos que se encuentran en las ubicaciones de contenido que se desea buscar](media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    r. el nombre de la ubicación del contenido.
    
    b. el tipo de ubicación de contenido que son aplicables a las estadísticas de ubicación.
    
    c. hay columnas para cada búsqueda que se van a mostrar las estadísticas de. Esta columna muestra el número (y el tamaño total) de los elementos que coinciden con la consulta de búsqueda en cada ubicación de contenido. Tenga en cuenta que cuando se van a mostrar las estadísticas de varias búsquedas, "NA" en esta columna indica que la ubicación del contenido no se incluyen en la búsqueda. 

## <a name="get-keyword-statistics-for-content-searches"></a>Obtener estadísticas de palabras clave para las búsquedas de contenido

Como anterior se explica, muestra la página de **consultas de** la consulta de búsqueda y el número (y tamaño) de los elementos que coinciden con la consulta. Si utiliza una lista de palabras clave al crear o editar una consulta de búsqueda, puede obtener estadísticas mejoradas que muestran el número de elementos que coinciden con cada palabra clave o frase de palabras clave. Esto puede ayudarle a identificar rápidamente qué partes de la consulta son los más (y menos) eficaces. Por ejemplo, si una palabra clave devuelve un gran número de elementos, es posible que elija refinar la consulta de palabras clave para restringir los resultados de búsqueda. Puede configurar una lista de palabras clave al crear o editar una búsqueda de contenido. 




  
Para crear una lista de palabras clave y ver las estadísticas de palabra clave para una búsqueda de contenido:
  
1. En la seguridad de Office 365 &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> **búsqueda de contenido**.
    
2. En la lista de búsquedas de contenido, haga clic en y una búsqueda y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
3. Haga clic en **consulta** y, a continuación, hacer lo siguiente: 
    
    ![Haga clic en la casilla de verificación Mostrar lista de palabras clave y escriba una palabra clave en cada fila](media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    r. Haga clic en la casilla de verificación **Mostrar la lista de palabras clave** . 
    
    b. Escriba una palabra clave o la fase de palabra clave en una fila en la tabla de palabras clave. Por ejemplo, escriba **presupuesto** en la primera fila y, a continuación, escriba **seguridad** en la segunda fila. 
    
4. Después de agregar las palabras clave que desea buscar y obtener las estadísticas de, haga clic en **Buscar** para ejecutar la búsqueda revisada. 
    
5. Una vez completada la búsqueda, seleccione en la lista de búsquedas y, a continuación, haga clic en **estadísticas de búsqueda** ![botón estadísticas de búsqueda](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png). También puede mostrar y comparar las estadísticas de palabra clave de varias búsquedas.
    
6. En la página de **estadísticas de búsqueda** , haga clic en **consulta** para mostrar las estadísticas de palabra clave para las búsquedas seleccionadas. 
    
    ![Se muestran las estadísticas de cada palabra clave para las búsquedas seleccionadas](media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Como se muestra en la captura de pantalla anterior, se muestran las estadísticas de cada palabra clave; Esto incluye: 
    
    - Las estadísticas de palabra clave para cada tipo de ubicación de contenido incluido en la búsqueda.
    
    - La consulta de búsqueda reales para cada palabra clave, que incluye las condiciones de la consulta de búsqueda. 
    
    - La consulta de búsqueda completa (identificado como **principal** en la columna **parte** ) y las estadísticas de la consulta completa. Tenga en cuenta que estos son las mismas que se muestra en la página de **Resumen** de estadísticas. 

> [!NOTE]
> Para ayudar a reducir los problemas de listas de palabras clave de gran tamaño, ahora está limitado a un máximo de 20 filas de la lista de palabras clave de una consulta de búsqueda.
