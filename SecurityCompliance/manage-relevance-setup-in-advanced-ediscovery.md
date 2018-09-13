---
title: Administrar la configuración de relevancia en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: 'Lea las recomendaciones para configurar el entrenamiento de Relevancia en eDiscovery avanzado de Office 365 con el fin de puntuar archivos según su relevancia y generar resultados de análisis.  '
ms.openlocfilehash: b2f1f848d14bdf77444c2026cbc675042c792542
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535787"
---
# <a name="manage-relevance-setup-in-office-365-advanced-ediscovery"></a><span data-ttu-id="f14da-103">Administrar la configuración de relevancia en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="f14da-103">Manage Relevance setup in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="f14da-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f14da-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="f14da-p102">La tecnología Relevancia de eDiscovery avanzado usa software guiado por expertos para puntuar archivos según su relevancia. Relevancia de eDiscovery avanzado puede usarse para la evaluación temprana de casos, la selección y la revisión de archivos de muestra.</span><span class="sxs-lookup"><span data-stu-id="f14da-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="f14da-p103">En eDiscovery avanzado, se incluyen componentes para el entrenamiento de Relevancia y para el etiquetado de archivos relevantes para un caso. eDiscovery avanzado aprende de las muestras entrenadas de archivos relevantes y no relevantes para asignar puntuaciones de relevancia a cada archivo y, además, genera resultados de análisis que pueden usarse durante y después del proceso de revisión de archivos.</span><span class="sxs-lookup"><span data-stu-id="f14da-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="f14da-110">Directrices para configurar el entrenamiento de Relevancia</span><span class="sxs-lookup"><span data-stu-id="f14da-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="f14da-p104">En eDiscovery avanzado, en la ventana **Casos**, seleccione un caso y haga clic en **Ir al caso**. Haga clic en **Relevancia** \> **Configuración de relevancia**. Siga las recomendaciones para configurar Relevancia.</span><span class="sxs-lookup"><span data-stu-id="f14da-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevanace setup**. Follow these recommended guidelines to setup Relevance.</span></span> 
  
- <span data-ttu-id="f14da-114">**Etiquetado**: la efectividad del proceso de entrenamiento iterativo de Relevancia depende de la capacidad del experto de etiquetar archivos de muestra con precisión y coherencia.</span><span class="sxs-lookup"><span data-stu-id="f14da-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>
    
- <span data-ttu-id="f14da-115">**Problemas de casos**:</span><span class="sxs-lookup"><span data-stu-id="f14da-115">**Case issues**:</span></span> 
    
  - <span data-ttu-id="f14da-p105">Para cada problema, use el mismo experto en todo el proceso de entrenamiento de Relevancia. No se permite el etiquetado simultánea del mismo problema por varios expertos.</span><span class="sxs-lookup"><span data-stu-id="f14da-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
    
  - <span data-ttu-id="f14da-118">Determine si cada grupo de archivos es relevante solo para un problema específico.</span><span class="sxs-lookup"><span data-stu-id="f14da-118">Determine if each group of files is pertinent only to a specific issue.</span></span> 
    
  - <span data-ttu-id="f14da-p106">Si un problema se define de forma demasiado amplia, es posible que eDiscovery avanzado muestre demasiados archivos que no sean relevantes en realidad. Si un problema se define de forma demasiado restringida, es posible que el proceso de entrenamiento de Relevancia tarde más tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="f14da-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are actually not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 
    
  - <span data-ttu-id="f14da-121">Durante cada ciclo de entrenamiento de Relevancia, eDiscovery avanzado se centra en un único problema activo y, en consecuencia, muestra los resultados de muestra provisionales.</span><span class="sxs-lookup"><span data-stu-id="f14da-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>
    
  - <span data-ttu-id="f14da-p107">En un escenario de varios problemas, el modo Muestreo permite seleccionar los archivos que se incluirán en el procesamiento. Los problemas definidos como “Desactivados” no se procesarán hasta que se cambie el modo de Muestreo. Un problema puede estar “inactivo” o “activo” para solo un experto.</span><span class="sxs-lookup"><span data-stu-id="f14da-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>
    
  -  <span data-ttu-id="f14da-p108">eDiscovery avanzado puede usarse para generar archivos de privilegios de candidatos. Configure un problema separado por privilegio. Si es posible, entrene y seleccione primero para relevancia y, después, realice el entrenamiento para privilegios solo en el conjunto seleccionado (vuelva a cargar el conjunto seleccionado como un caso separado).</span><span class="sxs-lookup"><span data-stu-id="f14da-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 
    
  - <span data-ttu-id="f14da-p109">El cálculo por lotes solo puede realizarse cuando no haya muestras abiertas (al hacer clic en Cálculo por lotes, se mostrará una lista de usuarios con muestras abiertas). Para “cerrar” las muestras de otros usuarios (esto solo puede realizarse si los usuarios no están etiquetando esas muestras), un administrador puede usar la utilidad “Modificar relevancia” con la opción “Muestra de todos los usuarios”.</span><span class="sxs-lookup"><span data-stu-id="f14da-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>
    
- <span data-ttu-id="f14da-p110">**Metadatos**: eDiscovery avanzado se centra en el contenido. No tiene en cuenta los metadatos como parte de los criterios de relevancia.</span><span class="sxs-lookup"><span data-stu-id="f14da-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span> 
    
- <span data-ttu-id="f14da-132">**Riqueza**: si la riqueza de un problema es inferior al 3 % después de la evaluación, puede inicializar el entrenamiento de Relevancia con archivos conocidos que sean relevantes y no relevantes.</span><span class="sxs-lookup"><span data-stu-id="f14da-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>
    
- <span data-ttu-id="f14da-p111">**Tamaño de archivo**: los archivos de gran tamaño (con más de 5 242 880 caracteres de texto extraído) se omiten en Relevancia. Los archivos no se incluyen en el proceso de entrenamiento de Relevancia y no reciben una puntuación de Relevancia después del cálculo por lotes. Los archivos con un tamaño superior a 5 MB se pueden incluir en el conjunto de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f14da-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5MB can be included in the Assessment set.</span></span>
    
## <a name="setting-up-case-issues"></a><span data-ttu-id="f14da-136">Configurar problemas de casos</span><span class="sxs-lookup"><span data-stu-id="f14da-136">Setting up case issues</span></span>

<span data-ttu-id="f14da-137">Los parámetros descritos en esta sección están disponibles en eDiscovery avanzado **Relevancia** \> **Configuración de Relevancia**.</span><span class="sxs-lookup"><span data-stu-id="f14da-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span> 
  
- <span data-ttu-id="f14da-138">Los problemas tienen que asignarse a un usuario que entrenará los archivos.</span><span class="sxs-lookup"><span data-stu-id="f14da-138">Issues must be assigned to a user who will train the files.</span></span>
    
- <span data-ttu-id="f14da-139">Después, los archivos importados tienen que agregarse a la carga que vaya a procesarse.</span><span class="sxs-lookup"><span data-stu-id="f14da-139">Imported files must then be added to the load being processed.</span></span>
    
- <span data-ttu-id="f14da-140">Defina y organice problemas cuidadosamente, ya que esto puede afectar a los resultados de entrenamiento de Relevancia.</span><span class="sxs-lookup"><span data-stu-id="f14da-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>
    
<span data-ttu-id="f14da-141">Después de establecer los parámetros, el revisor o experto puede empezar a entrenar los archivos en la pestaña **Relevancia**.</span><span class="sxs-lookup"><span data-stu-id="f14da-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f14da-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="f14da-142">See also</span></span>

[<span data-ttu-id="f14da-143">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="f14da-143">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f14da-144">Definir problemas y asignar usuarios</span><span class="sxs-lookup"><span data-stu-id="f14da-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="f14da-145">Configurar cargas para agregar archivos importados</span><span class="sxs-lookup"><span data-stu-id="f14da-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="f14da-146">Definir palabras clave resaltadas y opciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="f14da-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

