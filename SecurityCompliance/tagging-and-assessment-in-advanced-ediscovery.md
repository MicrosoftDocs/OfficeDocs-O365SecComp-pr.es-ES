---
title: Etiquetado y evaluación en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Revise los pasos para realizar la formación sobre la evaluación, incluidos los archivos de etiquetado y la revisión de los resultados de la evaluación en eDiscovery avanzado de Office 365. '
ms.openlocfilehash: 02dae23b6489b40243272beea1d79e871ca6a911
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217940"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="13e58-103">Etiquetado y evaluación en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="13e58-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="13e58-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="13e58-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="13e58-106">En esta sección se describe el procedimiento para el módulo de evaluación de relevancia de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="13e58-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="13e58-107">Realización de análisis y aprendizaje de evaluación</span><span class="sxs-lookup"><span data-stu-id="13e58-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="13e58-108">En la **pestaña \> seguimiento de relevancia** , haga clic en **evaluación** para iniciar la evaluación de casos.</span><span class="sxs-lookup"><span data-stu-id="13e58-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="13e58-109">Por ejemplo, en este procedimiento, se crea un conjunto de evaluación de ejemplo de 500 archivos y se muestra la pestaña **etiqueta** , que contiene el panel etiquetado, el contenido del archivo mostrado y otras opciones de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="13e58-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![Pestaña de etiqueta de relevancia para la evaluación](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="13e58-111">Revise cada archivo de la muestra, determine la relevancia del archivo para cada problema de caso y etiquete el archivo con los botones relevancia (R), no relevante (NR) y omitir en el panel de **etiquetado** .</span><span class="sxs-lookup"><span data-stu-id="13e58-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="13e58-p102">La evaluación requiere 500 de archivos etiquetados. Si los archivos se "omiten", recibirás más archivos para etiquetar.</span><span class="sxs-lookup"><span data-stu-id="13e58-p102">Assessment requires 500 tagged files. If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="13e58-114">Después de etiquetar todos los archivos en el ejemplo, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="13e58-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="13e58-p103">El margen y la riqueza del error actual de la evaluación se calculan y muestran en la pestaña **seguimiento de relevancia** , con detalles expandidos por problema, tal como se muestra a continuación. Para obtener más información sobre este cuadro de diálogo, vea la sección posterior "revisión de los resultados de las evaluaciones".</span><span class="sxs-lookup"><span data-stu-id="13e58-p103">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below. More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![Seguimiento de relevancia: evaluación](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="13e58-p104">De forma predeterminada, se recomienda continuar con el paso siguiente predeterminado cuando se haya completado el indicador de progreso de la evaluación para el problema, lo que indica que se ha revisado la muestra de evaluación y que se han etiquetado los archivos relevantes necesarios. > de lo contrario, si desea ver los resultados de la ficha **seguimiento** y controlar el margen de error y el siguiente paso, haga clic en **modificar** junto al **siguiente paso**, seleccione **continuar evaluación**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13e58-p104">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged. > Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="13e58-p105">Haga clic en **modificar** a la derecha de la casilla **evaluación** para ver y especificar los parámetros de evaluación por problema. Se muestra un cuadro de diálogo de **nivel de evaluación** para cada problema, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="13e58-p105">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue. An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![Problema de caso del nivel de evaluación](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="13e58-123">Los siguientes parámetros para el problema se calculan y se muestran en el cuadro de diálogo **nivel de evaluación** :</span><span class="sxs-lookup"><span data-stu-id="13e58-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="13e58-p106">**Margen de error de destino para estimaciones de recuperación**: según este valor, se calcula el número estimado de archivos adicionales necesarios para la revisión. El margen usado para la recuperación es superior al 75% y con un nivel de confianza de 95%.</span><span class="sxs-lookup"><span data-stu-id="13e58-p106">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated. The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="13e58-126">Se **requieren archivos de evaluación adicionales**: indica el número de archivos necesarios si no se han cumplido los requisitos del margen de error actual.</span><span class="sxs-lookup"><span data-stu-id="13e58-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="13e58-127">Para ajustar el margen de error actual y ver el efecto de los distintos márgenes de error (por problema):</span><span class="sxs-lookup"><span data-stu-id="13e58-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="13e58-128">En la lista **seleccionar problema** , seleccione un problema.</span><span class="sxs-lookup"><span data-stu-id="13e58-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="13e58-129">En el **margen del error de destino para las estimaciones de recuperación**, escriba un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="13e58-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="13e58-130">Haga clic en **actualizar valores** para ver el impacto de los ajustes.</span><span class="sxs-lookup"><span data-stu-id="13e58-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="13e58-131">Haga clic en **avanzadas** en el cuadro de diálogo **nivel de evaluación** para ver los siguientes parámetros y detalles adicionales:</span><span class="sxs-lookup"><span data-stu-id="13e58-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![Vista avanzada del problema de caso del nivel de evaluación](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="13e58-133">**Riqueza estimada**: riqueza estimada de acuerdo con los resultados de la evaluación actual</span><span class="sxs-lookup"><span data-stu-id="13e58-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="13e58-p107">**Para RECALL**recalld: de forma predeterminada, el margen de error de destino se aplica a RECALL por encima del 75%. Haga clic en **Editar** si desea cambiar este parámetro y controlar el margen de error en un intervalo diferente de valores de recuperación.</span><span class="sxs-lookup"><span data-stu-id="13e58-p107">**For assumed recall**: By default, the target error margin applies to recall above 75%. Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="13e58-p108">**Nivel de confianza**: de forma predeterminada, el margen de error recomendado para la confianza es del 95%. Haga clic en **Editar** si desea cambiar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="13e58-p108">**Confidence level**: By default, the recommended error margin for confidence is 95%. Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="13e58-138">**Margen de error de riqueza esperado**: dados los valores actualizados, este es el margen de error esperado de la riqueza, una vez que se han revisado todos los archivos de evaluación adicionales.</span><span class="sxs-lookup"><span data-stu-id="13e58-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="13e58-139">Se **requieren archivos de evaluación adicionales**: dados los valores actualizados, el número de archivos de evaluación adicionales que deben revisarse para llegar al destino.</span><span class="sxs-lookup"><span data-stu-id="13e58-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="13e58-140">**Total de archivos de evaluación necesarios**: dados los valores actualizados, los archivos de evaluación totales necesarios para la revisión.</span><span class="sxs-lookup"><span data-stu-id="13e58-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="13e58-141">**Número previsto de archivos relevantes en la evaluación**: dados los valores actualizados, el número previsto de archivos relevantes en toda la evaluación después de revisar todos los archivos de evaluación adicionales.</span><span class="sxs-lookup"><span data-stu-id="13e58-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="13e58-p109">Haga clic en **recalcular valores**, si se modifican los parámetros. Cuando haya terminado, si hay un problema, haga clic en **Aceptar** para guardar los cambios (o en **siguiente** cuando haya varios problemas para revisar o modificar y, a continuación, **Finalizar**).</span><span class="sxs-lookup"><span data-stu-id="13e58-p109">Click **Recalculate values**, if parameters are changed. When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="13e58-144">Cuando hay varios problemas, una vez que se han revisado o ajustado todos los problemas, se muestra un cuadro de diálogo de **Resumen:** cuadro de diálogo de Resumen, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13e58-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Resumen del nivel de evaluación](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="13e58-146">Una vez finalizada correctamente la evaluación, continúe con la siguiente fase del aprendizaje de relevancia.</span><span class="sxs-lookup"><span data-stu-id="13e58-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="13e58-147">Revisión de los resultados de la evaluación</span><span class="sxs-lookup"><span data-stu-id="13e58-147">Reviewing assessment results</span></span>

<span data-ttu-id="13e58-148">Después de etiquetar un ejemplo de evaluación, los resultados de la evaluación se calculan y se muestran en la pestaña seguimiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="13e58-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="13e58-149">Los siguientes resultados se muestran en la pantalla de la pista expandida:</span><span class="sxs-lookup"><span data-stu-id="13e58-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="13e58-150">Margen de error actual de la evaluación para estimaciones de recuperación</span><span class="sxs-lookup"><span data-stu-id="13e58-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="13e58-151">Riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="13e58-151">Estimated richness</span></span>
    
- <span data-ttu-id="13e58-152">Se requieren archivos de evaluación adicionales (para revisión)</span><span class="sxs-lookup"><span data-stu-id="13e58-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="13e58-p110">El margen de error actual de la evaluación es el margen de error recomendado por eDiscovery avanzado. El número que se muestra para los "archivos de evaluación adicionales necesarios" corresponde a esa recomendación.</span><span class="sxs-lookup"><span data-stu-id="13e58-p110">The Assessment current error margin is the error margin recommended by Advanced eDiscovery. The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="13e58-p111">El indicador de progreso de la evaluación muestra el nivel de finalización de la evaluación, según el margen de error actual. Cuando se está realizando la evaluación, el usuario etiquetará otra muestra de evaluación.</span><span class="sxs-lookup"><span data-stu-id="13e58-p111">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin. When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="13e58-157">Cuando el indicador de progreso de la evaluación muestra la evaluación como completada, significa que se ha completado la revisión de muestreo de la evaluación y que se han etiquetado los archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="13e58-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="13e58-158">La pantalla expandida muestra el siguiente paso recomendado, las estadísticas de la evaluación y el acceso a los resultados detallados.</span><span class="sxs-lookup"><span data-stu-id="13e58-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="13e58-p112">Cuando la riqueza es muy baja, el número de archivos de evaluación adicionales necesarios para alcanzar un número mínimo de archivos relevantes para producir estadísticas útiles es muy alto. La exhibición avanzada de documentos electrónicos le recomendará continuar con el aprendizaje. El indicador de progreso de la evaluación se verá sombreado y no habrá estadísticas disponibles.</span><span class="sxs-lookup"><span data-stu-id="13e58-p112">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high. Advanced eDiscovery will then recommend moving on to training. The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="13e58-p113">En ausencia de estabilización basada en estadísticas, habrá resultados con un nivel inferior de precisión y nivel de confianza. Sin embargo, estos resultados se pueden usar para buscar archivos relevantes cuando no es necesario conocer el porcentaje de archivos relevantes encontrados. De forma similar, este estado puede usarse para entrenar problemas con escasa riqueza, donde los resultados de relevancia pueden acelerar el acceso a los archivos relevantes para un problema específico.</span><span class="sxs-lookup"><span data-stu-id="13e58-p113">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level. However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found. Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="13e58-p114">En la **pestaña \> seguimiento de relevancia** , la visualización de problemas expandida, están disponibles las siguientes opciones de visualización: > el siguiente paso recomendado, como **paso siguiente: el etiquetado** se puede omitir (por problema) haciendo clic en el botón **modificar** para su a la derecha y, a continuación, seleccione un paso diferente en el **paso siguiente**. Cuando no se haya completado el indicador de progreso de la evaluación, la evaluación será la siguiente opción recomendada, para etiquetar más archivos de evaluación y aumentar la precisión de las estadísticas. > puede cambiar el margen de error y evaluar su impacto; para ello, haga clic en **modificar**y, en el **cuadro de diálogo nivel de evaluación**, cambie el **margen de error de destino para RECALL estimaciones**y haga clic en **actualizar valores**. Además, en este cuadro de diálogo, puede ver las opciones avanzadas haciendo clic en **avanzadas**. > puede ver estadísticas adicionales del nivel de evaluación y su impacto haciendo clic en **Ver**. En el cuadro de diálogo resultados deTallados mostrados, las estadísticas están disponibles por problema, cuando hay al menos 500 archivos de evaluación etiquetada y al menos 18 archivos se etiquetan como pertinentes para el problema.</span><span class="sxs-lookup"><span data-stu-id="13e58-p114">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**. When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy. > You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**. Also, in this dialog, you can view advanced options, by clicking **Advanced**. > You can view additional assessment level statistics and their impact by clicking **View**. In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="13e58-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="13e58-171">See also</span></span>

[<span data-ttu-id="13e58-172">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="13e58-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="13e58-173">Descripción de la evaluación en relevancia</span><span class="sxs-lookup"><span data-stu-id="13e58-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13e58-174">Aprendizaje de etiquetas y relevancia</span><span class="sxs-lookup"><span data-stu-id="13e58-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13e58-175">Seguimiento del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="13e58-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13e58-176">Decisiones basadas en los resultados</span><span class="sxs-lookup"><span data-stu-id="13e58-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13e58-177">Prueba del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="13e58-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

