---
title: Configuración de la detección de privilegios de clientes de abogado en eDiscovery avanzado
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ee5f2257e73467c50a0ecc296d8d3b70b7c3d0f8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155192"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a><span data-ttu-id="507df-102">Configurar un abogado-detección de privilegios de cliente (versión preliminar) en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="507df-102">Set up attorney-client privilege detection (preview) in Advanced eDiscovery</span></span>

<span data-ttu-id="507df-103">Un aspecto importante y costoso de la parte de revisión de cualquier proceso de detección es la revisión del contenido privilegiado.</span><span class="sxs-lookup"><span data-stu-id="507df-103">A major and costly aspect of the review portion of any discovery process is reviewing for privileged content.</span></span> <span data-ttu-id="507df-104">EDiscovery avanzado proporciona una detección de contenido privilegiado basada en AI en su caso, de modo que pueda hacer que este proceso sea más eficaz.</span><span class="sxs-lookup"><span data-stu-id="507df-104">Advanced eDiscovery provides an AI-based detection of privileged content in your case so that you can make this process more efficient.</span></span> <span data-ttu-id="507df-105">Como esta característica está actualmente en versión beta, un administrador de eDiscovery tiene que participar en la característica para usarla.</span><span class="sxs-lookup"><span data-stu-id="507df-105">As this feature is currently in beta, an eDiscovery Administrator has to opt into the feature to use it.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="507df-106">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="507df-106">How does it work?</span></span>

<span data-ttu-id="507df-107">Con la característica activada, al analizar un conjunto de revisión en un caso, todos los documentos se ejecutan a través del modelo de detección de privilegios de clientes de abogados.</span><span class="sxs-lookup"><span data-stu-id="507df-107">With the feature turned on, when you analyze a review set within a case, all documents run through the attorney-client privilege detection model.</span></span> <span data-ttu-id="507df-108">El modelo examina dos cosas:</span><span class="sxs-lookup"><span data-stu-id="507df-108">The model looks at two things:</span></span>

- <span data-ttu-id="507df-109">Contenido: el modelo de ML determina la probabilidad de que el contenido del documento sea legal por naturaleza.</span><span class="sxs-lookup"><span data-stu-id="507df-109">Content: the ML model determines the likelihood of the document's content being legal in nature.</span></span>

- <span data-ttu-id="507df-110">Participantes: si hay una lista de abogados cargados por el usuario para el inquilino, el modelo compara los participantes del documento con la lista para determinar si el documento tiene al menos un participante abogado.</span><span class="sxs-lookup"><span data-stu-id="507df-110">Participants: if there is a user-uploaded list of attorneys for the tenant, the model compares the participants of the document against the list to determine whether the document has at least one attorney participant.</span></span>
<span data-ttu-id="507df-111">El modelo da como resultado tres valores para cada documento, todos los cuales se pueden buscar en un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="507df-111">The model outputs three values for every document, all of which will be searchable within a review set:</span></span>

- <span data-ttu-id="507df-112">Puntuación del contenido: la probabilidad de que el documento sea legal por naturaleza (puntuación entre 0 y 1)</span><span class="sxs-lookup"><span data-stu-id="507df-112">Content score: the likelihood of the document being legal in nature (score between 0 and 1)</span></span>

- <span data-ttu-id="507df-113">Tiene un abogado: true si uno de los participantes se encuentra en la lista de abogados cargados; de lo contrario, es false o si no hay ninguna lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="507df-113">Has Attorney: True if one of the participants is found in the uploaded attorney list, false otherwise, or if there is no attorney list.</span></span>

-  <span data-ttu-id="507df-114">Potencialmente privilegiado: true si la puntuación del contenido es superior al umbral o tiene un participante abogado; de lo contrario, es false.</span><span class="sxs-lookup"><span data-stu-id="507df-114">Potentially Privileged: True if content score is above threshold or has an attorney participant, false otherwise.</span></span>

## <a name="opting-into-attorney-client-privilege-detection"></a><span data-ttu-id="507df-115">Optar a abogado-detección de privilegios de clientes</span><span class="sxs-lookup"><span data-stu-id="507df-115">Opting into Attorney-client privilege detection</span></span>

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a><span data-ttu-id="507df-116">Paso 1: participar en la detección de privilegios de cliente (eDiscovery admin)</span><span class="sxs-lookup"><span data-stu-id="507df-116">Step 1: Opt into Attorney-client privilege detection (eDiscovery Admin)</span></span>

<span data-ttu-id="507df-117">Como abogado-la detección de privilegios de cliente es una característica de vista previa, el administrador de eDiscovery debe participar para que la característica esté disponible en sus casos.</span><span class="sxs-lookup"><span data-stu-id="507df-117">Because Attorney-client privilege detection is a preview feature, your eDiscovery Administrator needs to opt in to make the feature available in your cases.</span></span>

- <span data-ttu-id="507df-118">Vaya a "configurar características experimentales" en la página exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="507df-118">Go to "Configure experimental features" from Advanced eDiscovery page</span></span>

- <span data-ttu-id="507df-119">Haga clic en "administrar abogado-detección de privilegios de cliente".</span><span class="sxs-lookup"><span data-stu-id="507df-119">Click on "Manage Attorney-Client Privilege detection".</span></span>

- <span data-ttu-id="507df-120">Haga clic en el botón de alternancia para activar la característica.</span><span class="sxs-lookup"><span data-stu-id="507df-120">Click on the toggle to turn the feature on.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="507df-121">Paso 2: cargar una lista de abogados (opcional)</span><span class="sxs-lookup"><span data-stu-id="507df-121">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="507df-122">Para aprovechar todas las ventajas de la detección de privilegios de clientes y abogados, le recomendamos que proporcione una lista de abogados o personas jurídicas que trabajan para la empresa.</span><span class="sxs-lookup"><span data-stu-id="507df-122">In order to take full advantage of attorney-client privilege detection we recommend providing a list of email addresses lawyers or legal personas who work for the company.</span></span> <span data-ttu-id="507df-123">La lista debe ser un CSV sin encabezado, con una dirección de correo electrónico por línea.</span><span class="sxs-lookup"><span data-stu-id="507df-123">The list should be a header-less CSV, with one email address per line.</span></span>

## <a name="leveraging-attorney-client-privilege-detection"></a><span data-ttu-id="507df-124">Aprovechamiento de la detección de privilegios de clientes de abogados</span><span class="sxs-lookup"><span data-stu-id="507df-124">Leveraging attorney-client privilege detection</span></span> 

### <a name="step-1-analyze-a-review-set"></a><span data-ttu-id="507df-125">Paso 1: analizar un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="507df-125">Step 1: Analyze a review set</span></span>

<span data-ttu-id="507df-126">Al analizar el conjunto de revisión, también se ejecutará la detección de privilegios de clientes de abogados.</span><span class="sxs-lookup"><span data-stu-id="507df-126">When you analyze your review set, attorney-client privilege detection will be run as well.</span></span> <span data-ttu-id="507df-127">Para obtener más información acerca del análisis de datos en el conjunto de revisiones, consulte [analizar datos en un conjunto de revisiones en EDiscovery avanzado](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="507df-127">To learn more about analyzing data in review set, please refer to [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="507df-128">Paso 2: crear un grupo de etiquetas inteligentes con un modelo de detección de privilegios de clientes de abogados</span><span class="sxs-lookup"><span data-stu-id="507df-128">Step 2: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="507df-129">Una de las principales formas en que puede consumir los resultados de la detección de privilegios de clientes de abogados en el proceso de revisión consiste en usar un grupo de etiquetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="507df-129">One of the main ways you can consume the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="507df-130">Los grupos de etiquetas inteligentes toman los resultados de un modelo de ML y muestran los resultados del modelo en línea junto a las etiquetas, de modo que puede consumir fácilmente los resultados del modelo cuando sea relevante y usar las etiquetas en el proceso de revisión como lo haría con cualquier otra etiqueta del panel de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="507df-130">Smart tag groups take the results of an ML model and show the results of the model in-line next to the tags, so that you can easily consume the results of the model where relevant, and use the tags in your review process as you would any other tags in your tagging panel.</span></span> <span data-ttu-id="507df-131">Para obtener más información, consulte [Configurar etiquetas inteligentes para la revisión asistida por ml en EDiscovery avanzado](smart-tags.md) .</span><span class="sxs-lookup"><span data-stu-id="507df-131">Please refer to [Set up smart tags for ML-assisted review in Advanced eDiscovery](smart-tags.md) for more information.</span></span>

- <span data-ttu-id="507df-132">En "administrar etiquetas", haga clic en "agregar sección de etiquetas inteligentes".</span><span class="sxs-lookup"><span data-stu-id="507df-132">In "Manage tags", click on "Add smart tag section".</span></span>

- <span data-ttu-id="507df-133">Seleccione "abogado-detección de privilegios de clientes".</span><span class="sxs-lookup"><span data-stu-id="507df-133">Select "Attorney-client privilege detection".</span></span> <span data-ttu-id="507df-134">Verá que se han creado un grupo de etiquetas y dos etiquetas, correspondientes a los resultados posibles del modelo.</span><span class="sxs-lookup"><span data-stu-id="507df-134">You will see that a tag group and two tags, corresponding to the possible results of the model, have been created.</span></span>

- <span data-ttu-id="507df-135">Cambie el nombre del grupo de etiquetas y las etiquetas según sus propias revisiones.</span><span class="sxs-lookup"><span data-stu-id="507df-135">Rename the tag group and tags as you see fit for your review.</span></span>

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a><span data-ttu-id="507df-136">Paso 3: usar el grupo de etiquetas inteligentes para la revisión de privilegios</span><span class="sxs-lookup"><span data-stu-id="507df-136">Step 3: Use the smart tag group for privilege review</span></span>

<span data-ttu-id="507df-137">Al revisar un documento, si el modelo ha determinado que el documento tiene potencialmente privilegios, la etiqueta inteligente correspondiente expondrá el resultado:</span><span class="sxs-lookup"><span data-stu-id="507df-137">When you review a document, if the model has determined that the document is potentially privileged, the corresponding smart tag will expose the result:</span></span>

- <span data-ttu-id="507df-138">Si el documento tiene contenido que puede ser legal por naturaleza, aparecerá una etiqueta de "contenido legal" junto a la etiqueta inteligente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="507df-138">If the document has content that may be legal in nature, a "Legal content" label will appear next to the corresponding smart tag.</span></span>

- <span data-ttu-id="507df-139">Si el documento tiene un participante que se encuentra en la lista de abogados cargados, aparecerá una etiqueta "abogado" junto a la etiqueta inteligente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="507df-139">If the document has a participant that is found in the uploaded attorney list, an "Attorney" label will appear next to the corresponding smart tag.</span></span>