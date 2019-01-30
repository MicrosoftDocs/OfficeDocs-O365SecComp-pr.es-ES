---
title: Analizar datos en un conjunto de trabajo en la exhibición de documentos electrónicos avanzada (vista previa)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a6284204fd709bcf936688f36f38f6b3283b1f98
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608335"
---
# <a name="analyzing-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="f234f-102">Analizar datos en un conjunto de trabajo en la exhibición de documentos electrónicos avanzada (vista previa)</span><span class="sxs-lookup"><span data-stu-id="f234f-102">Analyzing data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="f234f-p101">Cuando el número de documentos recopilados es grande, puede ser muy difícil revisar todas ellas. Exhibición de documentos electrónicos avanzada (vista previa) proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se debe revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información acerca de estas funciones, vea:</span><span class="sxs-lookup"><span data-stu-id="f234f-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="f234f-106">Cerca de detección de duplicados</span><span class="sxs-lookup"><span data-stu-id="f234f-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="f234f-107">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f234f-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="f234f-108">Temas</span><span class="sxs-lookup"><span data-stu-id="f234f-108">Themes</span></span>](themes.md)

<span data-ttu-id="f234f-109">Para analizar los datos en un conjunto de trabajo:</span><span class="sxs-lookup"><span data-stu-id="f234f-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="f234f-p102">Configuración de análisis para su caso. Para obtener más información, vea el tema [configuración de búsqueda y análisis](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f234f-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="f234f-112">Abra el conjunto de trabajo que desee analizar.</span><span class="sxs-lookup"><span data-stu-id="f234f-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="f234f-113">Vaya a "Grupo de trabajo de administrar".</span><span class="sxs-lookup"><span data-stu-id="f234f-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="f234f-114">Haga clic en "Analizar".</span><span class="sxs-lookup"><span data-stu-id="f234f-114">Click "Analyze".</span></span>

<span data-ttu-id="f234f-115">Puede comprobar el progreso del análisis, en la ficha trabajos en su caso.</span><span class="sxs-lookup"><span data-stu-id="f234f-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="f234f-116">Una vez que se complete el análisis, puede ver el informe de análisis, ejecutar consultas dentro de su trabajo establecer en los resultados del análisis (para obtener más información, vea [consulta dentro de su trabajo establecida](working-set-search.md)) y ver los documentos relacionados de un documento determinado (para obtener más información, vea [ Revisión de datos en el conjunto de trabajo](reviewing-data-in-working-set.md)).</span><span class="sxs-lookup"><span data-stu-id="f234f-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="f234f-117">Informe de análisis</span><span class="sxs-lookup"><span data-stu-id="f234f-117">Analytics report</span></span>

<span data-ttu-id="f234f-118">Para ver un informe de análisis de su conjunto de trabajo:</span><span class="sxs-lookup"><span data-stu-id="f234f-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="f234f-119">Abra el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f234f-119">Open your working set.</span></span>
2. <span data-ttu-id="f234f-120">Vaya a "Grupo de trabajo de administrar".</span><span class="sxs-lookup"><span data-stu-id="f234f-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="f234f-121">Haga clic en "Informe".</span><span class="sxs-lookup"><span data-stu-id="f234f-121">Click "Report".</span></span>

<span data-ttu-id="f234f-122">El informe tiene cuatro componentes de análisis:</span><span class="sxs-lookup"><span data-stu-id="f234f-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="f234f-123">**Desglose** - ¿cuántos mensajes de correo electrónico, datos adjuntos y documentos sueltos se han encontrado en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f234f-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="f234f-124">**Documentos (excluyendo los datos adjuntos)** - cuántos documentos sueltos eran tablas dinámicas, únicos cerca de duplicados de una tabla dinámica o un duplicado exacto de otro documento.</span><span class="sxs-lookup"><span data-stu-id="f234f-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="f234f-125">**Mensajes de correo electrónico** - ¿cuántos mensajes de correo electrónico se han inclusives, copias inclusivas, ambos inclusivas inconvenientes o ninguno de los anteriores</span><span class="sxs-lookup"><span data-stu-id="f234f-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="f234f-126">**Datos adjuntos** : ¿cuántos datos adjuntos de correo electrónico se únicos o duplicados de los datos adjuntos de correo electrónico diferentes dentro del conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f234f-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>