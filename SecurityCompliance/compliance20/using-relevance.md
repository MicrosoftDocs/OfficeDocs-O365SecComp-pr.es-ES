---
title: Usar el módulo relevancia para analizar datos en la exhibición avanzada de documentos electrónicos (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 6e94adc6e6b7fb7d8757b161ffdf01066cadac7a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242130"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery-preview"></a><span data-ttu-id="c0f71-102">Usar el módulo relevancia para analizar datos en la exhibición avanzada de documentos electrónicos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c0f71-102">Use the Relevance module to analyze data in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="c0f71-103">En la exhibición avanzada de documentos electrónicos (versión preliminar), el módulo de relevancia incluye el entrenamiento de relevancia y la revisión de los archivos relacionados con un caso.</span><span class="sxs-lookup"><span data-stu-id="c0f71-103">In Advanced eDiscovery (Preview), the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="c0f71-104">Para usar el flujo de trabajo de relevancia, vaya a Manage working set in a working set y haga clic en Mostrar relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-104">In order to use the Relevance workflow, go to Manage Working Set within a working set and click on Show Relevance.</span></span> <span data-ttu-id="c0f71-105">Hay un par de pasos que debe realizar antes de poder iniciar el flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="c0f71-105">There are a couple of steps you need to complete before you can start the workflow:</span></span>
- <span data-ttu-id="c0f71-106">Proceso: cada conjunto de carga agregado al conjunto de trabajo se mostrará como "contenedor" aquí.</span><span class="sxs-lookup"><span data-stu-id="c0f71-106">Process: each load set added to the working set will show up as a "container" here.</span></span> <span data-ttu-id="c0f71-107">Debe procesar estos documentos para poder agregarlos al módulo de relevancia; Aquí también puede marcarlos como semilla o etiquetarse previamente para un problema específico.</span><span class="sxs-lookup"><span data-stu-id="c0f71-107">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>
- <span data-ttu-id="c0f71-108">Agregar a relevancia: en cargas \> de relevancia, puede agregar documentos que se han procesado en relevancia para que estén disponibles para su aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c0f71-108">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="c0f71-109">El flujo de trabajo de relevancia se muestra y se describe de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c0f71-109">The Relevance workflow is shown and described as follows:</span></span>
  
![Flujo de trabajo de relevancia](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="c0f71-111">**Ciclos de evaluación y seguimiento**:</span><span class="sxs-lookup"><span data-stu-id="c0f71-111">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="c0f71-112">**Evaluación**: permite realizar evaluaciones tempranas basándose en un ejemplo aleatorio de archivos y usa esta evaluación para aplicar decisiones para determinar el rendimiento del proceso de codificación predictivo.</span><span class="sxs-lookup"><span data-stu-id="c0f71-112">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="c0f71-113">**Track**: calcule y muestre los resultados temporales de la evaluación mientras supervisa la validez estadística del proceso.</span><span class="sxs-lookup"><span data-stu-id="c0f71-113">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="c0f71-114">**Ciclos de formación y seguimiento**</span><span class="sxs-lookup"><span data-stu-id="c0f71-114">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="c0f71-115">**Tag**: Advanced eDiscovery (Preview) aprende los criterios de relevancia específicos de cada problema en función de la revisión iterativa del experto y el etiquetado de archivos individuales.</span><span class="sxs-lookup"><span data-stu-id="c0f71-115">**Tag**: Advanced eDiscovery (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="c0f71-116">**Track**: calcule y muestre los resultados temporales de la formación de relevancia mientras supervisa la validez estadística del proceso.</span><span class="sxs-lookup"><span data-stu-id="c0f71-116">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="c0f71-117">**Cálculo del lote**: los criterios de relevancia acumulados y adquiridos se aplican a toda la colección de archivos y se genera una puntuación de relevancia para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="c0f71-117">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="c0f71-118">**Decida**: los resultados del análisis aplicado a todo el caso se muestran tras el cálculo del lote y se muestran los datos usados para realizar las decisiones de revisión del documento.</span><span class="sxs-lookup"><span data-stu-id="c0f71-118">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="c0f71-119">**Prueba**: se pueden probar los resultados para comprobar la validez y la eficacia del procesamiento de eDiscovery avanzado (vista previa).</span><span class="sxs-lookup"><span data-stu-id="c0f71-119">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery (Preview) processing.</span></span>

- <span data-ttu-id="c0f71-120">**Buscar**: una vez que se ha completado el flujo de trabajo de relevancia, puede usar el resultado como, por ejemplo, el percentil de lectura de un documento para su problema al ejecutar una consulta en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0f71-120">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="c0f71-121">Directrices para la revisión y el aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="c0f71-121">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="c0f71-122">A continuación, se encuentra una descripción general de las directrices para la revisión y aprendizaje de relevancia:</span><span class="sxs-lookup"><span data-stu-id="c0f71-122">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="c0f71-123">**Errores e**incoherencias: si se producen errores de etiquetado durante el aprendizaje, vuelva a ejemplos de archivos anteriores para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-123">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="c0f71-124">Si hay demasiados errores para corregir o hay una nueva perspectiva del caso o problema, el administrador debe volver a definir los criterios de relevancia y se reiniciará el entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-124">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="c0f71-125">**Etiquetado y aprendizaje**:</span><span class="sxs-lookup"><span data-stu-id="c0f71-125">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="c0f71-126">Los archivos deben etiquetarse en función del contenido únicamente.</span><span class="sxs-lookup"><span data-stu-id="c0f71-126">Files should be tagged based on content only.</span></span> <span data-ttu-id="c0f71-127">No tenga en cuenta los metadatos, como custodios, Date o path de archivo.</span><span class="sxs-lookup"><span data-stu-id="c0f71-127">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="c0f71-128">No se deben tener en cuenta las indicaciones de intervalo de fechas en el texto al etiquetar archivos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-128">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="c0f71-129">No considere las imágenes gráficas incrustadas cuando etiquete archivos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-129">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="c0f71-130">Omitir el texto aplicado a la relevancia se quitará en el contenido del archivo que se muestra en la vista de texto en relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-130">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="c0f71-131">Si los valores de omitir texto se definieron después de que ya se haya iniciado el entrenamiento de relevancia, el nuevo texto omitido se aplicará a los archivos de ejemplo creados a partir del punto en que se definió.</span><span class="sxs-lookup"><span data-stu-id="c0f71-131">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="c0f71-132">La característica omitir texto debe usarse con cuidado, ya que su uso puede reducir el rendimiento del análisis de archivos</span><span class="sxs-lookup"><span data-stu-id="c0f71-132">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="c0f71-133">Use la opción **omitir etiquetado** solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c0f71-133">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="c0f71-134">La exhibición avanzada de documentos electrónicos (vista previa) no se basa en archivos omitidos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-134">Advanced eDiscovery (Preview) does not train based on skipped files.</span></span> <span data-ttu-id="c0f71-135">En la evaluación, si es difícil distinguir si un archivo es relevante, es mejor marcar como relevante (R) o no relevante (NR) siempre que sea posible, en lugar de seleccionar **SKIP**.</span><span class="sxs-lookup"><span data-stu-id="c0f71-135">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="c0f71-136">Cuando la exhibición avanzada de documentos electrónicos (versión preliminar) evalúa el aprendizaje, puede ver cómo se procesaron estos tipos de archivos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-136">When Advanced eDiscovery (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="c0f71-137">Incluso los archivos con una cantidad muy pequeña de texto extraído deben etiquetarse en el aprendizaje como R/NR, en lugar de "omitir", cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="c0f71-137">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="c0f71-138">El etiquetado puede afectar al clasificador siempre que el archivo sea legible y pueda etiquetarse como R/NR.</span><span class="sxs-lookup"><span data-stu-id="c0f71-138">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="c0f71-139">El número de secuencia de archivo en la lista de archivos de ejemplo mostrados de la ficha **etiqueta** permite al usuario volver al orden original mostrado de los archivos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-139">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="c0f71-140">Puede volver a cualquier muestra y cambiar la etiquetación de los archivos de la evaluación y el conjunto de formación.</span><span class="sxs-lookup"><span data-stu-id="c0f71-140">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="c0f71-141">Los cambios se aplicarán al crear el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0f71-141">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="c0f71-142">Los archivos de Excel examinados en formato PDF deben tratarse igual que los archivos de Excel nativos al etiquetar archivos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-142">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="c0f71-143">Si tiene dudas sobre el etiquetado de relevancia de un archivo, consulte a un experto.</span><span class="sxs-lookup"><span data-stu-id="c0f71-143">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="c0f71-144">Un etiquetado incorrecto durante el aprendizaje de relevancia puede llevar a la pérdida de tiempo más adelante en el proceso y también puede tener un impacto negativo en la calidad de los resultados generales.</span><span class="sxs-lookup"><span data-stu-id="c0f71-144">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="c0f71-145">Las palabras clave que se definieron en las listas de palabras clave se mostrarán en colores para ayudar al usuario a identificar los archivos relevantes al etiquetar.</span><span class="sxs-lookup"><span data-stu-id="c0f71-145">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="c0f71-146">**Cálculo del lote**: los archivos que el experto etiquetó como R/NR recibirán una puntuación de 0 o 100.</span><span class="sxs-lookup"><span data-stu-id="c0f71-146">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="c0f71-147">Esto se aplica a las etiquetas realizadas antes del cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="c0f71-147">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="c0f71-148">Si el experto ha cambiado el problema a inActivo tras el cálculo del lote y ha seguido el etiquetado de este problema, los nuevos resultados etiquetados no serán 100/0, sino la puntuación original.</span><span class="sxs-lookup"><span data-stu-id="c0f71-148">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="c0f71-149">**Problemas y modo de muestreo**: los problemas suelen estar desactivados cuando se completa el trabajo en ellos (el entrenamiento de relevancia está estabilizado y se ha realizado el cálculo del lote), cuando se cancelan los problemas o cuando otro usuario está trabajando en los problemas.</span><span class="sxs-lookup"><span data-stu-id="c0f71-149">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="c0f71-150">Pasos de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="c0f71-150">Steps in Relevance training</span></span>

<span data-ttu-id="c0f71-151">En la **pestaña \> seguimiento de relevancia** , eDiscovery avanzado proporciona recomendaciones sobre cómo continuar en el procesamiento, con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-151">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="c0f71-152">Las implicaciones se describen a continuación cuando se recomienda cada uno de los pasos siguientes en el proceso de entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-152">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="c0f71-153">Etiquetado/continuar etiquetado: revisión de archivos y etiquetado de relevancia realizado por un experto para cada archivo y problema dentro de un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c0f71-153">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="c0f71-154">Implicación: debe etiquetarse una muestra existente.</span><span class="sxs-lookup"><span data-stu-id="c0f71-154">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="c0f71-155">Evaluación/continuar evaluación: permite la validación temprana de la relevancia de los casos y una vista preliminar de la relevancia de la población de archivos importada para el caso actual.</span><span class="sxs-lookup"><span data-stu-id="c0f71-155">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="c0f71-156">Implicación: se requiere o se recomienda más evaluación.</span><span class="sxs-lookup"><span data-stu-id="c0f71-156">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="c0f71-157">Aprendizaje/continuar aprendizaje: proceso durante el cual eDiscovery avanzado aprende del experto que etiqueta los ejemplos de archivos y adquiere la capacidad de identificar criterios de relevancia relacionados con cada problema en el contexto de cada caso.</span><span class="sxs-lookup"><span data-stu-id="c0f71-157">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="c0f71-158">Implicación: el problema necesita más formación; la siguiente muestra se debe crear y etiquetar.</span><span class="sxs-lookup"><span data-stu-id="c0f71-158">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="c0f71-159">Cálculo del lote: proceso de relevancia en el que eDiscovery avanzado toma los conocimientos adquiridos durante la fase de capacitación y los aplica a todo el llenado de archivos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-159">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="c0f71-160">Todos los archivos del grupo de archivos pertinentes se evalúan para su relevancia y se les asigna una puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-160">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="c0f71-161">Implicación: el problema se ha estabilizado y se puede realizar el cálculo del lote.</span><span class="sxs-lookup"><span data-stu-id="c0f71-161">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="c0f71-162">Puesta en marcha: la relevancia indica cuando un experto revisa y etiqueta una muestra de archivos seleccionados desde una carga de archivos adicional durante un escenario de cargas sucesivas.</span><span class="sxs-lookup"><span data-stu-id="c0f71-162">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="c0f71-163">Implicación: se ha agregado una nueva carga y se debe realizar la puesta en marcha para seguir trabajando.</span><span class="sxs-lookup"><span data-stu-id="c0f71-163">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="c0f71-164">Incoherencias de etiquetas: el proceso identifica, a través de un algoritmo de exhibición de documentos electrónicos avanzado, incoherencias en el proceso de etiquetado de archivos que pueden repercutir negativamente en el análisis.</span><span class="sxs-lookup"><span data-stu-id="c0f71-164">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="c0f71-165">Implicación: el ejemplo siguiente incluirá los archivos que se han etiquetado en ejemplos anteriores y se debe rehacer su etiquetado.</span><span class="sxs-lookup"><span data-stu-id="c0f71-165">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="c0f71-166">Actualizar clasificador: permite al usuario aplicar cambios de etiquetado o de inicialización.</span><span class="sxs-lookup"><span data-stu-id="c0f71-166">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="c0f71-167">Implicación: se pueden aplicar los cambios de etiquetado y de inicialización sin necesidad de ejecutar manualmente otro ejemplo de relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-167">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="c0f71-168">En espera: se ha completado el proceso de entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-168">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="c0f71-169">Implicación: en este momento no se requiere ningún entrenamiento sobre la relevancia.</span><span class="sxs-lookup"><span data-stu-id="c0f71-169">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="c0f71-170">Aunque la exhibición avanzada de documentos electrónicos le guía a través del proceso, con los pasos siguientes recomendados en diferentes etapas, también le permite navegar entre pestañas y páginas, y elegir opciones para abordar las situaciones que puedan ser pertinentes para su caso individual, problema o proceso de revisión de documentos.</span><span class="sxs-lookup"><span data-stu-id="c0f71-170">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="c0f71-171">Es posible aceptar o invalidar las opciones de procesamiento avanzado de paso posterior de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c0f71-171">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="c0f71-172">Si desea realizar un paso que no sea el siguiente paso recomendado, haga clic en el **siguiente paso** que aparece en la pantalla problema expandido en el cuadro de diálogo, haga clic en el botón **modificar** junto al paso siguiente y seleccione otra opción de paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0f71-172">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c0f71-173">Algunas opciones pueden permanecer deshabilitadas tras el desbloqueo porque no se pueden usar en ese punto del proceso.</span><span class="sxs-lookup"><span data-stu-id="c0f71-173">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="c0f71-174">Más información</span><span class="sxs-lookup"><span data-stu-id="c0f71-174">More information</span></span>

[<span data-ttu-id="c0f71-175">Descripción de la evaluación en relevancia</span><span class="sxs-lookup"><span data-stu-id="c0f71-175">Understanding Assessment in Relevance</span></span>](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c0f71-176">Etiquetado y evaluación</span><span class="sxs-lookup"><span data-stu-id="c0f71-176">Tagging and Assessment</span></span>](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c0f71-177">Aprendizaje de etiquetas y relevancia</span><span class="sxs-lookup"><span data-stu-id="c0f71-177">Tagging and Relevance training</span></span>](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c0f71-178">Seguimiento del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="c0f71-178">Tracking Relevance analysis</span></span>](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c0f71-179">Decisiones basadas en los resultados</span><span class="sxs-lookup"><span data-stu-id="c0f71-179">Deciding based on the results</span></span>](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c0f71-180">Prueba del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="c0f71-180">Testing Relevance analysis</span></span>](../test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="c0f71-181">Consulta dentro del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="c0f71-181">Query within working set</span></span>](working-set-search.md)
