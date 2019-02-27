---
title: Crear consultas de búsqueda
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e62d486b102fa035ae21b379d30bb0657b82acc9
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296223"
---
# <a name="build-search-queries"></a><span data-ttu-id="d60d1-102">Crear consultas de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d60d1-102">Build search queries</span></span>

<span data-ttu-id="d60d1-103">Al compilar la consulta, puede usar varias palabras clave y condiciones para definir los elementos que se van a buscar.</span><span class="sxs-lookup"><span data-stu-id="d60d1-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="d60d1-104">Búsquedas de palabras clave</span><span class="sxs-lookup"><span data-stu-id="d60d1-104">Keyword searches</span></span>

<span data-ttu-id="d60d1-p101">Escriba una consulta de búsqueda en el cuadro **palabras clave** . Puede especificar palabras clave, propiedades del mensaje, como las fechas de envío y recepción, o propiedades del documento, como nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar consultas más complejas que usen un operador booleano, como **and**, **or**, **Not**y **Near**. También puede buscar información confidencial (por ejemplo, los números de la seguridad social) en documentos o buscar documentos que se han compartido de forma externa. Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d60d1-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="d60d1-p102">Como alternativa, puede hacer clic en la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. Si hace esto, las palabras clave de cada fila están conectadas por un operador lógico ( **c:s**) que es similar en funcionalidad al operador **or** en la consulta de búsqueda que se crea.</span><span class="sxs-lookup"><span data-stu-id="d60d1-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="d60d1-p103">¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestren cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente qué palabras clave son más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, consulte [estadística de búsqueda](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="d60d1-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="d60d1-117">Condiciones</span><span class="sxs-lookup"><span data-stu-id="d60d1-117">Conditions</span></span>
    
<span data-ttu-id="d60d1-p104">Puede agregar condiciones de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave (especificada en el cuadro palabra clave) por un operador lógico (**c:c**) que es similar en funcionalidad al operador **and** . Esto significa que los elementos deben cumplir con la consulta de palabra clave y una o más condiciones que se van a incluir en los resultados. Este es el modo en que las condiciones ayudan a restringir los resultados. Para obtener una lista y una descripción de las condiciones que puede usar en una consulta de búsqueda, consulte la sección "condiciones de búsqueda" en [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](../keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="d60d1-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


