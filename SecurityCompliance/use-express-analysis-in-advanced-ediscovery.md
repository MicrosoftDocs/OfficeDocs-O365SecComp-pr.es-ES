---
title: Usar análisis rápido en eDiscovery avanzado de Office 365
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Obtenga información sobre cómo ejecutar el modo de análisis rápido de Office 365 Advanced eDiscovery
ms.openlocfilehash: e306aa03962c646ce4083b7385e527b523e86fd6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217630"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="77e80-103">Usar análisis rápido en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="77e80-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="77e80-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="77e80-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="77e80-106">Puede usar el **análisis** rápido para analizar rápidamente un caso y exportar los resultados.</span><span class="sxs-lookup"><span data-stu-id="77e80-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="77e80-p102">Puede usar el análisis rápido para calcular los subprocesos de correo electrónico y los subprocesos casi duplicados, y calcular temas. También puede establecer determinados parámetros para los temas, la similitud de documentos y los archivos de exportación en la [Configuración avanzada de análisis rápido](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span><span class="sxs-lookup"><span data-stu-id="77e80-p102">You can use express analysis to calculate near-duplicates and email threads and calculate themes. You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="77e80-109">Ejecutar el análisis rápido</span><span class="sxs-lookup"><span data-stu-id="77e80-109">Run Express analysis</span></span>

1. <span data-ttu-id="77e80-110">En la ficha **análisis rápido** (1), seleccione un contenedor para habilitar los botones \* \* Express Analysis \* \* (2) y **Configuración avanzada** .</span><span class="sxs-lookup"><span data-stu-id="77e80-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![Captura de pantalla de la página de análisis de Express](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="77e80-112">En **parámetros de análisis**:</span><span class="sxs-lookup"><span data-stu-id="77e80-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="77e80-p103">Si desea ejecutar el análisis, marque **calcular Near-duplicados y conversaciones de correo electrónico** . Está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77e80-p103">Check **Calculate near-duplicates and email threads** if you want to run the analysis. It is selected by default.</span></span> 
    
  - <span data-ttu-id="77e80-p104">Marque la casilla **calcular temas** para procesar todos los archivos y asignarles temas. Está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77e80-p104">Check **Calculate Themes** to process all files and assign themes to them. It is selected by default.</span></span> 
    
3. <span data-ttu-id="77e80-117">En **destino de exportación**:</span><span class="sxs-lookup"><span data-stu-id="77e80-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="77e80-118">Consulte **Descargar en** el equipo local para descargar en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="77e80-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="77e80-119">Si comprueba **exportar a BLOB de Azure definido por el usuario** , también puede especificar una dirección URL de contenedor y un token de SAS.</span><span class="sxs-lookup"><span data-stu-id="77e80-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="77e80-p105">Una vez que un paquete de exportación se almacena en el BLOB de Azure definido por el usuario, los datos ya no se administran mediante la exhibición avanzada de documentos electrónicos. se administra mediante el BLOB de Azure. Esto significa que, al eliminar el caso, los archivos exportados seguirán en el BLOB de Azure.</span><span class="sxs-lookup"><span data-stu-id="77e80-p105">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery. it is managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="77e80-123">**Guardar token de SAS para sesión de exportación en el futuro**: si se activa, el token de SAS se cifrará en la base de datos interna de eDiscovery avanzado para su uso en el futuro.</span><span class="sxs-lookup"><span data-stu-id="77e80-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="77e80-p106">Actualmente, el token de SAS expira después de un mes. Si intenta descargar después de más de un mes, deshaga la última sesión y, a continuación, vuelva a exportar.</span><span class="sxs-lookup"><span data-stu-id="77e80-p106">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="77e80-126">Para iniciar el análisis de Express con la configuración predeterminada, elija **análisis rápido**y aparecerá la página estado de la **tarea** .</span><span class="sxs-lookup"><span data-stu-id="77e80-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="77e80-127">En la **Página estado** de la tarea, puede ampliar las pestañas **proceso**, **analizar** y **exportar** para mostrar detalles sobre la ejecución rápida.</span><span class="sxs-lookup"><span data-stu-id="77e80-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![Captura de pantalla de la página de estado de tarea de análisis avanzado de eDiscovery Express](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="77e80-129">Seleccione la página **Resumen de análisis urgente** para enumerar la información detallada sobre la ejecución.</span><span class="sxs-lookup"><span data-stu-id="77e80-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="77e80-p107">En la parte inferior de la página **Resumen de análisis urgente** , elija **Descargar última sesión** para descargar los archivos de análisis (TP) en el equipo local. Primero tendrá que descargar la herramienta de exportación de exhibición de documentos electrónicos y pegar la clave de exportación a la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="77e80-p107">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer. You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="77e80-132">Configuración avanzada de análisis rápido</span><span class="sxs-lookup"><span data-stu-id="77e80-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="77e80-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="77e80-133"></span></span>

<span data-ttu-id="77e80-134">Opcionalmente, puede establecer la **Configuración avanzada** para cambiar los parámetros predeterminados de análisis de Express.</span><span class="sxs-lookup"><span data-stu-id="77e80-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="77e80-135">En la sección **analizar** :</span><span class="sxs-lookup"><span data-stu-id="77e80-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="77e80-136">En las **conversaciones de correo electrónico y los duplicaDos Near**, escriba el valor de **similitud del documento** o acepte el valor predeterminado de 65%.</span><span class="sxs-lookup"><span data-stu-id="77e80-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="77e80-p108">En el **número máximo de temas** , escriba o seleccione un valor para el número de temas que se va a crear. El valor predeterminado es 200.</span><span class="sxs-lookup"><span data-stu-id="77e80-p108">In the **Max number of themes** enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="77e80-p109">El aumento del número de temas afecta al rendimiento, así como la capacidad de un tema de generalizar. Cuanto mayor sea el número de temas, más granular serán. Por ejemplo, si un conjunto de 50 temas incluye un tema como "baloncesto, podas, Clippers, Lagoros"; 300 temas pueden incluir temas separados: "", "," podadoras "," lago ". Si no ha tenido conocimiento del tema "baloncesto" y usa esta característica para ECA, puede resultar útil ver el tema "baloncesto". Sin embargo, si el procesamiento tenía demasiados temas, es posible que nunca vea la palabra "baloncesto" y que no sepa que las pausas y las Clippers son buenos temas de baloncesto que revisar, en lugar de que se inician y se usan para el pelo.</span><span class="sxs-lookup"><span data-stu-id="77e80-p109">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="77e80-p110">En los **temas sugeridos** , elija **modificar** para sugerir palabras del tema para controlar el procesamiento de temas. EDiscovery avanzado se centrará en estas palabras sugeridas y intentará crear uno o más temas relevantes, en función de la configuración del "número máximo de temas".</span><span class="sxs-lookup"><span data-stu-id="77e80-p110">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="77e80-p111">Por ejemplo, si la palabra sugerida es "equipo" y ha especificado "2" como "número máximo de temas", la exhibición avanzada de documentos electrónicos intentará generar dos temas relacionados con la palabra "equipo". Por ejemplo, los dos temas podrían ser "software de equipo" y "hardware de equipo".</span><span class="sxs-lookup"><span data-stu-id="77e80-p111">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![Agregar tema sugerido](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="77e80-149">**Modo** En la lista desplegable, seleccione una opción de **temas** :</span><span class="sxs-lookup"><span data-stu-id="77e80-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="77e80-150">**Crear y aplicar modelo**: calcula los temas por modelos de un segmento de los archivos y, a continuación, distribuye los archivos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="77e80-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="77e80-p112">**Create Model**: calcula un modelo de temas a partir de un segmento de los archivos. El proceso de aplicar divisiones de archivos se realiza por separado en otro momento.</span><span class="sxs-lookup"><span data-stu-id="77e80-p112">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="77e80-p113">**Aplicar modelo**: esta opción solo se muestra si un modelo se ha creado anteriormente y todavía no se ha aplicado. Se dividirán los archivos según los temas.</span><span class="sxs-lookup"><span data-stu-id="77e80-p113">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="77e80-155">En la sección **exportar** :</span><span class="sxs-lookup"><span data-stu-id="77e80-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="77e80-156">En el **Seleccione lote de exportación**:</span><span class="sxs-lookup"><span data-stu-id="77e80-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="77e80-157">En la lista **exportar lote** , seleccione el nombre del lote o exportar resultados al lote de exportación 01, (el lote predeterminado).</span><span class="sxs-lookup"><span data-stu-id="77e80-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="77e80-p114">Para exportar los resultados de los nuevos archivos que agregó a un caso existente, continúe con el lote actual. Para crear una sesión en el lote, seleccione el mismo número de lote y haga clic en **crear sesión de exportación** puede usar esta opción para exportar los mismos parámetros que el lote anterior, de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="77e80-p114">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="77e80-p115">Para exportar a un nuevo lote, haga \*\*\*\*![clic en agregar](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icono Agregar y escriba un nuevo nombre en **nombre de lote** (o acepte el valor predeterminado) y una descripción en **Descripción del lote**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="77e80-p115">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="77e80-162">Para editar un nombre de lote o una descripción, seleccione el nombre en **lote de exportación**, haga](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)clic en **Editar** ![icono Editar y, a continuación, modifique los campos.</span><span class="sxs-lookup"><span data-stu-id="77e80-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="77e80-p116">Después de ejecutar sesiones para un lote de exportación, no se pueden eliminar. Además, solo algunos parámetros pueden editarse una vez ejecutada la primera sesión.</span><span class="sxs-lookup"><span data-stu-id="77e80-p116">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="77e80-165">Para crear un lote de exportación duplicado \*\*\*\*![, elija duplicar lote de exportación cree un](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) icono de exportación de lote duplicado y escriba un nombre y una descripción para el lote duplicado en el panel.</span><span class="sxs-lookup"><span data-stu-id="77e80-165">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="77e80-166">Para eliminar un lote de exportación, elija **eliminar**![eliminar lote de exportación](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span><span class="sxs-lookup"><span data-stu-id="77e80-166">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="77e80-167">Para ver el historial de un lote, seleccione icono![](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)de historial de vista de **historial por lotes**.</span><span class="sxs-lookup"><span data-stu-id="77e80-167">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="77e80-p117">En definir p? **opulation:** seleccione **incluir sólo los archivos** que superen la puntuación de recorte de relevancia o refinar el **lote de exportación** si desea ajustar la configuración del lote de exportación. Si selecciona **incluir sólo los archivos**de la puntuación de recorte de la relevancia, el **problema** está habilitado y, si la puntuación de relevancia del archivo es superior a la puntuación de corte para el problema seleccionado, el archivo se exportará. El archivo se exportará a menos que el filtro " **para revisión** " lo excluya. Si selecciona refinar **lote de exportación**, los botones de opción desduplicación y **filtrar por "para revisión"** están habilitados. \*\*\*\* Si elige desduplicación, los archivos duplicados se filtrarán de acuerdo con la Directiva definida: [nivel de caso (predeterminado): de cada conjunto de archivos duplicados en todo el caso, se desduplicarán todos los archivos menos uno. \*\*\*\* Nivel de custodio: de cada conjunto de archivos duplicados del mismo custodio, se desduplicarán todos menos un archivo. Hay disponible un registro de todos los archivos duplicados en la salida de la exportación. Si elige **filtrar por ' para revisión '** , seleccione **modificar en metadatos** para escribir la configuración del campo **' para revisión '**. Seleccione **incluir archivos de entrada**para incluir los archivos de origen en el contenido del paquete. Puede desactivar esta opción para acelerar el proceso de exportación. Tenga en cuenta que los archivos nativos se exportarán en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="77e80-p117">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch. If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported. The file will be exported unless it's excluded by the ' **For review** filter. If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled. If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped. A record of all duplicate files is available in export output. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files**to include source files in the package content. You can clear this option to speed up the export process. Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="77e80-179">En **definir metadatos**, seleccione una de las siguientes opciones de la lista **exportar plantilla** (una vez por sesión).</span><span class="sxs-lookup"><span data-stu-id="77e80-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="77e80-p118">**Standard**: conjunto básico de elementos de datos, metadatos y propiedades. Use esta opción si ya se procesó la importación de datos en eDiscovery avanzado y los datos de exportación se cargan en un sistema que ya contiene los archivos. De forma predeterminada, las columnas de plantilla de exportación se crean y se rellenan.</span><span class="sxs-lookup"><span data-stu-id="77e80-p118">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="77e80-p119">**All**: conjunto completo de metadatos estándar, incluidos todos los datos de procesamiento, así como los resultados del análisis y la relevancia. Esta plantilla es necesaria cuando la exhibición avanzada de documentos electrónicos realiza el procesamiento y los datos de archivos se cargan en un sistema externo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="77e80-p119">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="77e80-185">**Problemas**: seleccione **todos los problemas** o seleccione un asunto concreto que haya creado.</span><span class="sxs-lookup"><span data-stu-id="77e80-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="77e80-186">Elija **Aceptar**para guardar la configuración avanzada, **restaurar** los valores predeterminados para usar los valores predeterminados o **Cancelar** para cancelar la configuración avanzada.</span><span class="sxs-lookup"><span data-stu-id="77e80-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77e80-187">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77e80-187">See also</span></span>
<span data-ttu-id="77e80-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="77e80-188"></span></span>

[<span data-ttu-id="77e80-189">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="77e80-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

