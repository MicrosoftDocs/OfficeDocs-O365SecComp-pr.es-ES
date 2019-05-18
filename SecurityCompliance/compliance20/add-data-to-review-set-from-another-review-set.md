---
title: Agregar datos de un conjunto de revisión a otro conjunto de revisión
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
ms.openlocfilehash: 9dc75717ac0a57c8ccb38b1e01ec2fcb9c5737ab
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151972"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Agregar datos a un conjunto de revisión desde otro conjunto de revisión

En algunos casos, puede ser necesario dividir una parte de los documentos de un conjunto de revisión y trabajar con ellos de forma individual en otro conjunto de revisión.  Esto es especialmente útil si ha seleccionado contenido en un conjunto de revisión y desea ejecutar análisis en el subconjunto de datos.

Siga el flujo de trabajo de este artículo para agregar contenido de un conjunto de revisión a otro.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar, deberá crear un nuevo conjunto de revisión para agregar los datos a.  Se puede Agregar un nuevo conjunto de revisiones en la ficha **Review sets** del caso. Para obtener más información, vea [Create a Review Set](managing-review-sets.md#create-a-review-set).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Paso 1: identificar el contenido que se va a agregar a otro conjunto de revisión

Puede agregar contenido de un conjunto de revisión a otro seleccionando documentos específicos en el conjunto de revisión de origen o b seleting todos los elementos devueltos por el Review Set Query.  Si va a agregar elementos seleccionados, seleccione los elementos, haga clic en **acción**y, a continuación, haga clic en **Agregar a otro conjunto de revisión**.

![Agregar a otro conjunto de revisión](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Paso 2: especificar opciones para agregar a otro conjunto de revisión

En la página **Agregar a otro** control flotante opciones de definición de revisión, elija el conjunto de revisiones al que desea agregar los elementos. Elija si desea agregar **todos los resultados de búsqueda** o los **elementos seleccionados**.  Información adicional proporciona opciones para incluir todos los metadatos de los elementos y si desea incluir las etiquetas (activando la casilla de verificación **etiquetas** ) desde el conjunto de revisión de origen cuando se agregan los documentos al nuevo conjunto de revisión.  

![Agregar a otro conjunto de revisión](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

Después de hacer clic en **Aceptar**, se crea un nuevo trabajo (denominado **Agregar datos a otro conjunto de revisión**) para agregar el contenido a otro conjunto de revisión.  Puede ir a la pestaña de **trabajos** y supervisar el progreso de este trabajo. Para obtener más información, consulte [Manage Jobs](managing-jobs-ediscovery20.md).
