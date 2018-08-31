---
title: Exportar un informe de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: En lugar de exportar los resultados reales de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento, sólo puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de búsqueda y un documento con información detallada acerca de cada elemento que se van a exportar.
ms.openlocfilehash: 45415f25754b4549a919e4ce56853a6ae09a9bdc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535603"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="63ea4-104">Exportar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="63ea4-104">Export a Content Search report</span></span>

<span data-ttu-id="63ea4-105">En lugar de exportar el conjunto completo de búsqueda de resultados de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento (y de una búsqueda de contenido que está asociado con un caso de exhibición de documentos electrónicos), sólo tiene que puede exportar los mismos informes que se generan cada vez exportar los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="63ea4-105">Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="63ea4-p102">Al exportar un informe, se descarga en una carpeta que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly* . Por ejemplo, si la búsqueda de contenido se denomina *ContosoCase0815* , el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly* . Para obtener una lista de los documentos que se incluyen en el informe, vea [qué se incluye en el informe](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="63ea4-p102">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="63ea4-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="63ea4-109">Before you begin</span></span>

- <span data-ttu-id="63ea4-p103">Para exportar un informe de búsqueda de contenido, tiene que tener asignado el rol de administración de búsqueda de cumplimiento de la seguridad de Office 365 &amp; centro de cumplimiento. Esta función se asigna a los grupos de roles de administrador y administración de la organización de exhibición de documentos electrónicos integrados. No se asigna de forma predeterminada al grupo de funciones de administración de la organización. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="63ea4-p103">To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="63ea4-p104">Al exportar un informe, los datos se almacenan temporalmente en un área de almacenamiento de Windows Azure único en la nube de Microsoft antes de se descarga en el equipo local. Asegúrese de que la organización puede conectarse al extremo en Azure, que es \*\* \*. blob.core.windows.net\*\* (el carácter comodín representa un identificador único para la exportación). Los datos de los resultados de la búsqueda se eliminan desde el área de almacenamiento de Azure dos semanas después de crearla.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p104">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="63ea4-117">El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:</span><span class="sxs-lookup"><span data-stu-id="63ea4-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="63ea4-118">Versiones de 32 o 64 bits de Windows 7 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="63ea4-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="63ea4-119">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="63ea4-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="63ea4-120">Un explorador compatible:</span><span class="sxs-lookup"><span data-stu-id="63ea4-120">A supported browser:</span></span>
    
    - <span data-ttu-id="63ea4-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="63ea4-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="63ea4-122">o</span><span class="sxs-lookup"><span data-stu-id="63ea4-122">or</span></span>
    
    - <span data-ttu-id="63ea4-123">Microsoft Internet Explorer 10 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="63ea4-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="63ea4-p105">**Nota:** Microsoft no fabrica las extensiones de terceros o complementos para las aplicaciones ClickOnce. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con las extensiones de terceros o los complementos.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
    
## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="63ea4-126">Generar y descargar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="63ea4-126">Generate and download a Content Search report</span></span>

<span data-ttu-id="63ea4-127">Los pasos necesarios para generar y descargar un informe de búsqueda de contenido son muy similares a realmente exportar los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="63ea4-127">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="63ea4-128">Paso 1: Generar el informe para la exportación</span><span class="sxs-lookup"><span data-stu-id="63ea4-128">Step 1: Generate the report for export</span></span>

<span data-ttu-id="63ea4-p106">El primer paso consiste en preparar el informe para la descarga a su equipo de exportación. Cuando se el informe, el informe se cargan documentos en un área de almacenamiento de Azure en Microsoft en la nube.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p106">The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="63ea4-131">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="63ea4-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="63ea4-132">Inicie sesión en Office 365 con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="63ea4-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="63ea4-133">En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **Búsqueda de contenido**.</span><span class="sxs-lookup"><span data-stu-id="63ea4-133">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="63ea4-134">En la página de **búsqueda de contenido** , seleccione una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="63ea4-134">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="63ea4-135">En el panel de detalles, en **exportar el informe a un equipo**, haga clic en **Generar informe**.</span><span class="sxs-lookup"><span data-stu-id="63ea4-135">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63ea4-p107">Si los resultados de una búsqueda son más de 7 días, se le pedirán para actualizar los resultados de búsqueda. Si esto sucede, cancelar la exportación, haga clic en **resultados de búsqueda de actualizaciones** en el panel de detalles para la búsqueda seleccionada y, a continuación, iniciar la exportación de informes después de que se actualizan los resultados.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p107">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="63ea4-138">En la página **exportar un informe** , en **incluir estos elementos de la búsqueda**, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="63ea4-138">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="63ea4-139">Exportar solo los elementos indexados</span><span class="sxs-lookup"><span data-stu-id="63ea4-139">Export only indexed items</span></span>
    
    - <span data-ttu-id="63ea4-140">Exportar los elementos indexados y sin indexar</span><span class="sxs-lookup"><span data-stu-id="63ea4-140">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="63ea4-141">Exportar solo los elementos sin indexar</span><span class="sxs-lookup"><span data-stu-id="63ea4-141">Export only unindexed items</span></span>
    
    <span data-ttu-id="63ea4-142">Para obtener más información acerca de los elementos sin indizar, consulte [parcialmente indizar los elementos de búsqueda de contenido](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="63ea4-142">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="63ea4-p108">Elija esta opción incluir las estadísticas de búsqueda para todas las versiones de documentos de SharePoint. Esta opción aparece únicamente si los orígenes de contenido de la búsqueda incluye SharePoint o OneDrive para los sitios de negocio.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p108">Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="63ea4-145">Haga clic en **Generar informe**.</span><span class="sxs-lookup"><span data-stu-id="63ea4-145">Click **Generate report**.</span></span>
    
    <span data-ttu-id="63ea4-p109">El informe de resultados de búsqueda está preparado para descargar el archivo, lo que significa que los documentos de informe se cargará en el área de almacenamiento de Azure en la nube de Microsoft. Cuando el informe está listo para su descarga, se muestra el vínculo **Descargar informe** en **exportar el informe a un equipo** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p109">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="63ea4-p110">También puede exportar un informe para una búsqueda de contenido que está asociado con un caso de exhibición de documentos electrónicos. Para ello, vaya a **búsqueda &amp; investigación** \> seleccione un caso de **exhibición de documentos electrónicos**y haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). En la página de **búsquedas** , seleccione una búsqueda y, a continuación, haga clic en **Exportar** ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **exportar un informe**.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p110">You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="63ea4-151">Paso 2: Descargar el informe</span><span class="sxs-lookup"><span data-stu-id="63ea4-151">Step 2: Download the report</span></span>

<span data-ttu-id="63ea4-152">El siguiente paso es descargar el informe desde el área de almacenamiento de Azure en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="63ea4-152">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="63ea4-153">En el panel de detalles de la búsqueda que generó el informe, en **exportar el informe a un equipo**, haga clic en **Descargar informe**.</span><span class="sxs-lookup"><span data-stu-id="63ea4-153">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="63ea4-154">La página **Descargar informe** se muestra y contiene la siguiente información sobre el informe hasta que se descargan en el equipo.</span><span class="sxs-lookup"><span data-stu-id="63ea4-154">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="63ea4-155">El número de elementos que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="63ea4-155">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="63ea4-156">El tamaño total estimado de los elementos que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="63ea4-156">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="63ea4-p111">Se exportará si indexados o no indexados. Elementos sin indizar son elementos que tienen un formato reconocido, se cifran o no estaban indizados por otras razones.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p111">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="63ea4-159">Si las versiones de los documentos de SharePoint se descargarán o no.</span><span class="sxs-lookup"><span data-stu-id="63ea4-159">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="63ea4-p112">El estado del proceso de exportación de informe. Puede iniciar la descarga del informe, incluso si la preparación del informe no está completa.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p112">The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="63ea4-p113">**Exportar la clave**, haga clic en **Copiar al Portapapeles**. Para descargar el informe va a usar esta clave en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p113">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="63ea4-164">Dado que cualquier persona puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, use esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave, al igual que protege a las contraseñas u otra información relacionada con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="63ea4-164">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="63ea4-165">Haga clic en **Descargar informe**.</span><span class="sxs-lookup"><span data-stu-id="63ea4-165">Click **Download report**.</span></span>
    
4. <span data-ttu-id="63ea4-166">Si le pide para instalar la **exhibición de documentos de Microsoft Office 365 herramienta para exportar**, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="63ea4-166">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="63ea4-167">En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="63ea4-167">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="63ea4-168">Haga clic en **Examinar** para especificar la ubicación donde desea descargar el informe.</span><span class="sxs-lookup"><span data-stu-id="63ea4-168">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="63ea4-169">Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.</span><span class="sxs-lookup"><span data-stu-id="63ea4-169">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="63ea4-p114">La **exhibición de documentos electrónicos herramienta para exportar** muestra información de estado sobre el proceso de exportación, así como una estimación del número (y tamaño) de los elementos restantes para ser descargado. Cuando se completa el proceso de exportación, puede tener acceso a los archivos en la ubicación donde se han descargado.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p114">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="63ea4-p115">Puede descargar el informe para una búsqueda de contenido que está asociado con un caso de exhibición de documentos electrónicos. Para ello, vaya a **búsqueda &amp; investigación** \> seleccione un caso de **exhibición de documentos electrónicos**y haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). En la página de **exportaciones** , seleccione una exportación de informe y, a continuación, haga clic en **Descargar informe** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p115">You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="63ea4-175">¿Qué se incluye en el informe</span><span class="sxs-lookup"><span data-stu-id="63ea4-175">What's included in the report</span></span>

<span data-ttu-id="63ea4-176">Al generar y exportar un informe sobre los resultados de una búsqueda de contenido, se descargan los documentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="63ea4-176">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="63ea4-p116">**Exportar resumen** - documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se han buscado, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se van a exportar y el tamaño estimado y real de los elementos que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p116">**Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="63ea4-p117">Si al exportar el informe incluye elementos sin indizar, el número de elementos sin indizar se incluyen en el número total de resultados de búsqueda estimado y en el número total de descargado los resultados de búsqueda (si estuviera exportar los resultados de búsqueda) que se enumeran en la Exportar el informe de resumen. En otras palabras, el número total de elementos que se necesiten descargar es igual que el número total de resultados estimados y el número total de elementos sin indizar.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p117">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="63ea4-181">**Manifiesto** - un archivo de manifiesto (en formato XML) que contiene información acerca de los artículos incluidos en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="63ea4-181">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="63ea4-p118">**Resultados** - documento de Excel que contiene una fila con información acerca de cada elemento indizado que sería exportado con los resultados de búsqueda. Para el correo electrónico, el registro de resultados contiene información acerca de cada mensaje, incluidos:</span><span class="sxs-lookup"><span data-stu-id="63ea4-p118">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="63ea4-184">La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).</span><span class="sxs-lookup"><span data-stu-id="63ea4-184">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="63ea4-185">La fecha en que se envió o se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="63ea4-185">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="63ea4-186">La línea Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="63ea4-186">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="63ea4-187">El remitente y los destinatarios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="63ea4-187">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="63ea4-188">Para los documentos de SharePoint y OneDrive para los sitios comerciales, el registro de los resultados contiene información acerca de cada documento, incluidos:</span><span class="sxs-lookup"><span data-stu-id="63ea4-188">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="63ea4-189">La dirección URL del documento.</span><span class="sxs-lookup"><span data-stu-id="63ea4-189">The URL for the document.</span></span>
    
  - <span data-ttu-id="63ea4-190">La dirección URL de la colección de sitio donde se ubica el documento.</span><span class="sxs-lookup"><span data-stu-id="63ea4-190">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="63ea4-191">La fecha en la que el documento se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="63ea4-191">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="63ea4-192">El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).</span><span class="sxs-lookup"><span data-stu-id="63ea4-192">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63ea4-193">El número de filas en el informe de **resultados** debe ser igual que el número total de resultados de búsqueda que se necesiten descargar menos el número total de elementos que aparecen en el informe de **Elementos no indizados** .</span><span class="sxs-lookup"><span data-stu-id="63ea4-193">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="63ea4-p119">**Elementos sin indizar** - documento de Excel que contiene información acerca de todos los elementos sin indizar que se incluirán en los resultados de búsqueda. Si no incluye elementos sin indizar cuando se genera el informe de resultados de búsqueda, se descargará este informe, pero estará vacía.</span><span class="sxs-lookup"><span data-stu-id="63ea4-p119">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
