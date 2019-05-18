---
title: Ejecutar el análisis para investigar más rápido
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
ms.openlocfilehash: 7462b415c2e5b0a66c08bb9b5abb647f366e9785
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153662"
---
# <a name="run-analytics-to-investigate-faster"></a>Ejecutar el análisis para investigar más rápido

Cuando una colección de evidencias es grande, puede ser difícil revisarlas todas. Un conjunto de evidencias suele incluir varias copias de los mismos mensajes de correo electrónico o de documentos similares. Las investigaciones de datos (versión preliminar) proporcionan una serie de herramientas de análisis que pueden ayudarle a reducir el volumen de documentos que deben revisarse sin que se pierda información. Para obtener más información acerca de estas funciones, consulte:

- [Detección de semiduplicados](near-duplicates.md)

- [Subprocesos de correo electrónico](email-threading.md)

- [Temas](themes.md)

Para analizar los datos de un conjunto de evidencias:

1. Configure las opciones de Analytics para su investigación. Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-analytics-settings.md).

2. Abra el conjunto de evidencias.

3. Haga clic en **administrar evidencias**.

4. En **análisis**, haga clic en **analizar**.

Puede comprobar el progreso del análisis en la ficha **trabajos** de la investigación. El tipo de trabajo que se desencadena se denomina **análisis en ejecución**.

 Una vez completado el análisis, puede ver una lista de duplicados exactos o casi duplicados del documento que está revisando ubicado en el panel de la derecha. Para seleccionar todos los duplicados del documento que está viendo, puede hacerlo fácilmente con este panel. Para obtener más información sobre otras características de este panel, consulte [Review Data in Evidence](review-data-in-evidence.md). 

También puede ejecutar consultas adicionales en su evidencia usando los resultados del análisis, como los temas. Para obtener más información, vea [consultar los datos en evidencias](evidence-query.md).

## <a name="analytics-report"></a>Informe de análisis

Para ver un informe de análisis para su evidencia:

1. Abra el conjunto de evidencias.

2. Haga clic en **administrar evidencias**.

3. En **análisis**, haga clic en **Ver informe**.

El informe tiene cuatro componentes del análisis:

- **Desglose** : el número de correos electrónicos sin procesar, datos adjuntos y documentos que se encuentran en el conjunto de evidencias.

- Mensajes de **correo electrónico** : el número de mensajes de eamil que son inclusivos, ambos inclusive, copias inclusivas o ninguna de las anteriores.
   - Inclusivos: el último mensaje del hilo de correo electrónico que contiene todo el historial anterior y requiere revisión.
   - Minus inclusive: el mensaje del hilo que contiene uno o varios datos adjuntos diferentes que requieren revisión.
   - Copias inclusivas: mensaje que es una copia de otro mensaje menos inclusivo o inclusivo (asunto y cuerpo).

- **Datos** adjuntos: número de datos adjuntos de correo electrónico únicos o duplicados de un archivo adjunto de correo electrónico diferente dentro de la misma evidencia.

- **Documentos (excepto archivos adjuntos de correo electrónico)** : número de documentos únicos que requieren revisión, por ejemplo, el documento más representativo del conjunto casi duplicado o un duplicado exacto de otro documento).