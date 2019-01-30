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
# <a name="near-duplicate-detection"></a>Cerca de detección de duplicados

Considere la posibilidad de un conjunto de revisión de documentos en la que se basa en la misma plantilla un subconjunto y tiene principalmente el mismo texto reutilizable idioma, con algunas diferencias ahí. Si un revisor podría identificar este subconjunto, revise uno de ellos detenidamente y revisar las diferencias para el resto, no habría perdidas cualquier información única mientras teniendo sólo una fracción del tiempo que habría tomado para leer todos los documentos de portada a portada. Detección de duplicados near grupos documentos textual similares conjuntamente para ayudarle a realizar el proceso de revisión más eficaz.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se ejecuta cerca de detección de duplicados, el sistema analiza todos los documentos con texto. A continuación, compara todos los documentos frente a la otra para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan juntos. Una vez que todos los documentos se han comparado y agrupados, un documento desde cada grupo está marcado como "dinámica"; en la revisión de los documentos, puede revisar una tabla dinámica en primer lugar y revise los otros documentos en el mismo cerca de conjunto de duplicados, centrándose en la diferencia entre la tabla dinámica y el documento que se encuentra en revisión.