---
title: Usar análisis rápido en eDiscovery avanzado de Office 365
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Obtenga información sobre cómo ejecutar el modo de análisis Express de exhibición de documentos electrónicos avanzada de Office 365
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536060"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="f9a40-103">Usar análisis rápido en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="f9a40-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="f9a40-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f9a40-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f9a40-106">Puede usar **Express análisis** para analizar rápidamente un caso y exportar los resultados.</span><span class="sxs-lookup"><span data-stu-id="f9a40-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="f9a40-p102">Puede usar análisis express para calcular cerca de duplicados y subprocesos de correo electrónico y calcular los temas. También puede establecer determinados parámetros para temas, similitud de documento y los archivos de exportación en la [Configuración avanzada para el análisis de Express](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span><span class="sxs-lookup"><span data-stu-id="f9a40-p102">You can use express analysis to calculate near-duplicates and email threads and calculate themes. You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="f9a40-109">Ejecutar el análisis de Express</span><span class="sxs-lookup"><span data-stu-id="f9a40-109">Run Express analysis</span></span>

1. <span data-ttu-id="f9a40-110">En la ficha **análisis Express** (1), seleccione un contenedor para habilitar la ** Express análisis ** (2) y los botones de **Configuración avanzada** .</span><span class="sxs-lookup"><span data-stu-id="f9a40-110">In the **Express analysis** (1) tab, select a container to enable the ** Express analysis ** (2), and **Advanced settings** buttons.</span></span> 
    
    ![Captura de pantalla de la página de análisis de Express](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="f9a40-112">En los **parámetros de análisis**:</span><span class="sxs-lookup"><span data-stu-id="f9a40-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="f9a40-p103">Comprobar **calcular cerca de duplicados y subprocesos de correo electrónico** si desea ejecutar el análisis. Se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p103">Check **Calculate near-duplicates and email threads** if you want to run the analysis. It is selected by default.</span></span> 
    
  - <span data-ttu-id="f9a40-p104">Comprobar **Calcular temas** para procesar todos los archivos y asignar los temas a ellos. Se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p104">Check **Calculate Themes** to process all files and assign themes to them. It is selected by default.</span></span> 
    
3. <span data-ttu-id="f9a40-117">En la **exportación de destino**:</span><span class="sxs-lookup"><span data-stu-id="f9a40-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="f9a40-118">Compruebe la **descarga en el equipo local** para descargar en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="f9a40-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="f9a40-119">Si marca **Exportar a blob Azure definidas por el usuario** también puede especificar un token de dirección URL y SAS de contenedor.</span><span class="sxs-lookup"><span data-stu-id="f9a40-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f9a40-p105">Una vez que se almacena un paquete de exportación para el usuario definido Azure blob, los datos ya no se administran mediante avanzada exhibición de documentos electrónicos. se administra mediante el blob de Azure. Esto significa que si se elimina el caso, los archivos exportados seguirá estando en el blob de Azure.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p105">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery. it is managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="f9a40-123">**Guardar SAS símbolo (token) de sesión de exportación futuras**: si está activado, el token de SAS se cifrarán en la base de datos interna de la exhibición de documentos avanzadas para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f9a40-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9a40-p106">Actualmente, el token de SAS expira después de un mes. Si se intenta descargar después de más de un mes que tenga que deshacer la última sesión, a continuación, exportar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p106">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="f9a40-126">Para iniciar el análisis express con predeterminada configuración, elija **Express análisis**y se mostrará la página de **estado de la tarea**</span><span class="sxs-lookup"><span data-stu-id="f9a40-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="f9a40-127">En la página de **estado de la tarea** se pueden expandir las fichas de **proceso**, **analizar** y **Exportar** para mostrar detalles acerca de la ejecución de express.</span><span class="sxs-lookup"><span data-stu-id="f9a40-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![Captura de pantalla de avanzada página de estado de tarea de exhibición de documentos electrónicos Express análisis](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="f9a40-129">Elija la página **Resumen de análisis de Express** para obtener información detallada acerca de la ejecución de la lista.</span><span class="sxs-lookup"><span data-stu-id="f9a40-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="f9a40-p107">En la parte inferior de la página **Resumen de análisis de Express** , elija **Descargar la última sesión** para descargar el tp de los archivos de análisis en el equipo local. En primer lugar deberá descargar la herramienta de exportación de exhibición de documentos electrónicos y pegue la clave de exportación para la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p107">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer. You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="f9a40-132">Configuración avanzada para el análisis de Express</span><span class="sxs-lookup"><span data-stu-id="f9a40-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="f9a40-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="f9a40-133"></span></span>

<span data-ttu-id="f9a40-134">Opcionalmente puede establecer la **Configuración avanzada** para cambiar los parámetros de análisis de Express de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f9a40-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="f9a40-135">En la sección **analizar** :</span><span class="sxs-lookup"><span data-stu-id="f9a40-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="f9a40-136">En el **próximo duplicados y subprocesos de correo electrónico**, escriba el valor de **similitud de documento** o acepte el valor predeterminado de 65%.</span><span class="sxs-lookup"><span data-stu-id="f9a40-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="f9a40-p108">En el **número máximo de temas** Introduzca o seleccione un valor para el número de temas para crear. El valor predeterminado es 200.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p108">In the **Max number of themes** enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f9a40-p109">El aumento del número de temas afecta al rendimiento, así como la capacidad de un tema para generalizar. Cuanto mayor sea el número de temas, más granulares son. Por ejemplo, si un conjunto de 50 temas incluye un tema, como "Baloncesto, cambio, cortar, Lakers"; temas de 300 pueden incluir temas independientes: "Cual insta", "Cortar", "Lakers". Si no tenía ningún conocimiento del tema "Baloncesto" y usar esta característica para ECA, vea el tema "Baloncesto" podría ser útil. Sin embargo, si el procesamiento tenía demasiados temas, es posible que vea nunca la palabra "Baloncesto" y no puede saber que cambio y cortar es una buena temas baloncesto para revisar, en lugar de los elementos que vaya de se inicia y se usa de forma.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p109">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="f9a40-p110">En los **temas que se sugiere** elija **Modificar** para sugerir palabras de tema para controlar el procesamiento de temas. Exhibición de documentos electrónicos avanzada se centrarse en estas palabras sugeridas y pruebe a crear uno o varios temas relevantes, en función de la configuración de "Número de temas de Max".</span><span class="sxs-lookup"><span data-stu-id="f9a40-p110">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="f9a40-p111">Por ejemplo, si la palabra sugerida es "computer", y especificó "2" como el "número de temas de Max", intentará avanzada exhibición de documentos electrónicos generar dos temas que se relacionan con la palabra "equipo". Los dos temas podrían ser "software informático" y "hardware del equipo", por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p111">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![Agregar tema sugerido](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="f9a40-149">**Modo** En la lista desplegable, seleccione una opción de **temas** :</span><span class="sxs-lookup"><span data-stu-id="f9a40-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="f9a40-150">**Crear y aplicar el modelo de**: calcula los temas por modelos de un segmento de los archivos y, a continuación, distribuye los archivos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="f9a40-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="f9a40-p112">**Crear modelo**: calcula un modelo de temas de un segmento de los archivos. El proceso de aplicación de dividir los archivos se realiza por separado en otro momento.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p112">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="f9a40-p113">**Aplicar modelo**: esta opción sólo se muestra si un modelo se ha creado anteriormente y todavía no se ha aplicado. Esto dividirá los archivos basándose en los temas.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p113">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="f9a40-155">En la sección **Exportar** :</span><span class="sxs-lookup"><span data-stu-id="f9a40-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="f9a40-156">En la **sección de exportación Select**:</span><span class="sxs-lookup"><span data-stu-id="f9a40-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="f9a40-157">En la lista **Exportar por lotes** , seleccione el nombre del lote o exportar los resultados a la sección de exportación 01, (el lote de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="f9a40-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="f9a40-p114">Para exportar los resultados de los archivos nuevos que ha agregado a un caso existente, continúe con el lote actual. Para crear una sesión en el lote, seleccione el mismo número de lote y haga clic en **crear exportación sesión** puede usar esta opción para exportar los mismos parámetros como el lote anterior, de manera incremental.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p114">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="f9a40-p115">Para exportar a un nuevo lote, haga clic en **Agregar**![agregar icono](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) y especifique un nuevo nombre en **nombre de lote** (o acepte el valor predeterminado) y una descripción en la **Descripción de lote**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p115">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="f9a40-162">Para editar un nombre de proceso por lotes o una descripción, seleccione el nombre de **exportación por lotes**, haga clic en **Editar** ![icono Editar](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)y, a continuación, modifique los campos.</span><span class="sxs-lookup"><span data-stu-id="f9a40-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9a40-p116">Una vez ejecutado el sesiones de una sección de exportación, no se puede eliminar. Además, se pueden editar sólo algunos parámetros una vez que se ejecuta la primera sesión.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p116">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="f9a40-165">Para crear un lote de exportación duplicados, elija **por lotes de exportación de duplicado**![crear un icono de proceso por lotes de exportación duplicados](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) y escriba un nombre y una descripción para el lote de duplicados en el panel.</span><span class="sxs-lookup"><span data-stu-id="f9a40-165">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="f9a40-166">Para eliminar una sección de exportación, elija **Eliminar**![eliminar un icono de exportación de lote](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span><span class="sxs-lookup"><span data-stu-id="f9a40-166">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="f9a40-167">Para ver el historial de un lote, elija **Historial por lotes**![icono de vista de historial](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span><span class="sxs-lookup"><span data-stu-id="f9a40-167">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="f9a40-p117">En definir p **opulation:** seleccione **incluir solo los archivos por encima de la puntuación de relevancia corte** o **por lotes de exportación de refinar** si desea ajustar la configuración de la sección de exportación. Si selecciona **incluir sólo archivos por encima de la puntuación de relevancia corte**, a continuación, se habilita el **problema** y, si la puntuación de relevancia del archivo es mayor que la puntuación de límite para el problema seleccionado, a continuación, se exporta el archivo. El archivo se exportará a menos que lo excluye la ' filtro **para su revisión** . Si selecciona **por lotes de exportación de refinar**, a continuación, la **desduplicación** y **Filter by 'Para revisión' campo** se habilitan los botones de opción. Si elige **la desduplicación**, a continuación, los archivos duplicados se se filtran-out según la directiva definida: [Case nivel (valor predeterminado): de cada conjunto de archivos duplicados en el caso todo, será desaprovisionamiento duped todos menos un archivo. Nivel de custodia: de cada conjunto de archivos duplicados de la misma custodia, será desaprovisionamiento duped todos menos un archivo. Un registro de todos los archivos duplicados está disponible en los resultados de la exportación. Si elige **filtrar por 'para revisión'** campo, seleccione **modificar en metadatos** para escribir la configuración de campo **'para revisión'**. Seleccione **incluir los archivos de entrada**para incluir los archivos de origen en el contenido del paquete. Puede desactivar esta opción para acelerar el proceso de exportación. Tenga en cuenta que se exportará los archivos nativos en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p117">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch. If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported. The file will be exported unless it's excluded by the ' **For review** filter. If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled. If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped. A record of all duplicate files is available in export output. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files**to include source files in the package content. You can clear this option to speed up the export process. Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="f9a40-179">En **definir metadatos**, seleccione entre las siguientes opciones en la lista **plantilla de exportación** (una vez por sesión).</span><span class="sxs-lookup"><span data-stu-id="f9a40-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="f9a40-p118">**Estándar**: conjunto básico de propiedades, metadatos y elementos de datos. Use esta opción cuando importar datos ya se procesan en la exhibición de documentos electrónicos avanzada y exportar datos se carguen a un sistema que ya contiene los archivos. De forma predeterminada, se crean las columnas de plantilla de exportación y se rellena.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p118">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="f9a40-p119">**Todos los**: conjunto completo de metadatos estándar, incluidos todos los datos de procesamiento, así como las puntuaciones de análisis y la relevancia. Esta plantilla se requiere cuando exhibición de documentos electrónicos avanzada realiza el procesamiento y datos de archivo se carguen a un sistema externo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f9a40-p119">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="f9a40-185">**Problemas**: seleccione **Todos los problemas** o seleccione un problema determinado que haya creado.</span><span class="sxs-lookup"><span data-stu-id="f9a40-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="f9a40-186">Elija **Aceptar**, para guardar la configuración avanzada, **restaurar la configuración predeterminada** para utilizar los valores predeterminados o **Cancelar** para cancelar la configuración de la configuración avanzada.</span><span class="sxs-lookup"><span data-stu-id="f9a40-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f9a40-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9a40-187">See also</span></span>
<span data-ttu-id="f9a40-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="f9a40-188"></span></span>

[<span data-ttu-id="f9a40-189">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="f9a40-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

