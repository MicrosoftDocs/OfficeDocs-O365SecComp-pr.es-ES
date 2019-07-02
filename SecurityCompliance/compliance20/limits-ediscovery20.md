---
title: Límites avanzados de eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre los límites en vigor para la solución Advanced eDiscovery en Microsoft 365. Esto incluye los límites de mayúsculas y minúsculas, los límites de indización y los límites de búsqueda cuando se usa la herramienta de búsqueda para recopilar datos de casos.
ms.openlocfilehash: 622d2669457a2a1e84909aadae9b653ca37684ce
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222294"
---
# <a name="limits-in-advanced-ediscovery"></a>Límites de eDiscovery avanzado

En este artículo se describen los límites de la solución Advanced eDiscovery en Microsoft 365.

## <a name="case-limits"></a>Límites de casos

En la siguiente tabla se enumeran los límites de los casos en eDiscovery avanzado.

|**Descripción del límite**|**Límite**|
|:-----|:-----|
|Número total de documentos que se pueden agregar a un caso (para todos los conjuntos de revisión en un caso).  <br/> |1 millón  <br/> |
|Tamaño total de archivo por conjunto de carga.  <br/> |100 GB  <br/> |
|Cantidad total de datos que se cargan en un caso por día.<br/> |2 TB <br/> |
|Número máximo de conjuntos de carga por caso.  <br/> |15  <br/> |
|Número máximo de conjuntos de revisión por caso.  <br/> |20 <br/> |
|||

## <a name="indexing-limits"></a>Límites de indexación

En la siguiente tabla se enumeran los límites de indización en la exhibición avanzada de documentos electrónicos.

|**Descripción del límite**|**Límite**|
  |:-----|:-----|
  |Número máximo de caracteres extraídos de un solo archivo.  <br/> |10 millones<sup>1</sup> <br/> |
  |Tamaño máximo de un solo archivo.   <br/> |100 MB<sup>1</sup> <br/> |
  |Profundidad máxima de elementos incrustados en un documento.  <br/> |25<sup>1</sup> <br/> |
  |Tamaño máximo del archivo procesado por el reconocimiento óptico de caracteres (OCR).  <br/> |24 MB<sup>1</sup> <br/> |  
|||

## <a name="search-limits"></a>Límites de búsqueda

Los límites descritos en esta sección están relacionados con el uso de la herramienta de búsqueda en la ficha **búsquedas** para recopilar datos para un caso. Para obtener más información, vea [recopilar datos para un caso en EDiscovery avanzado](collecting-data-for-ediscovery.md).

|**Descripción del límite**|**Límite**|
|:-----|:-----|
|Número máximo de buzones o sitios en los que se puede buscar en una sola búsqueda.  <br/> |Sin límite  <br/> |
|Número máximo de búsquedas que se pueden ejecutar al mismo tiempo.  <br/> |Sin límite  <br/> | 
|Número máximo de búsquedas que un solo usuario puede iniciar al mismo tiempo.  <br/> |10   <br/> | 
|Número máximo de caracteres para una consulta de búsqueda (incluidos los operadores y las condiciones).  <br/> |**Buzones de correo**: 10.000<br/>**Sitios**: 4.000 al buscar en todos los sitios o en 2.000 al buscar hasta 20 sitios <sup>2</sup> <br/> |
|Número mínimo de caracteres alfabéticos para comodines de prefijo; por ejemplo **,\* uno o un** **conjunto\***. <br/> |3   <br/> |  
|Número máximo de variantes que se devuelven al usar el carácter comodín de prefijo para buscar una frase exacta o al usar un carácter comodín de prefijo y el operador booleano **Near** o **ONEAR** .  <br/> |10.000 <sup>3</sup> <br/> |
|Número máximo de elementos por buzón de usuario que se muestran en la página de vista previa para las búsquedas. Se muestran los elementos más recientes.   <br/> |100  <br/> |
|Número máximo de elementos de todos los buzones mostrados en la página de vista previa para las búsquedas.  <br/> |1,000  <br/> |
|Número máximo de buzones en los que se puede obtener una vista previa de los resultados de búsqueda.  Si hay más de 1000 buzones de correo que contienen elementos que coinciden con la consulta de búsqueda, solo los principales buzones de correo de 1.000 con más resultados están disponibles para la vista previa.<br/> |1,000  <br/> |
|Número máximo de elementos de los sitios de SharePoint y OneDrive para la empresa que se muestran en la página de vista previa para las búsquedas. Se muestran los elementos más recientes.  <br/> |200  <br/> |
|Número máximo de sitios de SharePoint y OneDrive para la empresa en los que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 200 sitios que contienen elementos que coinciden con la consulta de búsqueda, solo los principales sitios de 200 con más resultados están disponibles para la vista previa.  <br/> |200  <br/> |
|Número máximo de elementos por buzón de carpeta pública que se muestra en la página de vista previa para las búsquedas.  <br/> |100  <br/> |
|Número máximo de elementos encontrados en todos los elementos de buzón de carpetas públicas que se muestran en la página de vista previa para las búsquedas.  <br/> |200  <br/> |
|Número máximo de buzones de carpetas públicas en los que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 500 buzones de carpetas públicas que contienen elementos que coinciden con la consulta de búsqueda, solo los principales buzones de correo de 500 con más resultados están disponibles para la vista previa.  <br/> |500  <br/> |
|||

## <a name="viewer-limits"></a>Límites del visor

|**Descripción del límite**|**Límite**|
  |:-----|:-----|
  |Tamaño máximo del archivo de Excel que se puede ver en el visor nativo.  <br/> |4 MB  <br/> |
|||

## <a name="review-set-download-limits"></a>Revisión del conjunto de límites de descarga

|**Descripción del límite**|**Límite**|
|:-----|:-----|
|Tamaño total de archivo o número máximo de documentos descargados de un conjunto de revisión.  <br/> |3 MB o 50 documentos <sup>4</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> cualquier elemento que supere un solo límite de archivo se mostrará como un error de procesamiento.<br/>
> <sup>2</sup> al buscar ubicaciones de SharePoint y OneDrive para la empresa, los caracteres de las direcciones URL de los sitios en los que se está realizando la búsqueda cuentan en este límite.<br/>
> <sup>3</sup> para las consultas que no son de frases (un valor de palabra clave que no usa comillas dobles) usamos un índice de prefijo especial. Esto indica que se produce una palabra en un documento, pero no donde se produce en el documento. Para realizar una consulta de frases (un valor de palabra clave con comillas dobles), debemos comparar la posición del documento con las palabras de la frase. Esto significa que no podemos usar el índice de prefijos para las consultas de frases. En este caso, la consulta se expande internamente con todas las palabras posibles a las que se expande el prefijo; por ejemplo, **el\* tiempo** se puede expandir a **"tiempo, temporizadores u horas o Timex o timeboxed o..."**. El límite de 10.000 es el número máximo de variantes a las que se puede expandir la palabra, no el número de documentos que coinciden con la consulta. Para los términos que no son frases no hay ningún límite superior.<br/>
> <sup>4</sup> este límite se aplica a la descarga de documentos seleccionados de un conjunto de revisión. No se aplica a la exportación de documentos de un conjunto de revisión. Para obtener más información sobre cómo descargar y exportar documentos, vea [exportar datos de casos en EDiscovery avanzado](exporting-data-ediscover20.md). <br/>

