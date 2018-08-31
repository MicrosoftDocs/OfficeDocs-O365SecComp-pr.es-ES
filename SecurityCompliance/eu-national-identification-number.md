---
title: Número de identificación de la UE nacional
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de número nacional de identificación de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536137"
---
# <a name="eu-national-identification-number"></a>Número de identificación de la UE nacional

En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de número nacional de identificación de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Una combinación de 24 caracteres de letras, números y caracteres especiales
  
### <a name="pattern"></a>Patrón

24 caracteres:
  
-  22 letras (no distingue mayúsculas de minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más 
    
- (No distingue mayúsculas de minúsculas) de dos letras, dígitos, barras diagonales inversas, barras diagonales, signos más o signos igual
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_austria_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_austria_eu_national_id_card` se encuentra. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeunationalidcard"></a>Keywords_austria_eu_national_id_card

número de identidad austriaco
  
número de identidad nacional
  
número de identidad
  

national id
  
personalausweis República österreich
  
## <a name="belgium"></a>Bélgica

Para obtener información detallada, vea la sección "Número nacional de Bélgica" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Diez dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Diez dígitos sin espacios y los delimitadores
  
-  Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD) 
    
- Dos dígitos que se corresponden con el orden de nacimiento
    
- Un dígito que corresponde al género: un dígito par para masculino y un dígito impar para hembra
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_national_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_bulgaria_national_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_national_number` busca contenido que coincide con el patrón. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsbulgarianationalnumber"></a>Keywords_bulgaria_national_number

egn
  
egn #
  
Búlgaro número nacional
  
número nacional
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
número de identificación personal
  
personalidnumber #
  
ЕДИНЕН ГРАЖДАНСКИ НОМЕР
  
edinen grazhdanski nomer
  
ЕГН
  
ЕГН #
  
## <a name="croatia"></a>Croacia

Para obtener información detallada, vea la sección "Número de identidad Croacia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

Diez dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

 Diez dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_cyprus_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_cyprus_eu_national_id_card` se encuentra. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscypruseunationalidcard"></a>Keywords_cyprus_eu_national_id_card

número de identificador de tarjeta
  
número de identificación nacional
  
número de identificación personal
  
número de tarjeta de identidad
  
ΤΑΥΤΟΤΗΤΑΣ
  
## <a name="czech-republic"></a>República Checa

Para obtener información detallada, vea la sección "Número nacional de identidad de checo" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="denmark"></a>Dinamarca

Para obtener información detallada, vea la sección "Número de identificación Personal de Dinamarca" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Un dígito que corresponde al sexo y century de nacimiento (masculino número impar, número par femenino; 1-2: 19 century; 3-4: 20 century; 5-6: century 21)
    
- Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)
    
- Tres dígitos que se corresponden con un número de serie separación de nacimiento en la misma fecha de personas
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_estonia_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsestoniaeunationalidcard"></a>Keywords_estonia_eu_national_id_card

código de identificación personal
  
número de identificación personal
  
número de identificación nacional
  
número nacional
  
número de identificación personal
  
personalidnumber #
  
IK
  
isikukood
  
identificador de kaart
  
## <a name="finland"></a>Finlandia

Para obtener información detallada, vea la sección "Finlandia nacional ID" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Para obtener información detallada, vea la sección "Francia nacional tarjeta de identificación (CNI)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener información detallada, vea la sección "Número de tarjeta de identidad de Alemania" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Para obtener información detallada, vea la sección "tarjeta de identificación nacional Grecia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

11 dígitos
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
-  Un dígito que corresponde al género (hombre de 1, 2-hembra, de otros números también son posibles para los ciudadanos nacidos antes de 1900 o los ciudadanos con posea doble) 
    
- Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)
    
- Tres dígitos que se corresponden con un número de serie
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_hungary_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeunationalidcard"></a>Keywords_hungary_eu_national_id_card

número de identificación personal
  
identification number

  
número de identificación personal
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Una combinación de nueve caracteres de letras, dígitos y un espacio en el patrón especificado
  
### <a name="pattern"></a>Patrón

Una combinación de nueve caracteres de letras, dígitos y un espacio en el patrón especificado
  
Desde 01 de enero de 2013 hasta ahora:
  
-  Siete dígitos  
    
- Dígito de un control
    
- Un espacio o la letra mayúscula "W" (se distingue entre mayúsculas y minúsculas)
    
Antes de 01 de enero de 2013:
  
-  Siete dígitos  
    
- Dígito de un control
    
- Un espacio o una letra mayúscula (distinguir mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función busca contenido que coincide con el patrón.
    
- Se ha encontrado una palabra clave de.
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función busca contenido que coincide con el patrón.
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsirelandeunationalidcard"></a>Keywords_ireland_eu_national_id_card

número de servicio público personal
  
PPS no
  
número de ingresos y seguridad social
  
RSI no
  
número de identificación personal
  
identification number

  
número de identificación personal
  
uimhir phearsanta seirbhíse poiblí
  
uimh. PSP
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Una combinación de 16 caracteres de letras y dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

Una combinación de 16 caracteres de letras y dígitos:
  
- Tres letras que corresponden a los tres primeros consonantes en el nombre de la familia
    
- Tres letras que corresponden a la primera, tercera y cuarta consonantes en el nombre
    
- Dos dígitos que corresponden a la última dígitos del año de nacimiento
    
- Una letra que corresponde a la letra para el mes de nacimiento: letras se usan en orden alfabético, pero se usan sólo las letras A E, H, L, M, P, R a T (por lo tanto, es enero y octubre es R)
    
- Dos dígitos que se corresponden con el día del mes de nacimiento, con el fin de diferenciar entre sexos, 40 se agrega en el día de nacimiento para mujeres
    
- Cuatro dígitos que se corresponde con el código de área específico para el ayuntamiento donde surgió la persona (códigos de todo el país se usan para países externas)
    
- Un dígito de paridad
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_italy_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsitalyeunationalidcard"></a>Keywords_italy_eu_national_id_card

código personal
  
número de código personal
  
número de certificado personal
  
código fiscal
  
personalcodeno #
  
número de identificación personal
  
código de identificación personal
  
Codice personale
  
numero certificato personale
  
numero personale
  
numero identificador personale
  
Codice identificador personale
  
Codice fiscale
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

de 11 dígitos y un guión en el formato especificado
  
### <a name="pattern"></a>Patrón

de 11 dígitos y un guión:
  
-  Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA) 
    
- Un guión 
    
- Un dígito que corresponde a la century de nacimiento ("0" para century 19, "1" para century 20 y "2" para century 21)
    
- Cuatro dígitos, generadas de forma aleatoria
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_latvia_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordslatviaeunationalidcard"></a>Keywords_latvia_eu_national_id_card

código personal
  
número de código personal
  
número de certificado personal
  
personalcodeno #
  
número de identificación personal
  
código de identificación personal
  
kods roles
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos sin espacios y los delimitadores:
  
- Un dígito que corresponde a la persona género y century de nacimiento
    
-  Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD) 
    
- Tres dígitos que se corresponden con el número de serie de la fecha de nacimiento
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_lithuania_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordslithuaniaeunationalidcard"></a>Keywords_lithuania_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de servicio de ciudadanos
  
número de identidad única
  
uniqueidentityno #
  
código personal.
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas.
  
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

11 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
- Un dígito que corresponde a la persona género y century de nacimiento
    
-  Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD) 
    
- Tres dígitos que se corresponden con el número de serie de la fecha de nacimiento
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_luxemburg_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_luxemburg_eu_national_id_card` se encuentra. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsluxemburgeunationalidcard"></a>Keywords_luxemburg_eu_national_id_card

identificador personal
  
número de identificación personal
  
personalidno #
  
número de identificador único
  
personalidnumber #
  
clave de identificador único
  
código de identificación personal
  
uniqueidkey #
  
código individual
  
identificador de individual
  
identificador de eindeutige-nummer
  
identificador de eindeutige
  
identificador personal
  
numéro de identificación personal
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Siete dígitos seguidos de una letra
  
### <a name="pattern"></a>Patrón

Siete dígitos seguidos de una letra:
  
-  Siete dígitos  
    
- Una letra mayúscula (se distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_malta_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsmaltaeunationalidcard"></a>Keywords_malta_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de servicio de ciudadanos
  
número de identidad única
  
uniqueidentityno #
  
kodiċi numerali personali
  
numru ta ' identifikazzjoni uniku
  
tareas servizz de numru taċ-ċittadin
  
numru ta' identità uniku
  
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

Nueve dígitos sin espacios o delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se ha encontrado una palabra clave de.
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsnetherlandseunationalidcard"></a>Keywords_netherlands_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de servicio de ciudadanos
  
número de identidad única
  
uniqueidentityno #
  
bsn
  
bsn #
  
código de numerieke persoonlijke
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>Polonia

Para obtener información detallada, vea la sección "Polonia nacional identificador (PESEL)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portugal

Para obtener información detallada, vea la sección "Número de tarjeta de Portugal ciudadanos" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

13 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_romania_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsromaniaeunationalidcard"></a>Keywords_romania_eu_national_id_card

código numérico personal
  
número de identificación único
  
cnp
  
cnp #
  
anclar
  
PIN #
  
número de seguro
  
insurancenumber #
  
número de identidad única
  
uniqueidentityno #
  
COD numérico personal
  
bacalao identificare personal
  
COD unic identificare
  
număr personal unic
  
număr identitate
  
număr identificare personal
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

Diez dígitos que contiene una barra diagonal inversa
  
### <a name="pattern"></a>Patrón

Diez dígitos que contiene una barra diagonal inversa:
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovakia_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsslovakiaeunationalidcard"></a>Keywords_slovakia_eu_national_id_card

número de nacimiento
  
número de identificación nacional
  
número de identificación personal
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
número nacional
  
número de identificación personal
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

13 dígitos sin espacios o delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos en el patrón especificado:
  
-  Siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL), donde "LLL" corresponde a la última tres dígitos del año de nacimiento 
    
- Dos dígitos que se corresponden con el área de nacimiento
    
- Tres dígitos que se corresponden con una combinación de género y número de serie para las personas nacidas en el mismo día (000-499 para hombre) y 500-999 para hembra
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovenia_eu_national_id_card` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordssloveniaeunationalidcard"></a>Keywords_slovenia_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de registro único
  
número de identidad única
  
uniqueidentityno #
  
número único ciudadanos maestra
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>España

### <a name="format"></a>Formato

Siete dígitos seguidos de un carácter
  
### <a name="pattern"></a>Patrón

Siete dígitos seguidos de un carácter
  
- Siete dígitos 
    
- Un dígito o letra (no distingue mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_spain_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_spain_eu_national_id_card"` se encuentra. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsspaineunationalidcard"></a>Keywords_spain_eu_national_id_card

DNI
  
número de identificación nacional
  
número de identidad nacional
  
número de seguro
  
número de identificación personal
  
identidad nacional
  
identidad personal no
  
número de identidad única
  
nationalidno #
  
UniqueID #
  
DNI #
  
nationalid #
  
NIE #
  
NIE
  
nienúmero #
  
número de NIE
  
documento nacional de identidad
  
identidad único
  
identidad de número nacional
  
número de DNI
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>Suecia

Para obtener información detallada, vea la sección "Suecia nacional ID" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

