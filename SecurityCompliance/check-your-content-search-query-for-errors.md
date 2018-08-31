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
# <a name="check-your-content-search-query-for-errors"></a>Comprobar errores en la consulta de búsqueda de contenido

Al crear o editar una búsqueda de contenido, puede hacer que Office 365 Compruebe su consulta para caracteres no admitidos y operadores booleanos que es posible que no se puso en mayúsculas. ¿Cómo? Haga clic en **Comprobar consulta si hay errores ortográficos** en la página de consulta de búsqueda de contenido. 
  
![Haga clic en "Comprobar la consulta para errores tipográficos" para comprobar la consulta de búsqueda de caracteres no admitidos](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
Aquí tiene una lista de los caracteres no admitidos que se comprueban si. Caracteres no admitidos a menudo están ocultos y que suele causan un error de búsqueda o devuelvan resultados inesperados.
  
- No se admiten **las comillas tipográficas** -inteligentes entre comillas sencillas y dobles (también denominado comillas tipográficas). Sólo las marcas de comillas rectas se puede usar en una consulta de búsqueda. 
    
- **Caracteres no imprimibles y control** - no imprimibles y caracteres de control no representan un símbolo escrito, como un carácter alfanumérico. Ejemplos de no imprimibles y caracteres de control incluyen caracteres que formato al texto o líneas independientes de texto. 
    
- **Las marcas de izquierda a derecha y de derecha a izquierda** - son caracteres de control que se utiliza para indicar la dirección del texto de idiomas de izquierda a derecha (por ejemplo, inglés y español) y los idiomas de derecha a izquierda (como árabe y hebreo).
    
- **Operadores booleanos en minúsculas** - si utiliza un operador booleano, como **AND**, **OR**y **no** en una consulta de búsqueda, debe estar en mayúscula. Cuando se protege una consulta para errores tipográficos, la sintaxis de consulta suele indicar que se está utilizando un operador booleano, aunque es posible que utilizará operadores en minúsculas; Por ejemplo, `(WordA or WordB) and (WordC or WordD)`.
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>¿Qué sucede si una consulta tiene un carácter no admitido?

Si se encuentran caracteres no admitidos en la consulta, se muestra un mensaje de advertencia que indica que los caracteres no admitidos que se han encontrado y un sugiere una alternativa. A continuación, a continuación, tiene la opción mantener la consulta original o reemplácelo por la consulta revisada sugerida. Este es un ejemplo del mensaje de advertencia que se muestra tras hacer clic en **Comprobar consulta si hay errores ortográficos** para la consulta de búsqueda en la captura de pantalla anterior. Tenga en cuenta que la consulta original contiene las comillas tipográficas y los operadores booleanos en minúsculas. 
  
![Se muestra un mensaje de advertencia con una revisión sugerida para la consulta](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Procedimiento para evitar que los caracteres no admitidos en las consultas de búsqueda

Caracteres no admitidos normalmente se agregan a una consulta cuando se copien la consulta o elementos de la consulta desde otras aplicaciones (como Microsoft Word o Microsoft Excel) y copiarlos en el cuadro de palabra clave en la página de consulta de búsqueda de contenido. Sólo tiene que escribir la consulta en el cuadro de palabra clave es la mejor forma de evitar que los caracteres no admitidos. Como alternativa, puede copiar una consulta de Word o Excel y, a continuación, péguelo en el archivo en un editor de texto sin formato, como Microsoft Notepad. A continuación, guarde el archivo de texto y seleccione **ANSI** en la lista desplegable de **codificación** . Esta acción eliminará todos los caracteres no admitidos y formato. A continuación, puede copiar y pegar la consulta desde el archivo de texto en el cuadro de consulta de palabra clave. 
