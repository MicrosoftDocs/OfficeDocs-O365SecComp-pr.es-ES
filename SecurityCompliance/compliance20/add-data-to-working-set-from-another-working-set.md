---
title: Adición de datos de un conjunto de trabajo a otro conjunto de trabajo
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
ms.openlocfilehash: e9e34d112cb84c27fec35e752eb2bfcbfe3136a3
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958241"
---
# <a name="add-data-to-a-working-set-from-another-working-set"></a><span data-ttu-id="30f20-102">Agregar datos a un conjunto de trabajo desde otro conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="30f20-102">Add data to a working set from another working set</span></span>
<span data-ttu-id="30f20-103">En algunos casos, puede ser necesario dividir una parte de los documentos de un conjunto de trabajo y trabajar con ellos de forma individual en otro conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="30f20-103">In some cases, it may be necessary to carve out a portion of documents from one working set and work with them individually in another working set.</span></span>  <span data-ttu-id="30f20-104">Esto es especialmente útil si ha seleccionado contenido en un conjunto de trabajo y desea ejecutar análisis en el subconjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="30f20-104">This is especially useful if you've culled content in a working set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="30f20-105">Use el siguiente flujo de trabajo para agregar contenido de un conjunto de trabajo a otro.</span><span class="sxs-lookup"><span data-stu-id="30f20-105">Use the following workflow to add content from one working set to another.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="30f20-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="30f20-106">Before you start</span></span>
<span data-ttu-id="30f20-107">Antes de empezar, deberá crear un nuevo conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="30f20-107">Before you start, you'll need to create a new working set.</span></span>  <span data-ttu-id="30f20-108">Se puede Agregar un nuevo conjunto de trabajo a través de la pestaña *conjuntos de trabajo* para obtener [más información](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets).</span><span class="sxs-lookup"><span data-stu-id="30f20-108">A new working set can be added through the *Working sets* tab [Learn more](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets).</span></span>

## <a name="step-1-identify-content-to-add-to-another-working-set"></a><span data-ttu-id="30f20-109">Paso 1: identificar el contenido que se va a agregar a otro conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="30f20-109">Step 1: Identify content to add to another working set</span></span>
<span data-ttu-id="30f20-110">Puede agregar contenido a un conjunto de trabajo seleccionando correos electrónicos y documentos en la cuadrícula del documento o todos los elementos de un resultado de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="30f20-110">You can add content to a working set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="30f20-111">Si elige agregar elementos seleccionados, seleccione los elementos y haga clic en el menú desplegable *acción* y, a continuación, *agregue a otro conjunto de trabajo*.</span><span class="sxs-lookup"><span data-stu-id="30f20-111">If choosing to add selected items, select the items and click the *Action* drop down then *Add to another working set*.</span></span>

![Agregar a otro conjunto de trabajo](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-workings-set"></a><span data-ttu-id="30f20-113">Paso 2: especificar opciones para agregar a otro conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="30f20-113">Step 2: Specify options for adding to another workings set</span></span>
<span data-ttu-id="30f20-114">En el control flotante *Opciones de agregar a otro conjunto de trabajo* , elija primero el conjunto de trabajo al que desea agregar los elementos.</span><span class="sxs-lookup"><span data-stu-id="30f20-114">In the *Add to another working set options* flyout, first choose the working set you want to add the items to.</span></span>  <span data-ttu-id="30f20-115">Elija si desea agregar todos los resultados de búsqueda o los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="30f20-115">Choose whether to add All search results or Selected items.</span></span>  <span data-ttu-id="30f20-116">Información adicional proporciona opciones para incluir todos los metadatos de los elementos y, finalmente, si las etiquetas del documento deben incluirse o no en el nuevo conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="30f20-116">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new working set.</span></span>  <span data-ttu-id="30f20-117">Después de hacer clic en *Aceptar* , se creará un nuevo trabajo para agregar el contenido a un conjunto de trabajo, puede supervisar el progreso de ese trabajo en ![la pestaña [trabajos](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20) . Agregar a otro conjunto de trabajo](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span><span class="sxs-lookup"><span data-stu-id="30f20-117">After clicking *OK* a new job will be created to add the content to a working set, you can monitor the progress of that job in the [Jobs](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20) tab. ![Add to another working set](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span></span>
