---
title: Comprender la similitud de documentos en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Revisión de cómo funciona el documento valor similitud, el nivel mínimo de similitud para los dos archivos se considere cerca de duplicados, en la exhibición de documentos electrónicos avanzada de Office 365. '
ms.openlocfilehash: 39cd8c31204f0164f6b52c71fa707253cb22758a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536026"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d6046-103">Comprender la similitud de documentos en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="d6046-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d6046-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="d6046-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d6046-106">En la exhibición de documentos electrónicos avanzada, similitud de documento es el nivel mínimo de similitud necesario para que dos documentos que se considerarán cerca de duplicados.</span><span class="sxs-lookup"><span data-stu-id="d6046-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="d6046-p102">Para la mayoría de las aplicaciones empresariales, se recomienda utilizar un valor de similitud del 60% - 75%. Muy mala calidad reconocimiento óptico de caracteres (OCR) (en inglés), se pueden aplicar los valores más bajos de similitud.</span><span class="sxs-lookup"><span data-stu-id="d6046-p102">For most business applications, it is recommended to use a Similarity value of 60%-75%. For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d6046-109">Una vez que ha establecido y ejecutar para un caso determinado, no se puede cambiar el valor de similitud.</span><span class="sxs-lookup"><span data-stu-id="d6046-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="d6046-p103">Dentro de un conjunto de duplicados Near (ND), es posible que haya documentos con un nivel de similitud por debajo del umbral de similitud. Para que un documento para unirse a un conjunto de ND, debe haber al menos un documento en el ND establecer con un nivel de la superación del límite de la similitud de similitud.</span><span class="sxs-lookup"><span data-stu-id="d6046-p103">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold. For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="d6046-112">Por ejemplo, supongamos que la similitud se establece en 80%, documento F1 es similar a documento F2 en un nivel de 85% y documento F2 es similar a documento F3 en un nivel de 90%.</span><span class="sxs-lookup"><span data-stu-id="d6046-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="d6046-p104">Sin embargo, el documento F1 puede ser similar a documento F3 en un nivel de sólo el 70%, que es por debajo del umbral. No obstante, en este ejemplo, documentos F1, F2 y F3 todos aparecen en la uno ND establecido. De forma similar, con un valor de similitud del 80%, nos podremos ha creado dos conjuntos, EquiSet-1 y EquiSet-2. EquiSet-1 contiene documentos E1 y E2. Equiset-2 contiene documentos F1, F2 y F3.</span><span class="sxs-lookup"><span data-stu-id="d6046-p104">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold. Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set. Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2. EquiSet-1 contains documents E1 and E2. Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="d6046-118">Los niveles de similitud se ilustran como sigue:</span><span class="sxs-lookup"><span data-stu-id="d6046-118">The levels of resemblance are illustrated as follows:</span></span>
  
![Similitud de documentos](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="d6046-p105">Se supone que el otro documento, X1, ahora se inserta. La similitud entre X1 y E3 es 87%. De forma similar, la similitud entre X1 y F1 es 92%. Como resultado, EquiSet -1, EquiSet -2 y X1 ahora se combinan en uno ND establecer.</span><span class="sxs-lookup"><span data-stu-id="d6046-p105">Assume that another document, X1, is now inserted. The resemblance between X1 and E3 is 87%. Similarly, the resemblance between X1 and F1 is 92%. As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![Similitud de documentos](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="d6046-125">Si los dos documentos están asignados a un conjunto de ND, seguirán siendo juntos en el mismo conjunto de ND, documentos incluso si adicionales se agregan al conjunto o si se combinan los conjuntos.</span><span class="sxs-lookup"><span data-stu-id="d6046-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="d6046-126">Después de que se combinan conjuntos, puede cambiar el documento de la tabla dinámica cuando se agregan nuevos documentos a un conjunto.</span><span class="sxs-lookup"><span data-stu-id="d6046-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d6046-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6046-127">See also</span></span>

[<span data-ttu-id="d6046-128">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="d6046-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d6046-129">Configurar las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="d6046-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d6046-130">Configuración de omitir el texto</span><span class="sxs-lookup"><span data-stu-id="d6046-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d6046-131">Análisis de la opción Configuración avanzada</span><span class="sxs-lookup"><span data-stu-id="d6046-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d6046-132">Ver los resultados del análisis</span><span class="sxs-lookup"><span data-stu-id="d6046-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

