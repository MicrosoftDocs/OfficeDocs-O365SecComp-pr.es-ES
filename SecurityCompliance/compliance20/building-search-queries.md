---
title: Creación de consultas de búsqueda
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 119cdd9d932b6c1be847c406988efa80b8534795
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608376"
---
# <a name="building-search-queries"></a><span data-ttu-id="c52a6-102">Creación de consultas de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c52a6-102">Building search queries</span></span>
<span data-ttu-id="c52a6-103">En la creación de la consulta, puede usar varias palabras clave y las condiciones para definir los elementos que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="c52a6-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="c52a6-104">Búsquedas de palabras clave</span><span class="sxs-lookup"><span data-stu-id="c52a6-104">Keyword searches</span></span>
<span data-ttu-id="c52a6-p101">En el cuadro **palabras clave** , escriba una consulta de búsqueda. Puede especificar las palabras clave, mensaje propiedades como envían y reciben fechas, o las propiedades de documento, como los nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar una de las consultas más complejas que usan un operador booleano, como **AND**, **OR**, **no**y **NEAR**. También puede buscar información confidencial (como números de la seguridad social) en los documentos o buscar documentos que se han compartido externamente. Si deja vacío el cuadro de palabra clave, todo el contenido que se encuentra en las ubicaciones de contenido especificadas se incluirán en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c52a6-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="c52a6-p102">Como alternativa, puede hacer clic en la casilla de verificación **Mostrar la lista de palabras clave** y el tipo de una palabra clave en cada fila. Si lo hace, las palabras clave en cada fila están conectadas mediante un operador lógico ( **c:s**) que es una funcionalidad similar para el operador **OR** en la consulta de búsqueda que se crea.</span><span class="sxs-lookup"><span data-stu-id="c52a6-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="c52a6-p103">¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente las palabras clave son los más (y menos) eficaces. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, vea [las estadísticas de búsqueda](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="c52a6-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="c52a6-117">Condiciones</span><span class="sxs-lookup"><span data-stu-id="c52a6-117">Conditions</span></span>    
<span data-ttu-id="c52a6-p104">Puede agregar condiciones de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crean y ejecutan cuando se inicia la búsqueda. Una condición lógicamente está conectada a la consulta de palabras clave (especificada en el cuadro de palabra clave) por un operador lógico (**c: c**) que es una funcionalidad similar para el operador **y** . Esto significa que los elementos tengan que satisfacer la consulta de palabras clave y una o varias condiciones que se deben incluir en los resultados. Se trata de cómo ayudar a condiciones para limitar los resultados. Para obtener una lista y descripción de las condiciones que puede utilizar en una consulta de búsqueda, vea la sección "Las condiciones de búsqueda" en [las consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](../keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="c52a6-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


