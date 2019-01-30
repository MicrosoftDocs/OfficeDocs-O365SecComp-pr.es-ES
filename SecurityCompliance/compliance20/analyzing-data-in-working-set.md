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
# <a name="analyzing-data-in-a-working-set-in-advanced-ediscovery-preview"></a>Analizar datos en un conjunto de trabajo en la exhibición de documentos electrónicos avanzada (vista previa)

Cuando el número de documentos recopilados es grande, puede ser muy difícil revisar todas ellas. Exhibición de documentos electrónicos avanzada (vista previa) proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se debe revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información acerca de estas funciones, vea:

- [Cerca de detección de duplicados](near-duplicates.md)
- [Subprocesos de correo electrónico](email-threading.md)
- [Temas](themes.md)

Para analizar los datos en un conjunto de trabajo:

1. Configuración de análisis para su caso. Para obtener más información, vea el tema [configuración de búsqueda y análisis](configure-search-analytics-settings.md).
2. Abra el conjunto de trabajo que desee analizar.
3. Vaya a "Grupo de trabajo de administrar".
4. Haga clic en "Analizar".

Puede comprobar el progreso del análisis, en la ficha trabajos en su caso.

 Una vez que se complete el análisis, puede ver el informe de análisis, ejecutar consultas dentro de su trabajo establecer en los resultados del análisis (para obtener más información, vea [consulta dentro de su trabajo establecida](working-set-search.md)) y ver los documentos relacionados de un documento determinado (para obtener más información, vea [ Revisión de datos en el conjunto de trabajo](reviewing-data-in-working-set.md)).

## <a name="analytics-report"></a>Informe de análisis

Para ver un informe de análisis de su conjunto de trabajo:

1. Abra el conjunto de trabajo.
2. Vaya a "Grupo de trabajo de administrar".
3. Haga clic en "Informe".

El informe tiene cuatro componentes de análisis:

- **Desglose** - ¿cuántos mensajes de correo electrónico, datos adjuntos y documentos sueltos se han encontrado en el conjunto de trabajo.

- **Documentos (excluyendo los datos adjuntos)** - cuántos documentos sueltos eran tablas dinámicas, únicos cerca de duplicados de una tabla dinámica o un duplicado exacto de otro documento.

- **Mensajes de correo electrónico** - ¿cuántos mensajes de correo electrónico se han inclusives, copias inclusivas, ambos inclusivas inconvenientes o ninguno de los anteriores

- **Datos adjuntos** : ¿cuántos datos adjuntos de correo electrónico se únicos o duplicados de los datos adjuntos de correo electrónico diferentes dentro del conjunto de trabajo.