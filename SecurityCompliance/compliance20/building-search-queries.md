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
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8e7f3d798d3b6cfe25d57b941ed2be1d8d5e92b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216990"
---
# <a name="build-search-queries"></a>Crear consultas de búsqueda

Al compilar la consulta, puede usar varias palabras clave y condiciones para definir los elementos que se van a buscar.

## <a name="keyword-searches"></a>Búsquedas de palabras clave

Escriba una consulta de búsqueda en el cuadro **palabras clave** . Puede especificar palabras clave, propiedades del mensaje, como las fechas de envío y recepción, o propiedades del documento, como nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar consultas más complejas que usen un operador booleano, como **and**, **or**, **Not**y **Near**. También puede buscar información confidencial (por ejemplo, los números de la seguridad social) en documentos o buscar documentos que se han compartido de forma externa. Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda.
    
Como alternativa, puede hacer clic en la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. Si hace esto, las palabras clave de cada fila están conectadas por un operador lógico ( **c:s**) que es similar en funcionalidad al operador **or** en la consulta de búsqueda que se crea. 
    
¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestren cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente qué palabras clave son más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, consulte [estadística de búsqueda](search-statistics.md).

## <a name="conditions"></a>Condiciones
    
Puede agregar condiciones de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave (especificada en el cuadro palabra clave) por un operador lógico (**c:c**) que es similar en funcionalidad al operador **and** . Esto significa que los elementos deben cumplir con la consulta de palabra clave y una o más condiciones que se van a incluir en los resultados. Este es el modo en que las condiciones ayudan a restringir los resultados. Para obtener una lista y una descripción de las condiciones que puede usar en una consulta de búsqueda, consulte la sección "condiciones de búsqueda" en [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](../keyword-queries-and-search-conditions.md#search-conditions).


