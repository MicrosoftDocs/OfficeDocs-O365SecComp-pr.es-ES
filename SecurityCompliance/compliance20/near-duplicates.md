---
title: Detección de semiduplicados
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
ms.openlocfilehash: 7ae5e695091d140089f979f28793876a2df77251
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151572"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="8e755-102">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="8e755-102">Near duplicate detection</span></span>

<span data-ttu-id="8e755-103">Considere un conjunto de documentos que se deben revisar en los que un subconjunto se basa en la misma plantilla y que tiene principalmente el mismo lenguaje reutilizable, con unas pocas diferencias aquí y allí.</span><span class="sxs-lookup"><span data-stu-id="8e755-103">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="8e755-104">Si un revisor puede identificar este subconjunto, revise una de ellas minuciosamente y revise las diferencias para el resto, no habría perdido ninguna información única y solo tardó una pequeña parte del tiempo que habría llevado a leer todos los documentos que abarcaban.</span><span class="sxs-lookup"><span data-stu-id="8e755-104">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="8e755-105">La detección de duplicados de casi todos los documentos con texto similar que le ayudarán a mejorar el eficacia del proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="8e755-105">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="8e755-106">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="8e755-106">How does it work?</span></span>

<span data-ttu-id="8e755-107">Cuando se ejecuta la detección cerca de duplicados, el sistema analiza todos los documentos con texto.</span><span class="sxs-lookup"><span data-stu-id="8e755-107">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="8e755-108">A continuación, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido.</span><span class="sxs-lookup"><span data-stu-id="8e755-108">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="8e755-109">Si es así, los documentos se agrupan.</span><span class="sxs-lookup"><span data-stu-id="8e755-109">If it is, the documents are grouped together.</span></span> <span data-ttu-id="8e755-110">Una vez que se han comparado y agrupado todos los documentos, un documento de cada grupo se marca como "pivot"; al revisar los documentos, puede revisar primero un pivote y revisar los demás documentos en el mismo conjunto Near duplicado, centrándose en la diferencia entre el pivote y el documento que se está revisando.</span><span class="sxs-lookup"><span data-stu-id="8e755-110">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>