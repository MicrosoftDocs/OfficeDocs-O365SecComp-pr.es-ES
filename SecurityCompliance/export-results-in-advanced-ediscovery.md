---
title: Exportar resultados en eDiscovery avanzado de Office 365
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
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: 'Obtenga información sobre cómo definir las opciones de exportación de resultados desde Office 365 avanzada exhibición de documentos electrónicos, incluido el procedimiento para especificar los parámetros de una sección de exportación. '
ms.openlocfilehash: 92ee107ad096393fbccbc9a3dbe81d8e7dd28da9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536788"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2d143-103">Exportar resultados en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2d143-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="2d143-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2d143-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2d143-106">En este tema se describe las opciones de configuración de exportación de exhibición de documentos electrónicos avanzada.</span><span class="sxs-lookup"><span data-stu-id="2d143-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="2d143-107">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="2d143-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="2d143-108">Definición de exportación de lotes y sesiones</span><span class="sxs-lookup"><span data-stu-id="2d143-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="2d143-109">Exporta incremental y adicional</span><span class="sxs-lookup"><span data-stu-id="2d143-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="2d143-110">Configurar los parámetros de exportación por lotes</span><span class="sxs-lookup"><span data-stu-id="2d143-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="2d143-111">Exportar archivos de salida de informe</span><span class="sxs-lookup"><span data-stu-id="2d143-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="2d143-112">Definición de exportación de lotes y sesiones</span><span class="sxs-lookup"><span data-stu-id="2d143-112">Defining export batches and sessions</span></span>
<span data-ttu-id="2d143-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="2d143-113"></span></span>

<span data-ttu-id="2d143-p102">Una sección de exportación permite el proceso de exportación con un conjunto de parámetros definidos. Exhibición de documentos electrónicos avanzada le permite definir lotes para personalizar cada exportación.</span><span class="sxs-lookup"><span data-stu-id="2d143-p102">An export batch allows export processing using a set of defined parameters. Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="2d143-p103">Los parámetros se definen por lotes de exportación. Se crea una sección denominada "Exportar por lotes 01" de forma predeterminada para el primer lote de un caso. También puede editar el nombre de la sección y la descripción.</span><span class="sxs-lookup"><span data-stu-id="2d143-p103">Parameters are defined per export batch. A batch named "Export batch 01" is created by default for the first batch of a case. You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="2d143-119">Una sesión de exportación es una ejecución de exportación de eDiscovery avanzada dentro de una sección de exportación.</span><span class="sxs-lookup"><span data-stu-id="2d143-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="2d143-120">Exporta incremental y adicional</span><span class="sxs-lookup"><span data-stu-id="2d143-120">Incremental and additional exports</span></span>
<span data-ttu-id="2d143-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="2d143-121"></span></span>

<span data-ttu-id="2d143-p104">Puede ejecutar varias sesiones de exportación dentro de una sección de exportación, para garantizar un resultado homogéneo en función de la misma plantilla de exportación y los parámetros. Para cada sesión dentro de un lote, puede exportar el análisis para recién procesan los datos de casos y procesar cada uno "incrementalmente".</span><span class="sxs-lookup"><span data-stu-id="2d143-p104">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters. For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="2d143-p105">Con el fin de exportar con un conjunto diferente de parámetros, primero debe crear un nuevo lote. La primera sesión en el nuevo lote generarán los resultados de los archivos procesados en el caso de hasta el momento, si estos archivos se han importado y procesan a través de una o varias de las importaciones. Vuelve a calcular cada lote de tablas dinámicas, similitud, inclusives, etcetera. Las sesiones de usar los parámetros definidos para el lote y no volver a calcular tablas dinámicas, similitud, inclusives, etc. para cada ejecución de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2d143-p105">In order to export using a different set of parameters, you first need to create a new batch. The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports. Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="2d143-p106">Por ejemplo, supongamos que se ha importado un caso y analizan sus datos. Con el fin de recuperar los resultados de subprocesos de correo electrónico para los datos incrementales y cerca de duplicados, haga clic en **crear exportación de sesión** en el mismo lote que se usó anteriormente para exportar datos.</span><span class="sxs-lookup"><span data-stu-id="2d143-p106">For example, assume a case was imported and its data analyzed. In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="2d143-129">Configurar los parámetros de exportación por lotes</span><span class="sxs-lookup"><span data-stu-id="2d143-129">Set up batch export parameters</span></span>
<span data-ttu-id="2d143-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="2d143-130"></span></span>

<span data-ttu-id="2d143-p107">La herramienta de exportación de exhibición de documentos se usa para exportar los resultados de búsqueda de exhibición de documentos electrónicos avanzada a su equipo local. Para aumentar el rendimiento de transferencia de datos y el proceso de exportación de velocidad, puede configurar una configuración del registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Si desea aumentar la velocidad de descarga, configurar la configuración del registro antes de configurar los parámetros de exportación. Para obtener más información, vea [aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span><span class="sxs-lookup"><span data-stu-id="2d143-p107">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer. To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results. If you'd like to increase the download speed, configure the registry setting before you set up the export parameters. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="2d143-135">En la exhibición de documentos electrónicos avanzada, seleccione un caso y haga clic en **Exportar** \> **el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="2d143-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
  - <span data-ttu-id="2d143-136">En la lista **Exportar por lotes** , seleccione el nombre del lote o exportar los resultados a la sección de exportación 01, (el lote de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="2d143-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="2d143-p108">Para exportar los resultados de los archivos nuevos que ha agregado a un caso existente, continúe con el lote actual. Para crear una sesión en el lote, seleccione el mismo número de lote y haga clic en **crear exportación sesión** puede usar esta opción para exportar los mismos parámetros como el lote anterior, de manera incremental.</span><span class="sxs-lookup"><span data-stu-id="2d143-p108">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="2d143-p109">Para exportar a un nuevo lote, haga clic en **Agregar**![agregar icono](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)y especifique un nuevo nombre en **nombre de lote** (o acepte el valor predeterminado) y una descripción en la **Descripción de lote**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d143-p109">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="2d143-141">Para editar un nombre de proceso por lotes o una descripción, seleccione el nombre de **exportación por lotes**, haga clic en **Editar** ![icono Editar](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)y, a continuación, modifique los campos.</span><span class="sxs-lookup"><span data-stu-id="2d143-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2d143-p110">Una vez ejecutado el sesiones de una sección de exportación, no se puede eliminar. Además, se pueden editar sólo algunos parámetros una vez que se ejecuta la primera sesión.</span><span class="sxs-lookup"><span data-stu-id="2d143-p110">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="2d143-144">Para crear un lote de exportación duplicados, elija **por lotes de exportación de duplicado**![crear un icono de proceso por lotes de exportación duplicados](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) y escriba un nombre y una descripción para el lote de duplicados en el panel.</span><span class="sxs-lookup"><span data-stu-id="2d143-144">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="2d143-145">Para eliminar una sección de exportación, elija **Eliminar**![eliminar un icono de exportación de lote](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span><span class="sxs-lookup"><span data-stu-id="2d143-145">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="2d143-146">Para ver el historial de un lote, elija **Historial por lotes**![icono de vista de historial](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span><span class="sxs-lookup"><span data-stu-id="2d143-146">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="2d143-147">En la **población**, seleccione **incluir sólo los archivos por encima de la puntuación de relevancia corte** o **por lotes de exportación de refinar** si desea ajustar la configuración de la sección de exportación.</span><span class="sxs-lookup"><span data-stu-id="2d143-147">Under **Population**,Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="2d143-p111">Si selecciona **incluir sólo archivos por encima de la puntuación de relevancia corte**, está habilitado el **problema** . Si la puntuación de relevancia del archivo es mayor que la puntuación de límite para el problema seleccionado, el archivo se exportará a menos que se excluye el filtro 'para revisión'.</span><span class="sxs-lookup"><span data-stu-id="2d143-p111">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled. If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
<span data-ttu-id="2d143-p112">Si selecciona **por lotes de exportación de refinar**, la **desduplicación** y filtro 'Para revisión' se habilitan los botones de opción de campo. Si elige **la desduplicación**, a continuación, los archivos duplicados se filtrarán según la directiva definida [Case nivel (valor predeterminado): en cada conjunto de archivos duplicados en el caso todo, será desaprovisionamiento duped todos menos un archivo. Nivel de custodia: de cada conjunto de archivos duplicados de la misma custodia, será desaprovisionamiento duped todos menos un archivo.] El resultado de exportación contiene un registro de todos los archivos duplicados. Si elige **filtrar por 'para revisión'** campo, seleccione **modificar en metadatos** para escribir la configuración de campo **'para revisión'** . Seleccione **incluir los archivos de entrada** para incluir los archivos de origen en el contenido del paquete. Puede desactivar esta opción para acelerar el proceso de exportación. Tenga en cuenta que se exportará los archivos nativos en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="2d143-p112">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled. If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files** to include source files in the package content. You can clear this setting to speed up the export process. Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="2d143-157">En **metadatos**, seleccione una de las siguientes opciones en la lista **plantilla de exportación** (una vez por sesión).</span><span class="sxs-lookup"><span data-stu-id="2d143-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="2d143-p113">**Estándar**: conjunto básico de propiedades, metadatos y elementos de datos. Use esta opción cuando importar datos ya se procesan en la exhibición de documentos electrónicos avanzada y exportar datos se carguen a un sistema que ya contiene los archivos. De forma predeterminada, se crean las columnas de plantilla de exportación y se rellena.</span><span class="sxs-lookup"><span data-stu-id="2d143-p113">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="2d143-p114">**Todos los**: conjunto completo de metadatos estándar, incluidos todos los datos de procesamiento, así como las puntuaciones de análisis y la relevancia. Esta plantilla se requiere cuando exhibición de documentos electrónicos avanzada realiza el procesamiento y datos de archivo se carguen a un sistema externo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="2d143-p114">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="2d143-163">**Problemas**: seleccione **Todos los problemas** o seleccione un problema determinado que haya creado.</span><span class="sxs-lookup"><span data-stu-id="2d143-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="2d143-164">En el área **destino**:</span><span class="sxs-lookup"><span data-stu-id="2d143-164">Under **Destination**:</span></span>
    
  - <span data-ttu-id="2d143-165">**Descargar en el equipo local**</span><span class="sxs-lookup"><span data-stu-id="2d143-165">**Download to local machine**</span></span>
    
  - <span data-ttu-id="2d143-166">**Exportar a definidas por el usuario Azure blob**: si se activa esta característica, puede especificar un token de dirección URL y SAS de contenedor.</span><span class="sxs-lookup"><span data-stu-id="2d143-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2d143-p115">Una vez que se almacena un paquete de exportación para el usuario definido Azure blob, los datos ya no se administran mediante avanzada exhibición de documentos electrónicos; se administra mediante el blob de Azure. Esto significa que si se elimina el caso, los archivos exportados seguirá estando en el blob de Azure.</span><span class="sxs-lookup"><span data-stu-id="2d143-p115">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="2d143-169">**Guardar SAS símbolo (token) de sesión de exportación futuras**: si está activado, el token de SAS se cifrarán en la base de datos interna de la exhibición de documentos avanzadas para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2d143-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2d143-p116">Actualmente, el token de SAS expira después de un mes. Si se intenta descargar después de más de un mes que tenga que deshacer la última sesión, a continuación, exportar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2d143-p116">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="2d143-172">Haga clic en **Modificar** para establecer el "para su revisión ' configuración de campo.</span><span class="sxs-lookup"><span data-stu-id="2d143-172">Click **Modify** to set the "for review' field settings.</span></span> 
    
> ![Configurar para la configuración de campo de revisión de un lote de exportación](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
    In **For review field settings** panel, in **Select scenario**, select the scenario and scope of the review. The settings are displayed based on your selection.
    
    **Review all** (default): All emails, attachments, and documents are selected by default. 
    
    **Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.
    
    **Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. 
    
    If you select custom, you can then customize the settings for emails, documents, attachments and miscellaneous.
    
> <span data-ttu-id="2d143-174">En los **mensajes de correo electrónico** , seleccione los mensajes de correo electrónico que desee exportar:</span><span class="sxs-lookup"><span data-stu-id="2d143-174">In **Emails** select the emails you want to export:</span></span> 
    
    **All emails**: (default) All emails are selected.
    
    **Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.
    
    **Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .
    
> <span data-ttu-id="2d143-175">En los **documentos** , seleccione los documentos que desea exportar:</span><span class="sxs-lookup"><span data-stu-id="2d143-175">In **Documents** select the documents you want to export:</span></span> 
    
    **All documents**: (default) All documents are selected.
    
    **Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.
    
    **Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).
    
> <span data-ttu-id="2d143-176">En **los datos adjuntos** , seleccione los datos adjuntos que desea exportar</span><span class="sxs-lookup"><span data-stu-id="2d143-176">In **Attachments** select the attachments you want to export</span></span> 
    
    **All attachments**: (default) All attachments are selected.
    
    **Unique attachment in case level**: Unique attachment files within the specified case.
    
    **Unique attachment in email set level**: Unique attachment files within the specified email case.
    
> <span data-ttu-id="2d143-p117">En **Micellaneous** puede elegir para **tratar los datos adjuntos como documentos**, **tratar los correos electrónicos como documentos**o **Expandir para incluir los archivos de la familia**. Cuando elija **Expandir para incluir los archivos de la familia**, para cada archivo que se marca para su revisión, también se marcará todos los archivos de la misma familia.</span><span class="sxs-lookup"><span data-stu-id="2d143-p117">In **Micellaneous** you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**. When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
    Choose **Save** to save the settings. 
    
7. <span data-ttu-id="2d143-179">Después de especificar los parámetros de exportación, para iniciar el proceso de exportación, haga clic en **Crear sesión de exportación**.</span><span class="sxs-lookup"><span data-stu-id="2d143-179">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="2d143-p118">Durante la exportación, el estado se muestra en el **estado de la tarea**. Los resultados se muestran en el **Resumen de exportación**.</span><span class="sxs-lookup"><span data-stu-id="2d143-p118">During export, the status is displayed in **Task status**. The results are displayed in **Export summary**.</span></span>
    
8. <span data-ttu-id="2d143-182">En la ventana **descarga de archivos** , haga clic en **Copiar al Portapapeles** para copiar la clave de exportación.</span><span class="sxs-lookup"><span data-stu-id="2d143-182">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![Descargar archivos](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
9. <span data-ttu-id="2d143-184">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2d143-184">Click **Close**.</span></span> 
    
    <span data-ttu-id="2d143-185">Se inicia la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="2d143-185">The eDiscovery Export Tool is started.</span></span>
    
    ![Herramienta de exportación de exhibición de documentos electrónicos](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
10. <span data-ttu-id="2d143-187">En la **exhibición de documentos electrónicos herramienta para exportar**:</span><span class="sxs-lookup"><span data-stu-id="2d143-187">In the **eDiscovery Export Tool**:</span></span>
    
1. <span data-ttu-id="2d143-188">En **Pegar que se usará para conectarse al origen de la firma de acceso compartidos**, pegue la clave de exportación que youcopied en el Portapapeles en el paso 7.</span><span class="sxs-lookup"><span data-stu-id="2d143-188">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
2. <span data-ttu-id="2d143-189">Haga clic en **Examinar** para seleccionar la ubicación de destino para almacenar los archivos de exportación descargado en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="2d143-189">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
11. <span data-ttu-id="2d143-p119">Haga clic en **Iniciar**. Los archivos de exportación se descargan en el equipo local. Si opta por **Exportar a blob Azure definidas por el usuario** en el paso 4, la sesión se exporta a un destino de dirección URL de almacenamiento de blobs de su elección.</span><span class="sxs-lookup"><span data-stu-id="2d143-p119">Click **Start**.The export files are downloaded to the local machine. If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span> 
    
<span data-ttu-id="2d143-192">Para obtener una descripción completa de los campos en el informe de exportación, consulte [los campos del informe de exportación](export-report-fields-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="2d143-192">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="2d143-193">Exportar archivos de salida de informe</span><span class="sxs-lookup"><span data-stu-id="2d143-193">Export report output files</span></span>
<span data-ttu-id="2d143-194"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="2d143-194"></span></span>

<span data-ttu-id="2d143-195">En la siguiente tabla se enumera los archivos de resultados que se generan cuando se ejecuta una sección de exportación.</span><span class="sxs-lookup"><span data-stu-id="2d143-195">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="2d143-196">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="2d143-196">**File name**</span></span>|<span data-ttu-id="2d143-197">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="2d143-197">**File type**</span></span>|<span data-ttu-id="2d143-198">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2d143-198">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d143-199">Resumen de exportación</span><span class="sxs-lookup"><span data-stu-id="2d143-199">Export summary</span></span>  <br/> |<span data-ttu-id="2d143-200">CSV</span><span class="sxs-lookup"><span data-stu-id="2d143-200">csv</span></span>  <br/> |<span data-ttu-id="2d143-201">Un archivo de registro generado por la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="2d143-201">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="2d143-202">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="2d143-202">Trace</span></span>  <br/> |<span data-ttu-id="2d143-203">txt</span><span class="sxs-lookup"><span data-stu-id="2d143-203">txt</span></span>  <br/> |<span data-ttu-id="2d143-204">Un archivo de registro generado por la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="2d143-204">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="2d143-205">Archivos de texto extraídos</span><span class="sxs-lookup"><span data-stu-id="2d143-205">Extracted text files</span></span>  <br/> |<span data-ttu-id="2d143-206">Carpeta de archivos</span><span class="sxs-lookup"><span data-stu-id="2d143-206">File folder</span></span>  <br/> |<span data-ttu-id="2d143-207">Carpeta que contiene los archivos extraídos de texto de los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="2d143-207">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="2d143-208">Archivos nativos o datos proporcionados por</span><span class="sxs-lookup"><span data-stu-id="2d143-208">Input or native files</span></span>  <br/> |<span data-ttu-id="2d143-209">Carpeta de archivos</span><span class="sxs-lookup"><span data-stu-id="2d143-209">File folder</span></span>  <br/> |<span data-ttu-id="2d143-210">Carpeta que contiene los archivos de entrada y nativos de los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="2d143-210">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="2d143-211">Lista de exportación</span><span class="sxs-lookup"><span data-stu-id="2d143-211">Export list</span></span>  <br/> |<span data-ttu-id="2d143-212">xlsx</span><span class="sxs-lookup"><span data-stu-id="2d143-212">xlsx</span></span>  <br/> |<span data-ttu-id="2d143-p120">Metadatos de los archivos exportados en formato xlsx. Se realicen los campos en los archivos de plantilla usuario selecciona para exportar. Si es necesario, se crean varios archivos, cada uno de ellos contiene filas de 100-150K. Si un determinado valor contiene más caracteres que puede contener una celda de Excel (actualmente el límite de caracteres es 32.767), a continuación, se recortará el valor para la longitud máxima permitida. Si un valor se recorta, color de fondo de la celda es rojo para indicar esto al usuario." Los participantes de correo electrónico"es un ejemplo de un campo que puede superar el límite de longitud, si el correo electrónico se envió a una distribución de gran tamaño. Para obtener información detallada acerca de los campos de resultados, vea [exportar campos de informe](export-report-fields-in-advanced-ediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="2d143-p120">Exported files metadata in xlsx format. Fields in files are according to template user selects to export. If needed, several files are created, each contains 100-150K rows. If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed. If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution. See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.  </span></span><br/> |
|<span data-ttu-id="2d143-219">Archivo de carga</span><span class="sxs-lookup"><span data-stu-id="2d143-219">Load file</span></span>  <br/> |<span data-ttu-id="2d143-220">CSV</span><span class="sxs-lookup"><span data-stu-id="2d143-220">csv</span></span>  <br/> |<span data-ttu-id="2d143-p121">Metadatos de los archivos exportados en formato csv para cargarse en otra aplicación. Se realicen los campos en los archivos de plantilla usuario selecciona para exportar.</span><span class="sxs-lookup"><span data-stu-id="2d143-p121">Exported files metadata in csv format for loading into a different application. Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="2d143-223">Indicador de éxito</span><span class="sxs-lookup"><span data-stu-id="2d143-223">Success indicator</span></span>  <br/> |<span data-ttu-id="2d143-224">txt</span><span class="sxs-lookup"><span data-stu-id="2d143-224">txt</span></span>  <br/> |<span data-ttu-id="2d143-p122">Sólo se crean al exportar para un 3 º Azure blob. Si la exportación se realiza correctamente completamente, se creará el archivo. En caso de fallo, parcial o no se creará el archivo correcto. Se creará el archivo en la carpeta raíz, lo que permite el seguimiento automatizado en diferentes Estados de lotes o sesiones de exportación. Esto es un archivo vacío. Su nombre es: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span><span class="sxs-lookup"><span data-stu-id="2d143-p122">Only created when exporting to a 3rd party Azure blob. If export succeed completely, the file will be created. In case of failure, or partial success the file will not be created. File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses. This is an empty file. Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2d143-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d143-231">See also</span></span>
<span data-ttu-id="2d143-232"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="2d143-232"></span></span>

[<span data-ttu-id="2d143-233">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2d143-233">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2d143-234">Visualización del historial de proceso por lotes y exportar más allá de los resultados</span><span class="sxs-lookup"><span data-stu-id="2d143-234">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="2d143-235">Configuración rápida de eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2d143-235">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="2d143-236">Campos de exportación de informe</span><span class="sxs-lookup"><span data-stu-id="2d143-236">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2d143-237">Aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365</span><span class="sxs-lookup"><span data-stu-id="2d143-237">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)

