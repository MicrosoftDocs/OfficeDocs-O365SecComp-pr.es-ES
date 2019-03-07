---
title: Consultar los datos de un conjunto de trabajo
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
ms.openlocfilehash: 2523072181307cce510f0f318834329b2c70b376
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454992"
---
# <a name="query-the-data-in-a-working-set"></a>Consultar los datos de un conjunto de trabajo

En la mayoría de los casos, será útil poder profundizar en lo que hay en un conjunto de trabajo y organizarlos para que revisen con mayor eficacia. Las consultas de un conjunto de trabajo le permiten hacerlo permitiéndole centrarse en un subconjunto de documentos que cumplan los criterios definidos por usted a la vez.

## <a name="creating-and-running-a-query-within-a-working-set"></a>Crear y ejecutar una consulta en un conjunto de trabajo

Para crear y ejecutar una consulta en el conjunto de trabajo, haga clic en "nueva consulta" en el conjunto de trabajo. Después de asignar un nombre a la consulta y definir las condiciones, haga clic en "guardar" para ejecutar la consulta. Para ejecutar una consulta guardada anteriormente, simplemente haga clic en la consulta guardada. Consulte campos de metadatos del documento para obtener una lista de [los](document-metadata-fields.md) metadatos que puede buscar.

## <a name="building-your-query"></a>Creación de la consulta

Puede crear su consulta usando una combinación de tarjetas de condición y lenguaje de consulta en la tarjeta de condición de palabras clave.

### <a name="condition-card"></a>Tarjeta de condición

Cada campo de búsqueda de un conjunto de trabajo tiene una tarjeta de condición correspondiente que puede usar para crear la consulta.

Hay varios tipos de tarjetas de condición:
- FREETEXT: la tarjeta de condición FREETEXT se usa para campos de texto como Subject. Puede enumerar varios términos de búsqueda separándolos con una coma.
- Fecha: la tarjeta de condición de fecha se usa para los campos de fecha como última fecha de modificación.
- Opciones de búsqueda: la tarjeta de condición opciones de búsqueda proporcionará una lista de valores posibles para el campo en particular en el conjunto de trabajo. Se usa para campos como Sender, donde hay un número finito de valores posibles en el conjunto de trabajo.
- Palabra clave: la tarjeta de condición de palabra clave es una instancia específica de la tarjeta de condición FREETEXT que puede usar para buscar términos o usar el lenguaje de consulta de tipo KQL en. Consulte a continuación para obtener más detalles.

### <a name="query-language"></a>Lenguaje de consulta

Además de las tarjetas de condición, puede usar un lenguaje de consulta de tipo KQL en la tarjeta de palabras clave para diseñar la consulta. El lenguaje de consulta admite la sintaxis KQL estándar como AND, OR, NOT y NEAR (n). También admite comodín de un solo carácter (?) y comodín de varios caracteres (*).