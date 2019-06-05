---
title: Generar el informe de términos de búsqueda para un conjunto de revisión
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34714999"
---
# <a name="generate-search-term-report-for-a-review-set"></a>Generar el informe de términos de búsqueda para un conjunto de revisión

En eDiscovery, una de las condiciones usadas con más frecuencia para consultar documentos es con los términos de búsqueda de palabras clave. Mediante la identificación de los documentos que contienen las palabras clave específicas (también denominadas " *términos*") que son importantes para un caso, los revisores pueden empezar a obtener una descripción de alto nivel de lo que enfrentan. En eDiscovery avanzado en Microsoft 365, puede hacer esto con precisión generando informes de términos de búsqueda en consultas guardadas en un conjunto de revisión.

## <a name="step-1-create-a-saved-query-in-the-review-set"></a>Paso 1: crear una consulta guardada en el conjunto de revisiones

Para generar un informe de términos de búsqueda con significado, cree una consulta guardada que defina el conjunto de documentos en el conjunto de revisión para el que desea generar un informe de términos de búsqueda. Por ejemplo, puede usar un intervalo de fechas o el conjunto real de términos de búsqueda (mediante la tarjeta de condición palabras clave) para crear la consulta. Para obtener más información sobre la revisión de las consultas de Set, consulte [consultar los datos de un conjunto de revisión](review-set-search.md).

## <a name="step-2-generate-a-search-term-report"></a>Paso 2: generar un informe de términos de búsqueda

Hay dos formas diferentes de generar un informe de términos de búsqueda: a través del menú contextual de la consulta guardada que ha creado en el paso 1, o a través de la consola de administración del informe de términos de búsqueda.

- Para usar el menú contextual, abra el menú contextual de la consulta guardada que creó en el paso 1 y haga clic en **generar informe de términos de búsqueda**.

- Para usar la consola de administración, vaya a **Manage View set > View Search term**Reports, haga clic en **nuevo**y, a continuación, seleccione la consulta guardada que creó en el paso 1.

A continuación, especifique los términos que desea incluir en el informe, separados por nueva línea. Si la consulta guardada que creó en el paso 1 ha usado la tarjeta de condición de palabra clave, la página de control flotante se rellenará previamente con los términos de la primera tarjeta de condición de palabra clave que se usa en la consulta guardada.

A continuación, seleccione hasta tres tablas dinámicas para informar sobre y haga clic en **generar**, que iniciará el trabajo de generación de informes de términos de búsqueda.

### <a name="what-is-a-pivot"></a>¿Qué es un pivote?

Las tablas dinámicas indican cómo se va a organizar el informe. Veamos el ejemplo siguiente.

- La consulta guardada recupera 10 documentos: doc1 a través de doc10.

- doc1, doc2, doc3, doc4, doc5, doc6 y doc7 contienen el término "eDiscovery".

- doc6, doc7, doc8, doc9 y doc10 contienen el término "investigación".

- doc1, doc3, doc5, doc7, doc9 son de custodio A.

- doc2, doc4, doc6, doc8, doc10 son de custodio B.

En este caso, si tuviera que generar un informe de término de búsqueda con los términos "eDiscovery" y "investigación" y Pivot en los custodios, el informe de término de búsqueda estaría organizado de la siguiente manera:

- "eDiscovery"-custodio A: 4 documentos

- "eDiscovery"-custodio B: 3 documentos

- "Investigación"-custodio A: 2 documentos

- "Investigación"-custodio B: 3 documentos

## <a name="step-3-download-report"></a>Paso 3: Descargar Informe

En la consola de administración de términos de búsqueda, puede realizar un seguimiento del estado de un trabajo de informe de términos de búsqueda creado anteriormente. Una vez completado el trabajo, puede hacer clic en la fila del informe de términos de búsqueda y hacer clic en "Descargar", que descargará el informe de términos de búsqueda en un formato CSV. Habrá una fila por tupla (término de búsqueda, tablas dinámicas) y cada fila contendrá la siguiente información:

- ¿Cuántos documentos se han recuperado?

- ¿Cuántas veces se encontró el término de búsqueda en los documentos?

- ¿Cuál es el volumen total de documentos recuperados?

- ¿Cuántas familias se han recuperado?

- ¿Cuál es el número total de documentos de esas familias, incluidos los documentos que no tenían el término de búsqueda?

- ¿Cuál es el volumen total de los anteriores?