---
title: Analizar datos en un conjunto de revisión en eDiscovery avanzado
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
ms.openlocfilehash: cfed07d473f2af367de4cb2e9fe924a29e4123cd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155212"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="fd471-102">Analizar datos en un conjunto de revisión en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="fd471-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="fd471-103">Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos.</span><span class="sxs-lookup"><span data-stu-id="fd471-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="fd471-104">EDiscovery avanzado proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se van a revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="fd471-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="fd471-105">Para obtener más información acerca de estas funciones, consulte:</span><span class="sxs-lookup"><span data-stu-id="fd471-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="fd471-106">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="fd471-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="fd471-107">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fd471-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="fd471-108">Temas</span><span class="sxs-lookup"><span data-stu-id="fd471-108">Themes</span></span>](themes.md)

<span data-ttu-id="fd471-109">Para analizar los datos de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="fd471-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="fd471-110">Configure las opciones de análisis en su caso.</span><span class="sxs-lookup"><span data-stu-id="fd471-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="fd471-111">Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fd471-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="fd471-112">Abra el conjunto de revisiones que desee analizar.</span><span class="sxs-lookup"><span data-stu-id="fd471-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="fd471-113">Haga clic en **administrar conjunto de revisiones**.</span><span class="sxs-lookup"><span data-stu-id="fd471-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="fd471-114">Haga clic en **analizar**.</span><span class="sxs-lookup"><span data-stu-id="fd471-114">Click **Analyze**.</span></span>

<span data-ttu-id="fd471-115">Puede comprobar el progreso del análisis en la ficha **trabajos** del caso.</span><span class="sxs-lookup"><span data-stu-id="fd471-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="fd471-116">Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas dentro de su conjunto de revisión en los resultados del análisis (vea [la consulta dentro del conjunto de revisión](review-set-search.md)) y ver los documentos relacionados de un documento determinado (vea [revisar los datos en el conjunto de revisiones](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="fd471-116">After analysis is completed, you can view analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="fd471-117">Informe de análisis</span><span class="sxs-lookup"><span data-stu-id="fd471-117">Analytics report</span></span>

<span data-ttu-id="fd471-118">Para ver un informe de análisis de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="fd471-118">To view a analytics report for a review set:</span></span>

1. <span data-ttu-id="fd471-119">Abra el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fd471-119">Open the review set.</span></span>

2. <span data-ttu-id="fd471-120">Haga clic en **administrar conjunto de revisiones**.</span><span class="sxs-lookup"><span data-stu-id="fd471-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="fd471-121">Haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="fd471-121">Click **Report**.</span></span>

<span data-ttu-id="fd471-122">El informe tiene cuatro componentes del análisis:</span><span class="sxs-lookup"><span data-stu-id="fd471-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="fd471-123">**Desglose** : cuántos mensajes de correo electrónico, datos adjuntos y documentos sueltos se encontraron en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fd471-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="fd471-124">**Documentos (sin datos adjuntos)** : Cuántos documentos sueltos eran tablas dinámicas, únicas cerca de duplicados de un pivote o un duplicado exacto de otro documento.</span><span class="sxs-lookup"><span data-stu-id="fd471-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="fd471-125">\*\*\*\* Mensajes de correo electrónico: cuántos mensajes de correo electrónico eran inclusivos, copias inclusivas, menos inclusivas o ninguna de las anteriores.</span><span class="sxs-lookup"><span data-stu-id="fd471-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="fd471-126">**Datos** adjuntos: Cuántos archivos adjuntos de correo electrónico eran únicos o duplicados de otro adjunto de correo electrónico en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fd471-126">**Attachments** - How many email attachments were unique or duplicates of a another email attachment in the review set.</span></span>