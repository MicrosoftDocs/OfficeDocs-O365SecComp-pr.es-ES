---
title: Etiquetado y evaluación en eDiscovery avanzado de Office 365
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Revise los pasos para realizar la formación de evaluación, incluidos archivos de etiquetado y revisar los resultados de la evaluación de exhibición de documentos electrónicos avanzada de Office 365. '
ms.openlocfilehash: 0f67dd4780a29536888231f556c18fe887f230ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536065"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="6f893-103">Etiquetado y evaluación en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f893-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="6f893-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="6f893-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6f893-106">En esta sección se describe el procedimiento para el módulo de evaluación de la relevancia de exhibición de documentos electrónicos avanzadas.</span><span class="sxs-lookup"><span data-stu-id="6f893-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="6f893-107">Realización de análisis y formación de evaluación</span><span class="sxs-lookup"><span data-stu-id="6f893-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="6f893-108">En el **la relevancia \> pista** ficha, haga clic en **evaluación** para iniciar la evaluación del caso.</span><span class="sxs-lookup"><span data-stu-id="6f893-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="6f893-109">Por ejemplo, con fines de este procedimiento, se crea un conjunto de evaluación de ejemplo de 500 archivos y se muestra la ficha **etiqueta** , que contiene el panel etiquetado, el contenido del archivo que se muestra y otras opciones de etiquetas temáticas.</span><span class="sxs-lookup"><span data-stu-id="6f893-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![Pestaña de etiqueta de relevancia para la evaluación](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="6f893-111">Revise cada archivo en el ejemplo, determinar la relevancia de un archivo por cada problema de mayúsculas y minúsculas y marcar el archivo mediante el Relevance (R), no relevante (n) y omitir los botones en el panel de **etiquetado** .</span><span class="sxs-lookup"><span data-stu-id="6f893-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="6f893-p102">Evaluación requiere 500 archivos con etiqueta. Si se "omiten archivos", recibirá más archivos a la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6f893-p102">Assessment requires 500 tagged files. If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="6f893-114">Después de etiquetar todos los archivos en el ejemplo, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="6f893-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="6f893-p103">El margen de error actual de evaluación y la flexibilidad se calculan y se muestran en la ficha **Seguimiento de relevancia** , con detalles expandidas por el problema, tal y como se muestra a continuación. Obtener más detalles acerca de este cuadro de diálogo se describen en la sección posterior "Los resultados de las evaluaciones de revisión".</span><span class="sxs-lookup"><span data-stu-id="6f893-p103">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below. More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![Seguimiento de relevancia: evaluación](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="6f893-p104">De forma predeterminada, se recomienda que realice el paso siguiente de forma predeterminada cuando haya finalizado el indicador de progreso de evaluación para el problema, que indica que se ha revisado el ejemplo de evaluación y etiquetaron suficientes archivos relevantes. > En caso contrario, si desea ver los resultados de la pestaña **seguimiento** y control el margen de error y el siguiente paso, haga clic en **Modificar** junto al **Paso siguiente**, seleccione **evaluación continuar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f893-p104">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged. > Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="6f893-p105">Haga clic en **Modificar** a la derecha de la casilla de verificación de **evaluación** para ver y especificar los parámetros de evaluación por el problema. Se muestra un cuadro de diálogo de **nivel de evaluación** para cada problema, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f893-p105">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue. An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![Problema de caso del nivel de evaluación](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="6f893-123">Los siguientes parámetros para el problema se calculan y se muestran en el cuadro de diálogo **nivel de evaluación** :</span><span class="sxs-lookup"><span data-stu-id="6f893-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="6f893-p106">**Calcula el margen de error de destino para la recuperación**: en función de este valor, se calcula el número estimado de archivos adicionales necesarios para revisar. El margen que se usa para recuperación es mayor que el 75% y con un nivel de confianza del 95%.</span><span class="sxs-lookup"><span data-stu-id="6f893-p106">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated. The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="6f893-126">**Los archivos de evaluación adicionales necesarios**: indica cuántos más archivos son necesarios si no se cumplen los requisitos del margen de error actual.</span><span class="sxs-lookup"><span data-stu-id="6f893-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="6f893-127">Para ajustar el margen de error actual y ver el efecto de los márgenes de error diferentes (por problema):</span><span class="sxs-lookup"><span data-stu-id="6f893-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="6f893-128">En la lista **Seleccione el problema** , seleccione un problema.</span><span class="sxs-lookup"><span data-stu-id="6f893-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="6f893-129">En el **margen de error de destino para recuperación estima**, escriba un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="6f893-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="6f893-130">Haga clic en **Actualizar valores** para ver el impacto de los ajustes.</span><span class="sxs-lookup"><span data-stu-id="6f893-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="6f893-131">Haga clic en **Avanzadas** en el cuadro de diálogo de **nivel de evaluación** para ver los siguientes parámetros adicionales y detalles:</span><span class="sxs-lookup"><span data-stu-id="6f893-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![Vista avanzada del problema de caso del nivel de evaluación](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="6f893-133">**Flexibilidad estimado**: estimado flexibilidad según los resultados de la evaluación actual</span><span class="sxs-lookup"><span data-stu-id="6f893-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="6f893-p107">**Para recuperación supuesta**: de forma predeterminada, se aplica el margen de error de destino para recuperar por encima del 75%. Si desea cambiar este parámetro y controlar el margen de error en un intervalo de valores de recuperación diferente, haga clic en **Editar** .</span><span class="sxs-lookup"><span data-stu-id="6f893-p107">**For assumed recall**: By default, the target error margin applies to recall above 75%. Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="6f893-p108">**Nivel de confianza**: de forma predeterminada, el margen de error recomendada para confianza es 95%. Si desea cambiar este parámetro, haga clic en **Editar** .</span><span class="sxs-lookup"><span data-stu-id="6f893-p108">**Confidence level**: By default, the recommended error margin for confidence is 95%. Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="6f893-138">**Margen de error de flexibilidad esperados**: dado los valores actualizados, este es el margen de error de la flexibilidad, esperado después de que se revisan todos los archivos de evaluación adicionales.</span><span class="sxs-lookup"><span data-stu-id="6f893-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="6f893-139">**Los archivos de evaluación adicionales necesarios**: dado los valores actualizados, el número de evaluación adicional de los archivos que necesitan para ser revisado para llegar a la de destino.</span><span class="sxs-lookup"><span data-stu-id="6f893-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="6f893-140">**Evaluación total archivos necesarios**: dado los valores actualizados, número total de archivos de evaluación necesarios para su revisión.</span><span class="sxs-lookup"><span data-stu-id="6f893-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="6f893-141">**Número esperado de archivos relevantes de evaluación**: dados los valores actualizados, el número esperado de los archivos relevantes en toda la evaluación después de que se revisan todos los archivos de evaluación adicionales.</span><span class="sxs-lookup"><span data-stu-id="6f893-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="6f893-p109">Haga clic en **volver a calcular valores**, si se modifican los parámetros. Cuando haya terminado, si hay un problema, haga clic en **Aceptar** para guardar los cambios (o **siguiente** cuando hay varios problemas para revisar o modificar y, a continuación, **Finalizar**).</span><span class="sxs-lookup"><span data-stu-id="6f893-p109">Click **Recalculate values**, if parameters are changed. When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="6f893-144">Cuando hay varios problemas, después de todos los problemas se han revisado o ajustados, un **nivel de evaluación: resumen** se muestra el cuadro de diálogo, tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6f893-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Resumen del nivel de evaluación](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="6f893-146">Una vez finalizada la correcta de evaluación, continúe con la siguiente fase de aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="6f893-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="6f893-147">Revisar los resultados de la evaluación</span><span class="sxs-lookup"><span data-stu-id="6f893-147">Reviewing assessment results</span></span>

<span data-ttu-id="6f893-148">Después de que se etiqueta un ejemplo de evaluación, se calculan los resultados de la evaluación y se muestran en la ficha seguimiento de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="6f893-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="6f893-149">Los siguientes resultados se muestran en la visualización de pista expandida:</span><span class="sxs-lookup"><span data-stu-id="6f893-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="6f893-150">Margen de error actual de evaluación para las estimaciones de recuperación</span><span class="sxs-lookup"><span data-stu-id="6f893-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="6f893-151">Flexibilidad estimado</span><span class="sxs-lookup"><span data-stu-id="6f893-151">Estimated richness</span></span>
    
- <span data-ttu-id="6f893-152">Archivos de evaluación adicionales necesarios (para revisión)</span><span class="sxs-lookup"><span data-stu-id="6f893-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="6f893-p110">El margen de error actual de evaluación es el margen de error recomendado por avanzada exhibición de documentos electrónicos. El número que se muestra para "archivos de la evaluación adicionales necesarios" corresponde a esa recomendación.</span><span class="sxs-lookup"><span data-stu-id="6f893-p110">The Assessment current error margin is the error margin recommended by Advanced eDiscovery. The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="6f893-p111">El indicador de progreso de la evaluación muestra el nivel de finalización de la evaluación, dada el margen de error actual. Cuando la evaluación está en curso, el usuario va a marcar otro ejemplo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="6f893-p111">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin. When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="6f893-157">Cuando el indicador de progreso de la evaluación muestra evaluación como completada, que significa que se completó la revisión de ejemplo de evaluación y etiquetaron suficientes archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="6f893-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="6f893-158">La visualización de pista expandida muestra el siguiente paso recomendado, las estadísticas de evaluación y acceso a resultados detallados.</span><span class="sxs-lookup"><span data-stu-id="6f893-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="6f893-p112">Cuando flexibilidad es muy bajo, el número de archivos de evaluación adicionales necesarios para llegar a un número mínimo de archivos relevantes para producir estadísticas útiles es muy alto. Exhibición de documentos electrónicos avanzada, a continuación, recomienda pasar a recursos de aprendizaje. El indicador de progreso de la evaluación será sombreado y no hay estadísticas estará disponible.</span><span class="sxs-lookup"><span data-stu-id="6f893-p112">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high. Advanced eDiscovery will then recommend moving on to training. The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="6f893-p113">En ausencia de estabilización estadísticamente en función, habrá resultados con un nivel de precisión y confianza de nivel inferior. Sin embargo, estos resultados pueden utilizarse para buscar archivos relevantes cuando no es necesario saber el porcentaje de archivos relevantes que se encuentran. De forma similar, se puede usar este estado para enseñar a los problemas con la flexibilidad baja, donde las puntuaciones de la relevancia pueden acelerar el acceso a archivos relevantes para un problema específico.</span><span class="sxs-lookup"><span data-stu-id="6f893-p113">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level. However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found. Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="6f893-p114">En el **la relevancia \> pista** ficha, mostrar problema expandida, están disponibles las siguientes opciones de visualización: > paso la próxima recomendada, tales como **siguiente paso: etiquetado** puede omitirse (por problema) haciendo clic en el botón **Modificar** para su derecha y, a continuación, seleccionar un paso diferente en el **paso siguiente**. Cuando no se ha completado el indicador de progreso de la evaluación, evaluación será la siguiente opción recomendada para etiquetar más archivos de evaluación y aumentar la precisión de las estadísticas. > Se puede cambiar el margen de error y evaluar su impacto, haciendo clic en **Modificar**y, en el **cuadro de diálogo nivel de evaluación**, cambiar el **margen de error de destino para recuperación estima**y haciendo clic en **Actualizar valores**. Además, en este cuadro de diálogo, puede ver las opciones avanzadas, haciendo clic en **Opciones avanzadas**. > Puede ver las estadísticas de nivel de evaluación adicionales y su impacto haciendo clic en **Ver**. En el diálogo de resultados de todos los detalles que se muestra, las estadísticas están disponibles por el problema, cuando hay al menos 500 archivos de evaluación con etiqueta y los archivos de al menos 18 se etiquetan como pertinente para el problema.</span><span class="sxs-lookup"><span data-stu-id="6f893-p114">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**. When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy. > You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**. Also, in this dialog, you can view advanced options, by clicking **Advanced**. > You can view additional assessment level statistics and their impact by clicking **View**. In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6f893-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f893-171">See also</span></span>

[<span data-ttu-id="6f893-172">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f893-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6f893-173">Evaluación de descripción en la relevancia</span><span class="sxs-lookup"><span data-stu-id="6f893-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f893-174">Etiquetado y formación de relevancia</span><span class="sxs-lookup"><span data-stu-id="6f893-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f893-175">Análisis de la relevancia de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6f893-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f893-176">Decidir en función de los resultados</span><span class="sxs-lookup"><span data-stu-id="6f893-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f893-177">Las pruebas de análisis de la relevancia</span><span class="sxs-lookup"><span data-stu-id="6f893-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

