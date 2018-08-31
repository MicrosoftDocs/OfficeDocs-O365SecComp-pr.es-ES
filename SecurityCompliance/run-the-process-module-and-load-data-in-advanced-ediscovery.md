---
title: Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Obtenga información sobre cómo usar la seguridad de Office 365 &amp; centro de cumplimiento para tener acceso a Office 365 avanzada exhibición de documentos electrónicos y ejecutar el módulo de proceso para un caso.  '
ms.openlocfilehash: 32052bccc37d20c8707a1efb0592f7c93daf3590
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536207"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="1b492-103">Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="1b492-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="1b492-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="1b492-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="1b492-106">En esta sección se describe la funcionalidad del módulo del proceso de exhibición de documentos electrónicos avanzadas.</span><span class="sxs-lookup"><span data-stu-id="1b492-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="1b492-p102">Además de los datos de archivo, se pueden cargar metadatos como tipo de archivo, extensión, ubicación o ruta de acceso, fecha de creación y tiempo, autor, custodia y asunto, en avanzada de exhibición de documentos electrónicos y guardan para cada caso. Algunos metadatos se calculan mediante avanzada exhibición de documentos electrónicos, por ejemplo, cuando se cargan archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="1b492-p102">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case. Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="1b492-p103">Exhibición de documentos electrónicos avanzada proporciona al sistema de valores de metadatos, como las agrupaciones de casi duplicados o las puntuaciones de la relevancia. Otros metadatos, como las anotaciones de archivo, se pueden agregar por el administrador.</span><span class="sxs-lookup"><span data-stu-id="1b492-p103">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores. Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="1b492-111">Proceso que se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="1b492-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="1b492-p104">Los números de lote se asignan a un archivo durante el proceso para permitir el seguimiento de los archivos. El número de lote también permite la identificación de los lotes de proceso para las opciones de reprocesamiento. Filtros adicionales están disponibles para filtrar por número de lote y sesiones.</span><span class="sxs-lookup"><span data-stu-id="1b492-p104">Batch numbers are assigned to a file during Process to allow the tracking of files. The batch number also enables identification of Process batches for reprocessing options. Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="1b492-115">Realice los pasos siguientes para ejecutar el proceso.</span><span class="sxs-lookup"><span data-stu-id="1b492-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="1b492-116">[Abrir la seguridad de Office 365 &amp; centro de cumplimiento](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="1b492-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="1b492-117">Vaya a **búsqueda &amp; investigación** \> **exhibición de documentos electrónicos** y, a continuación, haga clic en **Ir a la exhibición de documentos electrónicos avanzada**.</span><span class="sxs-lookup"><span data-stu-id="1b492-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="1b492-118">En la exhibición de documentos electrónicos avanzada, seleccione el caso apropiado en la página de **casos** mostrada en y haga clic en **Ir a caso**.</span><span class="sxs-lookup"><span data-stu-id="1b492-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="1b492-119">En **Prepare** \> **proceso** \> **el programa de instalación**, seleccione un contenedor de la lista de contenedores disponibles.</span><span class="sxs-lookup"><span data-stu-id="1b492-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![Haga clic en el proceso para agregar los resultados de búsqueda a las mayúsculas y minúsculas](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="1b492-121">Haga clic en **configuración... avanzada** si desea agregar el contenedor como archivos de inicialización o como archivos con previa a la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="1b492-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="1b492-p105">Usar archivos de inicialización para acelerar el aprendizaje para problemas con flexibilidad baja (normalmente un 2% o menos). Para los archivos de inicialización, se recomienda que seleccione una gran variedad de archivos claramente relevantes y procesar sobre semillas 20-50 por problema (demasiados archivos de inicialización pueden contraer los resultados de la relevancia). Archivos de inicialización deben ser revisados por la misma persona que enseñará el problema.</span><span class="sxs-lookup"><span data-stu-id="1b492-p105">Use seed files to accelerate training for issues with low richness (usually 2%, or less). For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results). Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="1b492-p106">Usar archivos con previa a la etiqueta para automatizar la formación de relevancia. Debe marcar los archivos al menos 1.500 y mantener la misma que en la colección que se agrega a la relevancia de la proporción de relevantes para los archivos que no sean relevantes. Estos archivos se deben etiquetar manualmente, y debe estar seguro de la calidad de etiquetas temáticas.</span><span class="sxs-lookup"><span data-stu-id="1b492-p106">Use pre-tagged files to automate Relevance training. You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance. These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![Captura de pantalla de avanzada de página de configuración para el procesamiento por lotes de archivos](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="1b492-129">En la sección **valor de inicialización** :</span><span class="sxs-lookup"><span data-stu-id="1b492-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="1b492-p107">Seleccione **Marcar como archivos de inicialización** para marcar el contenedor como archivos de inicialización. También necesita elegir asignar por problema desde la **para el problema de** lista desplegable. Elija **pertinente** o **no relevantes** en la lista desplegable de **etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="1b492-p107">Choose **Mark as seed files** to mark the container as seed files. You also need choose to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1b492-133">Una vez que los archivos se establece como **valor de inicialización**, no se puede marcarlos como **previamente con etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="1b492-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="1b492-134">En la sección **archivos con previa a la etiqueta** :</span><span class="sxs-lookup"><span data-stu-id="1b492-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="1b492-p108">Seleccione **Marcar como archivos con previa a la etiqueta** para marcar el contenedor como archivos con previa a la etiqueta. También debe asignar por problema desde la **para el problema de** lista desplegable. Elija **pertinente** o **no relevantes** en la lista desplegable de **etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="1b492-p108">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files. You also need to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1b492-138">Una vez establecido archivos como **previamente con la etiqueta**, no se puede marcarlos como **valor de inicialización**.</span><span class="sxs-lookup"><span data-stu-id="1b492-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="1b492-p109">En la sección **correo electrónico etiquetado** . conjunto de qué parte de un correo electrónico procesado deben estar marcados como semillas o con previa a la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="1b492-p109">In the **Email tagging** section. set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="1b492-p110">Para empezar, haga clic en **proceso**. Cuando se complete, se muestran los resultados del proceso.</span><span class="sxs-lookup"><span data-stu-id="1b492-p110">To begin, click **Process**. When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="1b492-143">(Opcional) Si necesita asignar orígenes de datos a una custodia específica, puede agregar y editar los nombres de custodia en **custodia** \> **Administrar** y asignar custodia en **custodia** \> **asignar**.</span><span class="sxs-lookup"><span data-stu-id="1b492-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="1b492-144">Si agrega a las mayúsculas y minúsculas, a continuación, puede procesar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1b492-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b492-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b492-145">See also</span></span>

[<span data-ttu-id="1b492-146">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="1b492-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1b492-147">Ver los resultados del módulo de proceso</span><span class="sxs-lookup"><span data-stu-id="1b492-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

