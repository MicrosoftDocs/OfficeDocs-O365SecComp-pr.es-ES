---
title: Decisión según los resultados en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Obtenga información sobre cómo la ficha Decide de exhibición de documentos electrónicos avanzada de Office 365 ofrece datos que le ayudarán a determinan el tamaño correcto del conjunto de revisión de los archivos de mayúsculas y minúsculas. '
ms.openlocfilehash: 58a181e00ad5843ccbbde4dcb47050eccf199225
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535911"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="4ca3d-103">Decisión según los resultados en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="4ca3d-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="4ca3d-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="4ca3d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="4ca3d-106">En la exhibición de documentos electrónicos avanzada, la ficha Decide proporciona información adicional para ver y usar las estadísticas de la toma de decisiones para determinar el tamaño del conjunto de revisión de los archivos de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="4ca3d-107">Mediante la ficha Decide</span><span class="sxs-lookup"><span data-stu-id="4ca3d-107">Using the Decide tab</span></span>

![Decisión de relevancia](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="4ca3d-109">Esta ficha incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ca3d-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="4ca3d-110">**Problema**: desde aquí, puede seleccionar el problema de interés de la lista.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="4ca3d-p102">**Proporción de retirada de revisión**: comparación de avanzada de revisión de exhibición de documentos electrónicos según las puntuaciones de la relevancia. El punto límite del gráfico representa el porcentaje de archivos para revisar, asignados a una puntuación de relevancia. Esto se usa en la fase de prueba de la relevancia y como un umbral de exportación para la selección. Es el punto límite predeterminado, para el número de archivos para revisar en el punto en el que el equilibrio entre la recuperación y la precisión es óptimo. El punto límite real se debe determinar por el usuario según los objetivos y el equilibrio de costo (revisión %) y el riesgo (recuperación %). Con el control deslizante, puede ajustar el punto límite y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de los archivos relevantes que se recuperarán y antes de validar una decisión.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-p102">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores. The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score. This is used in the Relevance Test phase and as an Export threshold for culling. The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal. The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="4ca3d-p103">**Parámetros**: Revise, recuerde, parámetros relevantes y el coste Total de la siguiente son acumulativas estadísticas calculadas perteneciente a la revisión que se establece en relación a la colección para el caso de todo. Las definiciones de estos parámetros son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ca3d-p103">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="4ca3d-118">**Revisión**: porcentaje de los archivos para revisar basándose en este límite.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="4ca3d-119">**Recuerde**: porcentaje de los archivos relevantes en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="4ca3d-120">**Siguiente relevantes**: costo para revisar e identificar un archivo relevante adicional que no está actualmente en la revisión establecido.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="4ca3d-p104">**Costo total**: costo para revisar este porcentaje de los archivos de mayúsculas y minúsculas. Configuración de los parámetros de costos se puede establecer por el Administrador de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-p104">**Total cost**: Cost for reviewing this percentage of the case files. Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="4ca3d-p105">**Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación de corte. Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje de archivos relacionado en el archivo de revisión que se establece en relación con el total de archivos.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-p105">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="4ca3d-p106">El panel de detalles expandido muestra detalles adicionales. Los archivos en las figuras de la colección no incluya archivos vacíos o imprecisas. Ilustraciones de archivos familia representan los archivos que no se cargados en la relevancia, sin embargo, aún se cuentan como parte de la familia.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-p106">The expanded Details pane displays additional details. Files in collection figures do not include empty or nebulous files. Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ca3d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ca3d-128">See also</span></span>

[<span data-ttu-id="4ca3d-129">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="4ca3d-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4ca3d-130">Evaluación de descripción en la relevancia</span><span class="sxs-lookup"><span data-stu-id="4ca3d-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4ca3d-131">Etiquetas temáticas y evaluación</span><span class="sxs-lookup"><span data-stu-id="4ca3d-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4ca3d-132">Realización de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="4ca3d-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4ca3d-133">Análisis de la relevancia de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4ca3d-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4ca3d-134">Las pruebas de análisis de la relevancia</span><span class="sxs-lookup"><span data-stu-id="4ca3d-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

