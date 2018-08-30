---
title: Qué buscan las funciones de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: Los tipos de información confidencial busca un patrón específico y comprobar al garantizar adecuada formato, aplicar las sumas de comprobación y busca las palabras clave relevantes u otra información. Parte de esta funcionalidad se realiza por funciones internas. En este tema se explica lo que estas funciones buscan, que le ayudarán a comprender cómo funcionan los tipos de información confidencial predefinidos.
ms.openlocfilehash: 510f98e2b4e1d2480550f11026cf445be6ffc931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013764"
---
# <a name="what-the-dlp-functions-look-for"></a>Qué buscan las funciones de DLP

La Prevención de pérdida de datos (DLP) incluye tipos de información confidencial, como el número de tarjeta de crédito y el número de tarjeta de débito de la UE, que están listos para su uso en las directivas de DLP. Estos tipos de información confidencial buscan un patrón específico y lo comprueban asegurándose de que el formato es el adecuado, forzando las sumas de comprobación y buscando palabras clave pertinentes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial de la tarjeta de crédito usa una función para buscar fechas con formato como la fecha de vencimiento, que ayuda a comprobar que un número es un número de tarjeta de crédito.
  
En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos. Para más información, consulte [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).
  
## <a name="funcusdate"></a>Func_us_date

Esta función busca una fecha en el formato utilizado con frecuencia en los Estados Unidos Esto incluye los formatos "día/mes/año", "día-mes-año" y "mes del año de día". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas. 
  
Ejemplos
  
- 2 de diciembre de 2016
    
- 2 de diciembre de 2016
    
- Dic 02 2016
    
- 2/12/2016
    
- 02/12/16
    
- Dic-2-2016
    
- 12-2-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Enero febrero marzo abril mayo junio julio agosto septiembre octubre noviembre Dic.
    
## <a name="funceudate"></a>Func_eu_date

Esta función busca una fecha en el formato que suele usarse en la UE (y en la mayoría de lugares fuera de los Estados Unidos). Esto incluye los formatos de "día/mes/año", "día-mes-año" y "día mes año". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.
  
Ejemplos
  
- 2 de diciembre de 2016
    
- Dic 02 2016
    
- 16 de diciembre de 2
    
- 12/2/2016
    
- 16/12/02
    
- 2-Dic-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Enero febrero marzo abril mayo junio julio agosto septiembre octubre noviembre Dic.
    
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Ene febrero maart Abr mei jun julio agosto sep septiembre oct okt noviembre Dic
    
- Francés
    
  - enero, febrero, mars, avril, mayo, julio de junio, août, septiembre, octubre, noviembre, diciembre de
    
  - janv. févr. mar avril mayo junio juil. septiembre août. octubre noviembre. déc.
    
- Alemán
    
  - jänuar, februar, märz, abril, mayo, juni juli, agosto, septiembre, octubre, noviembre, dezember
    
  - Ene. / Jän. Febrero März abril mayo Juni Juli agosto septiembre Okt. Dez de noviembre.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, noviembre, dicembre
    
  - Genn. febbr. mar. Abr. magg. giugno luglio ag. configuración. ott. noviembre. Dic.
    
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar abr mai jun julio hace establecidos dez noviembre
    
- Español
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero febrero. marzo abr. mayo Jun julio. agosto septiembre o establecer. octubre noviembre. Dic.
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1 (en desuso)

> [!NOTE]
> Esta función está desusada porque admite únicamente nombres de mes portugués, que ahora se incluyen en el `Func_eu_date` función anterior. 
  
Esta función busca una fecha en el formato de uso frecuente en portugués. El formato de esta función es el mismo que `Func_eu_date`y diferentes sólo en el idioma usado.
  
Ejemplos
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 12/2/2016
    
- 16/12/02
    
- 2-Dez-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar abr mai jun julio hace establecidos dez noviembre
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2 (en desuso)

> [!NOTE]
> Esta función está desusada porque admite únicamente nombres de mes neerlandés, que ahora se incluyen en el `Func_eu_date` función anterior. 
  
Esta función busca una fecha en el formato de uso frecuente en neerlandés. El formato de esta función es el mismo que `Func_eu_date`y diferentes sólo en el idioma usado.
  
Ejemplos
  
- 2 Mei 2016
    
- mei 02 2016
    
- Mei 2 16
    
- 12/2/2016
    
- 16/12/02
    
- 2-Mei-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Holandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Ene febrero maart Abr mei jun julio agosto sep septiembre oct okt noviembre Dic
    
## <a name="funcexpirationdate"></a>Func_expiration_date

Esta función busca una fecha en los formatos utilizadas frecuentemente por tarjetas de debe y haber, que excluyen días en favor de meses. Esta función coincidirá con las fechas en formato de "mes/año", "día-mes-año", "[nombre del mes] año" y "[abreviatura del mes]". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.
  
Ejemplos
  
- MM/AA: por ejemplo, 01/11 o 1/11
    
- MM/AAAA: por ejemplo, 01/2011 o 1/2011
    
- MM-AA: por ejemplo 01-11 o 1-11
    
- MM-AAAA: por ejemplo 01-2000 o 1-2000
    
Los formatos siguientes admiten AA o AAAA:
  
- Mes-AAAA: por ejemplo, ene-2010, enero-2010, ene-10 o enero-10
    
- Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"
    
- MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"
    
- Mes/aaaa--por ejemplo, ' enero/2010' o ' Ene/2010' o ' enero/10' o ' Ene/10'
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Febrero de Ene Abr de Mar, es posible que junio julio agosto septiembre octubre noviembre Dic
    
## <a name="funcusaddress"></a>Func_us_address

Esta función busca un nombre de estado de los Estados Unidos o una abreviatura postal seguidos de un código postal válido, tal como se usan en las direcciones postales. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.
  
Ejemplos
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

