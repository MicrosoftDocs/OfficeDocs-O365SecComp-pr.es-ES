---
title: Recopilar datos para un caso en eDiscovery avanzado
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 091d6f8835ae1aae2f075f0b510954255c3a6a5c
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703843"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="b5242-102">Recopilar datos para un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="b5242-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="b5242-103">Una vez que haya identificado los custodios y los orígenes de datos que sean de interés para su caso, es el momento de identificar el conjunto de documentos en los que profundizar.</span><span class="sxs-lookup"><span data-stu-id="b5242-103">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="b5242-104">Puede usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos para identificarlos de las instalaciones y las que no son de custodia en Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5242-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="b5242-105">Después de ejecutar una búsqueda, podrá ver las estadísticas de los elementos recuperados, como las ubicaciones en las que la mayoría de los elementos coinciden con la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b5242-105">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="b5242-106">También puede obtener una vista previa de un subconjunto de los resultados.</span><span class="sxs-lookup"><span data-stu-id="b5242-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="b5242-107">Cuando haya identificado el conjunto de documentos que desea examinar con más detalle, puede Agregar los resultados de la búsqueda a un conjunto de revisión para recopilar y procesar.</span><span class="sxs-lookup"><span data-stu-id="b5242-107">When you've identified the set of documents that want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="b5242-108">Create a search</span><span class="sxs-lookup"><span data-stu-id="b5242-108">Create a search</span></span>

<span data-ttu-id="b5242-109">Si hace clic en **nueva búsqueda** en la ficha **búsquedas** , se iniciará un asistente que le guiará a través de la creación de una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b5242-109">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="b5242-110">Para obtener información detallada sobre cómo crear una búsqueda, vea [crear una búsqueda para recopilar datos](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="b5242-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="b5242-111">Una vez creada la búsqueda, se muestra una página de control flotante con los detalles.</span><span class="sxs-lookup"><span data-stu-id="b5242-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="b5242-112">Tenga en cuenta que los botones **estadísticas** y **vista previa** aparecen inicialmente atenuados porque la búsqueda todavía no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="b5242-112">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet.</span></span> <span data-ttu-id="b5242-113">Puede realizar un seguimiento del progreso de la búsqueda en la ficha **búsquedas** .</span><span class="sxs-lookup"><span data-stu-id="b5242-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="b5242-114">Ver los resultados de la búsqueda y las estadísticas</span><span class="sxs-lookup"><span data-stu-id="b5242-114">View search results and statistics</span></span>

<span data-ttu-id="b5242-115">Hay dos componentes de una búsqueda de contenido: Statistics (Estimations) y Preview.</span><span class="sxs-lookup"><span data-stu-id="b5242-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="b5242-116">Cuando se completen todos estos componentes, verá que el estado mostrado en las columnas correspondientes de la ficha **búsquedas** cambia desde **enviado** a **en curso** a **completado**.</span><span class="sxs-lookup"><span data-stu-id="b5242-116">As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="b5242-117">Una vez completada la estimación de búsqueda, haga clic en la búsqueda para mostrar la página de control flotante, que mostrará algunas estadísticas de alto nivel sobre los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b5242-117">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="b5242-118">En este momento, el botón **estadísticas** estará activo.</span><span class="sxs-lookup"><span data-stu-id="b5242-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="b5242-119">Puede hacer clic en él para ver las estadísticas de búsqueda, como:</span><span class="sxs-lookup"><span data-stu-id="b5242-119">You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="b5242-120">Resumen</span><span class="sxs-lookup"><span data-stu-id="b5242-120">Summary</span></span>
- <span data-ttu-id="b5242-121">Principales ubicaciones</span><span class="sxs-lookup"><span data-stu-id="b5242-121">Top locations</span></span>
- <span data-ttu-id="b5242-122">Queries</span><span class="sxs-lookup"><span data-stu-id="b5242-122">Queries</span></span>

<span data-ttu-id="b5242-123">Para obtener más información acerca de las estadísticas de búsqueda, vea [estadísticas de búsqueda](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="b5242-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="b5242-124">Una vez completada la vista previa, el botón **vista previa** estará activo.</span><span class="sxs-lookup"><span data-stu-id="b5242-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="b5242-125">Haga clic en él para obtener una vista previa de un subconjunto muestreado de los resultados.</span><span class="sxs-lookup"><span data-stu-id="b5242-125">Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="b5242-126">Adición de resultados de búsqueda a un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="b5242-126">Adding search results to a review set</span></span>

<span data-ttu-id="b5242-127">Cuando esté listo para recopilar y procesar los resultados completos de una búsqueda, puede hacerlo agregándolo a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b5242-127">When you are ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="b5242-128">Para obtener más información, consulte [Agregar datos a un conjunto de revisión](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="b5242-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span> 