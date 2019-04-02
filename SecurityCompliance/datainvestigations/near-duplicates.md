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
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030529"
---
# <a name="near-duplicate-detection"></a>Detección de semiduplicados

Considere un conjunto de documentos que se deben revisar en los que un subconjunto se basa en la misma plantilla y que tiene principalmente el mismo lenguaje reutilizable, con unas pocas diferencias aquí y allí. Si un revisor puede identificar este subconjunto, revise una de ellas minuciosamente y revise las diferencias para el resto, no habría perdido ninguna información única y solo tardó una pequeña parte del tiempo que habría llevado a leer todos los documentos que abarcaban. La detección de duplicados de casi todos los documentos con texto similar que le ayudarán a mejorar el eficacia del proceso de revisión.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se ejecuta la detección cerca de duplicados, el sistema analiza todos los documentos con texto. A continuación, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan. Una vez que se han comparado y agrupado todos los documentos, un documento de cada grupo se marca como "pivot"; al revisar los documentos, puede revisar primero un pivote y revisar los demás documentos en el mismo conjunto Near duplicado, centrándose en la diferencia entre el pivote y el documento que se está revisando.