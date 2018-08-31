---
title: Número de identificación fiscal de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial del número de identificación de impuestos de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536170"
---
# <a name="eu-tax-identification-number"></a>Número de identificación fiscal de la UE

En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial del número de identificación fiscal (TIN) de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Nueve dígitos con guión opcional y barra diagonal
  
### <a name="pattern"></a>Patrón

Nueve dígitos con guión opcional y barra diagonal hacia delante:
  
-  Dos dígitos 
    
- Un guion (opcional)
    
- Tres dígitos
    
- Una barra diagonal (opcional)
    
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_austria_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

número de impuestos
  
número
  
número de registro de impuestos
  
tax id

  
St.nr.
  
steuernummer
  
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

11 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Dos dígitos
    
- Un "0" o "1"
    
- Un dígito
    
- Un "0" o "1" o "2" o "3" 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_belgium_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_belgium_eu_tax_file_number` se encuentra. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

número de impuestos
  
número de registro nacional
  
número de registro de impuestos
  
tax id

  
NIF
  
NIF #
  
numéro de registre nacional
  
numéro de identificación fiscale
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Diez dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_bulgaria_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
número civil uniforme
  
bucn #
  
uniformcivilnumber #
  
identificador uniforme de civil
  
no civil uniforme
  
egn
  
número civil uniforme búlgaro
  
uniformcivilno #
  
egn #
  
УНИФОРМ ГРАЖДАНСКИ НОМЕР
  
Identificador de униформ
  
Identificador граждански униформ
  
УНИФОРМ ГРАЖДАНСКИ НЕ
  
## <a name="croatia"></a>Croacia

### <a name="format"></a>Formato

11 dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Diez dígitos, elegidos de manera aleatoria
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_croatia_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

número de impuestos
  
impuestos
  
tax id

  
OID
  
OID #
  
porezni broj
  
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

Ocho dígitos y una carta en el patrón especificado
  
### <a name="pattern"></a>Patrón

Ocho dígitos y una carta:
  
-  UN "0" 
    
- Siete dígitos 
    
- Una letra (no distingue mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_cyprus_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

número de impuestos
  
impuestos
  
tax id

  
código de identificación de impuestos
  
TIC
  
TIC #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ
  
ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="czech-republic"></a>República Checa

### <a name="format"></a>Formato

Nueve o diez dígitos con una barra diagonal inversa opcional
  
### <a name="pattern"></a>Patrón

Nueve o diez dígitos con un backslashl opcional:
  
- Seis dígitos 
    
- Una barra diagonal inversa (opcional)
    
- Tres o cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_czech_republic_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_czech_republic_eu_tax_file_number` se encuentra. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

número de impuestos
  
impuestos
  
tax id

  
número de personal
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Diez dígitos que contiene un guión
  
### <a name="pattern"></a>Patrón

Diez dígitos que contiene un hyphenl:
  
-  Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA) 
    
- Un guión 
    
- Cuatro dígitos que se corresponden con un número de secuencia donde el primer dígito corresponde a la century de nacimiento y el último dígito corresponde al género del individuo (impar para hombre e incluso para hembra)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_denmark_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

número de impuestos
  
impuestos
  
tax id

  
número de rcp
  
rcp #
  
Skat nummer
  
identificador de Skat
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
-  Un dígito que corresponde al género y century de nacimiento donde un número impar indica masculino y el número par indica hembra de la siguiente manera: 1, 2 para el century 19; 3, 4 para el vigésimo century; y 5, 6 para el century 21 
    
- Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)
    
- Tres dígitos que se corresponden con un número de serie separación de nacimiento en la misma fecha de personas
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_estonia_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

número de impuestos
  
impuestos
  
tax id

  
código personal
  
maksunumber
  
identificador de maksu
  
isikukood
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinación de 11 caracteres de dígitos, letras, y más y menos de inicio de sesión
  
### <a name="pattern"></a>Patrón

Una combinación de 11 caracteres de dígitos, letras, y más y menos de inicio de sesión:
  
- Seis dígitos
    
- Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distinguir mayúsculas de minúsculas), donde el signo más significa nacimiento entre 1800-1899, el signo menos iniciar sesión significa nacimiento entre 1900-1999 y "A" significa nacida 2000 y posterior
    
- Tres dígitos
    
- Una letra o un número
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_finland_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

identification number

  
identificador personal
  
número de identidad
  
número de identificación nacional finlandés
  
personalidnumber #
  
número de identificación nacional
  
número de Id.
  
identificador de nacional no.
  
número de identificación nacional
  
identificador de ningún
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
numero de identiteetti
  
Suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
numero de tunnus kansallinen
  
## <a name="france"></a>Francia

### <a name="format"></a>Formato

13 dígitos para individuos y nueve dígitos para entidades
  
### <a name="pattern"></a>Patrón

13 dígitos para las personas:
  
- Un dígito que debe ser 0, 1, 2 o 3
    
- 12 dígitos
    
Nueve dígitos para entidades
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_france_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

número de identificación fiscal
  
número de impuestos
  
tax id

  
numéro de identificación fiscale
  
## <a name="germany"></a>Alemania

### <a name="format"></a>Formato

11 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
-  Diez dígitos 
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_germany_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

número de impuestos
  
fiscal no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
número de identificación fiscal
  
identificación de impuestos no.
  
steuernummer
  
identificador de steuer
  
steueridentifikationsnummer
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_greece_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_greece_eu_tax_file_number` se encuentra. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

AFM
  
tin

  
identificador de impuestos no.
  
identificador de impuestos no
  
número de identificación fiscal
  
número de registro de impuestos
  
el registro de impuestos no.
  
AFM #
  
estaño #
  
taxidno #
  
taxregistryno #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
aφμ
  
aφμ αριθμός
  
ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ.
  
ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Diez dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Diez dígitos:
  
-  Un dígito que debe ser "8" 
    
- Cinco dígitos que se corresponden con el número de días entre la fecha 01/01/1867 y la fecha de nacimiento de la persona
    
- Tres dígitos que se corresponden con el número generado al azar para diferenciar los individuos nacidos en el mismo día
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_hungary_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

número de identificación fiscal húngaro
  
estaño húngaro
  
número de identificación fiscal
  
CIF
  
autoridad fiscal no
  
número de identidad de impuestos de impuestos Id.
  
taxidnumber #
  
estaño #
  
hungatiantin #
  
identificación de impuestos no
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Siete dígitos seguidos de una letra sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Siete dígitos seguidos de una letra:
  
-  Siete dígitos  
    
- Una letra (no distingue mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_ireland_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

servicio público no
  
servicio público personal no
  
PPS no
  
personal de servicio no
  
no de servicio de PPS
  
ppsno #
  
Irlandés pps no
  
publicserviceno #
  
número de servicio público personal
  
uimhir phearsanta seirbhíse poiblí
  
uimh de PPS
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

16 letras y dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

16 letras y dígitos:
  
-  Tres letras que corresponden a los tres primeros consonantes en el nombre de la familia 
    
- Tres letras que corresponden a la primera, tercera y cuarta consonantes en el nombre
    
- Dos dígitos que corresponden a la última dígitos del año de nacimiento
    
- Un dígito que corresponde al mes de nacimiento: letras se usan en orden alfabético, pero se usan sólo las letras A E, H, L, M, P, R a T (por lo tanto, es enero y octubre es R)
    
- Dos dígitos que se corresponden con el día del mes de nacimiento donde 40 se agrega en el día de nacimiento para mujeres diferenciar de machos
    
- Cuatro dígitos que se corresponden con un código de área específico para el ayuntamiento donde surgió la persona, los códigos de país se usan para países extranjeros
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_italy_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

número de impuestos
  
fiscal no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
código fiscal
  
Codice fiscale
  
## <a name="latvia"></a>Letonia

### <a name="format"></a>Formato

11 dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos en el patrón especificado
  
-  Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA) 
    
- Un dígito que corresponde a la century de nacimiento donde "0" corresponde a century 19, "1" corresponde a century 20, y "2" corresponde a century 21
    
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_latvia_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

número de impuestos
  
fiscal no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
número de identificación fiscal
  
identificación de impuestos no.
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 dígitos sin espacios o delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_lithuania_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

número de impuestos
  
fiscal no.
  
fiscal no #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
número de identificación fiscal
  
identificación de impuestos no.
  
identificador de mokesčių
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

13 dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos:
  
-  11 dígitos 
    
- Dos dígitos de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_luxemburg_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

número de impuestos
  
fiscal no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
número de identificación fiscal
  
identificación de impuestos no.
  
steuernummer
  
identificador de steuer
  
steueridentifikationsnummer
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Para los nacionales Maltés: 7 dígitos y una carta en el patrón especificado
  
No Maltés nacionales y entidades Maltés: 9 dígitos
  
### <a name="pattern"></a>Patrón

Maltés nacionales: 7 dígitos y una carta
  
-  Siete dígitos  
    
- Una letra (no distingue mayúsculas de minúsculas)
    
No Maltés nacionales y entidades Maltés: 9 dígitos
  
-  Nueve dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_malta_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

número de impuestos
  
fiscal no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
número de identificación fiscal
  
identificación de impuestos no.
  
numru tat-taxxa
  
identificador tat-taxxa
  
numru ta ' identifikazzjoni tat-taxxa
  
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

Nueve dígitos sin espacios o delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_netherlands_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

número de identificación fiscal (Países Bajos)
  
identificación de impuestos (Países Bajos)
  
número de identificación de impuestos de países bajos
  
identificación de impuestos de países bajos
  
número de identificación fiscal
  
id de impuestos holandés
  
número de identificación fiscal neerlandés
  
tax id

  
identificador de impuestos #
  
número de impuestos
  
fiscal no #
  
impuestos #
  
tin

  
estaño #
  
estaño (Países Bajos)
  
estaño de países bajos
  
países bajos belasting identificatienummer
  
identificatienummer van belasting
  
belasting identificatienummer
  
países bajos belasting identificatie
  
países bajos belasting identificador nummer
  
países bajos belastingnummer
  
BTW nummer
  
Nederlandse belasting identificatie
  
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

Once dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Once dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_poland_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

número de impuestos
  
fiscal no.
  
taxno #
  
taxnumber #
  
taxnumber
  
NIP
  
NIP #
  
tax id

  
identificador de impuestos #
  
identificador de NIP
  
identificador de NIP #
  
número de identificación fiscal
  
identificación de impuestos no.
  
CIF
  
Nº de IVA.
  
vatno #
  
identificador de RFC
  
identificador de RFC #
  
número identyfikacji podatkowej
  
Polski número identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formato

Nueve dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_portugal_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

número de impuestos
  
fiscal no.
  
taxno #
  
taxnumber #
  
taxnumber
  
NIF
  
NIF #
  
numero fiscal
  
número de identificação fiscal
  
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

13 dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_romania_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_romania_eu_tax_file_number` se encuentra. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id

  
número de identificación fiscal
  
archivo de impuestos no
  


tax file number
  
fiscal no
  
número de impuestos
  
taxid #
  
taxno #
  
identificador ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

10 dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovakia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovakia_eu_tax_file_number` se encuentra. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id

  
número de identificación fiscal
  
identificador de estaño
  
no estaño
  
identificador de estaño eslovaco
  
tin

  
archivo de impuestos no
  


tax file number
  
fiscal no
  
número de impuestos
  
taxid #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

Ocho dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovenia_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id

  
número de identificación fiscal
  
identificador de estaño
  
no estaño
  
identificador de estaño esloveno
  
tin

  
archivo de impuestos no
  


tax file number
  
fiscal no
  
número de impuestos
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
Številka davčne datoteke
  
## <a name="spain"></a>España

### <a name="format"></a>Formato

Siete u ocho dígitos y uno o dos letras en el patrón especificado
  
### <a name="pattern"></a>Patrón

Personas físicas españolas con una tarjeta de identidad nacional de España:
  
-  Ocho dígitos 
    
- Una letra mayúscula (distingue mayúsculas de minúsculas) 
    
No residente Spaniards sin una tarjeta de identidad nacional de España
  
- Una letra mayúscula "L" (distingue mayúsculas de minúsculas)
    
- Siete dígitos 
    
- Una letra mayúscula (distingue mayúsculas de minúsculas) 
    
Spaniards residente menores de 14 años sin una tarjeta de identidad de nacionales de España:
  
- Una letra mayúscula "K" (distingue mayúsculas de minúsculas)
    
-  Siete dígitos  
    
- Una letra mayúscula (distingue mayúsculas de minúsculas)
    
Foreigners con el número de identificación de un Foreigner
  
- Uno en mayúsculas es decir letra "X", "Y" o "Z" (distingue mayúsculas de minúsculas) 
    
- Siete dígitos 
    
- Una letra mayúscula (distingue mayúsculas de minúsculas) 
    
Foreigners sin número de identificación de un Foreigner
  
- Una letra mayúscula que es "M" (distingue mayúsculas de minúsculas) 
    
- Siete dígitos 
    
- Una letra mayúscula (distingue mayúsculas de minúsculas) 
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_spain_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id

  
número de identificación fiscal
  
identificador de CIF
  
CIF no
  
identificador de cif español
  
CIF
  
archivo de impuestos no
  
número de cif español
  


tax file number
  
Español cif no
  
fiscal no
  
número de impuestos
  
taxid #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de impuesto Entreprise
  
número de identificación fiscal
  
número de CIF
  
cifnúmero #
  
## <a name="sweden"></a>Suecia

### <a name="format"></a>Formato

Diez dígitos y un símbolo en el patrón especificado
  
### <a name="pattern"></a>Patrón

Diez dígitos y un símbolo:
  
-  Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD) 
    
- Un signo más, signo menos o barra diagonal inversa
    
- Tres dígitos que hacen que la identificación de número único where: 
    
  - Para los números emitidos antes de 1990, el dígito séptimo y octavo identificar la provincia de nacimiento o personas foreign-born
    
  - El dígito en la posición noveno indica género por puede ser impar para hombre o incluso para hembra
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_sweden_eu_tax_file_number` se encuentra. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id

  
identificador de impuestos no.
  
número de identificación fiscal
  
tax identification

  
identificación de impuestos #
  
fiscal no.
  
impuestos #
  
taxid #
  
archivo de impuestos
  
archivo de impuestos no.
  
número de identificación personal
  
skatt identificador nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>REINO UNIDO

### <a name="format"></a>Formato

Referencia de contribuyente única (UTR): 10 dígitos sin espacios y los delimitadores
  
Número de seguros National (NINO): Para obtener información detallada, vea la sección "Reino Unido número nacional seguro (NINO)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
### <a name="pattern"></a>Patrón

Referencia de contribuyente única (UTR): 10 dígitos
  
Número de seguros National (NINO): Para obtener información detallada, vea la sección "Reino Unido número nacional seguro (NINO)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_uk_eu_tax_file_number` se encuentra. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id

  
identificador de impuestos no.
  
número de identificación fiscal
  
tax identification

  
identificación de impuestos #
  
fiscal no.
  
impuestos #
  
taxid #
  
archivo de impuestos
  
archivo de impuestos no.
  
## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

