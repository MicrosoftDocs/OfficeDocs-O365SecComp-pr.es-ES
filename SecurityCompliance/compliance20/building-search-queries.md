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
# <a name="building-search-queries"></a>Creación de consultas de búsqueda
En la creación de la consulta, puede usar varias palabras clave y las condiciones para definir los elementos que desea buscar.

## <a name="keyword-searches"></a>Búsquedas de palabras clave
En el cuadro **palabras clave** , escriba una consulta de búsqueda. Puede especificar las palabras clave, mensaje propiedades como envían y reciben fechas, o las propiedades de documento, como los nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar una de las consultas más complejas que usan un operador booleano, como **AND**, **OR**, **no**y **NEAR**. También puede buscar información confidencial (como números de la seguridad social) en los documentos o buscar documentos que se han compartido externamente. Si deja vacío el cuadro de palabra clave, todo el contenido que se encuentra en las ubicaciones de contenido especificadas se incluirán en los resultados de búsqueda.
    
Como alternativa, puede hacer clic en la casilla de verificación **Mostrar la lista de palabras clave** y el tipo de una palabra clave en cada fila. Si lo hace, las palabras clave en cada fila están conectadas mediante un operador lógico ( **c:s**) que es una funcionalidad similar para el operador **OR** en la consulta de búsqueda que se crea. 
    
¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente las palabras clave son los más (y menos) eficaces. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, vea [las estadísticas de búsqueda](search-statistics.md).

## <a name="conditions"></a>Condiciones    
Puede agregar condiciones de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crean y ejecutan cuando se inicia la búsqueda. Una condición lógicamente está conectada a la consulta de palabras clave (especificada en el cuadro de palabra clave) por un operador lógico (**c: c**) que es una funcionalidad similar para el operador **y** . Esto significa que los elementos tengan que satisfacer la consulta de palabras clave y una o varias condiciones que se deben incluir en los resultados. Se trata de cómo ayudar a condiciones para limitar los resultados. Para obtener una lista y descripción de las condiciones que puede utilizar en una consulta de búsqueda, vea la sección "Las condiciones de búsqueda" en [las consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](../keyword-queries-and-search-conditions.md#search-conditions).


