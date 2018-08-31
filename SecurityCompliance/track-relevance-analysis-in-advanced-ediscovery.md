---
title: Seguimiento del análisis de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Obtenga información sobre cómo ver e interpretar los resultados para problemas de casos de exhibición de documentos electrónicos avanzada de Office 365 y estado de recursos de aprendizaje de la relevancia.  '
ms.openlocfilehash: a19f7eaabf5dc15eefaa7209ded8261020d0d557
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536851"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="56901-103">Seguimiento del análisis de relevancia en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="56901-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="56901-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="56901-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="56901-106">En Avanzadas exhibición de documentos electrónicos, la ficha seguimiento de la relevancia muestra la validez de la formación de relevancia realizada en la ficha etiqueta calculada e indica el siguiente paso a tomar en el proceso de entrenamiento iterativo en la relevancia.</span><span class="sxs-lookup"><span data-stu-id="56901-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="56901-107">Seguimiento del estado de recursos de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="56901-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="56901-108">Ver los detalles siguientes de la relevancia de seguimiento para los problemas de mayúsculas y minúsculas, tal como se muestra en el siguiente ejemplo de un cuadro de diálogo **nombre del problema** que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="56901-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="56901-p102">**Evaluación**: este indicador de progreso muestra en qué medida la relevancia de recursos de aprendizaje a este punto se realizan ha logrado el destino de evaluación en términos de margen de error. También se muestra la flexibilidad de los resultados de aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="56901-p102">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error. The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="56901-p103">**Recursos de aprendizaje**: esta pantalla progreso codificada por colores de indicador y de información sobre herramientas indica el aprendizaje de la relevancia de resultados de estabilidad y una escala numérica que muestra el número de muestras de aprendizaje de la relevancia etiquetados para cada problema. El experto supervisa el progreso del proceso de aprendizaje de la relevancia iterativo.</span><span class="sxs-lookup"><span data-stu-id="56901-p103">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue. The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="56901-113">**Cálculo por lotes**: este indicador de progreso proporciona información acerca de la finalización de cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="56901-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="56901-114">**Siguiente paso**: muestra la recomendación para el siguiente paso que se debe realizar.</span><span class="sxs-lookup"><span data-stu-id="56901-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="56901-p104">En el ejemplo, se muestra una evaluación completada correctamente por un problema, indicada por el indicador de progreso de color completado y la marca de verificación. Etiquetado está en curso, pero el caso todavía se considera inestable (estado de estabilidad también se muestra en una información sobre herramientas). La recomendación de paso siguiente es "formación".</span><span class="sxs-lookup"><span data-stu-id="56901-p104">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark. Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip). The next step recommendation is "Training".</span></span> 
    
    ![Formación del seguimiento de relevancia paso 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="56901-p105">La vista expandida muestra opciones e información adicional. El margen de error actual que se muestra es el margen de error de la recuperación en el estado actual de evaluación, dado los archivos existentes de evaluación (ya etiquetado).</span><span class="sxs-lookup"><span data-stu-id="56901-p105">The expanded view displays additional information and options. The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="56901-p106">La fase de evaluación puede omitirse desactivando la casilla de verificación **evaluación** por el problema y, a continuación, para "todos los problemas". Sin embargo, como resultado, habrá ningún estadísticas para este problema. > Desactivando la casilla de verificación de **evaluación** sólo puede realizarse antes de realiza la evaluación. Cuando hay varios problemas en un caso, se omitirá el evaluación sólo si la casilla de verificación está desactivada por cada problema</span><span class="sxs-lookup"><span data-stu-id="56901-p106">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="56901-125">Cuando no se completa la evaluación con el primer ejemplo de conjunto de archivos, evaluación podría ser el siguiente paso para etiquetar los archivos más.</span><span class="sxs-lookup"><span data-stu-id="56901-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="56901-p107">En **la relevancia** \> **pista**, el indicador de progreso de aprendizaje y la información sobre herramientas indican el número estimado de ejemplos adicionales necesarios para llegar a la estabilidad. Esta estimación proporciona instrucciones para los recursos de aprendizaje adicionales necesitado.</span><span class="sxs-lookup"><span data-stu-id="56901-p107">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability. This estimate provides a guideline for the additional training needed.</span></span>
    
    ![Formación del seguimiento de relevancia](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="56901-p108">Cuando esté listo etiquetado y si necesita continuar la formación, haga clic en **recursos de aprendizaje**. Otro conjunto de archivos de ejemplo se genera a partir del archivo cargado establecido para recursos de aprendizaje adicionales. A continuación, se devuelven a la ficha de etiqueta para etiquetar y formar a más archivos.</span><span class="sxs-lookup"><span data-stu-id="56901-p108">When you're done tagging and if you need to continue training, click **Training**. Another sample set of files is generated from the loaded file set for additional training. You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="56901-132">Alcanzar los niveles de formación estable</span><span class="sxs-lookup"><span data-stu-id="56901-132">Reaching stable training levels</span></span>

<span data-ttu-id="56901-133">Después de que los archivos de evaluación han alcanzado un nivel estable de formación, exhibición de documentos electrónicos avanzada está preparada para cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="56901-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56901-p109">Normalmente, después de tres estable ejemplos de aprendizaje, el siguiente paso es "Cálculo por lotes". Puede haber excepciones, por ejemplo, cuando se produjeron cambios para el etiquetado de los archivos de ejemplos anteriores o cuando se han agregado los archivos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="56901-p109">Usually, after three stable training samples, the next step is "Batch calculation". There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="56901-136">Realizar el cálculo por lotes</span><span class="sxs-lookup"><span data-stu-id="56901-136">Performing Batch calculation</span></span>

<span data-ttu-id="56901-137">Cálculo por lotes se ejecuta como el siguiente paso después de que se haya completado correctamente aprendizaje (cuando un estado estable aprendizaje se muestra en la barra de progreso, una marca de verificación y un estado estable en la información sobre herramientas.) Cálculo del lote aplica el conocimiento adquirido durante el curso de la relevancia para la población de todo el archivo, para evaluar la relevancia de los archivos y para asignar las puntuaciones de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="56901-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="56901-p110">Cuando hay más de un problema, el cálculo de proceso por lotes se realiza por el problema. Durante el cálculo por lotes, se supervisa el progreso durante el procesamiento de todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="56901-p110">When there is more than one issue, Batch calculation is done per issue. During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="56901-p111">En este caso, el siguiente paso recomendado es "None", que indica que no hay recursos de aprendizaje de la relevancia iterativo adicionales es necesario en este momento. La siguiente fase es la **la relevancia de \> decidir** ficha.</span><span class="sxs-lookup"><span data-stu-id="56901-p111">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point. The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="56901-142">Si desea importar nuevos archivos después del cálculo por lotes, el administrador puede agregar los archivos importados a una carga de nuevo.</span><span class="sxs-lookup"><span data-stu-id="56901-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56901-p112">Si hace clic en **Cancelar** durante el cálculo por lotes, guarda el proceso de lo que ya se ha ejecutado. Si ejecuta el nuevo cálculo de proceso por lotes, el proceso continuará desde el último punto ejecutado.</span><span class="sxs-lookup"><span data-stu-id="56901-p112">If you click **Cancel** during Batch calculation, the process saves what was already executed. If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="56901-145">Evaluación de coherencia etiquetas temáticas</span><span class="sxs-lookup"><span data-stu-id="56901-145">Assessing tagging consistency</span></span>

<span data-ttu-id="56901-p113">Si hay incoherencias en archivo etiquetado, puede afectar el análisis. La exhibición de documentos electrónicos avanzada etiquetado proceso de coherencia se puede usar cuando los resultados no son óptimos o coherencia está en duda. Se devuelve una lista de archivos de forma incoherente con etiqueta posibles, y pueda revisarse y volver a etiquetados, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="56901-p113">If there are inconsistencies in file tagging, it can affect the analysis. The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt. A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56901-p114">Después de siete o más redondea aprendizaje siguiente evaluación, etiquetado coherencia puede verse en **la relevancia** \> **pista** \> **problema** \> **resultados detallados** \> **curso de formación**. Esta revisión se realiza para un problema a la vez.</span><span class="sxs-lookup"><span data-stu-id="56901-p114">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**. This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="56901-151">En **relevancia \> pista**, expanda la fila de un problema.</span><span class="sxs-lookup"><span data-stu-id="56901-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="56901-152">A la derecha del **siguiente paso**, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="56901-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="56901-153">Seleccione **las incoherencias de etiqueta** como la opción **siguiente paso** , después de siete ejemplos de aprendizaje y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="56901-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="56901-p115">Seleccione **las incoherencias de etiqueta**. Mostrar una lista de las incoherencias para volver a marcar cuando sea necesario, abre la ficha de la **etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="56901-p115">Select **Tag inconsistencies**. The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="56901-p116">Haga clic en **calcular** para enviar los cambios. El paso siguiente después de etiquetado incoherencias es "formación".</span><span class="sxs-lookup"><span data-stu-id="56901-p116">Click **Calculate** to submit the changes. The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="56901-158">Ver y usar los resultados de la relevancia</span><span class="sxs-lookup"><span data-stu-id="56901-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="56901-p117">En el **la relevancia \> pista** ficha, expanda la fila de un problema y junto a los **resultados detallados**, haga clic en **Ver**. Los paneles de resultados detallados se muestran, como se muestra y se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="56901-p117">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**. The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Resultados detallados de la formación de relevancia](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="56901-162">Resumen de las etiquetas temáticas</span><span class="sxs-lookup"><span data-stu-id="56901-162">Tagging summary</span></span>

 <span data-ttu-id="56901-163">En el ejemplo que se muestra a continuación, el **etiquetado de resumen** muestra los totales de cada uno de evaluación, formación y etiquetar los procesos de archivo puesta al día.</span><span class="sxs-lookup"><span data-stu-id="56901-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![Resumen de etiquetado del seguimiento de relevancia](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="56901-165">Keywords</span><span class="sxs-lookup"><span data-stu-id="56901-165">Keywords</span></span>

<span data-ttu-id="56901-p118">Una palabra clave es una cadena única, word, frase o secuencia de palabras en un archivo identificado por avanzada exhibición de documentos electrónicos como un indicador de si un archivo es relevante significativo. Lista de las columnas "Include" palabra clave y pesos en archivos etiquetados como pertinente y las columnas "Excluir" se enumeran las palabras clave y pesos en archivos etiquetados como no relevantes.</span><span class="sxs-lookup"><span data-stu-id="56901-p118">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant. The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="56901-p119">Exhibición de documentos electrónicos avanzada asigna palabras clave positivo o negativo los valores de weight. Cuanto mayor sea el peso, mayor será la probabilidad de que un archivo en el que aparece la palabra clave se asigna una puntuación más alta de la relevancia durante el cálculo de lote.</span><span class="sxs-lookup"><span data-stu-id="56901-p119">Advanced eDiscovery assigns negative or positive keyword weight values. The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="56901-170">La lista de exhibición de documentos electrónicos avanzada de palabras clave puede utilizarse para completar una lista creada por un experto o como una comprobación de validez indirecta en cualquier momento en el archivo de proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="56901-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="56901-171">Curso de formación</span><span class="sxs-lookup"><span data-stu-id="56901-171">Training progress</span></span>

<span data-ttu-id="56901-172">El panel **Progreso del aprendizaje** incluye un aprendizaje progreso gráfico y la calidad de visualización de indicador, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="56901-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![Progreso de formación del seguimiento de relevancia](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="56901-174">**Indicador de calidad de recursos de aprendizaje**: muestra la clasificación de la coherencia de las etiquetas temáticas de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="56901-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="56901-p120">**Buena**: los archivos se etiquetan de forma coherente. (Muestra de luz verde)</span><span class="sxs-lookup"><span data-stu-id="56901-p120">**Good**: Files are tagged consistently. (Green light displayed)</span></span>
    
- <span data-ttu-id="56901-p121">**Medio**: algunos archivos se pueden etiquetar de forma incoherente. (Muestra amarillo claro)</span><span class="sxs-lookup"><span data-stu-id="56901-p121">**Medium**: Some files may be tagged inconsistently. (Yellow light displayed)</span></span>
    
- <span data-ttu-id="56901-p122">**Advertencia**: es posible que se etiquetados muchos archivos de forma incoherente. (Muestra de luz roja)</span><span class="sxs-lookup"><span data-stu-id="56901-p122">**Warning**: Many files may be tagged inconsistently. (Red light displayed)</span></span>
    
 <span data-ttu-id="56901-p123">**Gráfico de progreso de recursos de aprendizaje**: muestra el grado de estabilidad de aprendizaje de la relevancia después de un número de ciclos de aprendizaje de la relevancia en comparación con el valor de medida de F. Tal y como se mueva desde la izquierda a la derecha en el gráfico, se restringe el intervalo de confianza y se usa junto con la medida de F, mediante la exhibición de documentos electrónicos avanzada la relevancia para determinar la estabilidad cuando el aprendizaje de la relevancia de resultados están optimizados.</span><span class="sxs-lookup"><span data-stu-id="56901-p123">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value. As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56901-p124">La relevancia usa F2, una métrica F medida donde recuperación recibe dos veces mucho peso como precisión. Para los casos con flexibilidad alta (más del 25%), usos de la relevancia F1 (proporción de 1:1). La proporción de F medida se puede configurar en **el programa de instalación de la relevancia** \> **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="56901-p124">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision. For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio). The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="56901-186">Resultados de los cálculos por lotes</span><span class="sxs-lookup"><span data-stu-id="56901-186">Batch calculation results</span></span>

<span data-ttu-id="56901-187">El panel de **resultados de los cálculos por lotes** incluye el número de archivos que se han obtenido de la relevancia, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="56901-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="56901-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="56901-188">**Success**</span></span>
    
- <span data-ttu-id="56901-189">**Vacío**: no contiene texto, por ejemplo, sólo espacios/fichas</span><span class="sxs-lookup"><span data-stu-id="56901-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="56901-190">**Error**: debido a un tamaño excesivo o no se pudo leer</span><span class="sxs-lookup"><span data-stu-id="56901-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="56901-191">**Omitido**: debido a un tamaño excesivo</span><span class="sxs-lookup"><span data-stu-id="56901-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="56901-192">**Nebulous**: contiene texto sin sentido o no relevantes para el problema de características</span><span class="sxs-lookup"><span data-stu-id="56901-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="56901-193">Vacío, error, Ignored o Nebulous recibirá una puntuación de relevancia de -1.</span><span class="sxs-lookup"><span data-stu-id="56901-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="56901-194">Estadísticas de recursos de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="56901-194">Training statistics</span></span>

<span data-ttu-id="56901-195">El panel de **estadísticas de recursos de aprendizaje** muestra estadísticas y gráficos basados en los resultados de aprendizaje de la relevancia de exhibición de documentos electrónicos avanzadas.</span><span class="sxs-lookup"><span data-stu-id="56901-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Estadísticas de formación del seguimiento de relevancia](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="56901-197">Esta vista muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56901-197">This view shows the following:</span></span>
  
- <span data-ttu-id="56901-p125">**Proporción de retirada de revisión**: comparación de resultados en función de la relevancia de puntuación en una revisión teoría lineal. Recuperación es estimada dado el conjunto de tamaño del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="56901-p125">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review. Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="56901-200">**Parámetros**: acumulativa calcula las estadísticas correspondientes a la revisión que se establece en relación con la población de archivo para el caso de todo.</span><span class="sxs-lookup"><span data-stu-id="56901-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="56901-201">**Revisión**: porcentaje de los archivos para revisar basándose en este límite.</span><span class="sxs-lookup"><span data-stu-id="56901-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="56901-202">**Recuerde**: porcentaje de pertinente archivos en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="56901-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="56901-p126">**Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación de corte. Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje de archivos relacionado en el archivo de revisión que se establece en relación con el total de archivos.</span><span class="sxs-lookup"><span data-stu-id="56901-p126">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="56901-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="56901-205">See also</span></span>

[<span data-ttu-id="56901-206">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="56901-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="56901-207">Evaluación de descripción en la relevancia</span><span class="sxs-lookup"><span data-stu-id="56901-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56901-208">Realizando y revisión de evaluación</span><span class="sxs-lookup"><span data-stu-id="56901-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56901-209">Realización de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="56901-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56901-210">En función de los resultados de la toma de decisiones</span><span class="sxs-lookup"><span data-stu-id="56901-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56901-211">Las pruebas de análisis de la relevancia</span><span class="sxs-lookup"><span data-stu-id="56901-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

