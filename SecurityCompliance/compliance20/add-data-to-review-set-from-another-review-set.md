---
title: Agregar datos de un conjunto de revisión a otro conjunto de revisión
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
ms.openlocfilehash: 025fd90373313f762ce1d1dab8d48286e32e3cbb
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527288"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Agregar datos a un conjunto de revisión desde otro conjunto de revisión

En algunos casos, puede ser necesario dividir una parte de los documentos de un conjunto de revisión y trabajar con ellos de forma individual en otro conjunto de revisión.  Esto es especialmente útil si ha seleccionado contenido en un conjunto de revisión y desea ejecutar análisis en el subconjunto de datos.

Use el siguiente flujo de trabajo para agregar contenido de un conjunto de revisión a otro.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar, deberá crear un nuevo conjunto de revisión para agregar los datos a.  Se puede Agregar un nuevo conjunto de revisiones en la ficha **Review sets** del caso. Para obtener más información, vea [Manage Review sets](managing-review-sets.md).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Paso 1: identificar el contenido que se va a agregar a otro conjunto de revisión

Puede agregar contenido a un conjunto de revisión seleccionando correos electrónicos y documentos en la cuadrícula del documento o todos los elementos de un resultado de búsqueda.  Si elige agregar elementos seleccionados, seleccione los elementos, haga clic en **acción**y, a continuación, haga clic en **Agregar a otro conjunto de revisión**.

![Agregar a otro conjunto de revisión](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Paso 2: especificar opciones para agregar a otro conjunto de revisión

En la página **Agregar a otro conjunto de revisión** , elija el conjunto de revisiones al que desea agregar los elementos. Elija si desea agregar **todos los resultados de búsqueda** o los **elementos seleccionados**.  Información adicional proporciona opciones para incluir todos los metadatos de los elementos y, finalmente, si las etiquetas del documento deben incluirse o no en el nuevo conjunto de revisión.  Después de hacer clic en **Aceptar** , se creará un nuevo trabajo para agregar el contenido a un conjunto de revisión; puede supervisar el progreso de ese trabajo en la pestaña **trabajo** . Para obtener más información, consulte [Manage Jobs](managing-jobs-ediscovery20.md).

![Agregar a otro conjunto de revisión](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)
