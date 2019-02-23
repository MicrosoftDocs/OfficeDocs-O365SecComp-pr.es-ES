---
title: Recopilar datos para un caso en eDiscovery avanzado (versión preliminar)
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2e9e7836a2dc777410b88ffac1aea0c5137b7b89
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219000"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="06956-102">Recopilar datos para un caso en eDiscovery avanzado (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="06956-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="06956-p101">Una vez que haya identificado los custodios y los orígenes de datos que sean de interés para su caso, es el momento de identificar el conjunto de documentos en los que profundizar. Puede usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos (versión preliminar) para identificarlos de las instalaciones y las que no son de custodia en Office 365.</span><span class="sxs-lookup"><span data-stu-id="06956-p101">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into. You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="06956-p102">Después de ejecutar una búsqueda, podrá ver las estadísticas de los elementos recuperados, como las ubicaciones en las que la mayoría de los elementos coinciden con la consulta de búsqueda. También puede obtener una vista previa de un subconjunto de los resultados. Cuando haya identificado el conjunto de documentos que desea examinar con más detalle, puede Agregar los resultados de la búsqueda a un conjunto de trabajo para recopilar y procesar.</span><span class="sxs-lookup"><span data-stu-id="06956-p102">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query. You can also preview a subset of the results. When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="06956-108">Crear una búsqueda</span><span class="sxs-lookup"><span data-stu-id="06956-108">Create a search</span></span>

<span data-ttu-id="06956-p103">Si hace clic en **nueva búsqueda** en la ficha **búsquedas** , se iniciará un asistente que le guiará a través de la creación de una búsqueda. Para obtener información detallada sobre cómo crear una búsqueda, vea [crear una búsqueda para recopilar datos](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="06956-p103">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search. For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="06956-p104">Una vez creada la búsqueda, se muestra una página de control flotante con los detalles. Tenga en cuenta que los botones **estadísticas** y **vista previa** aparecen inicialmente atenuados porque la búsqueda todavía no se ha completado. Puede realizar un seguimiento del progreso de la búsqueda en la ficha **búsquedas** .</span><span class="sxs-lookup"><span data-stu-id="06956-p104">After a search is created, a flyout page with details is displayed. Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet. You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="06956-114">Ver los resultados de la búsqueda y las estadísticas</span><span class="sxs-lookup"><span data-stu-id="06956-114">View search results and statistics</span></span>
<span data-ttu-id="06956-p105">Hay dos componentes de una búsqueda de contenido: Statistics (Estimations) y preView. Cuando se completen todos estos componentes, verá que el estado mostrado en las columnas correspondientes de la ficha **búsquedas** cambia desde **enviado** a **en curso** a **completado**.</span><span class="sxs-lookup"><span data-stu-id="06956-p105">There are two components of a content search: Statistics (Estimates) and Preview. As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="06956-p106">Una vez completada la estimación de búsqueda, haga clic en la búsqueda para mostrar la página de control flotante, que mostrará algunas estadísticas de alto nivel sobre los resultados de la búsqueda. En este momento, el botón **estadísticas** estará activo. Puede hacer clic en él para ver las estadísticas de búsqueda, como:</span><span class="sxs-lookup"><span data-stu-id="06956-p106">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search. At this point, the **Statistics** button will be active. You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="06956-120">Resumen</span><span class="sxs-lookup"><span data-stu-id="06956-120">Summary</span></span>
- <span data-ttu-id="06956-121">Principales ubicaciones</span><span class="sxs-lookup"><span data-stu-id="06956-121">Top locations</span></span>
- <span data-ttu-id="06956-122">Peticiones</span><span class="sxs-lookup"><span data-stu-id="06956-122">Queries</span></span>
- <span data-ttu-id="06956-123">Refinadores</span><span class="sxs-lookup"><span data-stu-id="06956-123">Refiners</span></span>

<span data-ttu-id="06956-124">Para obtener más información acerca de las estadísticas de búsqueda, vea [estadísticas de búsqueda](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="06956-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="06956-p107">Una vez completada la vista previa, el botón **vista previa** estará activo. Haga clic en él para obtener una vista previa de un subconjunto muestreado de los resultados.</span><span class="sxs-lookup"><span data-stu-id="06956-p107">Once preview is completed, the **Preview** button will be active. Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="06956-127">Adición de resultados de búsqueda a un conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="06956-127">Adding search results to a working set</span></span>

<span data-ttu-id="06956-p108">Cuando esté listo para recopilar y procesar los resultados completos de una búsqueda, puede hacerlo si lo agrega a un conjunto de trabajo. Para obtener más información, consulte [Agregar datos a un conjunto de trabajo](add-data-to-working-set.md).</span><span class="sxs-lookup"><span data-stu-id="06956-p108">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set. For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 