---
title: Decisión basada en los resultados de la exhibición avanzada de documentos electrónicos de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Obtenga información sobre cómo la pestaña decidir en Office 365 Advanced eDiscovery proporciona datos que pueden ayudarle a determinar el tamaño correcto del conjunto de revisión de los archivos de casos. '
ms.openlocfilehash: 3f8ce0343b5a09cf3ab4c4bd94a53d8d0cbe0cce
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153522"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b0d84-103">Decisión basada en los resultados de la exhibición avanzada de documentos electrónicos de Office 365</span><span class="sxs-lookup"><span data-stu-id="b0d84-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b0d84-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b0d84-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="b0d84-106">En la exhibición avanzada de documentos electrónicos, la pestaña decidir proporciona información adicional para ver y usar estadísticas de soporte de decisiones para determinar el tamaño del conjunto de revisión de los archivos de casos.</span><span class="sxs-lookup"><span data-stu-id="b0d84-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="b0d84-107">Uso de la pestaña decidir</span><span class="sxs-lookup"><span data-stu-id="b0d84-107">Using the Decide tab</span></span>

![Decisión de relevancia](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="b0d84-109">Esta ficha incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0d84-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="b0d84-110">**Problema**: desde aquí, puede seleccionar el asunto de interés de la lista.</span><span class="sxs-lookup"><span data-stu-id="b0d84-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="b0d84-111">**Tasa de revisión-RECALL**: comparación de la revisión avanzada de eDiscovery de acuerdo con los resultados de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b0d84-111">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="b0d84-112">El punto de corte en el gráfico representa el porcentaje de archivos que se van a revisar, asignado a una puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b0d84-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="b0d84-113">Se usa en la fase de prueba de relevancia y como un umbral de exportación para culling.</span><span class="sxs-lookup"><span data-stu-id="b0d84-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="b0d84-114">El punto de corte predeterminado, para el número de archivos que se van a revisar, es el punto en el que el equilibrio entre la recuperación y la precisión es óptimo.</span><span class="sxs-lookup"><span data-stu-id="b0d84-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="b0d84-115">El punto de corte real debe estar determinado por el usuario en función de los objetivos y del equilibrio de costes (% Review) y el riesgo (% recall). Con el control deslizante, puede ajustar el punto de corte y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de archivos relevantes que se van a recuperar y antes de validar una decisión.</span><span class="sxs-lookup"><span data-stu-id="b0d84-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="b0d84-116">**Parámetros**: los parámetros revisión, recuperación, siguiente relevante y costo total son estadísticas calculadas acumuladas relativas a la revisión establecida en relación con la colección para todo el caso.</span><span class="sxs-lookup"><span data-stu-id="b0d84-116">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="b0d84-117">Las definiciones de estos parámetros son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0d84-117">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="b0d84-118">**Revisión**: porcentaje de archivos que se van a revisar en función de este límite.</span><span class="sxs-lookup"><span data-stu-id="b0d84-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="b0d84-119">**RECALL**: porcentaje de archivos relevantes en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b0d84-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="b0d84-120">**Siguiente relevante**: costo para revisar e identificar un archivo relevante adicional que no se encuentra actualmente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b0d84-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="b0d84-121">**Costo total**: costo de revisión de este porcentaje de los archivos de casos.</span><span class="sxs-lookup"><span data-stu-id="b0d84-121">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="b0d84-122">La configuración del parámetro costo puede definirla el administrador de casos.</span><span class="sxs-lookup"><span data-stu-id="b0d84-122">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="b0d84-123">**Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación límite.</span><span class="sxs-lookup"><span data-stu-id="b0d84-123">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="b0d84-124">Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje relacionado de los archivos en el archivo de revisión establecido en relación con el total de archivos.</span><span class="sxs-lookup"><span data-stu-id="b0d84-124">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="b0d84-125">El panel de detalles expandido muestra detalles adicionales.</span><span class="sxs-lookup"><span data-stu-id="b0d84-125">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="b0d84-126">Los archivos de las figuras de la colección no incluyen archivos vacíos o Nebulous.</span><span class="sxs-lookup"><span data-stu-id="b0d84-126">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="b0d84-127">Las figuras de los archivos de familia representan los archivos que no se cargan en relevancia, aunque todavía se cuentan como parte de la familia.</span><span class="sxs-lookup"><span data-stu-id="b0d84-127">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0d84-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0d84-128">See also</span></span>

[<span data-ttu-id="b0d84-129">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="b0d84-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b0d84-130">Descripción de la evaluación en relevancia</span><span class="sxs-lookup"><span data-stu-id="b0d84-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b0d84-131">Etiquetado y evaluación</span><span class="sxs-lookup"><span data-stu-id="b0d84-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b0d84-132">Realizar entrenamiento de relevancia</span><span class="sxs-lookup"><span data-stu-id="b0d84-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b0d84-133">Seguimiento del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="b0d84-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b0d84-134">Prueba del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="b0d84-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

