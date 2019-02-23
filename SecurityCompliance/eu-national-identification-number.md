---
title: Número de identificación nacional de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación nacional de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 9a85fd6954f39de348874e03268a2e19ae47366c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220640"
---
# <a name="eu-national-identification-number"></a>Número de identificación nacional de la UE

En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación nacional de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Una combinación de letras, dígitos y caracteres especiales de 24 caracteres
  
### <a name="pattern"></a>Patrón

24 caracteres:
  
-  22 letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más 
    
- Dos letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales, signos más o signos igual
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_austria_eu_national_id_card` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_austria_eu_national_id_card` palabra clave de. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsaustriaeunationalidcard"></a>Keywords_austria_eu_national_id_card

número de identidad austriaco
  
número de identidad nacional
  
número de identidad
  

national id
  
personalausweis Republik Österreich
  
## <a name="belgium"></a>Bélgica

Para obtener más información, consulte la sección "número nacional de Bélgica" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Diez dígitos sin espacios y delimitadores
  
-  Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
    
- Dos dígitos que corresponden a la orden de nacimiento
    
- Un dígito que corresponde al género: un dígito par para macho y un dígito impar para hembra
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_national_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_bulgaria_national_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsbulgarianationalnumber"></a>Keywords_bulgaria_national_number

EGN
  
EGN #
  
número nacional búlgaro
  
número nacional
  
social security number

  
nationalnumber #
  
SSN
  
SSN
  
nationalnumber
  
BNN #
  
BNN
  
número de identificación personal
  
personalidnumber #
  
единен граждански номер
  
edinen grazhdanski Nomer
  
егн
  
егн #
  
## <a name="croatia"></a>Croacia

Para obtener más información, consulte la sección "número de identidad de Croacia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

Diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

 Diez dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_cyprus_eu_national_id_card` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_cyprus_eu_national_id_card` palabra clave de. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordscypruseunationalidcard"></a>Keywords_cyprus_eu_national_id_card

número de tarjeta de identificación
  
número de identificación nacional
  
número de identificación personal
  
número de tarjeta de identidad
  
ταυτοτητασ
  
## <a name="czech-republic"></a>Chequia

Para obtener más información, consulte la sección "número de identidad nacional Checa" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="denmark"></a>Dinamarca

Para obtener más información, vea la sección sobre el número de identificación personal de Dinamarca en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Un dígito que corresponde al sexo y al siglo de nacimiento (número impar macho, par hembra; 1-2: siglo XIX; 3-4: siglo XX; 5-6: siglo XXI)
    
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
    
- Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_estonia_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsestoniaeunationalidcard"></a>Keywords_estonia_eu_national_id_card

código de identificación personal
  
número de identificación personal
  
número de identificación nacional
  
número nacional
  
número de identificación personal
  
personalidnumber #
  
IK
  
isikukood
  
ID-Kaart
  
## <a name="finland"></a>Finlandia

Para obtener más información, consulte la sección "identificación nacional de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Para obtener más información, vea la sección sobre la tarjeta de identificación nacional (CNI) de Francia en la [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener más información, consulte la sección "número de tarjeta de identidades Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Para obtener más información, consulte la sección "tarjeta de identificación nacional de Grecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

11 dígitos
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
-  Un dígito que corresponde a sexo (1-macho, 2-hembra, otros números también son posibles para los ciudadanos nacidos antes del 1900 o los ciudadanos con doble nacionalidad) 
    
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
    
- Tres dígitos que corresponden a un número de serie
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_hungary_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordshungaryeunationalidcard"></a>Keywords_hungary_eu_national_id_card

número de identificación personal
  
identification number

  
número de identificación personal
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Una combinación de Letras de nueve caracteres, dígitos y un espacio en el patrón especificado
  
### <a name="pattern"></a>Patrón

Una combinación de Letras de nueve caracteres, dígitos y un espacio en el patrón especificado
  
De 01 de enero de 2013 a ahora:
  
-  Siete dígitos  
    
- Un dígito de control
    
- Un espacio o la letra mayúscula "W" (distingue entre mayúsculas y minúsculas)
    
Antes del 01 de enero de 2013:
  
-  Siete dígitos  
    
- Un dígito de control
    
- Un espacio o una letra mayúscula (distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función busca contenido que coincide con el patrón.
    
- Se encuentra una palabra clave de.
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsirelandeunationalidcard"></a>Keywords_ireland_eu_national_id_card

número de servicio público personal
  
n.º de PPS
  
número de la seguridad social y de ingresos
  
RSI no
  
número de identificación personal
  
identification number

  
número de identificación personal
  
uimhir phearsanta seirbhíse poiblí
  
uimh. PSP
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Una combinación de letras y dígitos de 16 caracteres en el patrón especificado
  
### <a name="pattern"></a>Patrón

Una combinación de letras y dígitos de 16 caracteres:
  
- Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia
    
- Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre
    
- Dos dígitos que corresponden a los últimos dígitos del año de nacimiento
    
- Una letra que corresponde a la carta del mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)
    
- Dos dígitos que corresponden al día del mes de nacimiento: para diferenciar entre los sexos, 40 se agrega al día de nacimiento para las mujeres
    
- Cuatro dígitos que corresponden al código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros)
    
- Un dígito de paridad
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_italy_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsitalyeunationalidcard"></a>Keywords_italy_eu_national_id_card

código personal
  
número de código personal
  
número de certificado personal
  
Código fiscal
  
personalcodeno #
  
número de identificación personal
  
código de identificación personal
  
personal Codice
  
numero certificato personal
  
personal numero
  
personal del identificador numero
  
personal del identificador Codice
  
Codice fiscal
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

11 dígitos y un guión en el formato especificado
  
### <a name="pattern"></a>Patrón

11 dígitos y un guión:
  
-  Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
    
- Un guión 
    
- Un dígito que corresponde al siglo de nacimiento ("0" para el siglo XIX, "1" para el siglo XX y "2" para el siglo XXI)
    
- Cuatro dígitos, generados aleatoriamente
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_latvia_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordslatviaeunationalidcard"></a>Keywords_latvia_eu_national_id_card

código personal
  
número de código personal
  
número de certificado personal
  
personalcodeno #
  
número de identificación personal
  
código de identificación personal
  
roles kods
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos sin espacios y delimitadores:
  
- Un dígito que corresponde al sexo de la persona y al siglo de nacimiento
    
-  Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
    
- Tres dígitos que corresponden al número de serie de la fecha de nacimiento
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_lithuania_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordslithuaniaeunationalidcard"></a>Keywords_lithuania_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de servicio de ciudadanos
  
número de identidad único
  
uniqueidentityno #
  
código personal.
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo número
  
piliečio paslaugos número
  
unikalus identifikavimo kodas
  
asmens kodas.
  
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
- Un dígito que corresponde al sexo de la persona y al siglo de nacimiento
    
-  Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
    
- Tres dígitos que corresponden al número de serie de la fecha de nacimiento
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_luxemburg_eu_national_id_card` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_luxemburg_eu_national_id_card` palabra clave de. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsluxemburgeunationalidcard"></a>Keywords_luxemburg_eu_national_id_card

identificador personal
  
número de identificación personal
  
personalidno #
  
número de identificador único
  
personalidnumber #
  
clave de identificador única
  
código de identificación personal
  
uniqueidkey #
  
Código individual
  
identificador individual
  
eindeutige ID-Nummer
  
identificador eindeutige
  
identificador personnelle
  
personal de numéro d'identification
  
idpersonnelle #
  
persönliche Identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Siete dígitos seguidos de una letra
  
### <a name="pattern"></a>Patrón

Siete dígitos seguidos de una letra:
  
-  Siete dígitos  
    
- Una letra mayúscula (distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_malta_eu_national_id_card` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_malta_eu_national_id_card` palabra clave de. 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_malta_eu_national_id_card` regular busca contenido que coincide con el patrón. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsmaltaeunationalidcard"></a>Keywords_malta_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de servicio de ciudadanos
  
número de identidad único
  
uniqueidentityno #
  
kodiċi numerali personali
  
numru ta ' identifikazzjoni uniku
  
numru Servizz taċ-ċittadin
  
numru ta ' Identità uniku
  
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

Nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de.
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsnetherlandseunationalidcard"></a>Keywords_netherlands_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de servicio de ciudadanos
  
número de identidad único
  
uniqueidentityno #
  
BSN
  
BSN
  
persoonlijke numerieke código
  
Uniek identificatienummer
  
Burgerservicenummer
  
Uniek identiteitsnummer
  
## <a name="poland"></a>Polonia

Para obtener más información, consulte la sección "identificación nacional (PESEL) de Polonia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portugal

Para obtener más información, consulte la sección "número de tarjeta de ciudadano de Portugal" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

13 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_romania_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsromaniaeunationalidcard"></a>Keywords_romania_eu_national_id_card

código numérico personal
  
número de identificación único
  
CNP
  
CNP #
  
anclar
  
patilla
  
número de seguro
  
insurancenumber #
  
número de identidad único
  
uniqueidentityno #
  
personal numérico de pago
  
c.o.d. identificare personal
  
Bacalao UNIC identificare
  
număr personal UNIC
  
număr identitate
  
număr identificare personal
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

Diez dígitos que contienen una barra diagonal inversa
  
### <a name="pattern"></a>Patrón

Diez dígitos que contienen una barra diagonal inversa:
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovakia_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsslovakiaeunationalidcard"></a>Keywords_slovakia_eu_national_id_card

número de nacimiento
  
número de identificación nacional
  
número de identificación personal
  
social security number

  
nationalnumber #
  
SSN
  
SSN
  
número nacional
  
número de identificación personal
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos en el patrón especificado:
  
-  Siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL) donde "LLL" corresponde a los tres últimos dígitos del año de nacimiento. 
    
- Dos dígitos que corresponden al área de nacimiento
    
- Tres dígitos que corresponden a una combinación de sexo y número de serie de las personas nacidos el mismo día (000-499 para macho y 500-999 para hembras)
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovenia_eu_national_id_card` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordssloveniaeunationalidcard"></a>Keywords_slovenia_eu_national_id_card

código numérico personal
  
número de identificación único
  
número de registro único
  
número de identidad único
  
uniqueidentityno #
  
número único de ciudadano principal
  
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
    
- Un dígito o letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_spain_eu_national_id_card` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_spain_eu_national_id_card"` palabra clave de. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsspaineunationalidcard"></a>Keywords_spain_eu_national_id_card

DNI
  
número de identificación nacional
  
número de identidad nacional
  
número de seguro
  
número de identificación personal
  
identidad nacional
  
número de la identidad personal
  
número de identidad único
  
nationalidno #
  
UniqueID
  
DNI
  
nationalid #
  
NIE
  
NIE
  
nienúmero #
  
NIE número
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
número de DNI
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>Suecia

Para obtener más información, consulte la sección "identificación nacional de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Consulte también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

