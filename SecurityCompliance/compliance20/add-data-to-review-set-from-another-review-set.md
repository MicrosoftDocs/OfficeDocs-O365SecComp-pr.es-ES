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
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="47b03-102">Agregar datos a un conjunto de revisión desde otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="47b03-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="47b03-103">En algunos casos, puede ser necesario dividir una parte de los documentos de un conjunto de revisión y trabajar con ellos de forma individual en otro conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="47b03-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="47b03-104">Esto es especialmente útil si ha seleccionado contenido en un conjunto de revisión y desea ejecutar análisis en el subconjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="47b03-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="47b03-105">Use el siguiente flujo de trabajo para agregar contenido de un conjunto de revisión a otro.</span><span class="sxs-lookup"><span data-stu-id="47b03-105">Use the following workflow to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="47b03-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="47b03-106">Before you begin</span></span>

<span data-ttu-id="47b03-107">Antes de empezar, deberá crear un nuevo conjunto de revisión para agregar los datos a.</span><span class="sxs-lookup"><span data-stu-id="47b03-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="47b03-108">Se puede Agregar un nuevo conjunto de revisiones en la ficha **Review sets** del caso.</span><span class="sxs-lookup"><span data-stu-id="47b03-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="47b03-109">Para obtener más información, vea [Manage Review sets](managing-review-sets.md).</span><span class="sxs-lookup"><span data-stu-id="47b03-109">For more information, see [Manage review sets](managing-review-sets.md).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="47b03-110">Paso 1: identificar el contenido que se va a agregar a otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="47b03-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="47b03-111">Puede agregar contenido a un conjunto de revisión seleccionando correos electrónicos y documentos en la cuadrícula del documento o todos los elementos de un resultado de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="47b03-111">You can add content to a review set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="47b03-112">Si elige agregar elementos seleccionados, seleccione los elementos, haga clic en **acción**y, a continuación, haga clic en **Agregar a otro conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="47b03-112">If choosing to add selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![Agregar a otro conjunto de revisión](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="47b03-114">Paso 2: especificar opciones para agregar a otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="47b03-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="47b03-115">En la página **Agregar a otro conjunto de revisión** , elija el conjunto de revisiones al que desea agregar los elementos.</span><span class="sxs-lookup"><span data-stu-id="47b03-115">In the **Add to another review set** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="47b03-116">Elija si desea agregar **todos los resultados de búsqueda** o los **elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="47b03-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="47b03-117">Información adicional proporciona opciones para incluir todos los metadatos de los elementos y, finalmente, si las etiquetas del documento deben incluirse o no en el nuevo conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="47b03-117">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new review set.</span></span>  <span data-ttu-id="47b03-118">Después de hacer clic en **Aceptar** , se creará un nuevo trabajo para agregar el contenido a un conjunto de revisión; puede supervisar el progreso de ese trabajo en la pestaña **trabajo** . Para obtener más información, consulte [Manage Jobs](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="47b03-118">After clicking **Ok** a new job will be created to add the content to a review set; you can monitor the progress of that job on the **Job** tab. For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>

![Agregar a otro conjunto de revisión](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)
