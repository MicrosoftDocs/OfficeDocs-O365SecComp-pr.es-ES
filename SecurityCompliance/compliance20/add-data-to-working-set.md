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
# <a name="add-search-results-to-a-working-set"></a><span data-ttu-id="1179f-102">Agregar los resultados de búsqueda a un conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="1179f-102">Add search results to a working set</span></span>

<span data-ttu-id="1179f-103">Después de identificar y seleccionar las búsquedas realizadas en Exchange, SharePoint y OneDrive para la empresa, puede Agregar los resultados a un conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1179f-103">After you've identified and culled with searches against Exchange, SharePoint and OneDrive for business, you can add the results to a working set.</span></span> <span data-ttu-id="1179f-104">Los conjuntos de trabajo representan un conjunto estático de documentos que indizaremos para obtener resultados de búsqueda de alta velocidad, analizar la identificación de subprocesos de correo electrónico, cerca de la detección de duplicados y los temas.</span><span class="sxs-lookup"><span data-stu-id="1179f-104">Working sets represent a static set of documents that we will index for lightning fast search results, analyze for email thread identification, near duplicate detection and themes.</span></span>  <span data-ttu-id="1179f-105">También puede Agregar a la vez datos de orígenes de datos que no son de Office 365 en paralelo con los datos recopilados de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1179f-105">You can also add data from Non-Office 365 data sources to live side by side with the data you collect from Office 365.</span></span>

<span data-ttu-id="1179f-106">Para agregar datos a un conjunto de trabajo, comience seleccionando una búsqueda y, en los resultados de la búsqueda, haga clic en el botón *+ Agregar resultados al conjunto de trabajo* .</span><span class="sxs-lookup"><span data-stu-id="1179f-106">To add data to a working set, start by selecting a search, in the search results fly out, click the *+ Add results to working set* button.</span></span>

![Adición de datos a un conjunto de trabajo](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="1179f-108">A continuación, puede optar por agregar a un conjunto de trabajo existente o a un *nuevo conjunto de trabajo*.</span><span class="sxs-lookup"><span data-stu-id="1179f-108">You can then choose to add to an existing working set or a *New working set*.</span></span>  <span data-ttu-id="1179f-109">Si se agrega a un nuevo espacio de trabajo, especifique el nombre y, por último, haga clic en el botón *Agregar* .</span><span class="sxs-lookup"><span data-stu-id="1179f-109">If adding to a new working set, specify the name and finally click the *Add* button.</span></span>

![Selección de un conjunto de trabajo](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="1179f-111">Agregar datos a un conjunto de trabajo es un proceso de ejecución larga, puede realizar el seguimiento del progreso en la ficha trabajos o en la columna *Estado del conjunto de trabajo* en la ficha *búsquedas* .  El proceso incluye la recopilación de elementos de Office 365 y, finalmente, la indización de & de recopilación.</span><span class="sxs-lookup"><span data-stu-id="1179f-111">Adding data to a working set is a long running process, you can either track the progress in the Jobs tab or in the *Working set status* column in the *Searches* tab.  The process includes gathering items from Office 365 and finally Ingestion & Indexing.</span></span>  <span data-ttu-id="1179f-112">Una vez que se haya completado el procesamiento del conjunto de trabajo, haga clic en la ficha *conjuntos* de trabajo para desplazarse hasta el conjunto de trabajo y, a continuación, haga clic en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1179f-112">Once working set processing is completed, you can navigate to the working set by clicking on the *Working Sets* tab and then clicking on the working set.</span></span>  <span data-ttu-id="1179f-113">A continuación, puede continuar con la búsqueda, la revisión, el etiquetado y la exportación de los datos relevantes.</span><span class="sxs-lookup"><span data-stu-id="1179f-113">You can then move on to searching, reviewing, tagging and exporting any relevant data.</span></span>

## <a name="adding-a-sample-to-a-working-set"></a><span data-ttu-id="1179f-114">Adición de un ejemplo a un conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="1179f-114">Adding a sample to a working set</span></span>

<span data-ttu-id="1179f-115">Si desea validar los resultados de la búsqueda más thorougly antes de recopilar todos los documentos que ha recuperado la búsqueda, puede Agregar un ejemplo aleatorio de los resultados de la búsqueda a un conjunto de trabajo en lugar de agregarlo todo.</span><span class="sxs-lookup"><span data-stu-id="1179f-115">If you would like to validate your search results more thorougly before collecting all documents that were retrieved by your search, you can add a random sample of the search results to a working set instead of adding everything.</span></span>

<span data-ttu-id="1179f-116">Para agregar un ejemplo a un conjunto de trabajo, empiece seleccionando una búsqueda, en el control flotante de resultados de la búsqueda, haga clic en botón de *muestra* .</span><span class="sxs-lookup"><span data-stu-id="1179f-116">To add a sample to a working set, start by selecting a search, in the search results flyout, click *Sample* button.</span></span>

<span data-ttu-id="1179f-117">A continuación, puede elegir el parámetro de su muestreo.</span><span class="sxs-lookup"><span data-stu-id="1179f-117">You can then choose the parameter of your sampling.</span></span> <span data-ttu-id="1179f-118">Hay dos opciones:</span><span class="sxs-lookup"><span data-stu-id="1179f-118">There are two options:</span></span>
- <span data-ttu-id="1179f-119">Intervalo y nivel de confianza: se elegirá el tamaño de muestra para cumplir los parámetros estadísticos especificados.</span><span class="sxs-lookup"><span data-stu-id="1179f-119">Confidence level and interval: sample size will be chosen to satisfy the given statistical parameters.</span></span>
- <span data-ttu-id="1179f-120">Porcentaje: el tamaño de muestra se determinará en función del número de elementos que ha devuelto la búsqueda y el parámetro elegido.</span><span class="sxs-lookup"><span data-stu-id="1179f-120">Percentage: sample size will be determined based on the number of items that was returned by the search, and the chosen parameter.</span></span>

<span data-ttu-id="1179f-121">Por último, elija el conjunto de trabajo al que desea agregar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1179f-121">Finally, choose the working set to add the sample to.</span></span> <span data-ttu-id="1179f-122">Desde allí, puede comprobar el estado del proceso de la misma manera que lo haría para agregar una búsqueda completa en un conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1179f-122">From there, you can check the status of the process just as you would for adding a whole search into a working set.</span></span> 