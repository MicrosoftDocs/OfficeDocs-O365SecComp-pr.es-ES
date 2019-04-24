---
title: Uso de utilidades avanzadas de exhibición de documentos electrónicos de Office 365
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Obtenga información sobre las utilidades de la exhibición avanzada de documentos electrónicos de Office 365, incluidos el registro de casos, datos claros, errores de proceso, modificación de relevancia y análisis de transparencia.  '
ms.openlocfilehash: bd100883804b300e77abcc8a2224cf1a59b53475
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265362"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="725b2-103">Uso de utilidades avanzadas de exhibición de documentos electrónicos de Office 365</span><span class="sxs-lookup"><span data-stu-id="725b2-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="725b2-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="725b2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="725b2-106">Las utilidades que se muestran y están disponibles en eDiscovery avanzado dependen de roles de usuario y contexto.</span><span class="sxs-lookup"><span data-stu-id="725b2-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="725b2-107">Registro de casos</span><span class="sxs-lookup"><span data-stu-id="725b2-107">Case log</span></span>

<span data-ttu-id="725b2-108">El registro de casos proporciona una lista detallada de las actividades de procesamiento de aplicaciones, que se pueden usar para realizar un seguimiento, solucionar problemas y resolver errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="725b2-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="725b2-109">El registro puede generarse y almacenarse de forma local en el host o servidor, o bien enviarse directamente a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="725b2-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="725b2-110">El archivo de registro también se puede descargar en el equipo del cliente.</span><span class="sxs-lookup"><span data-stu-id="725b2-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="725b2-111">La opción de descarga del cliente puede estar habilitada o deshabilitada según la configuración y el rol de usuario.</span><span class="sxs-lookup"><span data-stu-id="725b2-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="725b2-112">En la barra de menús, haga clic en el icono de **cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="725b2-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="725b2-113">En la pestaña **utilidades de \> configuración y utilidades** , seleccione **configuración \> del registro de casos**.</span><span class="sxs-lookup"><span data-stu-id="725b2-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="725b2-114">Seleccione el **nivel de registro** de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="725b2-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="725b2-115">**Standard**: incluye los datos de registro básicos.</span><span class="sxs-lookup"><span data-stu-id="725b2-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="725b2-116">Esta opción suele ser necesaria para la supervisión y se debe usar a menos que se recomiende lo contrario.</span><span class="sxs-lookup"><span data-stu-id="725b2-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="725b2-117">**Minimal**: se usa para casos muy grandes y solo devuelve los datos más recientes.</span><span class="sxs-lookup"><span data-stu-id="725b2-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="725b2-118">Haga clic en **Ejecutar registro de casos**.</span><span class="sxs-lookup"><span data-stu-id="725b2-118">Click **Run Case log**.</span></span> <span data-ttu-id="725b2-119">Se genera el registro y se muestra la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="725b2-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="725b2-120">La información de progreso de la tarea para la tarea actual y la última se muestra en el panel estado de tarea.</span><span class="sxs-lookup"><span data-stu-id="725b2-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="725b2-121">Borrar datos</span><span class="sxs-lookup"><span data-stu-id="725b2-121">Clear data</span></span>

<span data-ttu-id="725b2-122">Si es necesario eliminar o reinicializar los datos de las mayúsculas y minúsculas, se debe inicializar la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="725b2-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="725b2-123">La utilidad Clear Data elimina todas las entradas especificadas de la base de datos de casos, los archivos de texto, la carpeta Case y los resultados acumulados.</span><span class="sxs-lookup"><span data-stu-id="725b2-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="725b2-124">La función solo puede ser realizada por un administrador.</span><span class="sxs-lookup"><span data-stu-id="725b2-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="725b2-125">Esta acción no es reversible y eliminará todo el etiquetado y el análisis de relevancia que realiza el experto.</span><span class="sxs-lookup"><span data-stu-id="725b2-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="725b2-126">Guarde una copia de seguridad de los datos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="725b2-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="725b2-127">Use esta opción con sumo cuidado.</span><span class="sxs-lookup"><span data-stu-id="725b2-127">Use this option with extreme care.</span></span> <span data-ttu-id="725b2-128">La eliminación de archivos etiquetados y clasificados puede afectar a los resultados de relevancia.</span><span class="sxs-lookup"><span data-stu-id="725b2-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="725b2-129">En la barra de menús, haga clic en el icono de **cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="725b2-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="725b2-130">En la ficha **Opciones de \> configuración y utilidades** , seleccione **Borrar \> configuración de datos**.</span><span class="sxs-lookup"><span data-stu-id="725b2-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="725b2-131">Seleccione una opción para la información que se va a inicializar:</span><span class="sxs-lookup"><span data-stu-id="725b2-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="725b2-132">**Relevancia**: elimina todo el trabajo realizado en importancia, incluida la definición de cargas y la Asociación de archivos que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="725b2-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="725b2-133">Elimina todas las muestras y el etiquetado.</span><span class="sxs-lookup"><span data-stu-id="725b2-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="725b2-134">**Near-duplicados y subprocesos de correo electrónico**: elimina toda la información de análisis de los subprocesos de correo electrónico casi duplicados.</span><span class="sxs-lookup"><span data-stu-id="725b2-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="725b2-135">**Themes**: elimina los datos relacionados con los temas.</span><span class="sxs-lookup"><span data-stu-id="725b2-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="725b2-136">**Exportar historial**: elimina la información del historial de los lotes de exportación.</span><span class="sxs-lookup"><span data-stu-id="725b2-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="725b2-137">Haga clic en **Borrar datos**.</span><span class="sxs-lookup"><span data-stu-id="725b2-137">Click **Clear data**.</span></span> <span data-ttu-id="725b2-138">Se borran los datos de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="725b2-138">The case data is cleared.</span></span> <span data-ttu-id="725b2-139">La información de progreso de la tarea para la tarea actual y la última se muestra en el panel **Estado de tarea** .</span><span class="sxs-lookup"><span data-stu-id="725b2-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="725b2-140">Modificar relevancia</span><span class="sxs-lookup"><span data-stu-id="725b2-140">Modify Relevance</span></span>

<span data-ttu-id="725b2-141">En esta sección se describe cómo omitir o revertir un ejemplo de relevancia.</span><span class="sxs-lookup"><span data-stu-id="725b2-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="725b2-142">En la barra de menús, haga clic en el icono de **cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="725b2-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="725b2-143">En la ficha **utilidades de \> configuración y utilidades** , seleccione **modificar relevancia**.</span><span class="sxs-lookup"><span data-stu-id="725b2-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="725b2-144">Seleccione una de las opciones:</span><span class="sxs-lookup"><span data-stu-id="725b2-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="725b2-145">**Omitir el ejemplo actual: para el usuario actual**: Esto hará \*\*\*\* que se etiqueten todos los archivos sin etiquetar en el ejemplo de caso abierto del usuario que ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="725b2-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="725b2-146">El procesamiento de relevancia no se realizará en los archivos etiquetados como **SKIP**.</span><span class="sxs-lookup"><span data-stu-id="725b2-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="725b2-147">**Omitir el ejemplo actual: todas las muestras abiertas**: Esto hará \*\*\*\* que se etiqueten todos los archivos sin etiquetar en todas las muestras abiertas para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="725b2-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="725b2-148">Esta opción no se recomienda si los usuarios están etiquetando ejemplos en este momento.</span><span class="sxs-lookup"><span data-stu-id="725b2-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="725b2-149">**Revertir último ejemplo**: se revertirá el último ejemplo de entrenamiento de relevancia completado, independientemente de si es anterior o posterior al proceso de "cálculo".</span><span class="sxs-lookup"><span data-stu-id="725b2-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="725b2-150">No se permite reVertir una muestra de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="725b2-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="725b2-151">Haga clic en **Ejecutar** para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="725b2-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="725b2-152">Análisis de transparencia</span><span class="sxs-lookup"><span data-stu-id="725b2-152">Transparency analysis</span></span>

<span data-ttu-id="725b2-153">La utilidad de análisis de transparencia permite una vista detallada de los archivos y su puntuación de relevancia asignada.</span><span class="sxs-lookup"><span data-stu-id="725b2-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="725b2-154">El informe se puede usar como comprobación de validez o para comparar la relevancia de un archivo definido por un revisor humano en comparación con la relevancia asignada por la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="725b2-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="725b2-155">Además de los resultados de relevancia, eDiscovery avanzado calcula y asigna pesos de palabra clave que consideran el contexto de la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="725b2-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="725b2-156">Se puede asignar a la misma palabra en un archivo diferentes pesos, según el contexto y la ubicación.</span><span class="sxs-lookup"><span data-stu-id="725b2-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="725b2-157">Cada palabra clave se marca con una escala de color cada vez mayor que va de amarillo a naranja oscuro y a distintos tonos de gris.</span><span class="sxs-lookup"><span data-stu-id="725b2-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="725b2-158">La codificación en colores se usa para indicar visualmente la contribución positiva o negativa de la palabra relativa a la puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="725b2-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="725b2-159">En un escenario de casos de varios problemas, se puede generar un informe de análisis de transparencia para cada problema.</span><span class="sxs-lookup"><span data-stu-id="725b2-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="725b2-160">En la barra de menús, haga clic en el icono de **cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="725b2-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="725b2-161">En la ficha **utilidades de \> configuración y utilidades** , seleccione **configuración \> de análisis de transparencia**.</span><span class="sxs-lookup"><span data-stu-id="725b2-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="725b2-162">En \* \* ID de archivo \* \*, escriba el identificador de archivo del archivo que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="725b2-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="725b2-163">En la lista de **problemas** , seleccione el problema pertinente.</span><span class="sxs-lookup"><span data-stu-id="725b2-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="725b2-164">Haga clic en **análisis de transparencia**.</span><span class="sxs-lookup"><span data-stu-id="725b2-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="725b2-165">Una vez finalizado, se muestra el informe de análisis de transparencia del archivo, que muestra cómo los colores de palabra clave marcados correlacionan con la puntuación de relevancia general.</span><span class="sxs-lookup"><span data-stu-id="725b2-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="725b2-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="725b2-166">See also</span></span>

[<span data-ttu-id="725b2-167">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="725b2-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="725b2-168">Definir la configuración de casos y espacios empresariales</span><span class="sxs-lookup"><span data-stu-id="725b2-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

