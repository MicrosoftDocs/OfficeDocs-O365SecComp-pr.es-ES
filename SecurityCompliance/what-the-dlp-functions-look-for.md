---
title: Qué buscan las funciones de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: Los tipos de información confidencial buscan un patrón específico y corroborarlo asegurándose de que el formato es correcto, aplicando sumas de comprobación y buscando palabras clave relevantes u otra información. Parte de esta funcionalidad se realiza mediante funciones internas. En este tema se explica qué buscan estas funciones para ayudarle a comprender cómo funcionan los tipos de información confidencial predefinidos.
ms.openlocfilehash: 55c740e892e92902b368b2dcf7b0999cbc60f3ed
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219360"
---
# <a name="what-the-dlp-functions-look-for"></a>Qué buscan las funciones de DLP

La Prevención de pérdida de datos (DLP) incluye tipos de información confidencial, como el número de tarjeta de crédito y el número de tarjeta de débito de la UE, que están listos para su uso en las directivas de DLP. Estos tipos de información confidencial buscan un patrón específico y lo comprueban asegurándose de que el formato es el adecuado, forzando las sumas de comprobación y buscando palabras clave pertinentes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial de la tarjeta de crédito usa una función para buscar fechas con formato como la fecha de vencimiento, que ayuda a comprobar que un número es un número de tarjeta de crédito.
  
En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos. Para más información, consulte [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).
  
## <a name="funcusdate"></a>Func_us_date

Esta función busca una fecha con el formato que se usa habitualmente en Estados Unidos. Esto incluye los formatos "month/Day/Year", "month-Day-Year" y "month Day Year". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas. 
  
Ejemplos:
  
- 2 de diciembre de 2016
    
- 2 de diciembre de 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.
    
## <a name="funceudate"></a>Func_eu_date

Esta función busca una fecha en el formato que suele usarse en la UE (y en la mayoría de lugares fuera de los Estados Unidos). Esto incluye los formatos de "día/mes/año", "día-mes-año" y "día mes año". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- 2 Dec 2016
    
- 02 Dec 2016
    
- 2 16 de diciembre
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dic-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.
    
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec
    
- Francés
    
  - Janvier, février, Mars, Avril, Mai, juin Juillet, Août, Septembre, octobre, Novembre, décembre
    
  - janv. févr. Mars Avril Mai juin juil. Août Sept. Oct. Nov. déc.
    
- Alemán
    
  - Januar, Februar, März, April, Mai, Juni Juli, agosto, septiembre, Oktober, noviembre, Dezember
    
  - Ene./Jän. Feb. März Apr. Mai Juni Juli agosto de la OKT. Nov dez.
    
- Italiano
    
  - Gennaio, Febbraio, marzo, Aprile, Maggio, Giugno, Luglio, agosto, Settembre, Ottobre, Novembre, dicembre
    
  - Genn. febbr. graduación. TA. Magg. Giugno Luglio AG. SETT. Ott. noviembre. Dic.
    
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV mar abr Mai Jun-Nov hace dez
    
- Español
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Enero Feb. marzo Abr. Mayo Jun. Jul. Agosto Sept./set. Oct. Nov. Dic.
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes en Portugués, que ahora están incluidos en `Func_eu_date` la función anterior. 
  
Esta función busca una fecha con el formato que se usa habitualmente en Portugués. El formato de esta función es el mismo que `Func_eu_date`en el idioma usado.
  
Ejemplos:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV mar abr Mai Jun-Nov hace dez
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes en holandés, que ahora están incluidos en `Func_eu_date` la función anterior. 
  
Esta función busca una fecha con el formato que se usa normalmente en holandés. El formato de esta función es el mismo que `Func_eu_date`en el idioma usado.
  
Ejemplos:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Holandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec
    
## <a name="funcexpirationdate"></a>Func_expiration_date

Esta función busca una fecha en los formatos usados normalmente por tarjetas de crédito y débito, que excluyen los días en favor de los meses. Esta función coincidirá con las fechas en el formato "mes/año", "mes-año", "[nombre del mes]" y "[abreviatura del mes] año". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.
  
Ejemplos
  
- MM/AA: por ejemplo, 01/11 o 1/11
    
- MM/AAAA: por ejemplo, 01/2011 o 1/2011
    
- MM-AA: por ejemplo 01-11 o 1-11
    
- MM-AAAA: por ejemplo 01-2000 o 1-2000
    
Los formatos siguientes admiten AA o AAAA:
  
- Mes-AAAA: por ejemplo, ene-2010, enero-2010, ene-10 o enero-10
    
- Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"
    
- MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"
    
- Mes/AAAA: por ejemplo, "enero/2010" o "ene/2010" o "enero/10" o "ene/10"
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Jan Feb Marzo Apr mayo junio julio agosto Sept Oct Nov Dic
    
## <a name="funcusaddress"></a>Func_us_address

Esta función busca un nombre de estado de los Estados Unidos o una abreviatura postal seguidos de un código postal válido, tal como se usan en las direcciones postales. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.
  
Ejemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

