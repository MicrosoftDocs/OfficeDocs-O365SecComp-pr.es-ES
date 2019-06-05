---
title: Generar el informe de términos de búsqueda para un conjunto de revisión
ms.author: markjjo
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34714999"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="4563c-102">Generar el informe de términos de búsqueda para un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="4563c-102">Generate search term report for a review set</span></span>

<span data-ttu-id="4563c-103">En eDiscovery, una de las condiciones usadas con más frecuencia para consultar documentos es con los términos de búsqueda de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="4563c-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="4563c-104">Mediante la identificación de los documentos que contienen las palabras clave específicas (también denominadas " *términos*") que son importantes para un caso, los revisores pueden empezar a obtener una descripción de alto nivel de lo que enfrentan.</span><span class="sxs-lookup"><span data-stu-id="4563c-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="4563c-105">En eDiscovery avanzado en Microsoft 365, puede hacer esto con precisión generando informes de términos de búsqueda en consultas guardadas en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="4563c-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="4563c-106">Paso 1: crear una consulta guardada en el conjunto de revisiones</span><span class="sxs-lookup"><span data-stu-id="4563c-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="4563c-107">Para generar un informe de términos de búsqueda con significado, cree una consulta guardada que defina el conjunto de documentos en el conjunto de revisión para el que desea generar un informe de términos de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4563c-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="4563c-108">Por ejemplo, puede usar un intervalo de fechas o el conjunto real de términos de búsqueda (mediante la tarjeta de condición palabras clave) para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="4563c-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="4563c-109">Para obtener más información sobre la revisión de las consultas de Set, consulte [consultar los datos de un conjunto de revisión](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="4563c-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="4563c-110">Paso 2: generar un informe de términos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4563c-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="4563c-111">Hay dos formas diferentes de generar un informe de términos de búsqueda: a través del menú contextual de la consulta guardada que ha creado en el paso 1, o a través de la consola de administración del informe de términos de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4563c-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="4563c-112">Para usar el menú contextual, abra el menú contextual de la consulta guardada que creó en el paso 1 y haga clic en **generar informe de términos de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="4563c-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="4563c-113">Para usar la consola de administración, vaya a **Manage View set > View Search term**Reports, haga clic en **nuevo**y, a continuación, seleccione la consulta guardada que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="4563c-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="4563c-114">A continuación, especifique los términos que desea incluir en el informe, separados por nueva línea. Si la consulta guardada que creó en el paso 1 ha usado la tarjeta de condición de palabra clave, la página de control flotante se rellenará previamente con los términos de la primera tarjeta de condición de palabra clave que se usa en la consulta guardada.</span><span class="sxs-lookup"><span data-stu-id="4563c-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="4563c-115">A continuación, seleccione hasta tres tablas dinámicas para informar sobre y haga clic en **generar**, que iniciará el trabajo de generación de informes de términos de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4563c-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="4563c-116">¿Qué es un pivote?</span><span class="sxs-lookup"><span data-stu-id="4563c-116">What is a pivot?</span></span>

<span data-ttu-id="4563c-117">Las tablas dinámicas indican cómo se va a organizar el informe.</span><span class="sxs-lookup"><span data-stu-id="4563c-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="4563c-118">Veamos el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4563c-118">Consider the following example.</span></span>

- <span data-ttu-id="4563c-119">La consulta guardada recupera 10 documentos: doc1 a través de doc10.</span><span class="sxs-lookup"><span data-stu-id="4563c-119">The saved query retrieves 10 documents: doc1 thru doc10.</span></span>

- <span data-ttu-id="4563c-120">doc1, doc2, doc3, doc4, doc5, doc6 y doc7 contienen el término "eDiscovery".</span><span class="sxs-lookup"><span data-stu-id="4563c-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="4563c-121">doc6, doc7, doc8, doc9 y doc10 contienen el término "investigación".</span><span class="sxs-lookup"><span data-stu-id="4563c-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="4563c-122">doc1, doc3, doc5, doc7, doc9 son de custodio A.</span><span class="sxs-lookup"><span data-stu-id="4563c-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="4563c-123">doc2, doc4, doc6, doc8, doc10 son de custodio B.</span><span class="sxs-lookup"><span data-stu-id="4563c-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="4563c-124">En este caso, si tuviera que generar un informe de término de búsqueda con los términos "eDiscovery" y "investigación" y Pivot en los custodios, el informe de término de búsqueda estaría organizado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4563c-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="4563c-125">"eDiscovery"-custodio A: 4 documentos</span><span class="sxs-lookup"><span data-stu-id="4563c-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="4563c-126">"eDiscovery"-custodio B: 3 documentos</span><span class="sxs-lookup"><span data-stu-id="4563c-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="4563c-127">"Investigación"-custodio A: 2 documentos</span><span class="sxs-lookup"><span data-stu-id="4563c-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="4563c-128">"Investigación"-custodio B: 3 documentos</span><span class="sxs-lookup"><span data-stu-id="4563c-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="4563c-129">Paso 3: Descargar Informe</span><span class="sxs-lookup"><span data-stu-id="4563c-129">Step 3: Download report</span></span>

<span data-ttu-id="4563c-130">En la consola de administración de términos de búsqueda, puede realizar un seguimiento del estado de un trabajo de informe de términos de búsqueda creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4563c-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="4563c-131">Una vez completado el trabajo, puede hacer clic en la fila del informe de términos de búsqueda y hacer clic en "Descargar", que descargará el informe de términos de búsqueda en un formato CSV.</span><span class="sxs-lookup"><span data-stu-id="4563c-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="4563c-132">Habrá una fila por tupla (término de búsqueda, tablas dinámicas) y cada fila contendrá la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="4563c-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="4563c-133">¿Cuántos documentos se han recuperado?</span><span class="sxs-lookup"><span data-stu-id="4563c-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="4563c-134">¿Cuántas veces se encontró el término de búsqueda en los documentos?</span><span class="sxs-lookup"><span data-stu-id="4563c-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="4563c-135">¿Cuál es el volumen total de documentos recuperados?</span><span class="sxs-lookup"><span data-stu-id="4563c-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="4563c-136">¿Cuántas familias se han recuperado?</span><span class="sxs-lookup"><span data-stu-id="4563c-136">How many families were retrieved?</span></span>

- <span data-ttu-id="4563c-137">¿Cuál es el número total de documentos de esas familias, incluidos los documentos que no tenían el término de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="4563c-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="4563c-138">¿Cuál es el volumen total de los anteriores?</span><span class="sxs-lookup"><span data-stu-id="4563c-138">What is the total volume of the above?</span></span>