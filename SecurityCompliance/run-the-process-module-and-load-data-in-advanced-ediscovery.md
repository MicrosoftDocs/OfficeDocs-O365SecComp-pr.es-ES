---
title: Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Obtenga información sobre cómo usar el centro de &amp; seguridad y cumplimiento de Office 365 para obtener acceso a eDiscovery avanzado de Office 365 y ejecutar el módulo de proceso para un caso.  '
ms.openlocfilehash: 95c73c034ed2ffa1c45f9aacd8463c497a842859
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261418"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="6b6ab-103">Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="6b6ab-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="6b6ab-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="6b6ab-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6b6ab-106">En esta sección se describe la funcionalidad del módulo de proceso avanzado de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="6b6ab-107">Además de los datos de archivo, los metadatos como el tipo de archivo, la extensión, la ubicación o la ruta de acceso, la fecha y hora de creación, el autor, el custodio y el sujeto se pueden cargar en eDiscovery avanzado y guardarse para cada caso.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="6b6ab-108">Algunos metadatos los calcula la exhibición avanzada de documentos electrónicos, por ejemplo, cuando se cargan archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="6b6ab-109">EDiscovery avanzado proporciona valores de metadatos del sistema, como agrupaciones casi duplicadas o calificaciones de relevancia.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="6b6ab-110">El administrador puede agregar otros metadatos, como las anotaciones de archivo.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="6b6ab-111">Proceso en ejecución</span><span class="sxs-lookup"><span data-stu-id="6b6ab-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="6b6ab-112">Los números de lote se asignan a un archivo durante el proceso para permitir el seguimiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="6b6ab-113">El número de lote también permite la identificación de lotes de proceso para las opciones de reprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="6b6ab-114">Hay filtros adicionales disponibles para filtrar por número de lote y sesiones.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="6b6ab-115">Realice los siguientes pasos para ejecutar el proceso.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="6b6ab-116">[Abra el centro de seguridad &amp; y cumplimiento de Office 365](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="6b6ab-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="6b6ab-117">Vaya a la **exhibición** de documentos electrónicos de \*\* &amp; investigación\*\* \> y haga clic en **ir a exhibición avanzada**de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="6b6ab-118">En la exhibición avanzada de documentos electrónicos, seleccione el caso apropiado en la página **casos** mostrados y haga clic en **ir al caso**.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="6b6ab-119">En **preparar** \> el **proceso** \> de **instalación**, seleccione un contenedor de la lista de contenedores disponibles.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![Haga clic en proceso para agregar los resultados de la búsqueda al caso](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="6b6ab-121">Haga clic en **Configuración avanzada...** si desea agregar el contenedor como archivos semilla o como archivos etiquetados previamente.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="6b6ab-122">Use los archivos de inicialización para acelerar el entrenamiento de problemas con escasa riqueza (normalmente 2% o menos).</span><span class="sxs-lookup"><span data-stu-id="6b6ab-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="6b6ab-123">En el caso de los archivos de inicialización, se recomienda seleccionar una variedad de archivos y un proceso claramente relevantes alrededor de 20-50 de semillas por problema (demasiados archivos de inicialización pueden sesgar los resultados de relevancia).</span><span class="sxs-lookup"><span data-stu-id="6b6ab-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="6b6ab-124">Los archivos de inicialización deben ser revisados por la misma persona que va a entrenar el problema.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="6b6ab-125">Use archivos etiquetados previamente para automatizar el entrenamiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="6b6ab-126">Debe etiquetar al menos 1.500 archivos y mantener la proporción de archivos relevantes y no relevantes del mismo modo que en la colección agregada a relevancia.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="6b6ab-127">Estos archivos se deben etiquetar manualmente y debe estar seguro de la calidad de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![Captura de pantalla de la página Configuración avanzada para procesar archivos por lotes](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="6b6ab-129">En la sección **SEED** :</span><span class="sxs-lookup"><span data-stu-id="6b6ab-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="6b6ab-130">Elija **marcar como archivos semilla** para marcar el contenedor como archivos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="6b6ab-131">También tiene que elegir asignarlos por asunto en la lista desplegable **para problema** .</span><span class="sxs-lookup"><span data-stu-id="6b6ab-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="6b6ab-132">Elija **relevante** o **no relevante** en la lista desplegable de **etiquetas** .</span><span class="sxs-lookup"><span data-stu-id="6b6ab-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6b6ab-133">Una vez que haya establecido \*\*\*\* los archivos como inicialización, no podrá marcarlos como **etiquetados previamente**.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="6b6ab-134">En la sección **archivos etiquetaDos previamente** :</span><span class="sxs-lookup"><span data-stu-id="6b6ab-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="6b6ab-135">Elija **marcar como archivos etiquetados previamente** para marcar el contenedor como archivos etiquetados previamente.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="6b6ab-136">También tiene que asignarlos por problema desde la lista desplegable **para problema** .</span><span class="sxs-lookup"><span data-stu-id="6b6ab-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="6b6ab-137">Elija **relevante** o **no relevante** en la lista desplegable de **etiquetas** .</span><span class="sxs-lookup"><span data-stu-id="6b6ab-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6b6ab-138">Una vez que haya establecido los archivos como **etiquetaDos previamente**, no podrá marcarlos como **inicialización**.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="6b6ab-139">En la sección **etiquetado de correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="6b6ab-139">In the **Email tagging** section.</span></span> <span data-ttu-id="6b6ab-140">establecer qué parte de un correo electrónico procesado se marcará como semilla o preetiquetada.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="6b6ab-141">Para empezar, haga clic en **procesar**.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-141">To begin, click **Process**.</span></span> <span data-ttu-id="6b6ab-142">Una vez finalizado, se muestran los resultados del proceso.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="6b6ab-143">Opcional Si necesita asignar orígenes de datos a un custodio específico, puede Agregar y editar nombres de custodios en los **custodios** \> **administre** y asigne custodios en **asignación**de **custodios** \> .</span><span class="sxs-lookup"><span data-stu-id="6b6ab-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="6b6ab-144">Si agrega al caso, puede volver a procesar.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6b6ab-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b6ab-145">See also</span></span>

[<span data-ttu-id="6b6ab-146">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="6b6ab-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6b6ab-147">Visualización de los resultados del módulo de proceso</span><span class="sxs-lookup"><span data-stu-id="6b6ab-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

