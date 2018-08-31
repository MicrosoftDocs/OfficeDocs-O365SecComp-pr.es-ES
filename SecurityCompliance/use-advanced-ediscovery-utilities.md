---
title: Usar herramientas de eDiscovery avanzado de Office 365
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Obtenga información acerca de las utilidades de Office 365 avanzada exhibición de documentos electrónicos, incluidos el registro de casos, borrar los datos, errores del proceso, modificar y análisis de transparencia de la relevancia.  '
ms.openlocfilehash: a68c98dd353971fcaa13fdc6b8e12bcf00c2faf0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535679"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="ee34d-103">Usar herramientas de eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="ee34d-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="ee34d-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ee34d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ee34d-106">Las utilidades que se muestran y están disponibles en la exhibición de documentos electrónicos avanzada dependen de los roles de usuario y contexto.</span><span class="sxs-lookup"><span data-stu-id="ee34d-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="ee34d-107">Registro de casos</span><span class="sxs-lookup"><span data-stu-id="ee34d-107">Case log</span></span>

<span data-ttu-id="ee34d-p102">El registro de caso proporciona una lista detallada de las actividades de procesamiento de aplicación, que se puede usar para realizar un seguimiento, solución de problemas y para hacer frente a errores y advertencias. El registro se puede genera y almacena localmente en el host o el servidor o envían directamente a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p102">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings. The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="ee34d-p103">También se puede descargar el archivo de registro para el equipo del cliente. La opción de descarga del cliente puede habilitarse o deshabilitarse según la función de configuración y de usuario.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p103">The log file can also be downloaded to the client's computer. The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="ee34d-112">En la barra de menús, haga clic en el icono de **rueda dentada** .</span><span class="sxs-lookup"><span data-stu-id="ee34d-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ee34d-113">En el **configuración y utilidades \> utilidades** ficha, seleccione **registro de casos \> el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="ee34d-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="ee34d-114">Seleccione el **nivel de registro** de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ee34d-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="ee34d-p104">**Estándar**: incluye los datos de registro básico. Esta opción suele ser necesario para la supervisión y debe usarse a menos que se recomienda en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p104">**Standard**: Includes the basic log data. This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="ee34d-117">**Mínimo**: usados para los casos muy grandes y devuelve sólo los datos más recientes.</span><span class="sxs-lookup"><span data-stu-id="ee34d-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="ee34d-p105">Haga clic en **el registro de caso de ejecutar**. Se genera el registro y se muestra la ruta de acceso. En el panel de estado de la tarea, se muestra la información de progreso de tarea para la tarea actual y el apellido.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p105">Click **Run Case log**. The log is generated and path is displayed. The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="ee34d-121">Borrar datos</span><span class="sxs-lookup"><span data-stu-id="ee34d-121">Clear data</span></span>

<span data-ttu-id="ee34d-p106">Si es necesario eliminar o volver a inicializar los datos de los casos, se debe inicializar la instancia de base de datos. La utilidad de borrar datos elimina especificadas todas las entradas de la base de datos de mayúsculas y minúsculas, archivos de texto, carpeta mayúsculas y acumulados resultados. La función sólo puede realizarse por un administrador.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p106">If it is necessary to delete or reinitialize case data, the database instance must be initialized. The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results. The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ee34d-p107">Esta acción no es reversible y borrará todos los relevancia de etiquetado y análisis realizado por el experto. Guardar una copia de seguridad de datos, si es necesario. Use esta opción con cuidado extremo. Eliminación de archivos clasificados y etiquetados puede afectar a los resultados de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p107">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert. Save a backup of data, if necessary. Use this option with extreme care. Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="ee34d-129">En la barra de menús, haga clic en el icono de **rueda dentada** .</span><span class="sxs-lookup"><span data-stu-id="ee34d-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ee34d-130">En el **configuración y utilidades \> utilidades** ficha, seleccione **Borrar los datos \> el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="ee34d-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="ee34d-131">Seleccione una opción inicializar la información:</span><span class="sxs-lookup"><span data-stu-id="ee34d-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="ee34d-p108">**La relevancia**: elimina todo el trabajo realizado en la relevancia, incluida la definición de cargas y la asociación de archivos a las cargas. Elimina todos los ejemplos y etiquetado.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p108">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads. It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="ee34d-134">**Cerca de duplicados y subprocesos de correo electrónico**: elimina toda la información de análisis de cerca de duplicados y subprocesos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ee34d-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="ee34d-135">**Los temas**: elimina los datos relacionados con los temas.</span><span class="sxs-lookup"><span data-stu-id="ee34d-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="ee34d-136">**Exportar historial**: elimina la información del historial de lotes de exportación.</span><span class="sxs-lookup"><span data-stu-id="ee34d-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="ee34d-p109">Haga clic en **Borrar datos**. Los datos de escenario está desactivados. En el panel de **estado de la tarea** , se muestra la información de progreso de tarea para la tarea actual y el apellido.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p109">Click **Clear data**. The case data is cleared. The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="ee34d-140">Modificar la relevancia</span><span class="sxs-lookup"><span data-stu-id="ee34d-140">Modify Relevance</span></span>

<span data-ttu-id="ee34d-141">En esta sección se describe cómo omitir o revertir un ejemplo de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="ee34d-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="ee34d-142">En la barra de menús, haga clic en el icono de **rueda dentada** .</span><span class="sxs-lookup"><span data-stu-id="ee34d-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ee34d-143">En el **configuración y utilidades \> utilidades** , seleccione **Modificar relevancia**.</span><span class="sxs-lookup"><span data-stu-id="ee34d-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="ee34d-144">Seleccione una de las opciones:</span><span class="sxs-lookup"><span data-stu-id="ee34d-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="ee34d-p110">**Ejemplo de omisión actual - para el usuario actual**: Esto va a marcar, como **Omitir**, todos los archivos sin etiquetar en el ejemplo de mayúsculas y minúsculas open del usuario que ejecuta la utilidad. No se realizará el procesamiento de la relevancia en los archivos de etiquetado como **Omitir**.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p110">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility. Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="ee34d-p111">**Ejemplo actual de omitir: todos los ejemplos de abiertos**: Esto va a marcar, como **Omitir**, todos los archivos sin etiquetar en todos los ejemplos de todos los usuarios. No se recomienda esta opción si los usuarios actualmente son etiquetas temáticas ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p111">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users. This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="ee34d-p112">**Deshacer la última muestra**: el último completado la relevancia de ejemplo de entrenamiento se revertirá, independientemente de que sea antes o después del proceso de "Calcular". No se pueden deshacer los cambios de un ejemplo de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p112">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process. Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="ee34d-151">Haga clic en **Ejecutar** para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ee34d-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="ee34d-152">Análisis de transparencia</span><span class="sxs-lookup"><span data-stu-id="ee34d-152">Transparency analysis</span></span>

<span data-ttu-id="ee34d-p113">La utilidad de análisis de transparencia permite una vista detallada de los archivos y sus asignado puntuación de relevancia. El informe se puede usar como una comprobación de validez o para comparar la relevancia de un archivo definido por un revisor humano con respecto a la relevancia asignado por avanzada exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p113">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score. The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="ee34d-p114">Además de las puntuaciones de la relevancia, exhibición de documentos electrónicos avanzada calcula y asigna pesos de palabra clave que tener en cuenta el contexto de la palabra clave. Se puede asignar la misma palabra en un archivo de pesos diferentes, según el contexto y la ubicación. Cada palabra clave se marca con una escala de aumento de la intensidad de color desde amarillo a naranja oscuro y debido a distintos tonos de gris. Codificación de color se usa para indicar visualmente la palabra s relativa contribución positivo o negativo a la puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p114">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context. The same word in a file can be assigned different weights, depending on context and location. Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray. Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="ee34d-159">En un escenario de casos de varios problemas, se puede generar un informe de análisis de transparencia para cada problema.</span><span class="sxs-lookup"><span data-stu-id="ee34d-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="ee34d-160">En la barra de menús, haga clic en el icono de **rueda dentada** .</span><span class="sxs-lookup"><span data-stu-id="ee34d-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ee34d-161">En el **configuración y utilidades \> utilidades** ficha, seleccione **análisis de transparencia \> el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="ee34d-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="ee34d-162">En ** identificador de archivo **, escriba el identificador de archivo del archivo para procesar.</span><span class="sxs-lookup"><span data-stu-id="ee34d-162">In ** File ID **, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="ee34d-163">En la lista de **problemas** , seleccione el problema pertinente.</span><span class="sxs-lookup"><span data-stu-id="ee34d-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="ee34d-p115">Haga clic en **análisis de transparencia**. Una vez finalizada, se muestra el informe de análisis de transparencia para el archivo, que muestra cómo los colores de la palabra clave marcadas correlacionarse con la puntuación de relevancia general.</span><span class="sxs-lookup"><span data-stu-id="ee34d-p115">Click **Transparency analysis**. Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ee34d-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee34d-166">See also</span></span>

[<span data-ttu-id="ee34d-167">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="ee34d-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ee34d-168">Definir la configuración de mayúsculas y minúsculas e inquilino</span><span class="sxs-lookup"><span data-stu-id="ee34d-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

