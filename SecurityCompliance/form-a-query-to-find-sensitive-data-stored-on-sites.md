---
title: Crear una consulta para buscar datos confidenciales almacenados en los sitios
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: Con la prevención de pérdida de datos (DLP) en SharePoint Online, puede detectar los documentos que contienen información confidencial en todo el inquilino. Después de la detección de los documentos, puede trabajar con los propietarios del documento para proteger los datos. En este tema le ayudarán a crear una consulta para buscar datos confidenciales.
ms.openlocfilehash: 13954a856dd265e3b735d940c7d334d922713637
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013864"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Crear una consulta para buscar datos confidenciales almacenados en los sitios

A menudo, los usuarios almacenan datos confidenciales, como números de tarjeta de crédito, números de la seguridad social, o personal, en sus sitios y con el tiempo, esto puede exponer una organización a un riesgo significativo de pérdida de datos. Documentos almacenados en los sitios, incluidos OneDrive para sitios de profesionales: puede compartirse con personas fuera de la organización que no deberían tener acceso a la información. Con la prevención de pérdida de datos (DLP) en SharePoint Online, puede detectar los documentos que contienen información confidencial en todo el inquilino. Después de la detección de los documentos, puede trabajar con los propietarios del documento para proteger los datos. En este tema le ayudarán a crear una consulta para buscar datos confidenciales.
  
> [!NOTE]
> Detección electrónica, o exhibición de documentos electrónicos y DLP son características de premium que requieren [SharePoint Online Plan 2](https://go.microsoft.com/fwlink/?LinkId=510080). 
  
## <a name="forming-a-basic-dlp-query"></a>Formación de una consulta básica de DLP

Hay tres partes que componen una consulta básica de DLP: SensitiveType, contar el intervalo y el intervalo de confianza. Tal como se ilustra en el siguiente gráfico, **SensitiveType: "\<tipo\>"** es necesario y ambos**|\<contar intervalo\> ** y**|\<intervalo de confianza\> ** son opcionales. 
  
![Consulta de ejemplo dividida entre obligatorio y opcional](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>Tipo confidencial: obligatorio

¿Qué es cada elemento? Las consultas de SharePoint DLP normalmente comienzan con la propiedad `SensitiveType:"` y un tipo de información que el nombre de la [información confidencial de tipos de inventario](https://go.microsoft.com/fwlink/?LinkID=509999)y terminar con un `"`. También puede usar el nombre de un [tipo de información confidencial personalizada](create-a-custom-sensitive-information-type.md) que ha creado para su organización. Por ejemplo, puede que esté buscando para los documentos que contienen números de tarjeta de crédito. En tal caso, usaría el siguiente formato: `SensitiveType:"Credit Card Number"`. Dado que no ha incluido el intervalo de recuento o el intervalo de confianza, la consulta devuelve todos los documentos en la que se detecta un número de tarjeta de crédito. Ésta es la consulta más simple que puede ejecutar y devuelve la mayoría de los resultados. Tenga en cuenta que es importante la ortografía y el espaciado del tipo confidencial. 
  
### <a name="ranges---optional"></a>Intervalos: opcionales

Ambos de los dos elementos son intervalos, por lo que vamos a examinar rápidamente el aspecto de un rango. En las consultas de SharePoint DLP, un intervalo básico está representado por dos números separados por dos puntos, que tiene este aspecto: `[number]..[number]`. Por ejemplo, si `10..20` es usa, dicho rango debería capturar números entre 10 y 20. Hay muchas combinaciones de rango diferente y varios se tratan en este tema. 
  
Vamos a agregar un intervalo de recuento a la consulta. Puede usar el intervalo de recuento para definir el número de repeticiones de un documento debe contener antes de que se incluye en los resultados de consulta de información confidencial. Por ejemplo, si desea que la consulta para devolver sólo los documentos que contienen números de tarjeta de crédito exactamente cinco, use esto: `SensitiveType:"Credit Card Number|5"`. Intervalo de recuento también puede ayudar a identificar los documentos que suponen una alta grados de riesgo. Por ejemplo, su organización podría considerar documentos con cinco o más números de tarjeta de crédito un alto riesgo. Para buscar documentos ajustando este criterio, usaríamos la siguiente consulta: `SensitiveType:"Credit Card Number|5.."`. Como alternativa, puede buscar documentos con cinco o menos números de tarjeta de crédito mediante el uso de esta consulta: `SensitiveType:"Credit Card Number|..5"`. 
  
#### <a name="confidence-range"></a>Intervalo de confianza

Por último, el intervalo de confianza es el nivel de confianza que el tipo confidencial detectado es realmente una coincidencia. Los valores de intervalo de confianza funcionan de manera similar para contar el intervalo. Puede formar una consulta sin incluido un rango de recuento. Por ejemplo, para buscar documentos con cualquier número de números de tarjeta de crédito, siempre que el intervalo de confianza es un 85 por ciento o superior: usaría esta consulta: `SensitiveType:"Credit Card Number|*|85.."`. 
  
> [!IMPORTANT]
> El asterisco ( `*`) es un carácter comodín que significa cualquier funciona de valor. Puede usar el carácter comodín ( `*`) ya sea en el intervalo de recuento o en el intervalo de confianza, pero no en un tipo confidencial. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Propiedades de consulta y operadores de búsqueda adicionales disponibles en el centro de exhibición de documentos electrónicos

DLP en SharePoint también presenta la LastSensitiveContentScan (propiedad), que le ayudarán a buscar archivos examinados dentro de un período de tiempo específico. Para obtener ejemplos de consulta con el `LastSensitiveContentScan` (propiedad), vea los [ejemplos de consultas complejas](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries) en la siguiente sección. 
  
Puede usar las propiedades específicas de DLP para crear una consulta pero propiedades de búsqueda de exhibición de documentos electrónicos de SharePoint estándar como `Author` o `FileExtension`. Puede usar operadores para crear consultas complejas. Para la lista de propiedades disponibles y operadores, vea la entrada de blog de [uso de propiedades de búsqueda y operadores de exhibición de documentos electrónicos](https://go.microsoft.com/fwlink/?LinkId=510093) . 
  
## <a name="examples-of-complex-queries"></a>Ejemplos

Los siguientes ejemplos utilizan diferentes tipos confidenciales, propiedades y operadores para ilustrar cómo puede refinar las consultas para buscar exactamente lo está buscando.
  
|**Consulta**|**Explicación**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |El nombre que podría parecer extraño porque es tanto tiempo, pero es el nombre correcto para ese tipo confidencial. Asegúrese de utilizar nombres exactos del [inventario de tipos de información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999). También puede usar el nombre de un [tipo de información confidencial personalizada](create-a-custom-sensitive-information-type.md) que ha creado para su organización.<br/> |
| ' SensitiveType: "número de tarjeta de crédito|1..4294967295|1..100"' <br/> |Esto devuelve documentos con al menos una coincidencia para el tipo confidencial "Número de tarjeta de crédito". Los valores para cada intervalo son los valores máximos y mínimos respectivos. ¿Es una manera más sencilla para escribir esta consulta `SensitiveType:"Credit Card Number"`, pero donde es la diversión en que?<br/> |
| ' SensitiveType: "número de tarjeta de crédito| 5..25" y LastSensitiveContentScan:"8/11/2018..8/13/2018 "' <br/> |Esto devuelve documentos con 5-25 números de tarjeta de crédito que se han examinado de 11 de agosto de 2018 a través del 13 de agosto de 2018.  <br/> |
| ' SensitiveType: "número de tarjeta de crédito| 5..25" y LastSensitiveContentScan:"8/11/2018..8/13/2018 "no FileExtension:XLSX' <br/> |Esto devuelve documentos con 5-25 números de tarjeta de crédito que se han examinado de 11 de agosto de 2018 a través del 13 de agosto de 2018. Los archivos con una extensión XLSX no se incluyen en los resultados de consulta.  `FileExtension` es una de las muchas propiedades que se pueden incluir en una consulta. Para obtener más información, vea [uso de las propiedades de búsqueda y operadores de exhibición de documentos electrónicos](https://go.microsoft.com/fwlink/?LinkId=510093).<br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |Esto devuelve los documentos que contienen un número de tarjeta de crédito o un número de seguro social.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Ejemplos

No todas las consultas se crean iguales. En la siguiente tabla se proporciona ejemplos de consultas que no funcionan con DLP en SharePoint y describe por qué.
  
|**Consulta no compatible**|**Reason**|
|:-----|:-----|
| ' SensitiveType: "número de tarjeta de crédito|.." ` <br/> |Debe agregar, al menos, un número.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" no es un nombre de tipo confidencial válido. Sólo los nombres en el [inventario de tipos de información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999) funcionan en las consultas DLP.<br/> |
| ' SensitiveType: "número de tarjeta de crédito|0"' <br/> |Cero no es válido como el valor mínimo o el valor máximo en un intervalo.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Es podría ser difícil de ver, pero no hay espacio en blanco adicional entre "Crédito" y "Tarjeta" que realiza la consulta no válida. Usar nombres de tipo confidencial exacto del [inventario de tipos de información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999).<br/> |
| ' SensitiveType: "número de tarjeta de crédito|1.. 3"' <br/> |La parte de dos períodos no debe estar separada por un espacio.  <br/> |
| ' SensitiveType: "número de tarjeta de crédito| |1..|80.."' <br/> |Hay demasiados (delimitadores) barra vertical|). Siga en su lugar este formato: ' SensitiveType: "número de tarjeta de crédito|1..|80.."' <br/> |
| ' SensitiveType: "número de tarjeta de crédito|1..|80..101"' <br/> |Debido a que los valores de confianza representan un porcentaje, no pueden superar los 100. Elija un número comprendido entre 1 y 100 en su lugar.  <br/> |
   
## <a name="for-more-information"></a>Más información

[Buscar información confidencial almacenada en sitios de SharePoint Online](https://support.office.com/article/ef788d8f-9748-4025-bfe4-40541ca4cfb2)
  
[Inventario de tipos de información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999)
  
[Ejecutar una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento](run-a-content-search-in-the-security-and-compliance-center.md)
  
[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
  

