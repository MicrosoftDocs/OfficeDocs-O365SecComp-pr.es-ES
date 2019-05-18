---
title: Consultar los datos de un conjunto de revisión
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
description: ''
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154012"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="2e36a-102">Consultar los datos de un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="2e36a-102">Query the data in a review set</span></span>

<span data-ttu-id="2e36a-103">En la mayoría de los casos, será útil poder profundizar en lo que hay en un conjunto de revisión y organizarlas para que revisen con mayor eficacia.</span><span class="sxs-lookup"><span data-stu-id="2e36a-103">In most cases, it will be useful to be able to dig deeper into what is there in a review set and organize them to review more efficiently.</span></span> <span data-ttu-id="2e36a-104">Las consultas de un conjunto de revisión le permiten hacerlo permitiéndole centrarse en un subconjunto de documentos que cumplan los criterios definidos por usted a la vez.</span><span class="sxs-lookup"><span data-stu-id="2e36a-104">Queries within a review set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-review-set"></a><span data-ttu-id="2e36a-105">Creación y ejecución de una consulta en un conjunto de revisiones</span><span class="sxs-lookup"><span data-stu-id="2e36a-105">Creating and running a query within a review set</span></span>

<span data-ttu-id="2e36a-106">Para crear y ejecutar una consulta dentro de su conjunto de revisión, haga clic en "nueva consulta" en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2e36a-106">In order to create and run a query within your review set, click on "New Query" in your review set.</span></span> <span data-ttu-id="2e36a-107">Después de asignar un nombre a la consulta y definir las condiciones, haga clic en "guardar" para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="2e36a-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="2e36a-108">Para ejecutar una consulta guardada anteriormente, simplemente haga clic en la consulta guardada.</span><span class="sxs-lookup"><span data-stu-id="2e36a-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="2e36a-109">Consulte campos de metadatos del documento para obtener una lista de [los](document-metadata-fields.md) metadatos que puede buscar.</span><span class="sxs-lookup"><span data-stu-id="2e36a-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="2e36a-110">Creación de la consulta</span><span class="sxs-lookup"><span data-stu-id="2e36a-110">Building your query</span></span>

<span data-ttu-id="2e36a-111">Puede crear su consulta usando una combinación de tarjetas de condición y lenguaje de consulta en la tarjeta de condición de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="2e36a-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="2e36a-112">Puede agrupar las tarjetas de condición como un bloque para elaborar una consulta más compleja.</span><span class="sxs-lookup"><span data-stu-id="2e36a-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="2e36a-113">Tarjeta de condición</span><span class="sxs-lookup"><span data-stu-id="2e36a-113">Condition card</span></span>

<span data-ttu-id="2e36a-114">Cada campo de búsqueda de un conjunto de revisión tiene una tarjeta de condición correspondiente que puede usar para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="2e36a-114">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="2e36a-115">Hay varios tipos de tarjetas de condición:</span><span class="sxs-lookup"><span data-stu-id="2e36a-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="2e36a-116">FREETEXT: la tarjeta de condición FREETEXT se usa para campos de texto como Subject.</span><span class="sxs-lookup"><span data-stu-id="2e36a-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="2e36a-117">Puede enumerar varios términos de búsqueda separándolos con una coma.</span><span class="sxs-lookup"><span data-stu-id="2e36a-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="2e36a-118">Fecha: la tarjeta de condición de fecha se usa para los campos de fecha como última fecha de modificación.</span><span class="sxs-lookup"><span data-stu-id="2e36a-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="2e36a-119">Opciones de búsqueda: la tarjeta de condición opciones de búsqueda proporcionará una lista de valores posibles para el campo en particular en su conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2e36a-119">Search options: search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="2e36a-120">Se usa para los campos, como Sender, donde hay un número finito de valores posibles en su conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2e36a-120">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>
- <span data-ttu-id="2e36a-121">Palabra clave: la tarjeta de condición de palabra clave es una instancia específica de la tarjeta de condición FREETEXT que puede usar para buscar términos o usar el lenguaje de consulta de tipo KQL en.</span><span class="sxs-lookup"><span data-stu-id="2e36a-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="2e36a-122">Consulte a continuación para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="2e36a-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="2e36a-123">Lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="2e36a-123">Query language</span></span>

<span data-ttu-id="2e36a-124">Además de las tarjetas de condición, puede usar un lenguaje de consulta de tipo KQL en la tarjeta de palabras clave para diseñar la consulta.</span><span class="sxs-lookup"><span data-stu-id="2e36a-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="2e36a-125">El lenguaje de consulta admite la sintaxis KQL estándar como AND, OR, NOT y NEAR (n).</span><span class="sxs-lookup"><span data-stu-id="2e36a-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="2e36a-126">También admite comodín de un solo carácter (?) y comodín de varios caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="2e36a-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="2e36a-127">Filter</span><span class="sxs-lookup"><span data-stu-id="2e36a-127">Filter</span></span>

<span data-ttu-id="2e36a-128">Además de las consultas que puede guardar, puede superponer condiciones adicionales sobre la marcha a los resultados de la consulta mediante filtros.</span><span class="sxs-lookup"><span data-stu-id="2e36a-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="2e36a-129">Los filtros difieren de las consultas de varias maneras significativas:</span><span class="sxs-lookup"><span data-stu-id="2e36a-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="2e36a-130">Los filtros son transitorios (es decir, no persisten en sesiones diferentes), mientras que las consultas se guardan en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2e36a-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the review set.</span></span>
- <span data-ttu-id="2e36a-131">Los filtros siempre son aditivos; los filtros se aplicarán encima de la consulta que tiene en el momento, mientras que al aplicar una consulta se reemplazará la consulta en vigor.</span><span class="sxs-lookup"><span data-stu-id="2e36a-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>