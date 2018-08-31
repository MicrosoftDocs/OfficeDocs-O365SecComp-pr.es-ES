---
title: Configurar cargas para agregar archivos importados en eDiscovery avanzado de Office 365
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 'Revise los pasos para agregar los archivos importados a la última carga definido, o el lote, de los archivos antes de realizar la formación de relevancia de exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: 2c986578b969b671351930fd6939a90e3a821dc2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536719"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b0914-103">Configurar cargas para agregar archivos importados en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="b0914-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b0914-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b0914-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b0914-p102">En la exhibición de documentos electrónicos avanzada, una carga es un nuevo lote de archivos agregados a un caso. De forma predeterminada, se define una carga y todos los archivos importados se agregan a él. Antes de realizar la formación de relevancia, archivos importados deben agregarse a la carga.</span><span class="sxs-lookup"><span data-stu-id="b0914-p102">In Advanced eDiscovery, a load is a new batch of files added to a case. By default, one load is defined and all imported files are added to it. Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="b0914-109">Tenga en cuenta los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="b0914-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="b0914-p103">Los archivos nuevos se conocen como similar a los archivos anteriores cargados en la base de datos de mayúsculas y minúsculas, o la carga de archivos anterior era un conjunto aleatorio de la colección de archivos. En este caso, agregue los archivos importados a la carga del archivo actual.</span><span class="sxs-lookup"><span data-stu-id="b0914-p103">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection. In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="b0914-p104">Nuevos archivos son diferentes de los anteriores (por ejemplo, desde un origen diferente), o no tiene ningún conocimiento previo que son similares o diferentes a las cargas anteriores. En este escenario, agregar los archivos importados a una nueva carga de archivo. Exhibición de documentos electrónicos avanzada reconoce esto como un escenario de carga sucesivas, invoca un proceso de puesta al día, bloqueos de recursos de aprendizaje de la relevancia y cálculos de lote hasta que se complete ponerse al día, y la carga de nuevo es integrada y formación.</span><span class="sxs-lookup"><span data-stu-id="b0914-p104">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads. In this scenario, add the imported files to a new file load. Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="b0914-115">Adición de archivos importados a la carga actual</span><span class="sxs-lookup"><span data-stu-id="b0914-115">Adding imported files to the current load</span></span>

<span data-ttu-id="b0914-p105">Todos los archivos importados deben agregarse a una carga que va a procesar en la exhibición de documentos electrónicos avanzada. Los archivos importados se agregan a la última carga definida. Si importa archivos adicionales más adelante, también deben agregarse a la carga.</span><span class="sxs-lookup"><span data-stu-id="b0914-p105">All imported files must be added to a load to be processed in Advanced eDiscovery. Imported files are added to the last defined load. If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="b0914-119">En el **la relevancia \> el programa de instalación de la relevancia** ficha, seleccione **las cargas**.</span><span class="sxs-lookup"><span data-stu-id="b0914-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![Pestaña Cargas de configuración de relevancia](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="b0914-p106">**Archivos de inclusión**: seleccione una opción para los archivos que se incluirán. De forma predeterminada, la adición de archivos a la carga actual se basa en la población de "Todos los archivos".</span><span class="sxs-lookup"><span data-stu-id="b0914-p106">**Include files**: Select an option for files to include. By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b0914-p107">Cargar todos los archivos sacrificados disponibles en la relevancia. Si tiene previsto cargar sólo un subconjunto de los archivos disponibles, póngase en primer lugar en contacto con soporte técnico, como subconjuntos de carga puede afectar negativamente al aprendizaje de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="b0914-p107">Load all available culled files into Relevance. If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="b0914-125">En la **administración de cargas**, seleccione una carga.</span><span class="sxs-lookup"><span data-stu-id="b0914-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="b0914-p108">Haga clic en **Agregar archivos**. Los archivos se agregan a la carga y se muestra un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="b0914-p108">Click **Add files**. The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="b0914-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0914-128">Click **OK**.</span></span>
    
<span data-ttu-id="b0914-129">Ahora se pueden procesar los archivos en la exhibición de documentos electrónicos avanzada la relevancia para los archivos de recursos de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="b0914-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="b0914-130">Edición de un nombre de la carga dentro de un caso</span><span class="sxs-lookup"><span data-stu-id="b0914-130">Editing a load name within a case</span></span>

<span data-ttu-id="b0914-131">Si se cambia el nombre de la carga, se recomienda usar un nombre que es importante para el caso.</span><span class="sxs-lookup"><span data-stu-id="b0914-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="b0914-132">En el **la relevancia \> el programa de instalación de la relevancia** ficha, seleccione **las cargas**.</span><span class="sxs-lookup"><span data-stu-id="b0914-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="b0914-p109">En la lista de **administración de cargas** , seleccione una carga y haga clic en el icono **Editar** . Se muestra la ventana de carga de edición.</span><span class="sxs-lookup"><span data-stu-id="b0914-p109">From the **Loads management** list, select a load and click the **Edit** icon. The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="b0914-135">Escriba los cambios y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0914-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="b0914-136">Adición de archivos importados a una nueva carga</span><span class="sxs-lookup"><span data-stu-id="b0914-136">Adding imported files to a new load</span></span>

<span data-ttu-id="b0914-137">Después de iniciar el aprendizaje de la relevancia o realizar cálculos de lote, es posible que desee importar y procesar un conjunto de archivos adicional.</span><span class="sxs-lookup"><span data-stu-id="b0914-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="b0914-p110">Durante la puesta al día, puede crear, etiquetar y analizar el conjunto de ponerse al día. Exhibición de documentos electrónicos avanzada compara su evaluación de archivos pertinente y no pertinente en la carga de nuevo a los de cargas anteriores. En función de los resultados, le pedirá que tomar decisiones de ponerse al día, si es necesario y avanzada de exhibición de documentos electrónicos proporciona recomendaciones basadas en la información de la relevancia devengada.</span><span class="sxs-lookup"><span data-stu-id="b0914-p110">During Catch-up, you can create, tag, and analyze the Catch-up set. Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads. Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="b0914-141">Las sucesivas cargas y funcionalidad de puesta al día varían como sigue:</span><span class="sxs-lookup"><span data-stu-id="b0914-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="b0914-142">Cuando se importa un nuevo archivo de carga después de cálculo por lotes, exhibición de documentos electrónicos avanzada determina en qué medida se clasifican los archivos en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="b0914-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="b0914-143">Similar (homogéneo): no se requiere una ronda personalizada, nueva y de aprendizaje de la relevancia y el conocimiento acumulado de la carga anterior se puede aplicar "tal cual" a la carga de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b0914-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="b0914-144">DISTINCT (heterogéneo): se requiere una ronda personalizada, nueva y de aprendizaje de la relevancia y no se puede aplicar el conocimiento acumulado de la carga anterior.</span><span class="sxs-lookup"><span data-stu-id="b0914-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="b0914-145">Estos términos hacen referencia al nivel de similitud de archivos entre las cargas y no está dentro de las cargas.</span><span class="sxs-lookup"><span data-stu-id="b0914-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="b0914-p111">Al importar un nuevo archivo de carga durante el curso de la relevancia (antes de cálculo por lotes), permite ponerse al día continuar formación de relevancia en el conjunto de archivos united. Exhibición de documentos electrónicos avanzada no estimar si la carga de nuevo es similar a o distinta de la carga anterior. Simplemente recopila información sobre la carga de nuevo y habilita la relevancia de recursos de aprendizaje continuar en los nuevos y anteriores conjuntos de archivos.</span><span class="sxs-lookup"><span data-stu-id="b0914-p111">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set. Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load. It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="b0914-149">Cuando hay varios problemas en recursos de aprendizaje de la relevancia, así como problemas después de cálculo por lotes, el proceso de ponerse al día se lleva a cabo una vez para todos los problemas, y los resultados se calculan y se muestran para cada problema.</span><span class="sxs-lookup"><span data-stu-id="b0914-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b0914-p112">Puede variar el tamaño de la muestra de ponerse al día. Depende del tamaño de la carga de nuevo con respecto a las cargas anteriores y en el número de muestras completado antes de agregar la nueva carga. El ejemplo de ponerse al día normalmente es un conjunto de archivos de 200 a 2.000 desde la carga de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b0914-p112">The size of the Catch-up sample may vary. It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load. The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="b0914-p113">Ponerse al día detiene cualquier otras tareas y requiere revisión y etiquetado de archivo individuales. Por lo tanto, puede reducir una sobrecarga cuando se agregan nuevos archivos por lotes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="b0914-p113">Catch-up stops any other tasks and requires individual file tagging and review. Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="b0914-155">Adición de una nueva carga de archivo con puesta al día y sucesiva carga</span><span class="sxs-lookup"><span data-stu-id="b0914-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="b0914-156">En el **la relevancia \> el programa de instalación de la relevancia** ficha, seleccione **las cargas**.</span><span class="sxs-lookup"><span data-stu-id="b0914-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="b0914-p114">En **administración de cargas**, haga clic en el **+** icono para agregar una carga. Se muestra un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="b0914-p114">Under **Loads management**, click the **+** icon to add a load. A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="b0914-p115">Haga clic en **Sí** para continuar. Se muestra el cuadro de diálogo **Agregar nueva carga** .</span><span class="sxs-lookup"><span data-stu-id="b0914-p115">Click **Yes** to continue. The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b0914-161">Sólo se puede agregar una nueva carga si las acciones se realizaron a la carga anterior.</span><span class="sxs-lookup"><span data-stu-id="b0914-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="b0914-p116">En el cuadro de diálogo **Agregar nuevo de carga** , escriba información en **cargar el nombre** y **Descripción** y, a continuación, haga clic en **Aceptar**. Exhibición de documentos electrónicos avanzada agrega una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="b0914-p116">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**. Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="b0914-p117">Para importar el nuevo archivo de carga, haga clic en **Agregar archivos**. Todos los archivos nuevos se agregan a esta carga. Después de exhibición de documentos electrónicos avanzada importa los archivos, reconoce el escenario de cargas sucesivas e indica ponerse al día como el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="b0914-p117">To import the new load file, click **Add files**. All new files are added to this load. After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="b0914-167">Haga clic en **ponerse al día** en la parte inferior del cuadro de diálogo para ejecutar el escenario.</span><span class="sxs-lookup"><span data-stu-id="b0914-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="b0914-168">Un único conjunto de ponerse al día, que normalmente contiene los archivos de 200 a 2.000 de la carga de nuevo, se crea para que todos los problemas permitir que el etiquetado de archivo simultáneo.</span><span class="sxs-lookup"><span data-stu-id="b0914-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="b0914-169">Se proporcionan detalles acerca de si las cargas son similares o distintos, si avanzada exhibición de documentos electrónicos a combinar o divide automáticamente las cargas e información con respecto al procesamiento en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0914-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="b0914-p118">Puede, a continuación, los archivos de etiqueta y ejecutar una operación de calcular. El etiquetado permite la relevancia determinar si las cargas son similares o distintos y le permite continuar trabajando en el nuevo conjunto de archivos.</span><span class="sxs-lookup"><span data-stu-id="b0914-p118">You can then tag files and run a calculate operation. The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="b0914-172">Una vez que se revisa el conjunto ponerse al día, ver **relevancia \> pista** para los resultados de ponerse al día.</span><span class="sxs-lookup"><span data-stu-id="b0914-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="b0914-173">Si se ha agregado la nueva carga de archivo durante la formación de la relevancia (es decir, el problema no ha experimentado todavía cálculo por lotes), **aprendizaje continuar** es el siguiente paso, independientemente de los resultados de ponerse al día.</span><span class="sxs-lookup"><span data-stu-id="b0914-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="b0914-p119">Se procesan las cargas anteriores y nueva como una carga y continúa la formación de la relevancia en el conjunto de united. Ahora ha terminado con este procedimiento y puede continuar la formación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b0914-p119">The new and previous loads are processed as one load and Relevance training continues on the united set. You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="b0914-176">Si se ha agregado la nueva carga después del cálculo por lotes, continúe con los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="b0914-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="b0914-177">Cargas nuevo agregadas después del cálculo por lotes, de exhibición de documentos electrónicos avanzada determina si la carga de nuevo es similar a o distintos de cargas anteriores, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b0914-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="b0914-p120">Si se han encontrado cargas de forma similar: no hay recursos de aprendizaje adicionales de relevancia es necesario. El panel muestra el siguiente paso recomendado es ejecutar ** por lotes cálculo ** nuevamente para calcular las puntuaciones de relevancia para la carga de nuevo. Se han encontrado cargas de forma similar, por lo que se puede ejecutar el análisis de clasificador anterior en los nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="b0914-p120">If loads were found to be similar: No additional Relevance training is necessary. The dashboard shows the recommended next step is to run ** Batch calculation ** again to calculate Relevance scores for the new load. Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="b0914-p121">Si se han encontrado cargas distinto: formación más relevancia es necesario y el siguiente paso es decisión ponerse al día. Seleccione una decisión ponerse al día de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b0914-p121">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision. Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="b0914-p122">Si selecciona **Combinar cargas**, exhibición de documentos electrónicos avanzada combina cargas anteriores y nueva para el conjunto de recursos de aprendizaje. Aunque la primera carga salió a través de cálculo por lotes, se necesitan más recursos de formación. Continuar la formación anterior y nueva carga juntos. Cálculo por lotes, a continuación, se ejecutará de nuevo y se deben omitir las puntuaciones de cálculo por lotes anteriores. Elija esta selección cuando las puntuaciones de la relevancia para cargas existentes pueden volver a calcularse, por ejemplo, cuando no ha iniciado la revisión de las cargas de archivos existente.</span><span class="sxs-lookup"><span data-stu-id="b0914-p122">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set. Although the first load went through Batch calculation, more training is needed. Continue training new and previous loads together. Batch calculation will then run again and the previous Batch calculation scores should be ignored. Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="b0914-p123">Si selecciona **carga dividida**, continuar aprendizaje relevancia únicamente en la carga de nuevo. En esta instancia, las puntuaciones de cálculo de lote anteriores permanecerá tal y como está. Elija esta opción cuando las puntuaciones de la relevancia existentes para cargas existentes no se pueden volver a calcularse, por ejemplo, si ya ha iniciado la revisión de cargas existentes. Las puntuaciones de la relevancia se administran por separado desde este punto hacia adelante y no se pueden combinar.</span><span class="sxs-lookup"><span data-stu-id="b0914-p123">If you select **Split loads**, continue Relevance training only on the new load. In this instance, previous Batch calculation scores will remain as is. Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started. Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="b0914-192">Haga clic en **continuar formación**.</span><span class="sxs-lookup"><span data-stu-id="b0914-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b0914-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0914-193">See also</span></span>

[<span data-ttu-id="b0914-194">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="b0914-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b0914-195">Definición de problemas y la asignación de usuarios</span><span class="sxs-lookup"><span data-stu-id="b0914-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="b0914-196">Definición de resaltado de las palabras clave y avanzadas opciones</span><span class="sxs-lookup"><span data-stu-id="b0914-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

