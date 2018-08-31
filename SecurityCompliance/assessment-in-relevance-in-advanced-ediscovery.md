---
title: Comprender la evaluación de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 'Obtenga una visión general de la fase de evaluación y su función en la determinación de la flexibilidad de problemas durante la formación de la relevancia en la exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: a54a4134609b16568586f3cb6b60ebdeba860bac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536206"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7e3a9-103">Comprender la evaluación de relevancia en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="7e3a9-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="7e3a9-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7e3a9-p102">Exhibición de documentos electrónicos avanzada permite evaluación temprana, por ejemplo, para los problemas definidos y los datos importados para un caso. Exhibición de documentos electrónicos avanzada permite el experto para tomar decisiones relativas a un enfoque adoptado y para aplicarlos al proyecto de revisión de documentos.</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p102">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case. Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="7e3a9-108">Evaluación de descripción</span><span class="sxs-lookup"><span data-stu-id="7e3a9-108">Understanding assessment</span></span>

<span data-ttu-id="7e3a9-p103">En la evaluación, el experto revisa un conjunto aleatorio de al menos 500 archivos, que se utilizan para determinar la flexibilidad de los problemas y para producir estadísticas que reflejan los resultados de aprendizaje. Evaluación es correcta cuando se encuentran suficientes archivos relevantes para alcanzar un nivel estadístico que le ayudarán a la exhibición de documentos electrónicos avanzada la relevancia para proporcionar estadísticas precisas y para determinar el punto de estabilización en el proceso de aprendizaje de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p103">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results. Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="7e3a9-p104">Cuanto mayor sea que el número de relevantes archivos en el conjunto de evaluación, más preciso las estadísticas y la eficacia del algoritmo de estabilidad. El número de archivos relevantes dentro de los archivos de evaluación depende de la flexibilidad del problema. Flexibilidad es el porcentaje estimado de los archivos relevantes en el conjunto de relevante para un problema. Problemas con mayor flexibilidad va a llegar a un número mayor de archivos relevantes más rápidamente que problemas con flexibilidad inferior. Problemas con flexibilidad extremadamente baja (por ejemplo, un 2% o menos) requerirá una evaluación muy grande establecida para alcanzar un gran número de archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p104">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm. The number of relevant files within the assessment files depends on the richness of the issue. Richness is the estimated percent of relevant files in the set relevant to an issue. Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness. Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="7e3a9-p105">Las estadísticas, que se presentan en las fichas pista y Decide durante el entrenamiento y después del cálculo de lote, incluyen estimaciones de recuperación de conjuntos de revisión distinto. En estadísticas, establecen las estimaciones que se basan en una muestra (en este caso, los archivos de evaluación) incluyen el margen de error y el nivel de confianza de ese margen de error. Por ejemplo, la recuperación estimada de 80% puede tener un margen de error de más o menos el 5% con un nivel de confianza del 95%. Esto significa que la recuperación estimada es realmente 75-85% y esta estimación tiene confianza del 95%. Cuanto mayor sea el conjunto de evaluación, el margen de error pasa a ser más pequeño y las estadísticas son más precisas.</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p105">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets. In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin. For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%. This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence. The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="7e3a9-p106">Después de que el experto revisa un conjunto de evaluación inicial de los archivos de 500, la relevancia es capaz de determinar el margen de error de los valores de recuperación actual. La relevancia también establecerá un margen de error que recomienda para llegar a fin de optimizar el conjunto de evaluación predeterminado. Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p106">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values. Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set. Following are some examples:</span></span>
  
- <span data-ttu-id="7e3a9-124">Si la evaluación ya establecida generaron un margen de error de más o menos un 10%, se recomienda la relevancia para pasar a recursos de aprendizaje (revisión de evaluación adicionales no es necesario).</span><span class="sxs-lookup"><span data-stu-id="7e3a9-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="7e3a9-125">Si el conjunto de evaluación produjo un margen de error de más o menos el 13%, la relevancia es posible que recomienda la revisión de otro conjunto de archivos de evaluación ponerse en contacto con un margen más pequeño.</span><span class="sxs-lookup"><span data-stu-id="7e3a9-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="7e3a9-126">Si flexibilidad es muy bajo, la relevancia es posible que recomienda detener evaluación, aunque el margen de error es grande (realizar estadísticas práctico), debido a que el conjunto de evaluación sea necesario ponerse en contacto con un margen de error útil es demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="7e3a9-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="7e3a9-p107">Cada problema tiene su propia flexibilidad, el actual margen de error y, como resultado, número estimado de archivos de evaluación adicionales. Se crea el siguiente conjunto de evaluación según el número máximo de archivos (hasta 1.000 en un conjunto único).</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p107">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files. The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="7e3a9-p108">Puede aceptar las recomendaciones de la relevancia o ajustar el margen de error actual según sus necesidades. Se determina el margen de error actual de predeterminado para la recuperación a igual o superior al 75%.</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p108">You can accept the Relevance recommendations or adjust the current margin of error according to your needs. The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e3a9-p109">Se puede omitir la fase de evaluación, en la **la relevancia \> pista** ficha en la vista expandida para un problema, desactivando la casilla de verificación **evaluación** por el problema y, a continuación, para "todos los problemas". Sin embargo, como resultado, habrá ningún estadísticas para este problema. > Desactivando la casilla de verificación de **evaluación** sólo puede realizarse antes de realiza la evaluación. Cuando hay varios problemas en un caso, se omitirá el evaluación sólo si la casilla de verificación está desactivada por cada problema</span><span class="sxs-lookup"><span data-stu-id="7e3a9-p109">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7e3a9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e3a9-135">See also</span></span>

[<span data-ttu-id="7e3a9-136">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="7e3a9-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7e3a9-137">Etiquetas temáticas y evaluación</span><span class="sxs-lookup"><span data-stu-id="7e3a9-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7e3a9-138">Etiquetado y formación de relevancia</span><span class="sxs-lookup"><span data-stu-id="7e3a9-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7e3a9-139">Análisis de la relevancia de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7e3a9-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7e3a9-140">Decidir en función de los resultados</span><span class="sxs-lookup"><span data-stu-id="7e3a9-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7e3a9-141">Las pruebas de análisis de la relevancia</span><span class="sxs-lookup"><span data-stu-id="7e3a9-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

