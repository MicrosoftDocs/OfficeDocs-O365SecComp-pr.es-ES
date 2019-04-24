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
description: Use palabras clave y condiciones para restringir el ámbito de la búsqueda al buscar datos cuando use la investigación de datos en Microsoft 365.
ms.openlocfilehash: eeca1bf7ff89d1b7f79ceeed3334668e354f035a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262902"
---
# <a name="build-search-queries"></a>Crear consultas de búsqueda

Al crear consultas de búsqueda, puede usar palabras clave para buscar contenido y condiciones específicos para reducir el ámbito de la búsqueda y devolver los elementos más relevantes para la investigación.

![Usar palabras clave y condiciones para restringir los resultados de una búsqueda](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Búsquedas de palabras clave

Escriba una consulta de palabra clave en el cuadro **palabras clave** en la consulta de búsqueda. Puede especificar palabras clave, propiedades del mensaje de correo electrónico (como las fechas de envío y recepción) o propiedades del documento (como nombres de archivo o la fecha en que se modificó por última vez un documento). Puede usar consultas más complejas que usen un operador booleano, como **and**, **or**, **Not**y **Near**. También puede buscar información confidencial (por ejemplo, números de la seguridad social) en documentos de SharePoint y OneDrive (no en mensajes de correo electrónico), ni buscar documentos que se han compartido externamente. Si deja en blanco el cuadro **palabras clave** , todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda.
    
Como alternativa, puede hacer clic en la casilla **Mostrar lista de palabras clave** y escribir una palabra clave o frase de palabra clave en cada fila. Si hace esto, las palabras clave de cada fila están conectadas por un operador lógico (que se representa como *c:s*) que es similar en funcionalidad al operador **or** en la consulta de búsqueda que se crea. Esto significa que los elementos que contienen cualquier palabra clave en cualquier fila se incluirán en los resultados de la búsqueda.

![Usar la lista de palabras clave para obtener estadísticas de cada palabra clave de la consulta](../media/KeywordListSearch.png)

¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestren cuántos elementos coinciden con cada palabra clave de la lista de palabras clave. Esto puede ayudarle a identificar rápidamente las palabras clave más eficaces (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila de la lista de palabras clave. Para obtener más información acerca de las estadísticas de búsqueda, vea [estadísticas de búsqueda](search-statistics.md).

> [!NOTE]
> Para ayudar a reducir los problemas causados por listas de palabras clave grandes, está limitado a un máximo de 20 filas en la lista de palabras clave.

## <a name="conditions"></a>Condiciones
    
Puede agregar condiciones de búsqueda para restringir el ámbito de una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave (que se especifica en el cuadro palabra clave) por un operador lógico (que se representa como *c:c*) que es similar en funcionalidad al operador **and** . Esto significa que los elementos deben cumplir con la consulta de palabra clave y una o más condiciones que se van a incluir en los resultados de la búsqueda. De esta manera, las condiciones permiten restringir los resultados. Para obtener una lista y una descripción de las condiciones que se pueden usar en una consulta de búsqueda, vea la sección "condiciones de búsqueda" en [consultas de palabras clave y condiciones de búsqueda](../keyword-queries-and-search-conditions.md#search-conditions).
