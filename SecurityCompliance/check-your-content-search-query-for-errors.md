---
title: Comprobar errores en la consulta de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: Compruebe la consulta de palabras clave para la búsqueda de contenido de errores y de escritura, como caracteres no admitidos y minúsculas operadores booleanos, antes de ejecutar la búsqueda. Si se encuentra un error, le sugerimos una consulta revisada.
ms.openlocfilehash: 0d2119ceef4ce3777d3967a56357551e235e426c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536186"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="4db5e-104">Comprobar errores en la consulta de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="4db5e-104">Check your Content Search query for errors</span></span>

<span data-ttu-id="4db5e-p102">Al crear o editar una búsqueda de contenido, puede hacer que Office 365 Compruebe su consulta para caracteres no admitidos y operadores booleanos que es posible que no se puso en mayúsculas. ¿Cómo? Haga clic en **Comprobar consulta si hay errores ortográficos** en la página de consulta de búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="4db5e-p102">When you create or edit a Content Search, you can have Office 365 check your query for unsupported characters and Boolean operators that might not be capitalized. How? Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![Haga clic en "Comprobar la consulta para errores tipográficos" para comprobar la consulta de búsqueda de caracteres no admitidos](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="4db5e-p103">Aquí tiene una lista de los caracteres no admitidos que se comprueban si. Caracteres no admitidos a menudo están ocultos y que suele causan un error de búsqueda o devuelvan resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="4db5e-p103">Here's a list of the unsupported characters that we check for. Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="4db5e-p104">No se admiten **las comillas tipográficas** -inteligentes entre comillas sencillas y dobles (también denominado comillas tipográficas). Sólo las marcas de comillas rectas se puede usar en una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4db5e-p104">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported. Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="4db5e-p105">**Caracteres no imprimibles y control** - no imprimibles y caracteres de control no representan un símbolo escrito, como un carácter alfanumérico. Ejemplos de no imprimibles y caracteres de control incluyen caracteres que formato al texto o líneas independientes de texto.</span><span class="sxs-lookup"><span data-stu-id="4db5e-p105">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as a alpha-numeric character. Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="4db5e-115">**Las marcas de izquierda a derecha y de derecha a izquierda** - son caracteres de control que se utiliza para indicar la dirección del texto de idiomas de izquierda a derecha (por ejemplo, inglés y español) y los idiomas de derecha a izquierda (como árabe y hebreo).</span><span class="sxs-lookup"><span data-stu-id="4db5e-115">**Left-to-right and right-to-left marks** - These are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="4db5e-p106">**Operadores booleanos en minúsculas** - si utiliza un operador booleano, como **AND**, **OR**y **no** en una consulta de búsqueda, debe estar en mayúscula. Cuando se protege una consulta para errores tipográficos, la sintaxis de consulta suele indicar que se está utilizando un operador booleano, aunque es posible que utilizará operadores en minúsculas; Por ejemplo, `(WordA or WordB) and (WordC or WordD)`.</span><span class="sxs-lookup"><span data-stu-id="4db5e-p106">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase. When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="4db5e-118">¿Qué sucede si una consulta tiene un carácter no admitido?</span><span class="sxs-lookup"><span data-stu-id="4db5e-118">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="4db5e-p107">Si se encuentran caracteres no admitidos en la consulta, se muestra un mensaje de advertencia que indica que los caracteres no admitidos que se han encontrado y un sugiere una alternativa. A continuación, a continuación, tiene la opción mantener la consulta original o reemplácelo por la consulta revisada sugerida. Este es un ejemplo del mensaje de advertencia que se muestra tras hacer clic en **Comprobar consulta si hay errores ortográficos** para la consulta de búsqueda en la captura de pantalla anterior. Tenga en cuenta que la consulta original contiene las comillas tipográficas y los operadores booleanos en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4db5e-p107">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters that were found and a suggests an alternative. Then you then have the option keep the original query or replace it with the suggested revised query. Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot. Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![Se muestra un mensaje de advertencia con una revisión sugerida para la consulta](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="4db5e-124">Procedimiento para evitar que los caracteres no admitidos en las consultas de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4db5e-124">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="4db5e-p108">Caracteres no admitidos normalmente se agregan a una consulta cuando se copien la consulta o elementos de la consulta desde otras aplicaciones (como Microsoft Word o Microsoft Excel) y copiarlos en el cuadro de palabra clave en la página de consulta de búsqueda de contenido. Sólo tiene que escribir la consulta en el cuadro de palabra clave es la mejor forma de evitar que los caracteres no admitidos. Como alternativa, puede copiar una consulta de Word o Excel y, a continuación, péguelo en el archivo en un editor de texto sin formato, como Microsoft Notepad. A continuación, guarde el archivo de texto y seleccione **ANSI** en la lista desplegable de **codificación** . Esta acción eliminará todos los caracteres no admitidos y formato. A continuación, puede copiar y pegar la consulta desde el archivo de texto en el cuadro de consulta de palabra clave.</span><span class="sxs-lookup"><span data-stu-id="4db5e-p108">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and copy them to the keyword box on the query page of a Content Search. The best way to prevent unsupported characters is to just type the query in the keyword box. Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad. Then save the text file and select **ANSI** in the **Encoding** drop-down list. This will remove any formatting and unsupported characters. Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
