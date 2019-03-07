---
title: Crear una consulta para buscar datos confidenciales almacenados en los sitios
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Con la prevención de pérdida de datos (DLP) en SharePoint Online, puede detectar documentos que contengan datos confidenciales en todo el espacio empresarial. Una vez detectados los documentos, puede trabajar con los propietarios de documentos para proteger los datos. Este tema puede ayudarle a formar una consulta para buscar datos confidenciales.
ms.openlocfilehash: 8ea9622242775e7d411280707a61ba10aa02f4f2
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455072"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Crear una consulta para buscar datos confidenciales almacenados en los sitios

Los usuarios suelen almacenar datos confidenciales, como números de tarjetas de crédito, números de la seguridad social o personal, en sus sitios y con el tiempo, esto puede exponer a una organización a un riesgo significativo de pérdida de datos. Los documentos almacenados en sitios, incluidos los sitios de OneDrive para la empresa, se pueden compartir con personas de fuera de la organización que no deberían tener acceso a la información. Con la prevención de pérdida de datos (DLP) en SharePoint Online, puede detectar documentos que contengan datos confidenciales en todo el espacio empresarial. Una vez detectados los documentos, puede trabajar con los propietarios de documentos para proteger los datos. Este tema puede ayudarle a formar una consulta para buscar datos confidenciales.
  
> [!NOTE]
> El descubrimiento electrónico o la DLP son características Premium que requieren [SharePoint Online plan 2](https://go.microsoft.com/fwlink/?LinkId=510080). 
  
## <a name="forming-a-basic-dlp-query"></a>Formación de una consulta básica de DLP

Una consulta básica de DLP está formada por tres partes: SensitiveType, intervalo de recuento e intervalo de confianza. Tal y como se muestra en el siguiente gráfico, se requiere **SensitiveType: "\<\>Type"** y tanto**|\<el intervalo\> ** de recuento como el intervalo**|\<\> de confianza** son opcionales. 
  
![Consulta de ejemplo dividida entre obligatorio y opcional](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>Tipo confidencial: obligatorio

¿Qué es cada parte? Las consultas de DLP de SharePoint normalmente comienzan `SensitiveType:"` con la propiedad y un nombre de tipo de información desde el inventario de tipos de `"` [información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999)y terminan con un. También puede usar el nombre de un [tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md) que haya creado para su organización. Por ejemplo, tal vez esté buscando documentos que contienen números de tarjetas de crédito. En dicha instancia, use el siguiente formato: `SensitiveType:"Credit Card Number"`. Como no incluyó intervalo de recuento o intervalo de confianza, la consulta devuelve todos los documentos en los que se detecta un número de tarjeta de crédito. Esta es la consulta más sencilla que se puede ejecutar y devuelve la mayoría de los resultados. Tenga en cuenta que la ortografía y el espaciado del tipo confidencial son importantes. 
  
### <a name="ranges---optional"></a>Intervalos: opcionales

Las dos partes siguientes son rangos, así que vamos a examinar rápidamente qué aspecto tiene un rango. En las consultas de DLP de SharePoint, un intervalo básico se representa mediante dos números separados por dos puntos, que tiene `[number]..[number]`el siguiente aspecto:. Por ejemplo, si `10..20` se usa, ese intervalo podría capturar números de 10 a 20. Hay muchas combinaciones de intervalos diferentes y varias de ellas se tratan en este tema. 
  
Vamos a agregar un intervalo de recuento a la consulta. Puede usar el intervalo de recuento para definir el número de repeticiones de información confidencial que debe contener un documento antes de que se incluya en los resultados de la consulta. Por ejemplo, si desea que la consulta devuelva sólo documentos que contengan exactamente cinco números de tarjeta de crédito `SensitiveType:"Credit Card Number|5"`, use lo siguiente:. El intervalo de recuento también puede ayudar a identificar los documentos que suponen altos niveles de riesgo. Por ejemplo, su organización puede considerar como un riesgo alto los documentos con cinco o más números de tarjeta de crédito. Para buscar documentos que se ajusten a este criterio, debe usar `SensitiveType:"Credit Card Number|5.."`esta consulta:. Como alternativa, puede buscar documentos con cinco o menos números de tarjeta de crédito con esta consulta: `SensitiveType:"Credit Card Number|..5"`. 
  
#### <a name="confidence-range"></a>Intervalo de confianza

Por último, el intervalo de confianza es el nivel de confianza con el que el tipo confidencial detectado coincide en realidad. Los valores para el intervalo de confianza funcionan de forma similar al intervalo de recuento. Puede crear una consulta sin incluir un intervalo de recuento. Por ejemplo, para buscar documentos con cualquier número de números de tarjetas de crédito, siempre que el intervalo de confianza sea del 85 por ciento o superior, debería usar esta `SensitiveType:"Credit Card Number|*|85.."`consulta:. 
  
> [!IMPORTANT]
> El asterisco ( `*`) es un carácter comodín que significa que cualquier valor funciona. Puede usar el carácter comodín ( `*`) tanto en el intervalo de recuento como en el intervalo de confianza, pero no en un tipo confidencial. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Propiedades de consulta y operadores de búsqueda adicionales disponibles en el centro de exhibición de documentos electrónicos

DLP en SharePoint también presenta la propiedad LastSensitiveContentScan, que puede ayudarle a buscar archivos examinados dentro de un período de tiempo específico. Para obtener ejemplos de consultas `LastSensitiveContentScan` con la propiedad, vea los [ejemplos de consultas complejas](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries) en la siguiente sección. 
  
No solo puede usar propiedades específicas de DLP para crear una consulta, sino también las propiedades de búsqueda estándar de eDiscovery de `Author` SharePoint `FileExtension`, como o. Puede usar operadores para crear consultas complejas. Para obtener la lista de las propiedades y los operadores disponibles, consulte la publicación [usar propiedades de búsqueda y operadores con entrada de blog de eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093) . 
  
## <a name="examples-of-complex-queries"></a>Ejemplos

En los ejemplos siguientes se usan diferentes tipos, propiedades y operadores de distinción para ilustrar cómo puede ajustar las consultas para encontrar exactamente lo que está buscando.
  
|**Query**|**Explicación**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |El nombre puede parecer extraño porque es tan largo, pero es el nombre correcto para ese tipo confidencial. Asegúrese de usar nombres exactos del [inventario de tipos de información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999). También puede usar el nombre de un [tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md) que haya creado para su organización.  <br/> |
| "SensitiveType:" número de tarjeta de crédito|1.. 4294967295|1.. 100 "' <br/> |Esto devuelve documentos con al menos una coincidencia con el tipo confidencial "número de tarjeta de crédito". Los valores de cada intervalo son los respectivos valores mínimos y máximos. Una forma más sencilla de escribir esta consulta es `SensitiveType:"Credit Card Number"`, pero ¿Dónde está la diversión?  <br/> |
| "SensitiveType:" número de tarjeta de crédito| 5.. 25 "y LastSensitiveContentScan:" 8/11/2018.. 8/13/2018 "' <br/> |Esto devuelve los documentos con 5-25 números de tarjeta de crédito que fueron examinados del 11 de agosto de 2018 al 13 de agosto de 2018.  <br/> |
| "SensitiveType:" número de tarjeta de crédito| 5.. 25 "y LastSensitiveContentScan:" 8/11/2018.. 8/13/2018 "no FileExtension: XLSX" <br/> |Esto devuelve los documentos con 5-25 números de tarjeta de crédito que fueron examinados del 11 de agosto de 2018 al 13 de agosto de 2018. Los archivos con una extensión XLSX no se incluyen en los resultados de la consulta.  `FileExtension`es una de las muchas propiedades que se pueden incluir en una consulta. Para obtener más información, vea [using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |Esto devuelve los documentos que contienen un número de tarjeta de crédito o un número de seguro social.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Ejemplos

No todas las consultas son iguales. En la siguiente tabla, se proporcionan ejemplos de consultas que no funcionan con DLP en SharePoint y se describe por qué.
  
|**Consulta no compatible**|**Motivo**|
|:-----|:-----|
| "SensitiveType:" número de tarjeta de crédito|.."` <br/> |Debe agregar, al menos, un número.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" no es un nombre de tipo confidencial válido. Solo los nombres del [inventario de tipos de información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999) funcionan en las consultas de DLP.  <br/> |
| "SensitiveType:" número de tarjeta de crédito|0 "' <br/> |Cero no es válido como valor mínimo o como valor máximo en un intervalo.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Es posible que sea difícil ver, pero hay un espacio en blanco adicional entre "Credit" y "Card" que hace que la consulta no sea válida. Use nombres de tipo confidenciales exactos del [inventario de tipos de información confidencial](https://go.microsoft.com/fwlink/?LinkID=509999).  <br/> |
| "SensitiveType:" número de tarjeta de crédito|1.. 3 "' <br/> |La parte de dos puntos no debe estar separada por un espacio.  <br/> |
| "SensitiveType:" número de tarjeta de crédito| |1..|80.. "' <br/> |Hay demasiados delimitadores de canalización (|). Siga este formato en su lugar: ' SensitiveType: "número de tarjeta de crédito|1..|80.. "' <br/> |
| "SensitiveType:" número de tarjeta de crédito|1..|80.. 101 "' <br/> |Como los valores de confianza representan un porcentaje, no pueden exceder de 100. Elija un número del 1 al 100 en su lugar.  <br/> |
   
## <a name="for-more-information"></a>Más información

[Información que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
  
[Ejecutar una búsqueda de contenido en el centro de &amp; seguridad y cumplimiento de Office 365](run-a-content-search-in-the-security-and-compliance-center.md)
  
[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
  

