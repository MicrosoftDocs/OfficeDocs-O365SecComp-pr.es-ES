---
title: Agregar los resultados de búsqueda a un conjunto de revisión
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
ms.openlocfilehash: fac8ab829107befaa1a3f8b3afe1cec8d3468f1b
ms.sourcegitcommit: bac1b5be5db381e6f8d8f652cff1f8ef4d7f6330
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2019
ms.locfileid: "35233327"
---
# <a name="add-search-results-to-a-review-set"></a>Agregar los resultados de búsqueda a un conjunto de revisión

Cuando esté satisfecho con los resultados de una búsqueda y esté listo para revisar y analizar los resultados de la búsqueda, puede agregarlos a un conjunto de revisión en el caso. La copia de los datos originales en el conjunto de revisión también facilita el proceso de revisión y análisis al proporcionarle herramientas avanzadas de análisis como detección de temas, detección de casi duplicados y identificación de subprocesos de correo electrónico. También puede agregar datos de orígenes de datos que no sean de Office 365 a un conjunto de revisión, de modo que pueda revisar los datos además de los datos que recopila de Office 365.

Cuando se agregan los resultados de una búsqueda a un conjunto de revisión (los conjuntos de revisión se encuentran en la ficha **Review sets** del caso), se producen las siguientes situaciones:

- La búsqueda se vuelve a ejecutar. Esto significa que los resultados de la búsqueda reales que se copien en el conjunto de revisión pueden ser diferentes de los resultados estimados que se devolvieron cuando se ejecutó la búsqueda por última vez.

- Todos los elementos de los resultados de la búsqueda se copian del origen de datos original en los servicios Live 365 de Office y se copian en una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

- Todos los elementos (incluido el contenido y los metadatos) se vuelven a indizar para que todos los datos del conjunto de revisión se puedan buscar por completo durante la revisión de los datos del caso. Volver a indizar los datos da como resultado búsquedas exhaustivas y muy rápidas al buscar los datos en el conjunto de revisión durante la investigación de caso.

Para agregar datos a un conjunto de revisión, haga clic en una búsqueda en la ficha **búsquedas** y, a continuación, haga clic en **Agregar resultados a revisión establecida** en la página de flotante.

![Adición de datos a un conjunto de revisión](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

Puede Agregar a un conjunto de revisiones existente o crear un nuevo conjunto de revisión.  Si agrega a un nuevo conjunto de revisiones, especifique el nombre y, a continuación, haga clic en **Agregar**.

![Seleccionar un conjunto de revisión](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

Agregar datos a un conjunto de revisión es un proceso de ejecución prolongada. Este proceso incluye la recopilación de elementos de los orígenes de datos originales en Office 365 (por ejemplo, desde buzones y sitios), copiándolos en la ubicación de almacenamiento de Azure (este proceso ** de copia también se denomina ingesta) y, a continuación, vuelva a indizar los elementos. Puede realizar un seguimiento del progreso en la ficha **trabajos** o en la ficha **búsquedas** mediante la supervisión del estado en la columna **datos agregados a la configuración de revisión** . Una vez completado el procesamiento del conjunto de revisiones, haga clic en la pestaña **Review sets** en el caso y haga clic en el conjunto de revisión para iniciar el proceso de filtrado, revisión, etiquetado y exportación de datos en el conjunto de revisiones.

## <a name="add-a-sample-to-a-review-set"></a>Agregar un ejemplo a un conjunto de revisión

Si desea validar los resultados de una búsqueda más minuciosamente antes de agregarlos todos a un conjunto de revisión, puede Agregar una muestra de los resultados de la búsqueda a un conjunto de revisión en lugar de agregarlo todo.

Para agregar un ejemplo a un conjunto de revisión, haga clic en una búsqueda en la ficha **búsquedas** y haga clic en **muestra** en la página de flotante. En la página **parámetros de muestreo** , elija una de las siguientes opciones:

- **Nivel de confianza%** y **porcentaje de intervalo de confianza** : los elementos agregados al conjunto de revisión estarán determinados por los parámetros estadísticos que establezca. Si normalmente usa un nivel de confianza y un intervalo para los resultados de muestreo, debe especificarlos en los cuadros desplegables. De lo contrario, use la configuración predeterminada.

- **Muestra aleatoria%** : los elementos agregados al conjunto de revisión se basan en una selección aleatoria del porcentaje especificado del número total de elementos devueltos por la búsqueda.

Después de seleccionar y configurar una de las opciones anteriores, elija un conjunto de revisiones para agregar el ejemplo y, a continuación, haga clic en **Enviar**. Una vez más, puede realizar un seguimiento del progreso en la ficha **trabajos** o en la ficha **búsquedas** mediante la supervisión del estado en la columna **datos agregados a la configuración de revisión** .