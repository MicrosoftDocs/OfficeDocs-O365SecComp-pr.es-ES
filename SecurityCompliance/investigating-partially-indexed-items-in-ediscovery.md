---
title: Investigar elementos indizados parcialmente en eDiscovery de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Elementos indizados parcialmente (también llamada no indexado elementos) son los elementos del buzón de Exchange y documentos en SharePoint y sitios de OneDrive para la que, por algún motivo no estaba indizado completamente para la búsqueda de contenido. En este artículo, obtenga información sobre por qué elementos no se pueden indizar para la búsqueda y se devuelven como elementos indizados parcialmente, identificar errores de búsqueda para los elementos indizados parcialmente y usar un script de PowerShell para determinar la exposición de su organización a correo electrónico parcialmente indizado elementos.
ms.openlocfilehash: c1003f9907fffa37042ba62d01e4d938250cf570
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749344"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="7985c-104">Investigar elementos indizados parcialmente en eDiscovery de Office 365</span><span class="sxs-lookup"><span data-stu-id="7985c-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="7985c-p102">Una búsqueda de contenido que se ejecuta desde la seguridad de Office 365 &amp; centro de cumplimiento incluye automáticamente los elementos indizados parcialmente en los resultados de búsqueda estimado al ejecutar una búsqueda. Los elementos indizados parcialmente son los elementos del buzón de Exchange y documentos en SharePoint y OneDrive para los sitios de negocio que, por algún motivo, completamente no estaban indizados para la búsqueda. La mayoría de los mensajes de correo electrónico y documentos del sitio se indizan correctamente debido a que se encuentren dentro de los [límites de indización para mensajes de correo electrónico](limits-for-content-search.md#indexing-limits-for-email-messages). Sin embargo, algunos elementos pueden superar estos límites de indización y se van a indizar parcialmente. Estas son otras razones por qué elementos no se pueden indizar para la búsqueda y se devuelven como elementos indizados parcialmente cuando se ejecuta una búsqueda de contenido:</span><span class="sxs-lookup"><span data-stu-id="7985c-p102">A Content Search that you run from the Office 365 Security &amp; Compliance Center automatically includes partially indexed items in the estimated search results when you run a search. Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search. Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages). However, some items may exceed these indexing limits, and will be partially indexed. Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="7985c-110">Mensajes de correo electrónico tienen un archivo adjunto de un tipo de archivo que no se pueden indizar; en la mayoría de los casos, es el tipo de archivo [no reconocido o no compatibles para la indización](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="7985c-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="7985c-111">Mensajes de correo electrónico tienen un archivo adjunto sin un controlador válido, como archivos de imagen; Ésta es la causa más común de los elementos de correo electrónico parcialmente indizados</span><span class="sxs-lookup"><span data-stu-id="7985c-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="7985c-112">Demasiados archivos adjuntados a un mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7985c-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="7985c-113">Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande</span><span class="sxs-lookup"><span data-stu-id="7985c-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="7985c-114">Se admite el tipo de archivo para la indización, pero se produjo un error de indización para un archivo específico</span><span class="sxs-lookup"><span data-stu-id="7985c-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="7985c-p103">Aunque varía, la mayoría de los clientes de las organizaciones de Office 365 tienen menos del 1% de contenido por volumen y menor que 12% del contenido por tamaño que se indiza parcialmente. El motivo de la diferencia entre el volumen frente a tamaño es que los archivos más grandes tienen una mayor probabilidad de que contiene contenido que no se pueden indizar completamente.</span><span class="sxs-lookup"><span data-stu-id="7985c-p103">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed. The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="7985c-117">¿Por qué se cambia el número de elementos indizados parcialmente para una búsqueda?</span><span class="sxs-lookup"><span data-stu-id="7985c-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="7985c-p104">Después de ejecutar una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento, el número total y el tamaño de los elementos indizados parcialmente en las ubicaciones que se han buscado aparecen en las estadísticas de resultados de búsqueda que se muestran en las estadísticas detalladas para la búsqueda. Tenga en cuenta que estos se denominan *elementos sin indizar* en las estadísticas de búsqueda. A continuación presentamos algunas cosas que afectarán al número de elementos indizados parcialmente que se devuelven en los resultados de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="7985c-p104">After you run a Content Search in the Office 365 Security &amp; Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search. Note these are called  *unindexed items*  in the search statistics. Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="7985c-p105">Si un elemento se indiza parcialmente y coincide con la consulta de búsqueda, se incluye en el recuento (y tamaño) de los elementos de resultado de búsqueda y los elementos indizados parcialmente. Sin embargo, cuando se exportan los resultados de la misma que la búsqueda, el elemento se incluye únicamente con el conjunto de resultados de búsqueda; no se incluye como un elemento indizado parcialmente.</span><span class="sxs-lookup"><span data-stu-id="7985c-p105">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items. However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="7985c-p106">Si especifica un intervalo de fechas para una consulta de búsqueda (incluidos en la consulta de palabras clave) o mediante una condición, cualquier elemento parcialmente indizado que no coincide con el intervalo de fechas no se incluye en el recuento de los elementos indizados parcialmente. Sólo los elementos indizados parcialmente que se encuentren dentro del intervalo de fechas se incluyen en el recuento de elementos indizados parcialmente.</span><span class="sxs-lookup"><span data-stu-id="7985c-p106">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items. Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="7985c-p107">**Nota:** Parcialmente indizar los elementos ubicados en SharePoint y OneDrive sitios que *no están* incluidos en la estimación de los elementos indizados parcialmente que se muestra en las estadísticas detalladas para la búsqueda. Sin embargo, se pueden exportar los elementos indizados parcialmente al exportar los resultados de una búsqueda de contenido. Por ejemplo, si sólo busca sitios en una búsqueda de contenido, el número estimado parcialmente los elementos indizados será cero.</span><span class="sxs-lookup"><span data-stu-id="7985c-p107">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search. However, partially indexed items can be exported when you export the results of a Content Search. For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="7985c-128">Calcula la proporción de elementos indizados parcialmente en la organización</span><span class="sxs-lookup"><span data-stu-id="7985c-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="7985c-p108">Para entender la exposición de la organización a los elementos indizados parcialmente, se puede ejecutar una búsqueda de todo el contenido en todos los buzones (mediante el uso de una consulta de palabra clave en blanco). En el siguiente ejemplo, hay 56,208 (4,830 MB) totalmente indizados elementos y 470 (316 MB) elementos indizados parcialmente.</span><span class="sxs-lookup"><span data-stu-id="7985c-p108">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query). In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Ejemplo de que muestra estadísticas de búsqueda elementos indizados parcialmente](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="7985c-132">Puede determinar el porcentaje de los elementos indizados parcialmente mediante el uso de los siguientes cálculos.</span><span class="sxs-lookup"><span data-stu-id="7985c-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="7985c-133">**Para calcular la proporción de elementos indizados parcialmente en su organización:**</span><span class="sxs-lookup"><span data-stu-id="7985c-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="7985c-134">Mediante el uso de los resultados de búsqueda del ejemplo anterior,. parcialmente se indizan 84% de todos los elementos de los buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="7985c-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="7985c-135">**Para calcular el porcentaje del tamaño de los elementos indizados parcialmente en su organización:**</span><span class="sxs-lookup"><span data-stu-id="7985c-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="7985c-p109">Por lo tanto en el ejemplo anterior, son 6.54% del tamaño total de los elementos del buzón de los elementos indizados parcialmente. Como se mencionó anteriormente, la mayoría de las organizaciones de Office 365 los clientes tienen menos del 1% de contenido por volumen y menor que 12% del contenido por tamaño que se indiza parcialmente.</span><span class="sxs-lookup"><span data-stu-id="7985c-p109">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items. As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="7985c-138">Trabajar con parcialmente elementos indizados</span><span class="sxs-lookup"><span data-stu-id="7985c-138">Working with partially indexed items</span></span>

<span data-ttu-id="7985c-p110">En los casos cuando se necesita examinar parcialmente los elementos para validar que no contienen información relevante, puede [exportar un informe de búsqueda de contenido](export-a-content-search-report.md) que contiene información acerca de los elementos indizados parcialmente. Al exportar un informe de búsqueda de contenido, asegúrese de elegir una de las opciones de exportación que incluye los elementos indizados parcialmente.</span><span class="sxs-lookup"><span data-stu-id="7985c-p110">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items. When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![Elija la segunda o tercera opción para exportar los elementos indizados parcialmente](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="7985c-p111">Al exportar los resultados de la búsqueda de contenido o un informe de búsqueda de contenido mediante una de estas opciones, la exportación incluye un informe denominado Items.csv sin indizar. Este informe incluye la mayor parte de la misma información que el archivo ResultsLog.csv; Sin embargo, el archivo Items.csv no indizados también incluye dos campos relacionados con los elementos indizados parcialmente: **Error etiquetas** y **Propiedades de Error**. Estos campos contienen información sobre el error de indización para cada elemento indizado parcialmente. Uso de la información en estos dos campos puede ayudarle a determinar si el error de indización para un determinado repercute en la investigación. Si es así, puede realizar una búsqueda de contenido dirigida y recuperar y exportar mensajes de correo electrónico específicos y documentos de SharePoint o OneDrive para que se pueden examinar para determinar si son relevantes para la investigación. Para obtener instrucciones detalladas, consulte [Prepare un archivo CSV para una búsqueda de contenido dirigido en Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="7985c-p111">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv. This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**. These fields contain information about the indexing error for each partially indexed item. Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation. If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation. For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="7985c-p112">**Nota:** El archivo Items.csv no indizados también contiene campos con el nombre de **Tipo de Error** y el **Mensaje de Error**. Estos son heredados campos que contienen información que es similar a la información en los campos de **Etiquetas de Error** y **Las propiedades de Error** , pero con menos información detallada. Puede omitir estos campos heredados.</span><span class="sxs-lookup"><span data-stu-id="7985c-p112">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**. These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information. You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="7985c-151">Errores relacionados con los elementos indizados parcialmente</span><span class="sxs-lookup"><span data-stu-id="7985c-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="7985c-p113">Etiquetas de error se componen de dos tipos de información, el error y el tipo de archivo. Por ejemplo, en este par error/filetype:</span><span class="sxs-lookup"><span data-stu-id="7985c-p113">Error tags are made up of two pieces of information, the error and the file type. For example, in this error/filetype pair:</span></span>

```
 parseroutputsize_xls
```

   
 <span data-ttu-id="7985c-p114">`parseroutputsize`es el error y `xls` es el tipo de archivo del archivo que se produjo el error. En los casos eran no se reconoció el tipo de archivo o el tipo de archivo no es aplicable para el error, podrá ver el valor `noformat` en lugar del tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="7985c-p114">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on. In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="7985c-156">La siguiente es una lista de la indización de errores y una descripción de la causa posible del error.</span><span class="sxs-lookup"><span data-stu-id="7985c-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="7985c-157">**Etiqueta de error**</span><span class="sxs-lookup"><span data-stu-id="7985c-157">**Error tag**</span></span>|<span data-ttu-id="7985c-158">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7985c-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="7985c-159">Un mensaje de correo tenía demasiados datos adjuntos, y algunos de estos datos adjuntos no se han procesado.</span><span class="sxs-lookup"><span data-stu-id="7985c-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="7985c-p115">El analizador de almacenes de datos y documentos contenido encontró demasiados niveles de datos adjuntos que se pueden anidados dentro de otros datos adjuntos. Algunos de estos datos adjuntos no se procesaron.</span><span class="sxs-lookup"><span data-stu-id="7985c-p115">The content retriever and document parser found too many levels of attachments nested inside other attachments. Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="7985c-162">Datos adjuntos no pudo descodificar debido a que era protegidos con RMS.</span><span class="sxs-lookup"><span data-stu-id="7985c-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="7985c-163">Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande y no se pudo procesar.</span><span class="sxs-lookup"><span data-stu-id="7985c-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="7985c-p116">Al escribir el mensaje de correo electrónico procesados en el índice, una de las propiedades se pueden indizar era demasiado grande y se ha truncado. Se enumeran las propiedades truncadas en el campo de propiedades de Error.</span><span class="sxs-lookup"><span data-stu-id="7985c-p116">When writing the processed email message to the index, one of the indexable properties was too large and was truncated. The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="7985c-p117">Un mensaje de correo electrónico contiene texto que no se pudo procesar como Unicode válido. Indización de este elemento puede ser incompleta.</span><span class="sxs-lookup"><span data-stu-id="7985c-p117">An email message contained text that couldn't be processed as valid Unicode. Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="7985c-168">Se cifra el contenido de los datos adjuntos o un mensaje de correo electrónico y Office 365 no se pudo descodificar el contenido.</span><span class="sxs-lookup"><span data-stu-id="7985c-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="7985c-p118">Se ha producido un error desconocido durante el análisis. Esto da como resultado normalmente desde un error de software o un bloqueo del servicio.</span><span class="sxs-lookup"><span data-stu-id="7985c-p118">An unknown error occurred during parsing. This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="7985c-171">Era demasiado grande para el analizador para tratar un archivo adjunto, y el análisis de dichos datos adjuntos no hizo o no se completó.</span><span class="sxs-lookup"><span data-stu-id="7985c-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="7985c-p119">Un archivo adjunto está mal formado y no se ha podido ser tratado por el analizador. Da formato a este resultado desde el archivo antiguo can, los archivos creados por el software incompatible o virus que pretende ser algo distinto de solicitado.</span><span class="sxs-lookup"><span data-stu-id="7985c-p119">An attachment was malformed and couldn't be handled by the parser. This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="7985c-174">El resultado del análisis de los datos adjuntos es demasiado grande y que tuvieron que se trunca.</span><span class="sxs-lookup"><span data-stu-id="7985c-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="7985c-175">Datos adjuntos tenían un tipo de archivo que no se pudo detectar Office 365.</span><span class="sxs-lookup"><span data-stu-id="7985c-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="7985c-176">Datos adjuntos tenían un tipo de archivo que se detectan 365could de Office, pero ese tipo de archivo de análisis no es compatible.</span><span class="sxs-lookup"><span data-stu-id="7985c-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="7985c-p120">El valor de una propiedad de correo electrónico en Exchange era demasiado grande que se recuperarán almacén y no se pudo procesar el mensaje. Esto sólo ocurre normalmente a la propiedad de cuerpo de un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7985c-p120">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed. This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="7985c-179">No se pudo descodificar un mensaje protegido mediante RMS los almacenes de datos de contenido.</span><span class="sxs-lookup"><span data-stu-id="7985c-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="7985c-p121">Demasiadas palabras se han identificado en el documento durante la indización. Detener el procesamiento de la propiedad al alcanzar el límite, y la propiedad se trunca.</span><span class="sxs-lookup"><span data-stu-id="7985c-p121">Too many words were identified in the document during indexing. Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="7985c-p122">Campos de error describen los campos que se ven afectados por el error de procesamiento que aparecen en el campo de etiquetas de Error. Si va a buscar, como una propiedad `subject` o `participants`, errores en el cuerpo del mensaje no afectan a los resultados de la búsqueda. Esto puede resultar útil al determinar exactamente qué elementos indizados parcialmente es posible que deba investigar.</span><span class="sxs-lookup"><span data-stu-id="7985c-p122">Error fields describe which fields are affected by the processing error listed in the Error Tags field. If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search. This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="7985c-185">Uso de un script de PowerShell para determinar la exposición de la organización a los elementos de correo electrónico parcialmente indizados</span><span class="sxs-lookup"><span data-stu-id="7985c-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="7985c-p123">Los pasos siguientes muestran cómo ejecutar un script de PowerShell que busca todos los elementos de todos los buzones de Exchange y, a continuación, genera un informe sobre la relación de la organización de los elementos de correo electrónico parcialmente indizados (por el número y tamaño) y muestra el número de elementos (y el tipo de archivo) para cada error de indización que se produce. Use las descripciones de la etiqueta de error en la sección anterior para identificar el error de indización.</span><span class="sxs-lookup"><span data-stu-id="7985c-p123">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs. Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="7985c-188">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `PartiallyIndexedItems.ps1`.</span><span class="sxs-lookup"><span data-stu-id="7985c-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. <span data-ttu-id="7985c-189">[Conectarse a Office 365 seguridad &amp; centro de cumplimiento PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="7985c-189">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="7985c-190">En seguridad &amp; PowerShell de centro de cumplimiento, vaya a la carpeta donde guardó el script en el paso 1 y, a continuación, ejecute el script; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7985c-190">In Security &amp; Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
<span data-ttu-id="7985c-191">Este es un ejemplo fo el resultado devuelto por la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="7985c-191">Here's an example fo the output returned by the script.</span></span>
  
![Ejemplo de salida de secuencia de comandos que genera un informe sobre la exposición de la organización a los elementos de correo electrónico parcialmente indizados](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="7985c-193">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7985c-193">Note the following:</span></span>
  
1. <span data-ttu-id="7985c-194">El número total y el tamaño de los elementos de correo electrónico y la relación entre la organización de los elementos de correo electrónico parcialmente indizada (por el número y tamaño)</span><span class="sxs-lookup"><span data-stu-id="7985c-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="7985c-195">Las etiquetas de un error de lista y los tipos de archivo para el que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="7985c-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7985c-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="7985c-196">See also</span></span>

[<span data-ttu-id="7985c-197">Elementos parcialmente indizados en la búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="7985c-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
