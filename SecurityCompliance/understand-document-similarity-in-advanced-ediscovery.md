---
title: Comprender la similitud de documentos en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Revise cómo el valor de similitud de documentos, el nivel mínimo de semejanza entre dos archivos que se consideran casi duplicados, funciona en eDiscovery avanzado de Office 365. '
ms.openlocfilehash: ce9c2e6ea1d40c82b7a124c9d4d64ce915d266b0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156382"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="627bb-103">Comprender la similitud de documentos en Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="627bb-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="627bb-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="627bb-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="627bb-106">En eDiscovery avanzado, la similitud de documentos es el nivel mínimo de semejanza necesario para que dos documentos se consideren como Near-duplicados.</span><span class="sxs-lookup"><span data-stu-id="627bb-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="627bb-107">Para la mayoría de las aplicaciones empresariales, se recomienda usar un valor de similitud de 60%-75%.</span><span class="sxs-lookup"><span data-stu-id="627bb-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="627bb-108">Para un material de reconocimiento óptico de caracteres (OCR) de calidad deficiente, se pueden aplicar valores de similitud inferiores.</span><span class="sxs-lookup"><span data-stu-id="627bb-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="627bb-109">Una vez establecido y ejecutado para un caso determinado, el valor de similitud no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="627bb-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="627bb-110">Dentro de un conjunto Near-duplicado (ND), es posible que haya documentos con un nivel de semejanza inferior al umbral de similitud.</span><span class="sxs-lookup"><span data-stu-id="627bb-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="627bb-111">Para que un documento se incorpore a un conjunto ND, debe haber al menos un documento en el ND establecido con un nivel de similitud superior a la similitud.</span><span class="sxs-lookup"><span data-stu-id="627bb-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="627bb-112">Por ejemplo, supongamos que la similitud se establece en 80%, el documento F1 es similar al documento F2 en un nivel del 85% y el documento F2 se asemeja al documento F3 en un nivel de 90%.</span><span class="sxs-lookup"><span data-stu-id="627bb-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="627bb-113">Sin embargo, el documento F1 puede parecerse al documento F3 en un nivel de solo 70%, que está por debajo del umbral.</span><span class="sxs-lookup"><span data-stu-id="627bb-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="627bb-114">Sin embargo, en este ejemplo, los documentos F1, F2 y F3 aparecen en el único grupo ND.</span><span class="sxs-lookup"><span data-stu-id="627bb-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="627bb-115">De forma similar, con un valor de similitud de 80%, podríamos haber creado dos conjuntos, EquiSet-1 y EquiSet-2.</span><span class="sxs-lookup"><span data-stu-id="627bb-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="627bb-116">EquiSet-1 contiene los documentos E1 y E2.</span><span class="sxs-lookup"><span data-stu-id="627bb-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="627bb-117">Equiset-2 contiene los documentos F1, F2 y F3.</span><span class="sxs-lookup"><span data-stu-id="627bb-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="627bb-118">Los niveles de semejanza se ilustran de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="627bb-118">The levels of resemblance are illustrated as follows:</span></span>
  
![Similitud de documentos](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="627bb-120">Supongamos que ya se ha insertado otro documento, x1.</span><span class="sxs-lookup"><span data-stu-id="627bb-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="627bb-121">La semejanza entre x1 y E3 es de 87%.</span><span class="sxs-lookup"><span data-stu-id="627bb-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="627bb-122">De forma similar, la semejanza entre x1 y F1 es de 92%.</span><span class="sxs-lookup"><span data-stu-id="627bb-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="627bb-123">Como resultado, EquiSet-1, EquiSet-2 y x1 se combinan ahora en un conjunto ND.</span><span class="sxs-lookup"><span data-stu-id="627bb-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![Similitud de documentos](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="627bb-125">Si hay dos documentos asignados a un conjunto ND, se mantendrán juntos en el mismo conjunto ND, incluso si se agregan documentos adicionales al conjunto o si se combinan los conjuntos.</span><span class="sxs-lookup"><span data-stu-id="627bb-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="627bb-126">Una vez que se combinan los conjuntos, el documento dinámico puede cambiar cuando se agregan nuevos documentos a un conjunto.</span><span class="sxs-lookup"><span data-stu-id="627bb-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="627bb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="627bb-127">See also</span></span>

[<span data-ttu-id="627bb-128">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="627bb-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="627bb-129">Configuración de las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="627bb-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="627bb-130">Configuración de omitir texto</span><span class="sxs-lookup"><span data-stu-id="627bb-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="627bb-131">Configuración de la configuración avanzada de análisis</span><span class="sxs-lookup"><span data-stu-id="627bb-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="627bb-132">Visualización de los resultados del análisis</span><span class="sxs-lookup"><span data-stu-id="627bb-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

