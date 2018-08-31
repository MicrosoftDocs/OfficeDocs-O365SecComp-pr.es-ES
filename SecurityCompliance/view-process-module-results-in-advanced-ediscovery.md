---
title: Ver resultados del módulo de proceso en eDiscovery avanzado de Office 365
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'Obtenga información sobre cómo encontrar los resultados de un módulo de un proceso que se ejecutan en Office 365 avanzada exhibición de documentos electrónicos, incluidos el estado de la tarea y el proceso de resumen.  '
ms.openlocfilehash: 01093b0230aaf78ab7ccf1235f0874a0b69aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535611"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ab8a6-103">Ver resultados del módulo de proceso en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="ab8a6-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="ab8a6-104">Después de **Preparar** \> se inicia el **proceso** , puede ver el progreso y los resultados.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ab8a6-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ab8a6-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="ab8a6-107">Estado de la tarea de proceso</span><span class="sxs-lookup"><span data-stu-id="ab8a6-107">Process task status</span></span>

<span data-ttu-id="ab8a6-108">En **Prepare** \> **proceso** \> **los resultados**, la página muestra el estado actual (si el proceso se está ejecutando actualmente) o el último estado de tarea de estado de proceso tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![Estado de la tarea del módulo de proceso](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="ab8a6-110">Las tareas que se muestra pueden variar según las opciones de proceso seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="ab8a6-111">**Inventario**: exhibición de documentos electrónicos avanzada recorre en iteración todos los archivos seleccionados para el proceso y realiza la recolección de datos básica.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="ab8a6-112">**Las firmas de calcular**: calcula las firmas digitales de MD5.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="ab8a6-p102">**Extracción de compuestos**: extractos internos o contiene los archivos de forma recursiva de archivos compuestos (por ejemplo, PST, ZIP, MSG). Los archivos extraídos se almacenan en la carpeta de mayúsculas y minúsculas de las mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-p102">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG). Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="ab8a6-115">**Base de datos de sincronización**: proceso de base de datos interna.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="ab8a6-p103">**Copia de archivos**: proceso de copias de archivos. Siempre se muestra esta tarea, incluso cuando se selecciona la opción avanzada de los archivos de copia.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-p103">**File copy**: Copies Process files. This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="ab8a6-p104">**Extracción de texto**: cuando hay archivos nativos, exhibición de documentos electrónicos avanzada extrae el texto de estos archivos mediante DTSearch. El texto extraído de estos archivos se almacena como archivos de texto en la carpeta de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-p104">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch. The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="ab8a6-120">**Actualizar los metadatos**: procesa los metadatos cargados.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="ab8a6-121">**Finalizing**: procesamiento interno que finaliza los datos de carga archivos de casos (por ejemplo, identificar los archivos de error y éxito).</span><span class="sxs-lookup"><span data-stu-id="ab8a6-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="ab8a6-p105">Estado de la tarea: muestra una vez finalizada la tarea. Mientras se ejecutan las tareas, se muestra la duración de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-p105">Task status: Displayed after task completion. While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab8a6-124">Las tareas completadas también pueden incluir los totales de los archivos que se completó el procesamiento o con errores.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ab8a6-p106">"Cancelar" proporciona una opción de reversión para detener la ejecución del proceso y, a continuación, revertir a la población de datos anterior o guarda datos procesados. Reversión borra procesados todos los datos. Si no desea que los datos procesados se pierdan (por ejemplo, plan para volver a cargar estos archivos), seleccione la "Cancelar" opción en esta ventana Elegir no revertir.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-p106">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data. Rollback clears all processed data. If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="ab8a6-128">Resumen del proceso</span><span class="sxs-lookup"><span data-stu-id="ab8a6-128">Process summary</span></span>

<span data-ttu-id="ab8a6-129">En Prepare \> proceso \> los resultados \> proceso de resumen, se muestra un desglose de los resultados del archivo cargado según los resultados de procesamiento y error correcta de los archivos.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="ab8a6-130">Los paneles de presentan una representación gráfica de las estadísticas de archivo importado, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ab8a6-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="ab8a6-131">**Proceso de resumen se acumulan**d: en el caso de todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="ab8a6-132">**Resumen del proceso por última vez**: los archivos que se cargan desde la última sesión o acción.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="ab8a6-133">**Familias por última vez**: información de la familia en el caso (si hay alguno).</span><span class="sxs-lookup"><span data-stu-id="ab8a6-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="ab8a6-134">Si se han agregado los archivos de **inicialización** , aparece el número de archivos de inicialización por el problema que se ha definido para los archivos.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="ab8a6-135">Si el marcado de los archivos de **inicialización** no se pudo, que también se ha indicado.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="ab8a6-136">Si se agregaron archivos **previamente con etiqueta** , aparece el número de archivos con previa a la etiqueta por el problema que se ha definido para los archivos.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="ab8a6-137">Si el marcado de los archivos **etiquetados previamente** no se pudo, que también se ha indicado.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![Resumen del módulo de proceso](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="ab8a6-139">Resumen del proceso de acumulado y por última vez los gráficos</span><span class="sxs-lookup"><span data-stu-id="ab8a6-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="ab8a6-140">La barra izquierda incluye origen + archivos extraídos: que es todos los archivos que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="ab8a6-141">El derecho de la barra, procesada, incluye:</span><span class="sxs-lookup"><span data-stu-id="ab8a6-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="ab8a6-142">Archivos con errores de carga</span><span class="sxs-lookup"><span data-stu-id="ab8a6-142">Files with load errors</span></span>
    
- <span data-ttu-id="ab8a6-143">Archivos cargados correctamente, que pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="ab8a6-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="ab8a6-144">**Existente**: los archivos que se cargaron antes y ahora se cargan nuevo (incluidos los duplicados).</span><span class="sxs-lookup"><span data-stu-id="ab8a6-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="ab8a6-145">**Texto**: archivos únicos con texto.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="ab8a6-146">**No texto**: vaciar archivos de texto, archivos de texto nativa vacía, los archivos que no son de texto nativos.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="ab8a6-147">**Duplicar**s: duplicado archivos con texto.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="ab8a6-148">Última errores de proceso</span><span class="sxs-lookup"><span data-stu-id="ab8a6-148">Last process errors</span></span>

<span data-ttu-id="ab8a6-149">En Prepare \> proceso \> los resultados \> se muestran errores de proceso última, detalles de los errores en la última sesión o acción realizada.</span><span class="sxs-lookup"><span data-stu-id="ab8a6-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![Errores del módulo de proceso](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="ab8a6-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab8a6-151">See also</span></span>

[<span data-ttu-id="ab8a6-152">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="ab8a6-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ab8a6-153">Ejecute el módulo de proceso y carga de datos</span><span class="sxs-lookup"><span data-stu-id="ab8a6-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

