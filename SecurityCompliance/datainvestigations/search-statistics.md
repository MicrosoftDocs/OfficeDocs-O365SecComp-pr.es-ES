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
# <a name="search-statistics"></a><span data-ttu-id="33ec6-102">Estadísticas de búsqueda</span><span class="sxs-lookup"><span data-stu-id="33ec6-102">Search statistics</span></span>

<span data-ttu-id="33ec6-103">Una manera eficaz de validar los resultados de la búsqueda cuando la investigación es un incidente de datos es ver las estadísticas de los resultados de la búsqueda para asegurarse de que se ajustan a sus expectativas.</span><span class="sxs-lookup"><span data-stu-id="33ec6-103">An effective way to validate your search results when investigation a data incident is to view the statistics about your search results to make sure they align with your expectations.</span></span> <span data-ttu-id="33ec6-104">Cuando una búsqueda termina de ejecutarse, se muestran las siguientes estadísticas de alto nivel bajo **Estado** en la página flotante de búsqueda de detalles:</span><span class="sxs-lookup"><span data-stu-id="33ec6-104">When a search as finished running, the following high-level statistics are displayed under **Status** on the search details flyout page:</span></span>

![Página flotante de búsqueda en detalles de statisics de búsqueda](../media/SearchDetailsFlyout.png)

- <span data-ttu-id="33ec6-106">Número estimado y tamaño de los elementos que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-106">The estimated number and size of items that matched the search criteria.</span></span>

- <span data-ttu-id="33ec6-107">El número y el tamaño de los elementos parcialmente indizados (también denominados *elementos*sin indexar) que no se pueden buscar pero que se encontraron en las ubicaciones de contenido incluidas en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-107">The number and size of partially indexed items (also called *unindexed items*) that aren't searchable but that were found in the content locations that were included in the search.</span></span>

- <span data-ttu-id="33ec6-108">El número de buzones y sitios en los que se realizó la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-108">The number of mailboxes and sites that were searched.</span></span>

<span data-ttu-id="33ec6-109">Para ver estadísticas más detalladas, haga clic en **estadísticas** en la página flotante de detalles de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-109">To view more detailed statistics, click **Statistics** on the search details flyout page.</span></span> <span data-ttu-id="33ec6-110">En la página **estadísticas de búsqueda** , puede ver el Resumen de la búsqueda, la ubicación superior que contenía los elementos que coincidían con los resultados de la búsqueda, y estadísticas detalladas sobre la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-110">On the **Search statistics** page, you can view the search summary, the top location that contained items that matched the search results, and detailed statistics about the search query.</span></span>

![Lista desplegable de estadísticas de búsqueda](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a><span data-ttu-id="33ec6-112">Resumen</span><span class="sxs-lookup"><span data-stu-id="33ec6-112">Summary</span></span>

<span data-ttu-id="33ec6-113">En la vista de **Resumen** , puede ver los resultados de la búsqueda desglosados por tipo de ubicación (por ejemplo, las ubicaciones incluyen los buzones de Exchange y los sitios de SharePoint).</span><span class="sxs-lookup"><span data-stu-id="33ec6-113">In the **Summary** view, you can see the search results broken down by location type (for example, locations include Exchange mailboxes and SharePoint sites).</span></span> <span data-ttu-id="33ec6-114">Se muestra la siguiente información para cada tipo de Ubicación:</span><span class="sxs-lookup"><span data-stu-id="33ec6-114">The following information is displayed for each location type:</span></span>

- <span data-ttu-id="33ec6-115">El número de ubicaciones que tenían elementos que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-115">The number of locations that had items that matched the search criteria.</span></span>

- <span data-ttu-id="33ec6-116">El número total de elementos de cada tipo de ubicación que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-116">The total number of items from each location type that matched the search criteria.</span></span>

- <span data-ttu-id="33ec6-117">El tamaño total de los elementos de cada tipo de ubicación que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-117">The total size of items from each location type that matched the search criteria.</span></span>

## <a name="top-locations"></a><span data-ttu-id="33ec6-118">Principales ubicaciones</span><span class="sxs-lookup"><span data-stu-id="33ec6-118">Top locations</span></span>

<span data-ttu-id="33ec6-119">En la vista de **ubicaciones superiores** , verá las ubicaciones de contenido individuales con la mayoría de los elementos que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-119">In the **Top locations** view, you see the individual content locations with the most items that matched the search criteria.</span></span> <span data-ttu-id="33ec6-120">Para cada ubicación de contenido, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="33ec6-120">For each content location, the following information is displayed:</span></span>

- <span data-ttu-id="33ec6-121">Nombre de la ubicación; la dirección de correo electrónico de los buzones y la dirección URL de los sitios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="33ec6-121">The name of the location; the email address for mailboxes and the URL for SharePoint sites</span></span>

- <span data-ttu-id="33ec6-122">El tipo de ubicación</span><span class="sxs-lookup"><span data-stu-id="33ec6-122">The location type</span></span>

- <span data-ttu-id="33ec6-123">Número de elementos que coincidieron con los criterios de búsqueda</span><span class="sxs-lookup"><span data-stu-id="33ec6-123">Number of items that matched the search criteria</span></span>

- <span data-ttu-id="33ec6-124">Tamaño total de todos los elementos que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-124">The total size of all items that matched the search criteria.</span></span>

## <a name="queries"></a><span data-ttu-id="33ec6-125">Queries</span><span class="sxs-lookup"><span data-stu-id="33ec6-125">Queries</span></span>

<span data-ttu-id="33ec6-126">En la vista **consultas** , puede ver estadísticas detalladas para cada componente de la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-126">In the **Queries** view, you can see detailed statistics for each component of the search query.</span></span> <span data-ttu-id="33ec6-127">Si usó la lista de palabras clave en la consulta de búsqueda, puede ver estadísticas mejoradas en la vista **consultas** que muestran cuántos elementos coinciden con cada palabra clave o frase de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="33ec6-127">If you used the keyword list in the search query, you can view enhanced statistics in the **Queries** view  that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="33ec6-128">Esto puede ayudarle a identificar rápidamente qué partes de la consulta son las más eficaces (y menos) efectivas.</span><span class="sxs-lookup"><span data-stu-id="33ec6-128">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> 

<span data-ttu-id="33ec6-129">La siguiente información se muestra en la vista **consultas** :</span><span class="sxs-lookup"><span data-stu-id="33ec6-129">The following information is displayed in the **Queries** view:</span></span>

 - <span data-ttu-id="33ec6-130">**Tipo de ubicación** : tipo de ubicación de contenido para las estadísticas que se muestran en la fila.</span><span class="sxs-lookup"><span data-stu-id="33ec6-130">**Location type** - The type of content location for the statistics displayed in the row.</span></span>

- <span data-ttu-id="33ec6-131">**Elemento** : esta columna mostrará uno de los siguientes valores: **Primary** o **Keyword**.</span><span class="sxs-lookup"><span data-stu-id="33ec6-131">**Part** - This column will display one of the following values: **Primary** or **Keyword**.</span></span> <span data-ttu-id="33ec6-132">**Principal** significa que la fila presenta estadísticas sobre toda la consulta; **Palabra clave** significa que las estadísticas de la fila son para uno de los componentes de consulta.</span><span class="sxs-lookup"><span data-stu-id="33ec6-132">**Primary** means the row presents statistics on the entire query; **Keyword** means the statistics in the row are for one of the query components.</span></span>

- <span data-ttu-id="33ec6-133">**Condición** : el componente de consulta real de la consulta de búsqueda a la que hace referencia la fila.</span><span class="sxs-lookup"><span data-stu-id="33ec6-133">**Condition** - The actual query component of the search query the row refers to.</span></span> <span data-ttu-id="33ec6-134">Si el valor de la columna **Part** es **principal**, se muestran las estadísticas de toda la consulta de búsqueda; Si el valor es **Keyword**, se muestran las estadísticas del componente de la consulta que se muestra en la columna **consulta** .</span><span class="sxs-lookup"><span data-stu-id="33ec6-134">If the value in the **Part** column is **Primary**, then the statistics for the entire search query are displayed; if the value is **Keyword**, then the statistics for the component of the query shown in the **Query** column are displayed.</span></span> <span data-ttu-id="33ec6-135">Por ejemplo, si se usó la lista de palabras clave, se muestran las estadísticas de una de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="33ec6-135">For example, if the keyword list was used, then the statistics one of the keywords are displayed.</span></span>

  <span data-ttu-id="33ec6-136">Estas son algunas de las cosas que debe saber sobre las estadísticas que se muestran en la columna **consultas** :</span><span class="sxs-lookup"><span data-stu-id="33ec6-136">Here are some other things to know about the statistics displayed in the **Queries** column:</span></span>
  
  - <span data-ttu-id="33ec6-137">Cuando busca todo el contenido de los buzones (sin especificar ninguna palabra clave), la consulta real es **(Size > = 0)** para que se devuelvan todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="33ec6-137">When you search for all content in mailboxes (by not specifying any keywords), the actual query is **(size >= 0)** so that all items are returned</span></span>
  
  - <span data-ttu-id="33ec6-138">Al buscar sitios de SharePoint y OneDrive, los dos componentes siguientes se agregan a la consulta de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="33ec6-138">When you search SharePoint and OneDrive sites, the two following components are added to the search query:</span></span>
    
    <span data-ttu-id="33ec6-139">**No IsExternalContent: 1** : Esto excluye el contenido de una organización de SharePoint local.</span><span class="sxs-lookup"><span data-stu-id="33ec6-139">**NOT IsExternalContent:1** - This excludes any content from an on-premises SharePoint organization</span></span>
    
    <span data-ttu-id="33ec6-140">**No isOneNotePage: 1** : excluye todos los archivos de OneNote porque serían duplicados de cualquier documento que coincida con la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-140">**NOT isOneNotePage:1** - This excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="33ec6-141">**Ubicaciones en la búsqueda** Número de ubicaciones de contenido con elementos que coinciden con la consulta de búsqueda para el elemento o la condición mostrados en la fila.</span><span class="sxs-lookup"><span data-stu-id="33ec6-141">**Locations in search** The number of content locations that had items that matched the search query for the part/condition displayed in the row.</span></span> <span data-ttu-id="33ec6-142">Tenga en cuenta que los buzones de archivo se cuentan como una ubicación independiente si contienen elementos que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="33ec6-142">Note that archive mailboxes are counted as a separate location if they contain items that match the search criteria.</span></span>

- <span data-ttu-id="33ec6-143">**Items** : número total de elementos que coinciden con los criterios de búsqueda de la parte/condición mostrada en la fila.</span><span class="sxs-lookup"><span data-stu-id="33ec6-143">**Items** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

- <span data-ttu-id="33ec6-144">**Size** : número total de elementos que coinciden con los criterios de búsqueda de la parte/condición que se muestra en la fila.</span><span class="sxs-lookup"><span data-stu-id="33ec6-144">**Size** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>