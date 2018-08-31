---
title: Usar el módulo de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 'Obtenga información sobre el módulo de la relevancia en Office 365 avanzada exhibición de documentos electrónicos, incluidos un flujo de trabajo y los pasos para su revisión de aprendizaje y archivo e instrucciones.  '
ms.openlocfilehash: 2cf75ef95291c5393367ce01fb0cd660f9b99145
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535957"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8fc08-103">Usar el módulo de relevancia en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="8fc08-103">Use the Relevance module in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="8fc08-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="8fc08-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8fc08-p102">En la exhibición de documentos electrónicos avanzada, el módulo de la relevancia incluye el aprendizaje de la relevancia y la revisión de los archivos relacionados con un caso. El flujo de trabajo de la relevancia se muestran y se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="8fc08-p102">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![Flujo de trabajo de relevancia](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="8fc08-109">**Ciclos de evaluación y seguimiento de**:</span><span class="sxs-lookup"><span data-stu-id="8fc08-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="8fc08-110">**Evaluación**: exhibición de documentos electrónicos avanzada permite la evaluación temprana basándose en una muestra aleatoria de archivos y usa esta evaluación para aplicar las decisiones para determinar el rendimiento del proceso de codificación predictivo.</span><span class="sxs-lookup"><span data-stu-id="8fc08-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="8fc08-111">**Pista**: exhibición de documentos electrónicos avanzada calcula y muestra resultados provisionales de la evaluación mientras supervisaba validez estadística del proceso.</span><span class="sxs-lookup"><span data-stu-id="8fc08-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="8fc08-112">**Ciclos de formación y seguimiento de**:</span><span class="sxs-lookup"><span data-stu-id="8fc08-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="8fc08-113">**Etiqueta**: exhibición de documentos electrónicos avanzada aprende criterios de relevancia específicos de cada problema según revisión iterativa del experto y etiquetas temáticas de archivos individuales.</span><span class="sxs-lookup"><span data-stu-id="8fc08-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="8fc08-114">**Pista**: exhibición de documentos electrónicos avanzada calcula y muestra resultados provisionales de la formación de relevancia mientras supervisaba validez estadística del proceso.</span><span class="sxs-lookup"><span data-stu-id="8fc08-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="8fc08-115">**Cálculo por lotes**: exhibición de documentos electrónicos avanzada toma los criterios de relevancia acumulados y aprendidos, se aplica a la colección de todo el archivo y genera las puntuaciones de la relevancia para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="8fc08-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="8fc08-116">**Decide**: exhibición de documentos electrónicos avanzada muestra los resultados del análisis que se aplica el caso completo después de cálculo por lotes y muestra los datos para tomar decisiones de revisión del documento.</span><span class="sxs-lookup"><span data-stu-id="8fc08-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="8fc08-117">**Prueba**: los resultados de la exhibición de documentos electrónicos avanzada pueden probarse para comprobar la validez y la eficacia del procesamiento de exhibición de documentos electrónicos avanzadas.</span><span class="sxs-lookup"><span data-stu-id="8fc08-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="8fc08-118">Directrices para la formación de la relevancia y revisión</span><span class="sxs-lookup"><span data-stu-id="8fc08-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="8fc08-119">Es una visión general de las directrices de aprendizaje de la relevancia y revisión:</span><span class="sxs-lookup"><span data-stu-id="8fc08-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="8fc08-p103">**Errores e incoherencias**: si se realizan las etiquetas temáticas errores durante la formación, volver a los ejemplos de archivo anteriores a corregirlos. Si hay demasiados errores para corregir o no hay una nueva perspectiva de la caja o un problema, deben volver a definir los criterios de la relevancia por el administrador y reinicia el aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p103">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="8fc08-122">**Etiquetado y formación**:</span><span class="sxs-lookup"><span data-stu-id="8fc08-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="8fc08-p104">Los archivos se deben etiquetar basado en el contenido únicamente. No se considere la posibilidad de metadatos, como custodia, la fecha o la ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p104">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="8fc08-125">No considere la posibilidad de fecha indicaciones de rango en el texto al etiquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="8fc08-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="8fc08-126">No considere la posibilidad de imágenes gráficas incrustadas al etiquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="8fc08-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="8fc08-p105">Si la visualización de un archivo mediante el icono **con el formato de vista de texto** mientras etiquetas temáticas, no tenga en cuenta el formato del texto. Por ejemplo, una palabra que se muestra con formato de tachado (una línea horizontal a través de su centro de eliminación) todavía se considera por relevancia como parte del texto analizado.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p105">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text. For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="8fc08-p106">Omitir el texto que se aplica a la relevancia (según lo definido por el Administrador de casos o el administrador) se quitará en el contenido del archivo que se muestra en la vista de texto en la relevancia. Si se han definido los valores para omitir el texto después de la relevancia de formación ya ha iniciado, el nuevo texto omitido se aplicarán a los archivos de ejemplo creados desde el punto en el que se definió. La característica de omitir texto debe utilizarse con cautela, como su uso puede reducir el rendimiento de análisis de archivo</span><span class="sxs-lookup"><span data-stu-id="8fc08-p106">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="8fc08-p107">Use la opción **Omitir etiquetado** sólo cuando sea necesario. Exhibición de documentos electrónicos avanzada no enseñar a basándose en los archivos omitidos. En la evaluación, si es difícil saber si un archivo es relevante, es mejor etiqueta como Relevant (R) o no relevante (n) siempre que sea posible en lugar de seleccionar **Omitir**. Cuando avanzada exhibición de documentos electrónicos se evalúa como recursos de aprendizaje, se puede, a continuación, ver grado estos tipos de archivos se han procesado.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p107">Use the **Skip tagging** option only when necessary. Advanced eDiscovery does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="8fc08-136">Incluso los archivos con una cantidad muy pequeña de texto extraído se deben etiquetar en recursos de aprendizaje como R/NR, en lugar de "Omitir", cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="8fc08-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="8fc08-137">Etiquetas temáticas pueden afectar el clasificador siempre y cuando el archivo se puede leer y se puede etiquetar como R/NR.</span><span class="sxs-lookup"><span data-stu-id="8fc08-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="8fc08-138">El número de secuencia de archivo en la lista de archivos de ejemplo que se muestra en la ficha **etiqueta** permite al usuario devolver en el orden mostrado original de los archivos.</span><span class="sxs-lookup"><span data-stu-id="8fc08-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="8fc08-p108">Puede volver a cualquier ejemplo y cambiar el etiquetado de la evaluación y establecer los archivos de recursos de aprendizaje. Al crear el ejemplo siguiente, se aplicarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p108">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="8fc08-141">Excel detectado archivos en formato PDF que deben trata de la misma como archivos de Excel nativos al etiquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="8fc08-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="8fc08-p109">En caso de duda sobre el etiquetado de la relevancia de un archivo, consulte a un experto. Etiquetado incorrecto durante el aprendizaje de la relevancia puede dar lugar a pérdida de tiempo más adelante en el proceso y también puede tener un impacto negativo sobre la calidad de los resultados.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p109">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="8fc08-144">Palabras clave que se han definido en la palabra clave se mostrará listas en los colores para ayudar al usuario a identificar archivos relevantes al etiquetado.</span><span class="sxs-lookup"><span data-stu-id="8fc08-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="8fc08-p110">**Cálculo por lotes**: los archivos que se han etiquetado como R/NR por el experto recibirá una puntuación de 0 o 100. Esto se aplica a etiquetar realizados antes de cálculo por lotes. Si el experto había conmutada el problema a inactivo después de cálculo por lotes y había continuado etiquetado este problema, las puntuaciones recién con etiqueta no será 0 y 100, pero en su lugar la puntuación original.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p110">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="8fc08-148">**Problemas y el modo de muestreo**: problemas normalmente están desactivados cuando se complete el trabajo en ellos (formación de relevancia es estable y cálculo por lotes se llevó a cabo), cuando se cancelan los problemas o cuando otro usuario está trabajando en los problemas.</span><span class="sxs-lookup"><span data-stu-id="8fc08-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="8fc08-149">Pasos de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="8fc08-149">Steps in Relevance training</span></span>

<span data-ttu-id="8fc08-p111">En el **la relevancia \> pista** ficha, exhibición de documentos electrónicos avanzada proporciona recomendaciones sobre cómo proceder en el procesamiento, con los pasos siguientes. A continuación se describen las implicaciones cuando cada uno de los siguientes pasos se recomienda en el proceso de aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p111">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="8fc08-152">Etiquetas temáticas / Continue etiquetado: revisión de archivo y relevancia etiquetado realizado por un experto para cada archivo y emitir dentro de una muestra.</span><span class="sxs-lookup"><span data-stu-id="8fc08-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="8fc08-153">Implicación: Debe etiquetar un ejemplo existente.</span><span class="sxs-lookup"><span data-stu-id="8fc08-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="8fc08-154">Evaluación / Continue evaluación: permite la validación anticipada de la relevancia de mayúsculas y minúsculas del problema y una vista preliminar de la relevancia de la población de archivo importada para el caso de actual.</span><span class="sxs-lookup"><span data-stu-id="8fc08-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="8fc08-155">Implicación: Evaluación más es necesario o recomendado.</span><span class="sxs-lookup"><span data-stu-id="8fc08-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="8fc08-156">Recursos de aprendizaje / Continue aprendizaje: proceso durante qué avanzadas aprende exhibición de documentos electrónicos desde el experto que es etiquetar el archivo de ejemplos y adquiere la capacidad para identificar los criterios de relevancia pertinentes a cada problema dentro del contexto de cada caso.</span><span class="sxs-lookup"><span data-stu-id="8fc08-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="8fc08-157">Implicación: El problema necesita más recursos de formación; el ejemplo siguiente se debe crearse y etiquetado.</span><span class="sxs-lookup"><span data-stu-id="8fc08-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="8fc08-p112">Cálculo de lotes: proceso de relevancia en qué opciones avanzadas exhibición de documentos electrónicos toma la información obtenida durante la fase de aprendizaje y aplica a la población de todo el archivo. Todos los archivos en el grupo de archivos pertinente se evalúan para la relevancia y asigna una puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p112">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="8fc08-160">Implicación: El problema se estable y se puede realizar el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="8fc08-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="8fc08-161">Ponerse al día: La relevancia indica cuándo con un experto revisa y un ejemplo de los archivos seleccionados desde un archivo adicional de carga durante un escenario de carga sucesivas de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="8fc08-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="8fc08-162">Implicación: Se ha agregado una nueva carga y ponerse al día es necesario para continuar trabajando.</span><span class="sxs-lookup"><span data-stu-id="8fc08-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="8fc08-163">Marcar incoherencias: proceso identifica a través de un algoritmo de exhibición de documentos electrónicos avanzadas, incoherencias en el archivo etiquetado proceso que puede afectar negativamente el análisis.</span><span class="sxs-lookup"><span data-stu-id="8fc08-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="8fc08-164">Implicación: En el ejemplo siguiente se incluye los archivos que se han etiquetado en los ejemplos anteriores, y se pueden repetir su etiquetado.</span><span class="sxs-lookup"><span data-stu-id="8fc08-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="8fc08-165">Actualizar clasificador: permite al usuario aplicar cambios de inicialización o etiquetado.</span><span class="sxs-lookup"><span data-stu-id="8fc08-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="8fc08-166">Implicación: Etiquetado e inicialización cambios pueden aplicarse sin necesidad de realizar otro ejemplo de la relevancia de forma manual.</span><span class="sxs-lookup"><span data-stu-id="8fc08-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="8fc08-167">En espera: se complete el proceso de aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="8fc08-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="8fc08-168">Implicación: No hay recursos de aprendizaje de la relevancia es necesaria en ese momento.</span><span class="sxs-lookup"><span data-stu-id="8fc08-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="8fc08-169">Aunque avanzada exhibición de documentos electrónicos le guiará por el proceso, con recomienda seguir estos pasos en distintas etapas, también permite desplazarse por las fichas y páginas, así como a tomar decisiones a situaciones de dirección que pueden ser adecuadas para su caso individual, problema, o proceso de revisión de documentos.</span><span class="sxs-lookup"><span data-stu-id="8fc08-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="8fc08-p113">Es posible aceptar o reemplazar el paso siguiente de exhibición de documentos electrónicos avanzadas opciones de procesamiento. Si desea realizar un paso que no sea el próximo paso recomendado, haga clic en el **siguiente paso** que aparecen en la pantalla de problema expandida en el cuadro de diálogo, haga clic en el botón **Modificar** junto al paso siguiente y seleccione otra opción de paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="8fc08-p113">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8fc08-172">Algunas de las opciones pueden permanecer deshabilitadas después de desbloquear como no son compatibles para su uso en ese momento en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8fc08-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8fc08-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fc08-173">See also</span></span>

[<span data-ttu-id="8fc08-174">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="8fc08-174">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8fc08-175">Evaluación de descripción en la relevancia</span><span class="sxs-lookup"><span data-stu-id="8fc08-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8fc08-176">Etiquetas temáticas y evaluación</span><span class="sxs-lookup"><span data-stu-id="8fc08-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8fc08-177">Etiquetado y formación de relevancia</span><span class="sxs-lookup"><span data-stu-id="8fc08-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8fc08-178">Análisis de la relevancia de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8fc08-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8fc08-179">Decidir en función de los resultados</span><span class="sxs-lookup"><span data-stu-id="8fc08-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8fc08-180">Las pruebas de análisis de la relevancia</span><span class="sxs-lookup"><span data-stu-id="8fc08-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

