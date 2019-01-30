---
title: Con el módulo de la relevancia para analizar datos en la exhibición de documentos electrónicos avanzada (vista previa)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 5e30a7f6919f50d2d73606fae3b53f21ef33e223
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608341"
---
# <a name="using-the-relevance-module-to-analyze-data-in-advanced-ediscovery-preview"></a><span data-ttu-id="77a72-102">Con el módulo de la relevancia para analizar datos en la exhibición de documentos electrónicos avanzada (vista previa)</span><span class="sxs-lookup"><span data-stu-id="77a72-102">Using the Relevance module to analyze data in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="77a72-p101">En Avanzadas exhibición de documentos electrónicos (vista previa), el módulo de la relevancia incluye la formación de la relevancia y la revisión de los archivos relacionados con un caso. El flujo de trabajo de la relevancia se muestran y se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="77a72-p101">In Advanced eDiscovery (Preview), the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![Flujo de trabajo de relevancia](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="77a72-106">**Ciclos de evaluación y seguimiento de**:</span><span class="sxs-lookup"><span data-stu-id="77a72-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="77a72-107">**Evaluación**: habilita la evaluación temprana basándose en una muestra aleatoria de archivos y usa esta evaluación para aplicar las decisiones para determinar el rendimiento del proceso de codificación predictivo.</span><span class="sxs-lookup"><span data-stu-id="77a72-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="77a72-108">**Pista**: calcular y mostrar los resultados provisionales de la evaluación mientras supervisaba validez estadística del proceso.</span><span class="sxs-lookup"><span data-stu-id="77a72-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="77a72-109">**Ciclos de formación y seguimiento**</span><span class="sxs-lookup"><span data-stu-id="77a72-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="77a72-110">**Etiqueta**: exhibición de documentos electrónicos avanzada (vista previa) aprende criterios de relevancia específicos de cada problema según revisión iterativa del experto y etiquetas temáticas de archivos individuales.</span><span class="sxs-lookup"><span data-stu-id="77a72-110">**Tag**: Advanced eDiscovery (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="77a72-111">**Pista**: calcular y mostrar los resultados provisionales de la formación de relevancia durante la validez estadística del proceso de supervisión.</span><span class="sxs-lookup"><span data-stu-id="77a72-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="77a72-112">**Cálculo por lotes**: los criterios de relevancia acumulados y aprendidos se aplica a la colección de todo el archivo y se genera una puntuación de relevancia para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="77a72-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="77a72-113">**Decide**: los resultados del análisis aplicado a las mayúsculas y minúsculas toda se muestra después del cálculo por lotes, y se muestran los datos que se usa para tomar decisiones de revisión del documento.</span><span class="sxs-lookup"><span data-stu-id="77a72-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="77a72-114">**Prueba**: los resultados se pueden probar para comprobar la validez y la eficacia del procesamiento de exhibición de documentos electrónicos avanzada (vista previa).</span><span class="sxs-lookup"><span data-stu-id="77a72-114">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery (Preview) processing.</span></span>

- <span data-ttu-id="77a72-115">**Búsqueda**: una vez que se completa el flujo de trabajo de la relevancia, puede usar el resultado como percentil de lectura de un documento para su problema cuando se ejecuta una consulta dentro de su conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="77a72-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="77a72-116">Directrices para la formación de la relevancia y revisión</span><span class="sxs-lookup"><span data-stu-id="77a72-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="77a72-117">Es una visión general de las directrices de aprendizaje de la relevancia y revisión:</span><span class="sxs-lookup"><span data-stu-id="77a72-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="77a72-p102">**Errores e incoherencias**: si se realizan las etiquetas temáticas errores durante la formación, volver a los ejemplos de archivo anteriores a corregirlos. Si hay demasiados errores para corregir o no hay una nueva perspectiva de la caja o un problema, deben volver a definir los criterios de la relevancia por el administrador y reinicia el aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="77a72-p102">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="77a72-120">**Etiquetado y formación**:</span><span class="sxs-lookup"><span data-stu-id="77a72-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="77a72-p103">Los archivos se deben etiquetar basado en el contenido únicamente. No se considere la posibilidad de metadatos, como custodia, la fecha o la ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="77a72-p103">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="77a72-123">No considere la posibilidad de fecha indicaciones de rango en el texto al etiquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="77a72-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="77a72-124">No considere la posibilidad de imágenes gráficas incrustadas al etiquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="77a72-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="77a72-p104">Omitir texto aplicadas a la relevancia se quitarán en el contenido del archivo que se muestra en la vista de texto en la relevancia. Si se han definido los valores para omitir el texto después de la relevancia de formación ya ha iniciado, el nuevo texto omitido se aplicarán a los archivos de ejemplo creados desde el punto en el que se definió. La característica de omitir texto debe utilizarse con cautela, como su uso puede reducir el rendimiento de análisis de archivo</span><span class="sxs-lookup"><span data-stu-id="77a72-p104">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="77a72-p105">Use la opción **Omitir etiquetado** sólo cuando sea necesario. Exhibición de documentos electrónicos avanzada (vista previa) no entrenamiento basándose en los archivos omitidos. En la evaluación, si es difícil saber si un archivo es relevante, es mejor etiqueta como Relevant (R) o no relevante (n) siempre que sea posible en lugar de seleccionar **Omitir**. Cuando la exhibición de documentos electrónicos avanzada (vista previa) se evalúa como recursos de aprendizaje, se puede, a continuación, ver grado estos tipos de archivos se han procesado.</span><span class="sxs-lookup"><span data-stu-id="77a72-p105">Use the **Skip tagging** option only when necessary. Advanced eDiscovery (Preview) does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="77a72-132">Incluso los archivos con una cantidad muy pequeña de texto extraído se deben etiquetar en recursos de aprendizaje como R/NR, en lugar de "Omitir", cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="77a72-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="77a72-133">Etiquetas temáticas pueden afectar el clasificador siempre y cuando el archivo se puede leer y se puede etiquetar como R/NR.</span><span class="sxs-lookup"><span data-stu-id="77a72-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="77a72-134">El número de secuencia de archivo en la lista de archivos de ejemplo que se muestra en la ficha **etiqueta** permite al usuario devolver en el orden mostrado original de los archivos.</span><span class="sxs-lookup"><span data-stu-id="77a72-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="77a72-p106">Puede volver a cualquier ejemplo y cambiar el etiquetado de la evaluación y establecer los archivos de recursos de aprendizaje. Al crear el ejemplo siguiente, se aplicarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="77a72-p106">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="77a72-137">Excel detectado archivos en formato PDF que deben trata de la misma como archivos de Excel nativos al etiquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="77a72-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="77a72-p107">En caso de duda sobre el etiquetado de la relevancia de un archivo, consulte a un experto. Etiquetado incorrecto durante el aprendizaje de la relevancia puede dar lugar a pérdida de tiempo más adelante en el proceso y también puede tener un impacto negativo sobre la calidad de los resultados.</span><span class="sxs-lookup"><span data-stu-id="77a72-p107">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="77a72-140">Palabras clave que se han definido en la palabra clave se mostrará listas en los colores para ayudar al usuario a identificar archivos relevantes al etiquetado.</span><span class="sxs-lookup"><span data-stu-id="77a72-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="77a72-p108">**Cálculo por lotes**: los archivos que se han etiquetado como R/NR por el experto recibirá una puntuación de 0 o 100. Esto se aplica a etiquetar realizados antes de cálculo por lotes. Si el experto había conmutada el problema a inactivo después de cálculo por lotes y había continuado etiquetado este problema, las puntuaciones recién con etiqueta no será 0 y 100, pero en su lugar la puntuación original.</span><span class="sxs-lookup"><span data-stu-id="77a72-p108">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="77a72-144">**Problemas y el modo de muestreo**: problemas normalmente están desactivados cuando se complete el trabajo en ellos (formación de relevancia es estable y cálculo por lotes se llevó a cabo), cuando se cancelan los problemas o cuando otro usuario está trabajando en los problemas.</span><span class="sxs-lookup"><span data-stu-id="77a72-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="77a72-145">Pasos de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="77a72-145">Steps in Relevance training</span></span>

<span data-ttu-id="77a72-p109">En el **la relevancia \> pista** ficha, exhibición de documentos electrónicos avanzada proporciona recomendaciones sobre cómo proceder en el procesamiento, con los pasos siguientes. A continuación se describen las implicaciones cuando cada uno de los siguientes pasos se recomienda en el proceso de aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="77a72-p109">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="77a72-148">Etiquetas temáticas / Continue etiquetado: revisión de archivo y relevancia etiquetado realizado por un experto para cada archivo y emitir dentro de una muestra.</span><span class="sxs-lookup"><span data-stu-id="77a72-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="77a72-149">Implicación: Debe etiquetar un ejemplo existente.</span><span class="sxs-lookup"><span data-stu-id="77a72-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="77a72-150">Evaluación / Continue evaluación: permite la validación anticipada de la relevancia de mayúsculas y minúsculas del problema y una vista preliminar de la relevancia de la población de archivo importada para el caso de actual.</span><span class="sxs-lookup"><span data-stu-id="77a72-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="77a72-151">Implicación: Evaluación más es necesario o recomendado.</span><span class="sxs-lookup"><span data-stu-id="77a72-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="77a72-152">Recursos de aprendizaje / Continue aprendizaje: proceso durante qué avanzadas aprende exhibición de documentos electrónicos desde el experto que es etiquetar el archivo de ejemplos y adquiere la capacidad para identificar los criterios de relevancia pertinentes a cada problema dentro del contexto de cada caso.</span><span class="sxs-lookup"><span data-stu-id="77a72-152">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="77a72-153">Implicación: El problema necesita más recursos de formación; el ejemplo siguiente se debe crearse y etiquetado.</span><span class="sxs-lookup"><span data-stu-id="77a72-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="77a72-p110">Cálculo de lotes: proceso de relevancia en qué opciones avanzadas exhibición de documentos electrónicos toma la información obtenida durante la fase de aprendizaje y aplica a la población de todo el archivo. Todos los archivos en el grupo de archivos pertinente se evalúan para la relevancia y asigna una puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="77a72-p110">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="77a72-156">Implicación: El problema se estable y se puede realizar el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="77a72-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="77a72-157">Ponerse al día: La relevancia indica cuándo con un experto revisa y un ejemplo de los archivos seleccionados desde un archivo adicional de carga durante un escenario de carga sucesivas de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="77a72-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="77a72-158">Implicación: Se ha agregado una nueva carga y ponerse al día es necesario para continuar trabajando.</span><span class="sxs-lookup"><span data-stu-id="77a72-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="77a72-159">Marcar incoherencias: proceso identifica a través de un algoritmo de exhibición de documentos electrónicos avanzadas, incoherencias en el archivo etiquetado proceso que puede afectar negativamente el análisis.</span><span class="sxs-lookup"><span data-stu-id="77a72-159">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="77a72-160">Implicación: En el ejemplo siguiente se incluye los archivos que se han etiquetado en los ejemplos anteriores, y se pueden repetir su etiquetado.</span><span class="sxs-lookup"><span data-stu-id="77a72-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="77a72-161">Actualizar clasificador: permite al usuario aplicar cambios de inicialización o etiquetado.</span><span class="sxs-lookup"><span data-stu-id="77a72-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="77a72-162">Implicación: Etiquetado e inicialización cambios pueden aplicarse sin necesidad de realizar otro ejemplo de la relevancia de forma manual.</span><span class="sxs-lookup"><span data-stu-id="77a72-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="77a72-163">En espera: se complete el proceso de aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="77a72-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="77a72-164">Implicación: No hay recursos de aprendizaje de la relevancia es necesaria en ese momento.</span><span class="sxs-lookup"><span data-stu-id="77a72-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="77a72-165">Aunque avanzada exhibición de documentos electrónicos le guiará por el proceso, con recomienda seguir estos pasos en distintas etapas, también permite desplazarse por las fichas y páginas, así como a tomar decisiones a situaciones de dirección que pueden ser adecuadas para su caso individual, problema, o proceso de revisión de documentos.</span><span class="sxs-lookup"><span data-stu-id="77a72-165">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="77a72-p111">Es posible aceptar o reemplazar el paso siguiente de exhibición de documentos electrónicos avanzadas opciones de procesamiento. Si desea realizar un paso que no sea el próximo paso recomendado, haga clic en el **siguiente paso** que aparecen en la pantalla de problema expandida en el cuadro de diálogo, haga clic en el botón **Modificar** junto al paso siguiente y seleccione otra opción de paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="77a72-p111">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="77a72-168">Algunas de las opciones pueden permanecer deshabilitadas después de desbloquear como no son compatibles para su uso en ese momento en el proceso.</span><span class="sxs-lookup"><span data-stu-id="77a72-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="77a72-169">Más información</span><span class="sxs-lookup"><span data-stu-id="77a72-169">More information</span></span>

[<span data-ttu-id="77a72-170">Evaluación de descripción en la relevancia</span><span class="sxs-lookup"><span data-stu-id="77a72-170">Understanding Assessment in Relevance</span></span>](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77a72-171">Etiquetas temáticas y evaluación</span><span class="sxs-lookup"><span data-stu-id="77a72-171">Tagging and Assessment</span></span>](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77a72-172">Etiquetado y formación de relevancia</span><span class="sxs-lookup"><span data-stu-id="77a72-172">Tagging and Relevance training</span></span>](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77a72-173">Análisis de la relevancia de seguimiento</span><span class="sxs-lookup"><span data-stu-id="77a72-173">Tracking Relevance analysis</span></span>](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77a72-174">Decidir en función de los resultados</span><span class="sxs-lookup"><span data-stu-id="77a72-174">Deciding based on the results</span></span>](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77a72-175">Las pruebas de análisis de la relevancia</span><span class="sxs-lookup"><span data-stu-id="77a72-175">Testing Relevance analysis</span></span>](../test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="77a72-176">Realizar consultas en el conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="77a72-176">Query within working set</span></span>](working-set-search.md)
