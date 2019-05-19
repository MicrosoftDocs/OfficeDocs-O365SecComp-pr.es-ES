---
title: Seguimiento del análisis de relevancia en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Obtenga información sobre cómo ver e interpretar el estado de aprendizaje de relevancia y los resultados de los problemas de caso en eDiscovery avanzado de Office 365.  '
ms.openlocfilehash: 1018b414d0192491feebfbec25d865d4463fa26a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158332"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="abe12-103">Seguimiento del análisis de relevancia en Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="abe12-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="abe12-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="abe12-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="abe12-106">En la exhibición avanzada de documentos electrónicos, la pestaña seguimiento de relevancia muestra la validez calculada del entrenamiento de relevancia realizado en la pestaña etiqueta e indica el siguiente paso que debe realizar en el proceso de entrenamiento iterativo en relevancia.</span><span class="sxs-lookup"><span data-stu-id="abe12-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="abe12-107">Seguimiento del estado del entrenamiento de relevancia</span><span class="sxs-lookup"><span data-stu-id="abe12-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="abe12-108">Vea los siguientes detalles en el seguimiento de relevancia para los problemas de casos, como se muestra en el siguiente ejemplo de un cuadro de diálogo de **nombre de problema** a continuación.</span><span class="sxs-lookup"><span data-stu-id="abe12-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="abe12-109">**Evaluación**: este indicador de progreso muestra el grado en el que el entrenamiento de relevancia realizado hasta este punto ha logrado el objetivo de la evaluación en cuanto al margen de error.</span><span class="sxs-lookup"><span data-stu-id="abe12-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="abe12-110">También se muestra la riqueza de los resultados de entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="abe12-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="abe12-111">**Aprendizaje**: este indicador de progreso codificado por colores y muestra de la información sobre herramientas indica la estabilidad de los resultados del entrenamiento de relevancia y una escala numérica que muestra el número de muestras de aprendizaje de relevancia etiquetadas para cada problema.</span><span class="sxs-lookup"><span data-stu-id="abe12-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="abe12-112">El experto supervisa el progreso del proceso de entrenamiento de relevancia iterativa.</span><span class="sxs-lookup"><span data-stu-id="abe12-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="abe12-113">**Cálculo del lote**: este indicador de progreso proporciona información acerca de la finalización del cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="abe12-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="abe12-114">**Siguiente paso**: muestra las recomendaciones para el siguiente paso que se debe realizar.</span><span class="sxs-lookup"><span data-stu-id="abe12-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="abe12-115">En el ejemplo, se muestra una evaluación completada correctamente de un problema, indicada por el indicador de progreso de color completado y la marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="abe12-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="abe12-116">Se está realizando un etiquetado, pero el caso se considera inestable (el estado de estabilidad también se muestra en un Consejo de herramientas).</span><span class="sxs-lookup"><span data-stu-id="abe12-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="abe12-117">La recomendación de paso siguiente es "Training".</span><span class="sxs-lookup"><span data-stu-id="abe12-117">The next step recommendation is "Training".</span></span> 
    
    ![Formación del seguimiento de relevancia paso 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="abe12-119">La vista expandida muestra información adicional y opciones.</span><span class="sxs-lookup"><span data-stu-id="abe12-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="abe12-120">El margen de error actual mostrado es el margen de error de la recuperación en el estado actual de la evaluación, dados los archivos de evaluación existentes (ya etiquetados).</span><span class="sxs-lookup"><span data-stu-id="abe12-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="abe12-121">La fase de evaluación se puede omitir desactivando la casilla de verificación **evaluación** por problema y, a continuación, de "todos los problemas".</span><span class="sxs-lookup"><span data-stu-id="abe12-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="abe12-122">Sin embargo, como resultado, no habrá estadísticas para este problema.</span><span class="sxs-lookup"><span data-stu-id="abe12-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="abe12-123">> desactivar la casilla de verificación **evaluación** solo puede realizarse antes de que se realice la evaluación.</span><span class="sxs-lookup"><span data-stu-id="abe12-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="abe12-124">Cuando hay varios problemas en un caso, la evaluación se omite solo si la casilla de verificación está desactivada para cada problema</span><span class="sxs-lookup"><span data-stu-id="abe12-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="abe12-125">Cuando la evaluación no se completa con el primer conjunto de ejemplos de archivos, la evaluación podría ser el paso siguiente para etiquetar más archivos.</span><span class="sxs-lookup"><span data-stu-id="abe12-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="abe12-126">En el **seguimiento**de **relevancia** \> , el indicador de progreso de formación y la información sobre herramientas indican el número estimado de muestras adicionales necesarias para alcanzar la estabilidad.</span><span class="sxs-lookup"><span data-stu-id="abe12-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="abe12-127">Esta estimación proporciona una pauta para la formación adicional necesaria.</span><span class="sxs-lookup"><span data-stu-id="abe12-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![Formación del seguimiento de relevancia](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="abe12-129">Cuando haya terminado de realizar el etiquetado y tenga que continuar con la formación, haga clic en **entrenamiento**.</span><span class="sxs-lookup"><span data-stu-id="abe12-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="abe12-130">Se genera otro conjunto de archivos de ejemplo a partir del conjunto de archivos cargados para obtener más formación.</span><span class="sxs-lookup"><span data-stu-id="abe12-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="abe12-131">A continuación, se vuelve a la pestaña etiqueta para etiquetar y entrenar a más archivos.</span><span class="sxs-lookup"><span data-stu-id="abe12-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="abe12-132">Alcanzar niveles de formación estables</span><span class="sxs-lookup"><span data-stu-id="abe12-132">Reaching stable training levels</span></span>

<span data-ttu-id="abe12-133">Una vez que los archivos de evaluación alcanzan un nivel de formación estable, la exhibición avanzada de documentos electrónicos está lista para el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="abe12-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abe12-134">Normalmente, después de tres ejemplos de formación estables, el siguiente paso es "cálculo por lotes".</span><span class="sxs-lookup"><span data-stu-id="abe12-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="abe12-135">Puede haber excepciones, por ejemplo, cuando se han producido cambios en el etiquetado de archivos desde ejemplos anteriores o cuando se han agregado archivos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="abe12-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="abe12-136">Realizar el cálculo por lotes</span><span class="sxs-lookup"><span data-stu-id="abe12-136">Performing Batch calculation</span></span>

<span data-ttu-id="abe12-137">El cálculo del lote se ejecuta como el paso siguiente una vez que el entrenamiento se completa correctamente (cuando la barra de progreso muestra un estado de entrenamiento estable, una marca de verificación y un estado estable en la información sobre herramientas). El cálculo del lote aplica los conocimientos adquiridos durante el entrenamiento de relevancia a toda la población de archivos, para evaluar la relevancia de los archivos y asignar los resultados de relevancia.</span><span class="sxs-lookup"><span data-stu-id="abe12-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="abe12-138">Cuando hay más de un problema, el cálculo del lote se realiza por problema.</span><span class="sxs-lookup"><span data-stu-id="abe12-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="abe12-139">Durante el cálculo por lotes, el progreso se supervisa mientras se procesan todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="abe12-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="abe12-140">Aquí, el siguiente paso recomendado es "ninguno", que indica que no se requiere ningún aprendizaje de relevancia iterativo adicional en este punto.</span><span class="sxs-lookup"><span data-stu-id="abe12-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="abe12-141">La siguiente fase es la **pestaña \> decisión de relevancia** .</span><span class="sxs-lookup"><span data-stu-id="abe12-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="abe12-142">Si desea importar nuevos archivos tras el cálculo por lotes, el administrador puede Agregar los archivos importados a una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="abe12-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abe12-143">Si hace clic en **Cancelar** durante el cálculo por lotes, el proceso guarda lo que ya se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="abe12-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="abe12-144">Si vuelve a ejecutar el cálculo por lotes, el proceso continuará desde el último punto ejecutado.</span><span class="sxs-lookup"><span data-stu-id="abe12-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="abe12-145">Evaluación de la coherencia de etiquetado</span><span class="sxs-lookup"><span data-stu-id="abe12-145">Assessing tagging consistency</span></span>

<span data-ttu-id="abe12-146">Si hay incoherencias en el etiquetado de archivos, puede afectar al análisis.</span><span class="sxs-lookup"><span data-stu-id="abe12-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="abe12-147">El proceso de coherencia de etiquetado de exhibición de documentos electrónicos avanzado puede usarse cuando los resultados no son óptimos o la coherencia está en duda.</span><span class="sxs-lookup"><span data-stu-id="abe12-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="abe12-148">Se devuelve una lista de los archivos etiquetados que pueden ser incoherentes y se pueden revisar y volver a etiquetar, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="abe12-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abe12-149">Después de siete o más formación redondeos tras la evaluación, la coherencia de etiquetado se puede ver en el **seguimiento** \> \*\*\*\* \> de **relevancia** \> **progreso de aprendizaje**de **resultados** \> detallados.</span><span class="sxs-lookup"><span data-stu-id="abe12-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="abe12-150">Esta revisión se realiza por un problema a la vez.</span><span class="sxs-lookup"><span data-stu-id="abe12-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="abe12-151">En **el \> seguimiento de relevancia**, expanda la fila de un problema.</span><span class="sxs-lookup"><span data-stu-id="abe12-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="abe12-152">A la derecha del **paso siguiente**, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="abe12-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="abe12-153">Seleccione incoherencias de **etiquetas** como la opción de **paso siguiente** , después de siete ejemplos de aprendizaje y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="abe12-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="abe12-154">Seleccione incoherencias de **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="abe12-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="abe12-155">La ficha **etiqueta** se abre y muestra una lista de las incoherencias que se deben volver a etiquetar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="abe12-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="abe12-156">Haga clic en **calcular** para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="abe12-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="abe12-157">El paso siguiente tras las incoherencias de etiquetado es "Training".</span><span class="sxs-lookup"><span data-stu-id="abe12-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="abe12-158">Visualización y uso de los resultados de relevancia</span><span class="sxs-lookup"><span data-stu-id="abe12-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="abe12-159">En la **pestaña \> seguimiento de relevancia** , expanda la fila de un problema y, junto a **resultados**detallados, haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="abe12-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="abe12-160">Se mostrarán los paneles de resultados detallados, tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="abe12-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Resultados detallados de la formación de relevancia](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="abe12-162">Resumen de etiquetación</span><span class="sxs-lookup"><span data-stu-id="abe12-162">Tagging summary</span></span>

 <span data-ttu-id="abe12-163">En el ejemplo que se muestra a continuación, el **Resumen de etiquetado** muestra los totales de cada proceso de etiquetado de archivos de evaluación, formación y captura.</span><span class="sxs-lookup"><span data-stu-id="abe12-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![Resumen de etiquetado del seguimiento de relevancia](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="abe12-165">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="abe12-165">Keywords</span></span>

<span data-ttu-id="abe12-166">Una palabra clave es una cadena única, palabra, frase o secuencia de palabras en un archivo identificado por Advanced eDiscovery como un indicador significativo de si un archivo es relevante.</span><span class="sxs-lookup"><span data-stu-id="abe12-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="abe12-167">La palabra clave "include" de la lista de columnas y los pesos en archivos etiquetados como relevantes, y las columnas "excluir" enumeran palabras clave y pesos en archivos etiquetados como no relevantes.</span><span class="sxs-lookup"><span data-stu-id="abe12-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="abe12-168">La exhibición avanzada de documentos electrónicos asigna valores de peso de palabras clave negativas o positiva.</span><span class="sxs-lookup"><span data-stu-id="abe12-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="abe12-169">Cuanto mayor sea el peso, mayor será la probabilidad de que un archivo en el que aparezca la palabra clave tenga una puntuación de relevancia superior durante el cálculo del lote.</span><span class="sxs-lookup"><span data-stu-id="abe12-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="abe12-170">La lista de palabras clave de eDiscovery avanzada se puede usar para complementar una lista creada por un experto o como comprobación indirecta de validez en cualquier punto del proceso de revisión de archivos.</span><span class="sxs-lookup"><span data-stu-id="abe12-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="abe12-171">Progreso de formación</span><span class="sxs-lookup"><span data-stu-id="abe12-171">Training progress</span></span>

<span data-ttu-id="abe12-172">El panel **progreso del entrenamiento** incluye un gráfico de progreso de formación y una visualización del indicador de calidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="abe12-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![Progreso de formación del seguimiento de relevancia](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="abe12-174">**Indicador de calidad de formación**: muestra la clasificación de la coherencia de etiquetado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abe12-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="abe12-175">**Bueno**: los archivos se etiquetan de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="abe12-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="abe12-176">(Luz verde mostrada)</span><span class="sxs-lookup"><span data-stu-id="abe12-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="abe12-177">**Media**: es posible que algunos archivos se etiqueten de manera incoherente.</span><span class="sxs-lookup"><span data-stu-id="abe12-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="abe12-178">(Luz amarilla mostrada)</span><span class="sxs-lookup"><span data-stu-id="abe12-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="abe12-179">**ADVERTENCIA**: es posible que muchos archivos se etiqueten de manera incoherente.</span><span class="sxs-lookup"><span data-stu-id="abe12-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="abe12-180">(Luz roja mostrada)</span><span class="sxs-lookup"><span data-stu-id="abe12-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="abe12-181">**Gráfico de progreso de formación**: muestra el grado de estabilidad del aprendizaje de relevancia después de varios ciclos de aprendizaje de relevancia en comparación con el valor de la medida de F.</span><span class="sxs-lookup"><span data-stu-id="abe12-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="abe12-182">A medida que nos desplazamos de izquierda a derecha en el gráfico, el intervalo de confianza se reduce y se usa, junto con la medida F, por relevancia de eDiscovery avanzado para determinar la estabilidad cuando se optimizan los resultados de la formación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="abe12-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abe12-183">Relevancia usa F2, una métrica de F-Measure donde la recuperación recibe dos veces el peso de la precisión.</span><span class="sxs-lookup"><span data-stu-id="abe12-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="abe12-184">Para los casos con alta riqueza (más de 25%), relevancia usa F1 (proporción de 1:1).</span><span class="sxs-lookup"><span data-stu-id="abe12-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="abe12-185">La relación de medida F se puede configurar en la **Configuración avanzada**de la **configuración** \> de relevancia.</span><span class="sxs-lookup"><span data-stu-id="abe12-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="abe12-186">Resultados del cálculo por lotes</span><span class="sxs-lookup"><span data-stu-id="abe12-186">Batch calculation results</span></span>

<span data-ttu-id="abe12-187">El panel de **resultados de cálculo por lotes** incluye el número de archivos que se han puntuado para la relevancia, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abe12-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="abe12-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="abe12-188">**Success**</span></span>
    
- <span data-ttu-id="abe12-189">**Empty**: no contiene texto, por ejemplo, solo espacios/tabulaciones</span><span class="sxs-lookup"><span data-stu-id="abe12-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="abe12-190">**Error**: debido a un tamaño excesivo o no se pudo leer</span><span class="sxs-lookup"><span data-stu-id="abe12-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="abe12-191">**Ignorado**: debido a un tamaño excesivo</span><span class="sxs-lookup"><span data-stu-id="abe12-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="abe12-192">**Nebulous**: contiene texto sin significado o no tiene características relevantes para el problema</span><span class="sxs-lookup"><span data-stu-id="abe12-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="abe12-193">Empty, failed, Ignored o Nebulous recibirá una puntuación de relevancia de-1.</span><span class="sxs-lookup"><span data-stu-id="abe12-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="abe12-194">Estadísticas de formación</span><span class="sxs-lookup"><span data-stu-id="abe12-194">Training statistics</span></span>

<span data-ttu-id="abe12-195">El panel de **estadísticas de formación** muestra las estadísticas y los gráficos basados en los resultados de la formación avanzada de relevancia de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="abe12-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Estadísticas de formación del seguimiento de relevancia](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="abe12-197">Esta vista muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abe12-197">This view shows the following:</span></span>
  
- <span data-ttu-id="abe12-198">**Tasa de revisión-RECALL**: comparación de los resultados de acuerdo con los resultados de relevancia en una revisión hipotéticamente lineal.</span><span class="sxs-lookup"><span data-stu-id="abe12-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="abe12-199">La recuperación se calcula según el conjunto Review size set.</span><span class="sxs-lookup"><span data-stu-id="abe12-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="abe12-200">\*\*\*\* Parameters: estadísticas calculadas acumuladas relativas a la revisión establecida en relación con el llenado de archivos para todo el caso.</span><span class="sxs-lookup"><span data-stu-id="abe12-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="abe12-201">**Revisión**: porcentaje de archivos que se van a revisar en función de este límite.</span><span class="sxs-lookup"><span data-stu-id="abe12-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="abe12-202">**RECALL**: porcentaje de archivos relevantes en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="abe12-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="abe12-203">**Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación límite.</span><span class="sxs-lookup"><span data-stu-id="abe12-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="abe12-204">Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje relacionado de los archivos en el archivo de revisión establecido en relación con el total de archivos.</span><span class="sxs-lookup"><span data-stu-id="abe12-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="abe12-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="abe12-205">See also</span></span>

[<span data-ttu-id="abe12-206">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="abe12-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="abe12-207">Descripción de la evaluación en relevancia</span><span class="sxs-lookup"><span data-stu-id="abe12-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="abe12-208">Realización y revisión de la evaluación</span><span class="sxs-lookup"><span data-stu-id="abe12-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="abe12-209">Realizar entrenamiento de relevancia</span><span class="sxs-lookup"><span data-stu-id="abe12-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="abe12-210">Toma de decisiones basándose en los resultados</span><span class="sxs-lookup"><span data-stu-id="abe12-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="abe12-211">Prueba del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="abe12-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

