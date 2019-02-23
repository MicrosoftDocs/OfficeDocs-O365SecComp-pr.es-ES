---
title: Ver resultados del módulo de proceso en eDiscovery avanzado de Office 365
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'Obtenga información sobre cómo encontrar los resultados de un módulo de proceso en la exhibición avanzada de documentos de Office 365, incluido el estado de la tarea y el resumen del proceso.  '
ms.openlocfilehash: 0393cde78e559036d92b9ac48245afafc974a8b2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218060"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="5e4a1-103">Ver resultados del módulo de proceso en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e4a1-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="5e4a1-104">Una vez iniciado el **proceso** de **preparación** \> , puede ver el progreso y los resultados.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5e4a1-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="5e4a1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="5e4a1-107">Procesar el estado de la tarea</span><span class="sxs-lookup"><span data-stu-id="5e4a1-107">Process task status</span></span>

<span data-ttu-id="5e4a1-108">En **preparar** \> los **resultados**del **proceso** \> , la página muestra el estado actual (si el proceso se está ejecutando actualmente) o el estado de la tarea de estado de proceso último como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![Estado de la tarea del módulo de proceso](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="5e4a1-110">Las tareas mostradas pueden variar en función de las opciones de proceso seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="5e4a1-111">**Inventory**: Advanced eDiscovery recorre en iteración todos los archivos seleccionados para procesar y realiza la recopilación de datos básica.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="5e4a1-112">**Calcular firmas**: calcula las firmas digitales MD5.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="5e4a1-p102">**Extracción de compuestos**: extrae archivos internos o contenidos de forma recursiva de archivos compuestos (por ejemplo, PST, zip, MSG). Los archivos exTraídos se almacenan en la carpeta Case del caso.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-p102">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG). Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="5e4a1-115">**Sincronización de base de datos**: proceso de base de datos interno.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="5e4a1-p103">**Copia de archivos**: copia los archivos de proceso. Esta tarea se muestra siempre, incluso cuando está seleccionada la opción copias avanzadas de archivos.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-p103">**File copy**: Copies Process files. This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="5e4a1-p104">**Extracción de texto**: cuando hay archivos nativos, eDiscovery avanzado extrae texto de estos archivos mediante dtSearch. El texto extraído de estos archivos se almacena como archivos de texto en la carpeta Case.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-p104">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch. The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="5e4a1-120">**Actualización**de metadatos: procesa los metadatos cargados.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="5e4a1-121">**Finalización**: procesamiento interno que finaliza los datos de los archivos de mayúsculas y minúsculas cargados (por ejemplo, identificar los archivos de errores y correctos).</span><span class="sxs-lookup"><span data-stu-id="5e4a1-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="5e4a1-p105">Estado de la tarea: se muestra después de la finalización de la tarea. Mientras se ejecutan las tareas, se muestra la duración de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-p105">Task status: Displayed after task completion. While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e4a1-124">Las tareas completadas también pueden incluir los totales de los archivos que han completado el procesamiento o los archivos con errores.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="5e4a1-p106">"Cancelar" proporciona una opción de reversión para detener la ejecución del proceso y, a continuación, volver a la población de datos anterior o a los datos procesados guardados. Rollback borra todos los datos procesados. Si no desea que se pierdan los datos procesados (por ejemplo, si planea volver a cargar estos archivos), seleccione la opción "Cancelar" en esta ventana para elegir no revertirlos.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-p106">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data. Rollback clears all processed data. If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="5e4a1-128">Resumen del proceso</span><span class="sxs-lookup"><span data-stu-id="5e4a1-128">Process summary</span></span>

<span data-ttu-id="5e4a1-129">En preparar \> Resumen \> de \> proceso de resultados del proceso, se muestra un desglose de los resultados de los archivos cargados de acuerdo con resultados de errores y procesamiento de archivos correctos.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="5e4a1-130">Los paneles presentan una representación gráfica de las estadísticas del archivo importado, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5e4a1-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="5e4a1-131">**Resumen de proceso acumula**d: todos los archivos en el caso.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="5e4a1-132">**Resumen del proceso en último lugar**: archivos cargados desde la última sesión o acción.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="5e4a1-133">**Últimas familias**: información de la familia en el caso (en caso de que haya).</span><span class="sxs-lookup"><span data-stu-id="5e4a1-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="5e4a1-134">Si \*\*\*\* se agregaron archivos de inicialización, el número de archivos de inicialización se enumera por problema que se definió para los archivos.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="5e4a1-135">Si se produce un \*\*\*\* error en la marcación de los archivos de inicialización, también se indica.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="5e4a1-136">Si se agregaron archivos **etiquetaDos previamente** , el número de archivos predefinidos se enumera por problema que se definió para los archivos.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="5e4a1-137">Si se produce un error **en** la marcación de archivos predefinidos, también se indica.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![Resumen del módulo de proceso](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="5e4a1-139">Gráficos acumulativos y último resumen del proceso</span><span class="sxs-lookup"><span data-stu-id="5e4a1-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="5e4a1-140">La barra izquierda incluye el origen y los archivos extraídos: que son todos los archivos encontrados.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="5e4a1-141">La barra derecha, procesada, incluye:</span><span class="sxs-lookup"><span data-stu-id="5e4a1-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="5e4a1-142">Archivos con errores de carga</span><span class="sxs-lookup"><span data-stu-id="5e4a1-142">Files with load errors</span></span>
    
- <span data-ttu-id="5e4a1-143">Archivos cargados correctamente, que pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="5e4a1-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="5e4a1-144">**Existente**: archivos que se cargaron antes y que ahora se cargan de nuevo (incluidos duplicados).</span><span class="sxs-lookup"><span data-stu-id="5e4a1-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="5e4a1-145">**Text**: archivos únicos con texto.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="5e4a1-146">**No texto**: archivos de texto vacíos, archivos de texto nativos vacíos, archivos nativos que no son de texto.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="5e4a1-147">\*\*\*\* S duplicados: archivos duplicados con texto.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="5e4a1-148">Errores del último proceso</span><span class="sxs-lookup"><span data-stu-id="5e4a1-148">Last process errors</span></span>

<span data-ttu-id="5e4a1-149">En la \> sección \> preparar \> los resultados del proceso último error, se muestran detalles de los errores de la última sesión o acción realizada.</span><span class="sxs-lookup"><span data-stu-id="5e4a1-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![Errores del módulo de proceso](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="5e4a1-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e4a1-151">See also</span></span>

[<span data-ttu-id="5e4a1-152">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e4a1-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="5e4a1-153">Ejecutar el módulo de proceso y cargar datos</span><span class="sxs-lookup"><span data-stu-id="5e4a1-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

