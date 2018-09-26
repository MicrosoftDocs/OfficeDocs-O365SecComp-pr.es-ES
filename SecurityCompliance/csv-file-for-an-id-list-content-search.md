---
title: Preparar un archivo CSV para una lista de identificadores de búsqueda de contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Usar el archivo Results.csv o Items.csv no indizados desde una búsqueda de contenido existente para crear una búsqueda de la lista de identificador que devuelve los mensajes de correo electrónico específica. Las búsquedas de lista de identificador normalmente se utilizan para devolver los elementos del buzón parcialmente indizados.
ms.openlocfilehash: 9a7583c8f83626afb8dc0452bf72d834c8a28275
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038283"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="81b55-104">Preparar un archivo CSV para una lista de identificadores de búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="81b55-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="81b55-p102">Puede buscar mensajes de correo electrónico del buzón de correo específico y otros elementos de buzón de correo con una lista de identificadores de Exchange. Para crear una búsqueda en la lista ID (anteriormente denominada una búsqueda de destino), enviar un archivo (CSV) de valores separados por comas que identifica los elementos de buzón específico para buscar. Para este archivo CSV se usa el archivo **Results.csv** o el archivo **Items.csv no indizados** que se incluyen al exportar los resultados de búsqueda de contenido o exportar un informe de búsqueda de contenido desde y búsqueda de contenido existente. A continuación, edite uno de estos archivos para indicar los elementos específicos para buscar y, a continuación, crear una nueva búsqueda de la lista de identificador y enviar el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="81b55-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="81b55-109">Aquí es una introducción rápida al proceso de creación de una búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="81b55-110">Crear y ejecutar una búsqueda de contenido nuevo o guiada en la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="81b55-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="81b55-p103">Exportar los resultados de búsqueda de contenido o exportar el informe de búsqueda de contenido. Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="81b55-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="81b55-113">Exportar los resultados de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="81b55-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="81b55-114">Exportar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="81b55-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="81b55-p104">Editar el archivo **Results.csv** o la **Items.csv sin indizar** e identificar los elementos del buzón específico que desea incluir en la búsqueda de la lista de ID. Vea las [instrucciones](#prepare-the-csv-file-for-an-id-list-search) para la preparación de un archivo CSV para una búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="81b55-p105">Crear una nueva lista de identificador de búsqueda (vea las [instrucciones](#create-an-id-list-search)) y enviar el archivo CSV que ha preparado. La consulta de búsqueda que se crea sólo buscará los elementos seleccionados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="81b55-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="81b55-p106">Solo se admiten las búsquedas de lista de identificador para los elementos del buzón. No se puede buscar para SharePoint y búsqueda de documentos de OneDrive en un identificador de lista.</span><span class="sxs-lookup"><span data-stu-id="81b55-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="81b55-p107">**¿Por qué crear una búsqueda de identificador de lista?** Si no puede determinar que si un elemento responde a una solicitud de exhibición de documentos electrónicos en función de los metadatos en los archivos **Results.csv** o **Items.csv sin indizar** , puede usar una búsqueda de identificador de lista para buscar, obtener una vista previa y, a continuación, exportar ese elemento para determinar si tiene capacidad de respuesta para el caso de que esté investigar. Las búsquedas de lista de identificador normalmente se usan para buscar y devolver un conjunto específico de elementos sin indizar.</span><span class="sxs-lookup"><span data-stu-id="81b55-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="81b55-124">Preparar el archivo CSV para una búsqueda de la lista de Id.</span><span class="sxs-lookup"><span data-stu-id="81b55-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="81b55-p108">Después de exportar los resultados de búsqueda o del informe para una búsqueda de contenido, puede realizar los siguientes pasos para preparar el archivo CSV para una búsqueda de la lista de ID. Este archivo CSV identificará todos los elementos de la búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="81b55-p109">Tenga en cuenta que puede usar un archivo CSV de una búsqueda que incluye las cuentas de OneDrive y sitios de SharePoint, pero puede seleccionar *sólo* los elementos de buzón de correo para una búsqueda de la lista de ID. Si selecciona un documento en SharePoint o OneDrive, el archivo CSV se producirá un error validación al crear una búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="81b55-129">Abra el archivo **Results.csv** o **Items.csv no indizados** en Excel.</span><span class="sxs-lookup"><span data-stu-id="81b55-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="81b55-p110">Insertar una nueva columna y asígnele el nombre **seleccionado**. No importa dónde insertar la columna. Para mayor comodidad, considere la posibilidad de inserción a la izquierda de la primera columna.</span><span class="sxs-lookup"><span data-stu-id="81b55-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="81b55-p111">En la columna **seleccionado** , escriba **Sí** en la celda que se corresponde con el elemento que se desea buscar. Repita este paso para cada elemento que se desea buscar.</span><span class="sxs-lookup"><span data-stu-id="81b55-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="81b55-p112">Cuando abra el archivo CSV en Excel, se cambia el formato de datos para la columna de **ID de documento** a **General**. Esto da como resultado de mostrar el ID de documento para un elemento en la notación científica. Por ejemplo, el documento que se muestra el identificador de "481037338205" como "4.81037E + 11" se debe realizar los siguientes pasos para cambiar el formato de datos de la columna de **ID de documento** a **número** para restaurar el formato correcto para el ID de documento. Si no es así, se producirá un error en la búsqueda de la lista de identificador que usa el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="81b55-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="81b55-139">Haga clic en toda la columna de **ID de documento** y seleccione el **Formato de celdas**.</span><span class="sxs-lookup"><span data-stu-id="81b55-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="81b55-140">En el cuadro **categoría** , haga clic en **número**.</span><span class="sxs-lookup"><span data-stu-id="81b55-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="81b55-p113">Cambiar el número de posiciones decimales en **0**y, a continuación, haga clic en **Aceptar** para guardar los cambios. Tenga en cuenta que se cambian los valores en la columna de ID de documento a los números.</span><span class="sxs-lookup"><span data-stu-id="81b55-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="81b55-143">Este es un ejemplo de la un archivo CSV que está listo para ser enviado para una búsqueda de contenido de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![Ejemplo de un archivo CSV para una búsqueda de contenido dirigido](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="81b55-p114">Guarde el archivo CSV o use **Guardar como** para guardar el archivo con otro nombre de archivo. En ambos casos, asegúrese de guardar el archivo con el formato CSV.</span><span class="sxs-lookup"><span data-stu-id="81b55-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="81b55-147">Crear una búsqueda de la lista de Id.</span><span class="sxs-lookup"><span data-stu-id="81b55-147">Create an ID list search</span></span>

<span data-ttu-id="81b55-148">El siguiente paso es crear una nueva lista de identificadores de búsqueda de contenido y enviar el archivo CSV que ha preparado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="81b55-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="81b55-p115">Debe crear una búsqueda de identificador de lista no más de 2 días después de exportar los resultados o el informe de una búsqueda de contenido. Si la búsqueda de resultados o del informe donde exportado desde hace más de 2 días, debe volver a exportar los resultados de búsqueda o el informe para generar archivos CSV actualizados. A continuación, puede preparar uno de los archivos CSV actualizados y usarla para crear una búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="81b55-152">En la seguridad &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> **búsqueda de contenido**.</span><span class="sxs-lookup"><span data-stu-id="81b55-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="81b55-153">En la página de **búsqueda** , haga clic en la flecha junto a ![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nueva búsqueda**y, a continuación, haga clic en **Buscar por identificador de lista**.</span><span class="sxs-lookup"><span data-stu-id="81b55-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![Haga clic en Buscar por identificador de lista en la lista desplegable de búsqueda nueva](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="81b55-155">En la barra flotante **por identificador de lista de búsqueda** , asigne el nombre de la búsqueda (y, opcionalmente, describirlo) y, a continuación, haga clic en **Examinar** y seleccione el archivo CSV que ha preparado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="81b55-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="81b55-p116">Office 365 intenta validar el archivo CSV. Si la validación se realiza correctamente, se muestra un mensaje de error que pueden ayudar a solucionar los errores de validación. El archivo CSV debe validarse correctamente para crear una búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="81b55-159">Después de la CSV archivo se valida correctamente, haga clic en **búsqueda** para crear la búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="81b55-160">Este es un ejemplo de los resultados de búsqueda estimado y la consulta que se genera para una búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![Consulta de búsqueda para una búsqueda de contenido de destino en el panel de detalles](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="81b55-162">Tenga en cuenta que el número de elementos estimados que se muestran en las estadísticas de la búsqueda de identificador debe coincidir con el número de elementos que seleccionó en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="81b55-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="81b55-163">Obtener una vista previa o exportar los elementos devueltos por la búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="81b55-p117">Si mueve un buzón de correo después de crear una búsqueda de la lista de Id., la consulta para la búsqueda no devuelve los elementos especificados. Esto es debido a que la propiedad **DocumentId** para los elementos del buzón se cambian cuando se mueve un buzón de correo. En la instancia de poco frecuente cuando se mueve un buzón de correo después de crear una búsqueda de identificador de lista, debe crear una nueva búsqueda de contenido (o actualizar los resultados de búsqueda para la búsqueda de contenido existente) y, a continuación, exportar la búsqueda de resultados o del informe para generar archivos CSV actualizados que se pueden usar  Para crear una nueva búsqueda de la lista de ID.</span><span class="sxs-lookup"><span data-stu-id="81b55-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 
