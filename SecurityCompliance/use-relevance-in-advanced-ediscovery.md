---
title: Usar el módulo de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 'Obtenga información sobre el módulo relevancia en Office 365 Advanced eDiscovery, incluido un flujo de trabajo y directrices, y pasos para la revisión del archivo y el aprendizaje.  '
ms.openlocfilehash: ad44066c8b00bccacf1f4fe2088aa84096c4db84
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217460"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b4cf8-103">Usar el módulo de relevancia en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="b4cf8-103">Use the Relevance module in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b4cf8-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b4cf8-p102">En la exhibición avanzada de documentos electrónicos, el módulo de relevancia incluye el entrenamiento de relevancia y la revisión de los archivos relacionados con un caso. El flujo de trabajo de relevancia se muestra y se describe de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p102">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![Flujo de trabajo de relevancia](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="b4cf8-109">**Ciclos de evaluación y seguimiento**:</span><span class="sxs-lookup"><span data-stu-id="b4cf8-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="b4cf8-110">**Evaluación**: eDiscovery avanzado permite realizar evaluaciones tempranas basadas en una muestra aleatoria de archivos y usa esta evaluación para aplicar decisiones y determinar el rendimiento del proceso de codificación predictivo.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="b4cf8-111">**Track**: eDiscovery avanzado calcula y muestra los resultados provisionales de la evaluación mientras supervisa la validez estadística del proceso.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="b4cf8-112">**Ciclos de formación y seguimiento**:</span><span class="sxs-lookup"><span data-stu-id="b4cf8-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="b4cf8-113">**Tag**: Advanced eDiscovery aprende los criterios de relevancia específicos de cada problema en función de la revisión iterativa del experto y el etiquetado de archivos individuales.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="b4cf8-114">**Track**: eDiscovery avanzado calcula y muestra los resultados provisionales de la formación de relevancia mientras supervisa la validez estadística del proceso.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="b4cf8-115">**Cálculo del lote**: eDiscovery avanzado toma los criterios de relevancia acumulados y aprendidos, los aplica a toda la colección de archivos y genera calificaciones de relevancia para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="b4cf8-116">**Decida**: eDiscovery avanzado muestra los resultados del análisis aplicado a todo el caso tras el cálculo del lote y muestra los datos para tomar decisiones de revisión del documento.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="b4cf8-117">**Prueba**: se pueden probar los resultados de eDiscovery avanzado para comprobar la validez y la eficacia del procesamiento avanzado de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="b4cf8-118">Directrices para la revisión y el aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="b4cf8-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="b4cf8-119">A continuación, se encuentra una descripción general de las directrices para la revisión y aprendizaje de relevancia:</span><span class="sxs-lookup"><span data-stu-id="b4cf8-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="b4cf8-p103">**Errores e**incoherencias: si se producen errores de etiquetado durante el aprendizaje, vuelva a ejemplos de archivos anteriores para corregirlos. Si hay demasiados errores para corregir o hay una nueva perspectiva del caso o problema, el administrador debe volver a definir los criterios de relevancia y se reiniciará el entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p103">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="b4cf8-122">**Etiquetado y aprendizaje**:</span><span class="sxs-lookup"><span data-stu-id="b4cf8-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="b4cf8-p104">Los archivos deben etiquetarse en función del contenido únicamente. No tenga en cuenta los metadatos, como custodios, Date o path de archivo.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p104">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="b4cf8-125">No se deben tener en cuenta las indicaciones de intervalo de fechas en el texto al etiquetar archivos.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="b4cf8-126">No considere las imágenes gráficas incrustadas cuando etiquete archivos.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="b4cf8-p105">[! Importante] Si ve un archivo con el icono de la **vista de texto con formato** durante la etiquetación, no tenga en cuenta el formato del texto. Por ejemplo, una palabra mostrada con tachado (una línea horizontal a través de su centro que indica la eliminación) se sigue considerando por relevancia como parte del texto analizado.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p105">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text. For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="b4cf8-p106">Omitir el texto aplicado a la relevancia (según lo establecido por el administrador de casos o el administrador) se quitará en el contenido del archivo que se muestra en la vista de texto en relevancia. Si los valores de omitir texto se definieron después de que ya se haya iniciado el entrenamiento de relevancia, el nuevo texto omitido se aplicará a los archivos de ejemplo creados a partir del punto en que se definió. La característica omitir texto debe usarse con cuidado, ya que su uso puede reducir el rendimiento del análisis de archivos</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p106">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="b4cf8-p107">Use la opción **omitir etiquetado** solo cuando sea necesario. La exhibición avanzada de documentos electrónicos no realiza un entrenamiento basado en archivos omitidos. En la evaluación, si es difícil distinguir si un archivo es relevante, es mejor marcar como relevante (R) o no relevante (NR) siempre que sea posible, en lugar de seleccionar **SKIP**. Cuando la exhibición avanzada de documentos electrónicos evalúa el aprendizaje, puede ver cómo se procesaron estos tipos de archivos.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p107">Use the **Skip tagging** option only when necessary. Advanced eDiscovery does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="b4cf8-136">Incluso los archivos con una cantidad muy pequeña de texto extraído deben etiquetarse en el aprendizaje como R/NR, en lugar de "omitir", cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="b4cf8-137">El etiquetado puede afectar al clasificador siempre que el archivo sea legible y pueda etiquetarse como R/NR.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="b4cf8-138">El número de secuencia de archivo en la lista de archivos de ejemplo mostrados de la ficha **etiqueta** permite al usuario volver al orden original mostrado de los archivos.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="b4cf8-p108">Puede volver a cualquier muestra y cambiar la etiquetación de los archivos de la evaluación y el conjunto de formación. Los cambios se aplicarán al crear el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p108">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="b4cf8-141">Los archivos de Excel examinados en formato PDF deben tratarse igual que los archivos de Excel nativos al etiquetar archivos.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="b4cf8-p109">Si tiene dudas sobre el etiquetado de relevancia de un archivo, consulte a un experto. Un etiquetado incorrecto durante el aprendizaje de relevancia puede llevar a la pérdida de tiempo más adelante en el proceso y también puede tener un impacto negativo en la calidad de los resultados generales.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p109">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="b4cf8-144">Las palabras clave que se definieron en las listas de palabras clave se mostrarán en colores para ayudar al usuario a identificar los archivos relevantes al etiquetar.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="b4cf8-p110">**Cálculo del lote**: los archivos que el experto etiquetó como R/NR recibirán una puntuación de 0 o 100. Esto se aplica a las etiquetas realizadas antes del cálculo por lotes. Si el experto ha cambiado el problema a inActivo tras el cálculo del lote y ha seguido el etiquetado de este problema, los nuevos resultados etiquetados no serán 100/0, sino la puntuación original.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p110">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="b4cf8-148">**Problemas y modo de muestreo**: los problemas suelen estar desactivados cuando se completa el trabajo en ellos (el entrenamiento de relevancia está estabilizado y se ha realizado el cálculo del lote), cuando se cancelan los problemas o cuando otro usuario está trabajando en los problemas.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="b4cf8-149">Pasos de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="b4cf8-149">Steps in Relevance training</span></span>

<span data-ttu-id="b4cf8-p111">En la **pestaña \> seguimiento de relevancia** , eDiscovery avanzado proporciona recomendaciones sobre cómo continuar en el procesamiento, con los siguientes pasos. Las implicaciones se describen a continuación cuando se recomienda cada uno de los pasos siguientes en el proceso de entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p111">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="b4cf8-152">Etiquetado/continuar etiquetado: revisión de archivos y etiquetado de relevancia realizado por un experto para cada archivo y problema dentro de un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="b4cf8-153">Implicación: debe etiquetarse una muestra existente.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="b4cf8-154">Evaluación/continuar evaluación: permite la validación temprana de la relevancia de los casos y una vista preliminar de la relevancia de la población de archivos importada para el caso actual.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="b4cf8-155">Implicación: se requiere o se recomienda más evaluación.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="b4cf8-156">Aprendizaje/continuar aprendizaje: proceso durante el cual eDiscovery avanzado aprende del experto que etiqueta los ejemplos de archivos y adquiere la capacidad de identificar criterios de relevancia relacionados con cada problema en el contexto de cada caso.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="b4cf8-157">Implicación: el problema necesita más formación; la siguiente muestra se debe crear y etiquetar.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="b4cf8-p112">Cálculo del lote: proceso de relevancia en el que eDiscovery avanzado toma los conocimientos adquiridos durante la fase de capacitación y los aplica a todo el llenado de archivos. Todos los archivos del grupo de archivos pertinentes se evalúan para su relevancia y se les asigna una puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p112">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="b4cf8-160">Implicación: el problema se ha estabilizado y se puede realizar el cálculo del lote.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="b4cf8-161">Puesta en marcha: la relevancia indica cuando un experto revisa y etiqueta una muestra de archivos seleccionados desde una carga de archivos adicional durante un escenario de cargas sucesivas.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="b4cf8-162">Implicación: se ha agregado una nueva carga y se debe realizar la puesta en marcha para seguir trabajando.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="b4cf8-163">Incoherencias de etiquetas: el proceso identifica, a través de un algoritmo de exhibición de documentos electrónicos avanzado, incoherencias en el proceso de etiquetado de archivos que pueden repercutir negativamente en el análisis.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="b4cf8-164">Implicación: el ejemplo siguiente incluirá los archivos que se han etiquetado en ejemplos anteriores y se debe rehacer su etiquetado.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="b4cf8-165">Actualizar clasificador: permite al usuario aplicar cambios de etiquetado o de inicialización.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="b4cf8-166">Implicación: se pueden aplicar los cambios de etiquetado y de inicialización sin necesidad de ejecutar manualmente otro ejemplo de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="b4cf8-167">En espera: se ha completado el proceso de entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="b4cf8-168">Implicación: en este momento no se requiere ningún entrenamiento sobre la relevancia.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="b4cf8-169">Aunque la exhibición avanzada de documentos electrónicos le guía a través del proceso, con los pasos siguientes recomendados en diferentes etapas, también le permite navegar entre pestañas y páginas, y elegir opciones para abordar las situaciones que puedan ser pertinentes para su caso individual, problema o proceso de revisión de documentos.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="b4cf8-p113">Es posible aceptar o invalidar las opciones de procesamiento avanzado de paso posterior de eDiscovery. Si desea realizar un paso que no sea el siguiente paso recomendado, haga clic en el **siguiente paso** que aparece en la pantalla problema expandido en el cuadro de diálogo, haga clic en el botón **modificar** junto al paso siguiente y seleccione otra opción de paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-p113">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b4cf8-172">Algunas opciones pueden permanecer deshabilitadas tras el desbloqueo porque no se pueden usar en ese punto del proceso.</span><span class="sxs-lookup"><span data-stu-id="b4cf8-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b4cf8-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4cf8-173">See also</span></span>

[<span data-ttu-id="b4cf8-174">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="b4cf8-174">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf8-175">Descripción de la evaluación en relevancia</span><span class="sxs-lookup"><span data-stu-id="b4cf8-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf8-176">Etiquetado y evaluación</span><span class="sxs-lookup"><span data-stu-id="b4cf8-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf8-177">Aprendizaje de etiquetas y relevancia</span><span class="sxs-lookup"><span data-stu-id="b4cf8-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf8-178">Seguimiento del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="b4cf8-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf8-179">Decisiones basadas en los resultados</span><span class="sxs-lookup"><span data-stu-id="b4cf8-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf8-180">Prueba del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="b4cf8-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

