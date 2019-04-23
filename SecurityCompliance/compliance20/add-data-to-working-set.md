---
title: Agregar los resultados de búsqueda a un conjunto de trabajo
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
ms.openlocfilehash: 7830b483190a69e6055fae369580064c5df42f49
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958291"
---
# <a name="add-search-results-to-a-working-set"></a>Agregar los resultados de búsqueda a un conjunto de trabajo

Después de identificar y seleccionar las búsquedas realizadas en Exchange, SharePoint y OneDrive para la empresa, puede Agregar los resultados a un conjunto de trabajo. Los conjuntos de trabajo representan un conjunto estático de documentos que indizaremos para obtener resultados de búsqueda de alta velocidad, analizar la identificación de subprocesos de correo electrónico, cerca de la detección de duplicados y los temas.  También puede Agregar a la vez datos de orígenes de datos que no son de Office 365 en paralelo con los datos recopilados de Office 365.

Para agregar datos a un conjunto de trabajo, comience seleccionando una búsqueda y, en los resultados de la búsqueda, haga clic en el botón *+ Agregar resultados al conjunto de trabajo* .

![Adición de datos a un conjunto de trabajo](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

A continuación, puede optar por agregar a un conjunto de trabajo existente o a un *nuevo conjunto de trabajo*.  Si se agrega a un nuevo espacio de trabajo, especifique el nombre y, por último, haga clic en el botón *Agregar* .

![Selección de un conjunto de trabajo](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

Agregar datos a un conjunto de trabajo es un proceso de ejecución larga, puede realizar el seguimiento del progreso en la ficha trabajos o en la columna *Estado del conjunto de trabajo* en la ficha *búsquedas* .  El proceso incluye la recopilación de elementos de Office 365 y, finalmente, la indización de & de recopilación.  Una vez que se haya completado el procesamiento del conjunto de trabajo, haga clic en la ficha *conjuntos* de trabajo para desplazarse hasta el conjunto de trabajo y, a continuación, haga clic en el conjunto de trabajo.  A continuación, puede continuar con la búsqueda, la revisión, el etiquetado y la exportación de los datos relevantes.

## <a name="adding-a-sample-to-a-working-set"></a>Adición de un ejemplo a un conjunto de trabajo

Si desea validar los resultados de la búsqueda más thorougly antes de recopilar todos los documentos que ha recuperado la búsqueda, puede Agregar un ejemplo aleatorio de los resultados de la búsqueda a un conjunto de trabajo en lugar de agregarlo todo.

Para agregar un ejemplo a un conjunto de trabajo, empiece seleccionando una búsqueda, en el control flotante de resultados de la búsqueda, haga clic en botón de *muestra* .

A continuación, puede elegir el parámetro de su muestreo. Hay dos opciones:
- Intervalo y nivel de confianza: se elegirá el tamaño de muestra para cumplir los parámetros estadísticos especificados.
- Porcentaje: el tamaño de muestra se determinará en función del número de elementos que ha devuelto la búsqueda y el parámetro elegido.

Por último, elija el conjunto de trabajo al que desea agregar el ejemplo. Desde allí, puede comprobar el estado del proceso de la misma manera que lo haría para agregar una búsqueda completa en un conjunto de trabajo. 