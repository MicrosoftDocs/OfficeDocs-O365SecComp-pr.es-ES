---
title: Consultar los datos de un conjunto de trabajo
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
ms.openlocfilehash: 2523072181307cce510f0f318834329b2c70b376
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454992"
---
# <a name="query-the-data-in-a-working-set"></a><span data-ttu-id="d54de-102">Consultar los datos de un conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="d54de-102">Query the data in a working set</span></span>

<span data-ttu-id="d54de-103">En la mayoría de los casos, será útil poder profundizar en lo que hay en un conjunto de trabajo y organizarlos para que revisen con mayor eficacia.</span><span class="sxs-lookup"><span data-stu-id="d54de-103">In most cases, it will be useful to be able to dig deeper into what is there in a working set and organize them to review more efficiently.</span></span> <span data-ttu-id="d54de-104">Las consultas de un conjunto de trabajo le permiten hacerlo permitiéndole centrarse en un subconjunto de documentos que cumplan los criterios definidos por usted a la vez.</span><span class="sxs-lookup"><span data-stu-id="d54de-104">Queries within a working set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-working-set"></a><span data-ttu-id="d54de-105">Crear y ejecutar una consulta en un conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="d54de-105">Creating and running a query within a working set</span></span>

<span data-ttu-id="d54de-106">Para crear y ejecutar una consulta en el conjunto de trabajo, haga clic en "nueva consulta" en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d54de-106">In order to create and run a query within your working set, click on "New Query" in your working set.</span></span> <span data-ttu-id="d54de-107">Después de asignar un nombre a la consulta y definir las condiciones, haga clic en "guardar" para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="d54de-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="d54de-108">Para ejecutar una consulta guardada anteriormente, simplemente haga clic en la consulta guardada.</span><span class="sxs-lookup"><span data-stu-id="d54de-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="d54de-109">Consulte campos de metadatos del documento para obtener una lista de [los](document-metadata-fields.md) metadatos que puede buscar.</span><span class="sxs-lookup"><span data-stu-id="d54de-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="d54de-110">Creación de la consulta</span><span class="sxs-lookup"><span data-stu-id="d54de-110">Building your query</span></span>

<span data-ttu-id="d54de-111">Puede crear su consulta usando una combinación de tarjetas de condición y lenguaje de consulta en la tarjeta de condición de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="d54de-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span>

### <a name="condition-card"></a><span data-ttu-id="d54de-112">Tarjeta de condición</span><span class="sxs-lookup"><span data-stu-id="d54de-112">Condition card</span></span>

<span data-ttu-id="d54de-113">Cada campo de búsqueda de un conjunto de trabajo tiene una tarjeta de condición correspondiente que puede usar para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="d54de-113">Every searchable field in a working set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="d54de-114">Hay varios tipos de tarjetas de condición:</span><span class="sxs-lookup"><span data-stu-id="d54de-114">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="d54de-115">FREETEXT: la tarjeta de condición FREETEXT se usa para campos de texto como Subject.</span><span class="sxs-lookup"><span data-stu-id="d54de-115">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="d54de-116">Puede enumerar varios términos de búsqueda separándolos con una coma.</span><span class="sxs-lookup"><span data-stu-id="d54de-116">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="d54de-117">Fecha: la tarjeta de condición de fecha se usa para los campos de fecha como última fecha de modificación.</span><span class="sxs-lookup"><span data-stu-id="d54de-117">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="d54de-118">Opciones de búsqueda: la tarjeta de condición opciones de búsqueda proporcionará una lista de valores posibles para el campo en particular en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d54de-118">Search options: search options condition card will provide a list of possible values for the particular field in your working set.</span></span> <span data-ttu-id="d54de-119">Se usa para campos como Sender, donde hay un número finito de valores posibles en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d54de-119">This is used for fields such as sender, where there is a finite number of possible values in your working set.</span></span>
- <span data-ttu-id="d54de-120">Palabra clave: la tarjeta de condición de palabra clave es una instancia específica de la tarjeta de condición FREETEXT que puede usar para buscar términos o usar el lenguaje de consulta de tipo KQL en.</span><span class="sxs-lookup"><span data-stu-id="d54de-120">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="d54de-121">Consulte a continuación para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="d54de-121">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="d54de-122">Lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="d54de-122">Query language</span></span>

<span data-ttu-id="d54de-123">Además de las tarjetas de condición, puede usar un lenguaje de consulta de tipo KQL en la tarjeta de palabras clave para diseñar la consulta.</span><span class="sxs-lookup"><span data-stu-id="d54de-123">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="d54de-124">El lenguaje de consulta admite la sintaxis KQL estándar como AND, OR, NOT y NEAR (n).</span><span class="sxs-lookup"><span data-stu-id="d54de-124">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="d54de-125">También admite comodín de un solo carácter (?) y comodín de varios caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="d54de-125">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>