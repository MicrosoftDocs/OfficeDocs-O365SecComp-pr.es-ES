---
title: Comprobar errores en la consulta de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: Antes de ejecutar la búsqueda, compruebe si hay errores y errores tipográficos en la consulta de palabras clave para la búsqueda de contenido, por ejemplo, caracteres no admitidos y operadores booleanos en minúsculas. Si encontramos un error, sugerimos una consulta revisada.
ms.openlocfilehash: 9f9f59c4466102d678bc3a599aa208869bbd9d64
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155582"
---
# <a name="check-your-content-search-query-for-errors"></a>Comprobar errores en la consulta de búsqueda de contenido

Al crear o editar una búsqueda de contenido, puede hacer que Office 365 Compruebe la consulta en busca de caracteres no admitidos y operadores booleanos que podrían no estar en mayúsculas. ¿Cómo se hace? Solo tiene que hacer clic en **comprobar consulta si hay errores tipográficos** en la página consulta de una búsqueda de contenido. 
  
![Haga clic en "consultar si hay errores tipográficos" para comprobar la consulta de búsqueda en busca de caracteres no admitidos](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
Esta es una lista de los caracteres no admitidos que se buscarán. Los caracteres no admitidos suelen estar ocultos y, por lo general, provocan un error de búsqueda o devuelven resultados no deseados.
  
- **** Las comillas tipográficas: las comillas tipográficas sencillas y dobles (también denominadas comillas tipográficas) no son compatibles. Solo pueden usarse las comillas tipográficas en una consulta de búsqueda. 
    
- Los caracteres no **imprimibles y de control** (no imprimibles) y los caracteres de control no representan un símbolo escrito, como un carácter alfanumérico. Los ejemplos de caracteres de control no imprimibles incluyen caracteres que aplican formato al texto o que separan líneas de texto. 
    
- **Marcas de izquierda a derecha y de derecha a izquierda** : estos caracteres de control se usan para indicar la dirección del texto en los idiomas de izquierda a derecha (como el inglés y el español) y en los idiomas de derecha a izquierda (como el árabe y el hebreo).
    
- **Operadores booleanos** en minúsculas: Si usa un operador booleano, como **and**, **or**y **Not** en una consulta de búsqueda, debe estar en mayúsculas. Cuando comprobamos una consulta para comprobar si hay errores tipográficos, la sintaxis de la consulta suele indicar que se está usando un operador booleano, aunque se podrían usar operadores en minúsculas; por ejemplo, `(WordA or WordB) and (WordC or WordD)`.
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>¿Qué sucede si una consulta tiene un carácter no admitido?

Si se encuentran caracteres no admitidos en la consulta, se muestra un mensaje de advertencia que indica que se han encontrado caracteres no admitidos y que un sugiere una alternativa. A continuación, tendrá la opción de conservar la consulta original o reemplazarla por la consulta revisada sugerida. Este es un ejemplo del mensaje de advertencia que se muestra después de hacer clic en **consultar consulta para ver si hay errores ortográficos** para la consulta de búsqueda en la captura de pantalla anterior. Observe que la consulta original contiene comillas tipográficas y operadores booleanos en minúsculas. 
  
![Se muestra un mensaje de advertencia con una revisión sugerida de la consulta](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Cómo evitar los caracteres no admitidos en las consultas de búsqueda

Normalmente, los caracteres no admitidos se agregan a una consulta cuando se copia la consulta o partes de la consulta de otras aplicaciones (como Microsoft Word o Microsoft Excel) y se copian en el cuadro palabra clave de la página consulta de una búsqueda de contenido. La mejor manera de evitar los caracteres no admitidos es simplemente escribir la consulta en el cuadro de palabras clave. De manera alternativa, puede copiar una consulta de Word o Excel y, después, pegarla en un archivo de un editor de texto sin formato, como Microsoft Notepad. A continuación, guarde el archivo de texto y seleccione **ANSI** en la lista desplegable **Codificación**. Esto quitará cualquier carácter no admitido y de formato. Después, podrá copiar y pegar la consulta del archivo de texto en el cuadro de consulta de palabras clave. 
