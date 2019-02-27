---
title: Analizar datos en un conjunto de trabajo en eDiscovery avanzado (versión preliminar)
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
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295483"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="b8d6f-102">Analizar datos en un conjunto de trabajo en eDiscovery avanzado (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b8d6f-102">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="b8d6f-p101">Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos. La exhibición avanzada de documentos electrónicos (versión preliminar) proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se van a revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información acerca de estas funciones, consulte:</span><span class="sxs-lookup"><span data-stu-id="b8d6f-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="b8d6f-106">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="b8d6f-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="b8d6f-107">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b8d6f-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="b8d6f-108">Temas</span><span class="sxs-lookup"><span data-stu-id="b8d6f-108">Themes</span></span>](themes.md)

<span data-ttu-id="b8d6f-109">Para analizar datos en un conjunto de trabajo:</span><span class="sxs-lookup"><span data-stu-id="b8d6f-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="b8d6f-p102">Configure las opciones de análisis en su caso. Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b8d6f-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="b8d6f-112">Abra el conjunto de trabajo que desee analizar.</span><span class="sxs-lookup"><span data-stu-id="b8d6f-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="b8d6f-113">Vaya a "administrar el conjunto de trabajo".</span><span class="sxs-lookup"><span data-stu-id="b8d6f-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="b8d6f-114">Haga clic en "analizar".</span><span class="sxs-lookup"><span data-stu-id="b8d6f-114">Click "Analyze".</span></span>

<span data-ttu-id="b8d6f-115">Puede comprobar el progreso del análisis en la pestaña trabajos en su caso.</span><span class="sxs-lookup"><span data-stu-id="b8d6f-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="b8d6f-116">Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas en el conjunto de trabajo en los resultados del análisis (para obtener más información, vea [consultar en el conjunto de trabajo](working-set-search.md)) y ver los documentos relacionados de un documento determinado (para obtener más información, vea [ Revisión de datos en el conjunto de trabajo](reviewing-data-in-working-set.md)).</span><span class="sxs-lookup"><span data-stu-id="b8d6f-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="b8d6f-117">Informe de análisis</span><span class="sxs-lookup"><span data-stu-id="b8d6f-117">Analytics report</span></span>

<span data-ttu-id="b8d6f-118">Para ver un informe de análisis del espacio de trabajo:</span><span class="sxs-lookup"><span data-stu-id="b8d6f-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="b8d6f-119">Abra el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8d6f-119">Open your working set.</span></span>
2. <span data-ttu-id="b8d6f-120">Vaya a "administrar el conjunto de trabajo".</span><span class="sxs-lookup"><span data-stu-id="b8d6f-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="b8d6f-121">Haga clic en "informe".</span><span class="sxs-lookup"><span data-stu-id="b8d6f-121">Click "Report".</span></span>

<span data-ttu-id="b8d6f-122">El informe tiene cuatro componentes del análisis:</span><span class="sxs-lookup"><span data-stu-id="b8d6f-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="b8d6f-123">**Desglose** : Cuántos correos electrónicos, datos adjuntos y documentos sueltos se encontraron en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8d6f-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="b8d6f-124">**Documentos (sin datos adjuntos)** : Cuántos documentos sueltos eran tablas dinámicas, únicas cerca de duplicados de un pivote o un duplicado exacto de otro documento.</span><span class="sxs-lookup"><span data-stu-id="b8d6f-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="b8d6f-125">**Mensajes de correo electrónico** : Cuántos correos electrónicos eran inclusivos, copias inclusivas, menos inclusivas o ninguna de las anteriores.</span><span class="sxs-lookup"><span data-stu-id="b8d6f-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="b8d6f-126">**Datos** adjuntos: Cuántos archivos adjuntos de correo electrónico son únicos o duplicados de un archivo adjunto de correo electrónico diferente dentro del conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8d6f-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>