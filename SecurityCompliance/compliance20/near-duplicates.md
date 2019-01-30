---
title: Cerca de detección de duplicados
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
ms.openlocfilehash: a3f5945ee4ba0a1bc78ab6c8ccc9af934d392232
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608350"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="4cacf-102">Cerca de detección de duplicados</span><span class="sxs-lookup"><span data-stu-id="4cacf-102">Near duplicate detection</span></span>

<span data-ttu-id="4cacf-p101">Considere la posibilidad de un conjunto de revisión de documentos en la que se basa en la misma plantilla un subconjunto y tiene principalmente el mismo texto reutilizable idioma, con algunas diferencias ahí. Si un revisor podría identificar este subconjunto, revise uno de ellos detenidamente y revisar las diferencias para el resto, no habría perdidas cualquier información única mientras teniendo sólo una fracción del tiempo que habría tomado para leer todos los documentos de portada a portada. Detección de duplicados near grupos documentos textual similares conjuntamente para ayudarle a realizar el proceso de revisión más eficaz.</span><span class="sxs-lookup"><span data-stu-id="4cacf-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="4cacf-106">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="4cacf-106">How does it work?</span></span>

<span data-ttu-id="4cacf-p102">Cuando se ejecuta cerca de detección de duplicados, el sistema analiza todos los documentos con texto. A continuación, compara todos los documentos frente a la otra para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan juntos. Una vez que todos los documentos se han comparado y agrupados, un documento desde cada grupo está marcado como "dinámica"; en la revisión de los documentos, puede revisar una tabla dinámica en primer lugar y revise los otros documentos en el mismo cerca de conjunto de duplicados, centrándose en la diferencia entre la tabla dinámica y el documento que se encuentra en revisión.</span><span class="sxs-lookup"><span data-stu-id="4cacf-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>