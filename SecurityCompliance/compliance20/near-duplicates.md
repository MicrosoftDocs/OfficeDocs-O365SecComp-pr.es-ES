---
title: Detección de semiduplicados
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
ms.openlocfilehash: 941809193a3342d8c7b9de991370848aee4af070
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30294943"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="876c9-102">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="876c9-102">Near duplicate detection</span></span>

<span data-ttu-id="876c9-p101">Considere un conjunto de documentos que se deben revisar en los que un subconjunto se basa en la misma plantilla y que tiene principalmente el mismo lenguaje reutilizable, con unas pocas diferencias aquí y allí. Si un revisor puede identificar este subconjunto, revise una de ellas minuciosamente y revise las diferencias para el resto, no habría perdido ninguna información única y solo tardó una pequeña parte del tiempo que habría llevado a leer todos los documentos que abarcaban. La detección de duplicados de casi todos los documentos con texto similar que le ayudarán a mejorar el eficacia del proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="876c9-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="876c9-106">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="876c9-106">How does it work?</span></span>

<span data-ttu-id="876c9-p102">Cuando se ejecuta la detección cerca de duplicados, el sistema analiza todos los documentos con texto. A continuación, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan. Una vez que se han comparado y agrupado todos los documentos, un documento de cada grupo se marca como "pivot"; al revisar los documentos, puede revisar primero un pivote y revisar los demás documentos en el mismo conjunto Near duplicado, centrándose en la diferencia entre el pivote y el documento que se está revisando.</span><span class="sxs-lookup"><span data-stu-id="876c9-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>