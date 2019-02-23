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
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: ae024f423ac9b4ab9210ddfab519093a9fee3e42
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216800"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a>Analizar datos en un conjunto de trabajo en eDiscovery avanzado (versión preliminar)

Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos. La exhibición avanzada de documentos electrónicos (versión preliminar) proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se van a revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información acerca de estas funciones, consulte:

- [Detección de semiduplicados](near-duplicates.md)
- [Subprocesos de correo electrónico](email-threading.md)
- [Temas](themes.md)

Para analizar datos en un conjunto de trabajo:

1. Configure las opciones de análisis en su caso. Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-analytics-settings.md).
2. Abra el conjunto de trabajo que desee analizar.
3. Vaya a "administrar el conjunto de trabajo".
4. Haga clic en "analizar".

Puede comprobar el progreso del análisis en la pestaña trabajos en su caso.

 Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas en el conjunto de trabajo en los resultados del análisis (para obtener más información, vea [consultar en el conjunto de trabajo](working-set-search.md)) y ver los documentos relacionados de un documento determinado (para obtener más información, vea [ Revisión de datos en el conjunto de trabajo](reviewing-data-in-working-set.md)).

## <a name="analytics-report"></a>Informe de análisis

Para ver un informe de análisis del espacio de trabajo:

1. Abra el conjunto de trabajo.
2. Vaya a "administrar el conjunto de trabajo".
3. Haga clic en "informe".

El informe tiene cuatro componentes del análisis:

- **Desglose** : Cuántos correos electrónicos, datos adjuntos y documentos sueltos se encontraron en el conjunto de trabajo.

- **Documentos (sin datos adjuntos)** : Cuántos documentos sueltos eran tablas dinámicas, únicas cerca de duplicados de un pivote o un duplicado exacto de otro documento.

- **Mensajes de correo electrónico** : Cuántos correos electrónicos eran inclusivos, copias inclusivas, menos inclusivas o ninguna de las anteriores.

- **Datos** adjuntos: Cuántos archivos adjuntos de correo electrónico son únicos o duplicados de un archivo adjunto de correo electrónico diferente dentro del conjunto de trabajo.