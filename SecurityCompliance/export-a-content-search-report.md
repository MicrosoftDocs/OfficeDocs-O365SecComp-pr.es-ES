---
title: Exportar un informe de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: En lugar de exportar los resultados reales de una búsqueda de contenido en el centro de seguridad & cumplimiento en Office 365, puede simplemente exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de la búsqueda y un documento con información detallada sobre cada elemento que se exportará.
ms.openlocfilehash: 57c8a9be5c53998570f6ff15a49df69e27745e26
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255658"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="87971-104">Exportar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="87971-104">Export a Content Search report</span></span>

<span data-ttu-id="87971-105">En lugar de exportar el conjunto completo de resultados de búsqueda de una búsqueda de contenido en el centro de seguridad & cumplimiento (y desde una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos), puede exportar los mismos informes que se generan al exportar la búsqueda obtener.</span><span class="sxs-lookup"><span data-stu-id="87971-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="87971-106">Al exportar un informe, se descarga en una carpeta que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly* .</span><span class="sxs-lookup"><span data-stu-id="87971-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  .</span></span> <span data-ttu-id="87971-107">Por ejemplo, si la búsqueda de contenido se denomina *ContosoCase0815* , el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly* .</span><span class="sxs-lookup"><span data-stu-id="87971-107">For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  .</span></span> <span data-ttu-id="87971-108">Para obtener una lista de los documentos que se incluyen en el informe, consulte [what's included in the Report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="87971-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="87971-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="87971-109">Before you begin</span></span>

- <span data-ttu-id="87971-110">Para exportar un informe de búsqueda de contenido, debe tener asignado el rol de administración de búsqueda de cumplimiento en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="87971-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="87971-111">Este rol se asigna a los grupos de roles integrados administrador de eDiscovery y administración de la organización.</span><span class="sxs-lookup"><span data-stu-id="87971-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="87971-112">No se asigna de forma predeterminada al grupo de roles de administración de la organización.</span><span class="sxs-lookup"><span data-stu-id="87971-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="87971-113">Para obtener más información, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md)de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="87971-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="87971-114">Al exportar un informe, los datos se almacenan temporalmente en un área de almacenamiento única de Windows Azure en la nube de Microsoft antes de descargarlos en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="87971-114">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="87971-115">asegúrese de que su organización puede conectarse al extremo en Azure, que es \*\* \*. blob.core.windows.net\*\* (el carácter comodín representa un identificador único para la exportación).</span><span class="sxs-lookup"><span data-stu-id="87971-115">Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="87971-116">Los datos de los resultados de la búsqueda se eliminan del área de Azure Storage dos semanas después de su creación.</span><span class="sxs-lookup"><span data-stu-id="87971-116">The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="87971-117">El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:</span><span class="sxs-lookup"><span data-stu-id="87971-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="87971-118">Versiones de 32 o 64 bits de Windows 7 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="87971-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="87971-119">Microsoft .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="87971-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="87971-120">Un explorador compatible:</span><span class="sxs-lookup"><span data-stu-id="87971-120">A supported browser:</span></span>
    
    - <span data-ttu-id="87971-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="87971-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="87971-122">o</span><span class="sxs-lookup"><span data-stu-id="87971-122">or</span></span>
    
    - <span data-ttu-id="87971-123">Microsoft Internet Explorer 10 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="87971-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="87971-124">**Nota:** Microsoft no fabrica extensiones de terceros o complementos para aplicaciones ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="87971-124">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="87971-125">No se admite la exportación de resultados de búsqueda con un explorador no compatible con extensiones de terceros o complementos.</span><span class="sxs-lookup"><span data-stu-id="87971-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="87971-126">Si el tamaño total estimado de los resultados devueltos por una búsqueda de&nbsp;contenido supera los 20 TB, se producirá un error al exportar el informe.</span><span class="sxs-lookup"><span data-stu-id="87971-126">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail.</span></span> <span data-ttu-id="87971-127">Para exportar correctamente el informe, intente restringir el ámbito y vuelva a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a&nbsp;20 TB.</span><span class="sxs-lookup"><span data-stu-id="87971-127">To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

- <span data-ttu-id="87971-128">La exportación de informes de búsqueda de contenido cuenta con el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="87971-128">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="87971-129">Para obtener más información acerca de los límites de exportación, consulte [exportar resultados](export-search-results.md#export-limits)de la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="87971-129">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="87971-130">Generar y descargar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="87971-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="87971-131">Los pasos para generar y descargar un informe de búsqueda de contenido son muy similares a la exportación real de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87971-131">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="87971-132">Paso 1: generar el informe para la exportación</span><span class="sxs-lookup"><span data-stu-id="87971-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="87971-133">El primer paso consiste en preparar el informe para descargarlo en la exportación de su equipo.</span><span class="sxs-lookup"><span data-stu-id="87971-133">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="87971-134">Cuando se trata de un informe, los documentos del informe se cargan en un área de almacenamiento de Azure en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87971-134">When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="87971-135">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="87971-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="87971-136">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="87971-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="87971-137">En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en buscar **contenido**de **búsqueda** \> .</span><span class="sxs-lookup"><span data-stu-id="87971-137">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="87971-138">En la página **búsqueda de contenido** , seleccione una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87971-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="87971-139">En el panel de detalles, en **exportar informe a un equipo**, haga clic en **generar informe**.</span><span class="sxs-lookup"><span data-stu-id="87971-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="87971-140">Si los resultados de una búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87971-140">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="87971-141">Si esto ocurre, cancele la exportación, haga clic en **Actualizar resultados de búsqueda** en el panel de detalles de la búsqueda seleccionada y, a continuación, vuelva a iniciar la exportación del informe después de que se actualicen los resultados.</span><span class="sxs-lookup"><span data-stu-id="87971-141">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="87971-142">En la página **exportar un informe** , en **incluir estos elementos de la búsqueda**, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="87971-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="87971-143">Exportar solo los elementos indexados</span><span class="sxs-lookup"><span data-stu-id="87971-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="87971-144">Exportar los elementos indexados y sin indexar</span><span class="sxs-lookup"><span data-stu-id="87971-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="87971-145">Exportar solo los elementos sin indexar</span><span class="sxs-lookup"><span data-stu-id="87971-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="87971-146">Para obtener más información acerca de los elementos sin indexar, vea [elementos parcialmente indizados en la búsqueda de contenido](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="87971-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="87971-147">Elija incluir estadísticas de búsqueda para todas las versiones de los documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="87971-147">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="87971-148">Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios de SharePoint o de OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="87971-148">This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="87971-149">Haga clic en **generar informe**.</span><span class="sxs-lookup"><span data-stu-id="87971-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="87971-150">El informe de resultados de búsqueda está preparado para la descarga, lo que significa que los documentos del informe se cargarán en el área de almacenamiento de Azure en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87971-150">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="87971-151">Cuando el informe está listo para la descarga, el vínculo de **descarga del informe** se muestra en **exportar informe a un equipo** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="87971-151">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="87971-152">También puede exportar un informe para una búsqueda de contenido que esté asociada a un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="87971-152">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="87971-153">Para \*\*\*\* \> ello, vaya a eDiscovery **eDiscovery**, seleccione un caso y haga clic en **Editar** ![icono](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)de edición.</span><span class="sxs-lookup"><span data-stu-id="87971-153">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="87971-154">En la página **búsquedas** , seleccione una búsqueda y, a continuación, haga clic en **exportar** ![los resultados](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> de la búsqueda exportar **un informe**.</span><span class="sxs-lookup"><span data-stu-id="87971-154">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="87971-155">Paso 2: descargar el informe</span><span class="sxs-lookup"><span data-stu-id="87971-155">Step 2: Download the report</span></span>

<span data-ttu-id="87971-156">El siguiente paso es descargar el informe desde el área de almacenamiento de Azure a su equipo local.</span><span class="sxs-lookup"><span data-stu-id="87971-156">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="87971-157">En el panel de detalles de la búsqueda para la que generó el informe, en **exportar informe a un equipo**, haga clic en **Descargar Informe**.</span><span class="sxs-lookup"><span data-stu-id="87971-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="87971-158">Se muestra la página **Descargar Informe** , que contiene la siguiente información sobre el informe que se descargará en el equipo.</span><span class="sxs-lookup"><span data-stu-id="87971-158">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="87971-159">El número de elementos que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="87971-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="87971-160">El tamaño total estimado de los elementos que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="87971-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="87971-161">Si los elementos indexados o sin indexar se exportarán.</span><span class="sxs-lookup"><span data-stu-id="87971-161">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="87971-162">Los elementos sin indexar son elementos que tienen un formato reconocido, están cifrados o no se indexaron por otros motivos.</span><span class="sxs-lookup"><span data-stu-id="87971-162">Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="87971-163">Si las versiones de los documentos de SharePoint se descargarán o no.</span><span class="sxs-lookup"><span data-stu-id="87971-163">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="87971-164">El estado del proceso de exportación del informe.</span><span class="sxs-lookup"><span data-stu-id="87971-164">The status of the report export process.</span></span> <span data-ttu-id="87971-165">Puede iniciar la descarga del informe incluso si no se ha completado la preparación del informe.</span><span class="sxs-lookup"><span data-stu-id="87971-165">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="87971-166">En **Clave de exportación**, haga clic en **Copiar al Portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="87971-166">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="87971-167">Esta clave se utilizará en el paso 5 para descargar el informe.</span><span class="sxs-lookup"><span data-stu-id="87971-167">You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="87971-168">Dado que cualquiera puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave igual que lo haría con las contraseñas u otra información relacionada con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="87971-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="87971-169">Haga clic en **Descargar Informe**.</span><span class="sxs-lookup"><span data-stu-id="87971-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="87971-170">Si se le pide que instale la **herramienta de exportación MicrosoftOffice 365 eDiscovery**, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="87971-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="87971-171">En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="87971-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="87971-172">Haga clic en **examinar** para especificar la ubicación en la que desea descargar el informe.</span><span class="sxs-lookup"><span data-stu-id="87971-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="87971-173">Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.</span><span class="sxs-lookup"><span data-stu-id="87971-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="87971-174">La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar.</span><span class="sxs-lookup"><span data-stu-id="87971-174">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="87971-175">Una vez finalizado el proceso de exportación, puede tener acceso a los archivos en la ubicación en la que se descargaron.</span><span class="sxs-lookup"><span data-stu-id="87971-175">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="87971-176">Puede descargar el informe para una búsqueda de contenido que esté asociada con un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="87971-176">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="87971-177">Para \*\*\*\* \> ello, vaya a eDiscovery **eDiscovery**, seleccione un caso y haga clic en **Editar** ![icono](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)de edición.</span><span class="sxs-lookup"><span data-stu-id="87971-177">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="87971-178">En la página **exportaciones** , seleccione una exportación de informe y, a continuación, haga clic en **Descargar Informe** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="87971-178">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="87971-179">Contenido incluido en el informe</span><span class="sxs-lookup"><span data-stu-id="87971-179">What's included in the report</span></span>

<span data-ttu-id="87971-180">Cuando se genera y se exporta un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="87971-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="87971-181">**Resumen de exportación** : un documento de Excel que contiene un resumen de la exportación.</span><span class="sxs-lookup"><span data-stu-id="87971-181">**Export Summary** - An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="87971-182">Esto incluye información como el número de orígenes de contenido que se han buscado, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="87971-182">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="87971-183">Si incluye elementos sin indexar al exportar el informe, el número de elementos sin indexar se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de la búsqueda descargados (si se exportaron los resultados de la búsqueda) que aparecen en la lista Informe de Resumen de exportación.</span><span class="sxs-lookup"><span data-stu-id="87971-183">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="87971-184">Es decir, el número total de elementos que se descargarán es igual al número total de resultados estimados y el número total de elementos sin indexar.</span><span class="sxs-lookup"><span data-stu-id="87971-184">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="87971-185">**Manifest** -un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87971-185">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="87971-186">**Resultados** : un documento de Excel que contiene una fila con información sobre cada elemento indizado que se exportará con los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87971-186">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="87971-187">Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos:</span><span class="sxs-lookup"><span data-stu-id="87971-187">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="87971-188">La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).</span><span class="sxs-lookup"><span data-stu-id="87971-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="87971-189">La fecha en que se envió o se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="87971-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="87971-190">La línea Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="87971-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="87971-191">El remitente y los destinatarios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="87971-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="87971-192">Para los documentos de los sitios de SharePoint y OneDrive para la empresa, el registro de resultados contiene información sobre cada documento, incluidos:</span><span class="sxs-lookup"><span data-stu-id="87971-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="87971-193">La dirección URL del documento.</span><span class="sxs-lookup"><span data-stu-id="87971-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="87971-194">La dirección URL de la colección de sitio donde se ubica el documento.</span><span class="sxs-lookup"><span data-stu-id="87971-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="87971-195">La fecha en la que el documento se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="87971-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="87971-196">El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).</span><span class="sxs-lookup"><span data-stu-id="87971-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="87971-197">El número de filas en el informe de **resultados** debe ser igual al número total de resultados de búsqueda que se descargarían menos el número total de elementos que aparecen en el informe de **elementos** sin indexar.</span><span class="sxs-lookup"><span data-stu-id="87971-197">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="87971-198">**Elementos** sin indexar: un documento de Excel que contiene información sobre los elementos sin indexar que se incluirían en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87971-198">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results.</span></span> <span data-ttu-id="87971-199">Si no incluye elementos sin indexar al generar el informe de resultados de la búsqueda, este informe se descargará, pero estará vacío.</span><span class="sxs-lookup"><span data-stu-id="87971-199">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
