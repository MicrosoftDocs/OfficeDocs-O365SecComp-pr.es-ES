---
title: Preparar un archivo CSV para una búsqueda de contenido de la lista de IDENTIFICADOres en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Use el archivo Results. csv o unindexed items. csv de una búsqueda de contenido existente para crear una búsqueda de lista de IDENTIFICADOres que devuelva un mensaje de correo electrónico específico. Las búsquedas de listas de IDENTIFICADOres se usan normalmente para devolver elementos de buzón parcialmente indizados.
ms.openlocfilehash: 558a8512ed133995b2cc1d0d8b78fd7f08d11168
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296743"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="7d8f2-104">Preparar un archivo CSV para una búsqueda de contenido de la lista de IDENTIFICADOres en Office 365</span><span class="sxs-lookup"><span data-stu-id="7d8f2-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="7d8f2-p102">Puede buscar mensajes de correo electrónico específicos de buzones de correo y otros elementos de buzón mediante una lista de identificadores de Exchange. Para crear una búsqueda de lista de IDENTIFICADOres (anteriormente denominada búsqueda dirigida), envíe un archivo de valores separados por comas (CSV) que identifique los elementos de buzón específicos que se van a buscar. Para este archivo CSV, use el archivo **Results. csv** o el archivo **Items. csv** sin indexar que se incluyen al exportar los resultados de la búsqueda de contenido o a exportar un informe de búsqueda de contenido desde y búsqueda de contenido existente. A continuación, edite uno de estos archivos para indicar los elementos específicos que se deben buscar y, a continuación, cree una nueva búsqueda de la lista de IDENTIFICADOres y envíe el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="7d8f2-109">A continuación se muestra una introducción rápida del proceso para crear una búsqueda de lista de IDENTIFICADOres.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="7d8f2-110">Cree y ejecute una búsqueda de contenido nueva o guiada en el &amp; centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="7d8f2-p103">Exportar los resultados de la búsqueda de contenido o exportar el informe de búsqueda de contenido. Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="7d8f2-113">Exportar resultados de búsqueda de contenido desde el centro &amp; de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="7d8f2-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="7d8f2-114">Exportar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="7d8f2-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="7d8f2-p104">Edite el archivo **Results. csv** o sin **indizar items. csv** e identifique los elementos de buzón específicos que desea incluir en la búsqueda de la lista de ID. Vea las [instrucciones](#prepare-the-csv-file-for-an-id-list-search) para preparar un archivo CSV para una búsqueda de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="7d8f2-p105">Crear una nueva búsqueda de la lista de IDENTIFICADOres (consulte las [instrucciones](#create-an-id-list-search)) y enviar el archivo CSV que preparó. La consulta de búsqueda que se crea solo buscará los elementos seleccionados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7d8f2-p106">Las búsquedas de listas de IDENTIFICADOres solo se admiten para elementos de buzón. No puede buscar documentos de SharePoint y OneDrive en una búsqueda de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="7d8f2-p107">**¿Por qué crear una búsqueda de lista de identificadores?** Si no puede determinar si un elemento responde a una solicitud de exhibición de documentos electrónicos en función de los metadatos de los archivos **Results. csv** o sin **indexar items. csv** , puede usar una búsqueda de lista de identificadores para buscar, obtener una vista previa y, a continuación, exportar el elemento para determinar si está responde al caso que está investigando. Las búsquedas de listas de IDENTIFICADOres se usan normalmente para buscar y devolver un conjunto específico de elementos sin indizar.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="7d8f2-124">Preparar el archivo CSV para una búsqueda de lista de ID</span><span class="sxs-lookup"><span data-stu-id="7d8f2-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="7d8f2-p108">Después de exportar los resultados de búsqueda o el informe para una búsqueda de contenido, puede realizar los siguientes pasos para preparar el archivo CSV para una búsqueda de lista de ID. Este archivo CSV identificará todos los elementos de la búsqueda de la lista de IDENTIFICADOres.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="7d8f2-p109">Tenga en cuenta que puede usar un archivo CSV desde una búsqueda que incluya sitios de SharePoint y cuentas de OneDrive, pero *solo* puede seleccionar elementos de buzón para una búsqueda de lista de ID. Si selecciona un documento en SharePoint o OneDrive, el archivo CSV no superará la validación cuando se crea una búsqueda de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="7d8f2-129">Abra el archivo Results. **CSV** o **elementos** sin indexar en Excel.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="7d8f2-p110">Inserte una nueva columna y asígnele el nombre **seleccionado**. No importa dónde Inserte la columna. Para mayor comodidad, considere la posibilidad de insertarla a la izquierda de la primera columna.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="7d8f2-p111">En la columna **seleccionada** , escriba **yes** en la celda que corresponda al elemento que desea buscar. Repita este paso para cada elemento que desee buscar.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7d8f2-p112">Al abrir el archivo CSV en Excel, el formato de datos de la columna **identificador de documento** cambia a **General**. Esto da como resultado que se muestre el identificador de documento de un elemento en notación científica. Por ejemplo, el identificador de documento "481037338205" se muestra como "4.81037 E + 11" debe realizar los pasos siguientes para cambiar el formato de datos de la columna **identificador de documento** a **número** para restaurar el formato correcto para el identificador de documento. Si no lo hace, se producirá un error en la búsqueda de la lista de IDENTIFICADOres que usa el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="7d8f2-139">Haga clic con el botón secundario en la columna **identificador de documento** completo y seleccione **formato de celdas**.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="7d8f2-140">En el cuadro **categoría** , haga clic en **número**.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="7d8f2-p113">Cambie el número de posiciones decimales a **0**y, a continuación, haga clic en **Aceptar** para guardar los cambios. Observe que los valores de la columna identificador de documento cambian a números.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="7d8f2-143">Este es un ejemplo del archivo CSV que está listo para enviarse para una búsqueda de contenido de la lista de IDENTIFICADOres.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![Ejemplo de un archivo CSV para una búsqueda de contenido de destino](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="7d8f2-p114">Guarde el archivo CSV o use **Guardar como** para guardar el archivo con otro nombre de archivo. En ambos casos, asegúrese de guardar el archivo con el formato CSV.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="7d8f2-147">Crear una búsqueda de lista de IDENTIFICADOres</span><span class="sxs-lookup"><span data-stu-id="7d8f2-147">Create an ID list search</span></span>

<span data-ttu-id="7d8f2-148">El siguiente paso es crear una nueva búsqueda de contenido de la lista de IDENTIFICADOres y enviar el archivo CSV que preparó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7d8f2-p115">Debe crear una búsqueda de lista de IDENTIFICADOres de más de 2 días después de exportar los resultados o el informe de una búsqueda de contenido. Si los resultados de la búsqueda o el informe en el que se exportó hace más de 2 días, debe volver a exportar los resultados de la búsqueda o informar para generar archivos. CSV actualizados. A continuación, puede preparar uno de los archivos CSV actualizados y utilizarlo para crear una búsqueda de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="7d8f2-152">En el centro &amp; de seguridad y cumplimiento, vaya a búsqueda de \> **contenido**de \*\*investigación de búsqueda &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="7d8f2-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="7d8f2-153">En la **página Buscar** , haga clic en la flecha ![junto a](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) agregar icono **nueva búsqueda**y, a continuación, haga clic en **Buscar por lista de identificadores**.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![Haga clic en buscar por lista de IDENTIFICADOres en la nueva lista desplegable de búsqueda](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="7d8f2-155">En el control flotante de la **lista Buscar por identificador** , asigne un nombre a la búsqueda (y, opcionalmente, describa) y, a continuación, haga clic en **examinar** y seleccione el archivo CSV que preparó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="7d8f2-p116">Office 365 intenta validar el archivo CSV. Si la validación no se realiza correctamente, se muestra un mensaje de error que puede ayudarle a solucionar los errores de validación. El archivo CSV tiene que validarse correctamente para crear una búsqueda de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="7d8f2-159">Una vez validado correctamente el archivo CSV, haga clic en **Buscar** para crear la búsqueda de la lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="7d8f2-160">Este es un ejemplo de los resultados de búsqueda estimados y la consulta que se genera para una búsqueda de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![Consulta de búsqueda para una búsqueda de contenido dirigida en el panel de detalles](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="7d8f2-162">Tenga en cuenta que el número de elementos estimados que se muestran en las estadísticas para la búsqueda ID debe coincidir con el número de elementos que seleccionó en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="7d8f2-163">Obtenga una vista previa o exporte los elementos devueltos por la búsqueda de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7d8f2-p117">Si mueve un buzón después de crear una búsqueda de lista de IDENTIFICADOres, la consulta de la búsqueda no devolverá los elementos especificados. Esto se debe a que la propiedad **DocumentId** para los elementos del buzón de correo se cambia cuando se mueve un buzón. En la instancia poco frecuente, cuando se mueve un buzón después de crear una búsqueda de lista de IDENTIFICADOres, debe crear una nueva búsqueda de contenido (o actualizar los resultados de búsqueda para la búsqueda de contenido existente) y, a continuación, exportar los resultados de la búsqueda o el informe para generar archivos. CSV actualizados que se puedan usar  para crear una nueva búsqueda de la lista de IDENTIFICADOres.</span><span class="sxs-lookup"><span data-stu-id="7d8f2-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 
