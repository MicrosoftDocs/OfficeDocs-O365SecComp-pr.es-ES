---
title: Número de identificación fiscal de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación de impuestos de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 4914ff078695519c2a298190d82c86a6abebceb9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255528"
---
# <a name="eu-tax-identification-number"></a>Número de identificación fiscal de la UE

En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de identificación fiscal (CIF) de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Nueve dígitos con guión opcional y barra diagonal
  
### <a name="pattern"></a>Patrón

Nueve dígitos con guión opcional y barra diagonal:
  
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
    
- Se encuentra una `Keywords_austria_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

número de impuesto
  
number
  
NIF-CIF
  
tax id
  
St.Nr.
  
steuernummer
  
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
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
  
- La expresión `Regex_belgium_eu_tax_file_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_belgium_eu_tax_file_number` palabra clave de. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

número de impuesto
  
número de registro nacional
  
NIF-CIF
  
tax id
  
NIF
  
NIF
  
numéro de registros nacionales
  
numéro d'identification fiscal
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_bulgaria_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
número civil uniforme
  
bucn #
  
uniformcivilnumber #
  
identificador civil uniforme
  
Uniform civil no
  
EGN
  
número civil uniforme de búlgaro
  
uniformcivilno #
  
EGN #
  
униформ граждански номер
  
identificador униформ
  
униформ граждански ID
  
униформ граждански не
  
## <a name="croatia"></a>Croacia

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Diez dígitos, elegidos aleatoriamente
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_croatia_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

número de impuesto
  
Tax
  
tax id
  
oid
  
OID
  
porezni broj
  
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

Ocho dígitos y una letra en el patrón especificado
  
### <a name="pattern"></a>Patrón

Ocho dígitos y una letra:
  
-  Un "0" 
    
- Siete dígitos 
    
- Una letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_cyprus_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

número de impuesto
  
Tax
  
tax id
  
código de identificación de impuestos
  
verticales
  
verticales
  
αριθμός φορολογικού μητρώου
  
φορολογική ταυτότητα
  
κωδικός φορολογικού μητρώου
  
## <a name="czech-republic"></a>Chequia

### <a name="format"></a>Formato

Nueve o diez dígitos con una barra diagonal inversa opcional
  
### <a name="pattern"></a>Patrón

Nueve o diez dígitos con una barra diagonal inversa opcional:
  
- Seis dígitos 
    
- Una barra diagonal inversa (opcional)
    
- Tres o cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_czech_republic_eu_tax_file_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_czech_republic_eu_tax_file_number` palabra clave de. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

número de impuesto
  
Tax
  
tax id
  
número personal
  
daňové číslo
  
Osobní číslo
  
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Diez dígitos que contienen un guión
  
### <a name="pattern"></a>Patrón

Diez dígitos que contienen un guión:
  
-  Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
    
- Un guión 
    
- Cuatro dígitos que corresponden a un número de secuencia en el que el primer dígito corresponde al siglo de nacimiento y el último dígito corresponde al sexo de la persona (impar para macho e incluso para hembras)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_denmark_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

número de impuesto
  
Tax
  
tax id
  
RCP número
  
RCP
  
Nummer de patinaje
  
identificador de patinaje
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
-  Un dígito que corresponde al sexo y al siglo de nacimiento donde un número impar indica macho y el número par indica hembra de la siguiente manera: 1,2 para el siglo XIX; 3, 4 para el siglo XX; y 5, 6 para el siglo XXI 
    
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
    
- Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_estonia_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

número de impuesto
  
Tax
  
tax id
  
código personal
  
maksunumber
  
identificador maksu
  
isikukood
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinación de 11 caracteres de dígitos, letras y más y un signo menos
  
### <a name="pattern"></a>Patrón

Una combinación de 11 caracteres de dígitos, letras y más y un signo menos:
  
- Seis dígitos
    
- Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distingue entre mayúsculas y minúsculas) donde el signo más significa que nació entre 1800-1899, el signo menos significa que nació entre 1900-1999, y "A" significa que nació 2000 y posterior
    
- Tres dígitos
    
- Una letra o un número
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_finland_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

identification number
  
identificador personal
  
número de identidad
  
número de identificación nacional finlandesa
  
personalidnumber #
  
national identification number
  
número de identificador
  
n.º de identificación nacional
  
número de identificación nacional
  
identificador no
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
Ainutlaatuinen henkilökohtainen Tunnus
  
identiteetti numero
  
Suomen Kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
Kansallinen Tunnus numero
  
## <a name="france"></a>Francia

### <a name="format"></a>Formato

13 dígitos para personas y nueve dígitos para entidades
  
### <a name="pattern"></a>Patrón

13 dígitos para los usuarios:
  
- Un dígito que debe ser 0, 1, 2 o 3
    
- 12 dígitos
    
Nueve dígitos para entidades
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_france_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

número de identificación fiscal
  
número de impuesto
  
tax id
  
numéro d'identification fiscal
  
## <a name="germany"></a>Alemania

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
-  Diez dígitos 
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_germany_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
n.º de taxis
  
número de identificación fiscal
  
Nº identificación impto.
  
steuernummer
  
identificador Steuer
  
steueridentifikationsnummer
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_greece_eu_tax_file_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_greece_eu_tax_file_number` palabra clave de. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

AFM
  
/
  
Nº de identificación fiscal
  
n.º de identificación fiscal
  
número de identificación fiscal
  
número de registro de impuestos
  
n.º de registro de impuestos
  
AFM #
  
/
  
taxidno #
  
taxregistryno #
  
αριθμός φορολογικού μητρώου
  
aφμ
  
aφμ αριθμός
  
φορολογικού μητρώου νο.
  
τον αριθμό φορολογικού μητρώου
  
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Diez dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Diez dígitos:
  
-  Un dígito que debe ser "8" 
    
- Cinco dígitos que corresponden al número de días entre la fecha 01/01/1867 y la fecha de nacimiento del individuo.
    
- Tres dígitos que corresponden al número generado por oportunidad para diferenciar a los individuos nacidos en el mismo día
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_hungary_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

número de identificación fiscal húngara
  
NIF Húngaro
  
número de identificación fiscal
  
número de IVA
  
n.º de autoridad fiscal
  
número de identidad fiscal de identificador de impuesto
  
taxidnumber #
  
/
  
hungatiantin #
  
n.º de identificación fiscal
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Siete dígitos seguidos de una letra sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Siete dígitos seguidos de una letra:
  
-  Siete dígitos  
    
- Una letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_ireland_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

n.º de servicio público
  
número de servicio público personal
  
n.º de PPS
  
n.º de servicio personal
  
n.º de servicio de PPS
  
ppsno #
  
n.º de PPS irlandés
  
publicserviceno #
  
número de servicio público personal
  
uimhir phearsanta seirbhíse poiblí
  
PPS uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

16 letras y dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

16 letras y dígitos:
  
-  Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia 
    
- Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre
    
- Dos dígitos que corresponden a los últimos dígitos del año de nacimiento
    
- Un dígito que corresponde al mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)
    
- Dos dígitos que corresponden al día del mes de nacimiento donde se agrega 40 al día de nacimiento para hembras para diferenciar de machos
    
- Cuatro dígitos que corresponden a un código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros).
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_italy_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
n.º de taxis
  
Código fiscal
  
Codice fiscal
  
## <a name="latvia"></a>Letonia

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos en el patrón especificado
  
-  Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
    
- Un dígito que corresponde al siglo de nacimiento en el que "0" corresponde al siglo XIX, "1" corresponde al siglo XX y "2" corresponde al siglo XXI.
    
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_latvia_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
n.º de taxis
  
número de identificación fiscal
  
Nº identificación impto.
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_lithuania_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
impto.
  
taxnumber #
  
taxnumber
  
tax id
  
n.º de taxis
  
número de identificación fiscal
  
Nº identificación impto.
  
identificador mokesčių
  
numeración mokesčių
  
mokesčių identifikavimas número
  
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos:
  
-  11 dígitos 
    
- Dos dígitos de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_luxemburg_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
n.º de taxis
  
número de identificación fiscal
  
Nº identificación impto.
  
steuernummer
  
identificador Steuer
  
steueridentifikationsnummer
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Para los nacionales de Maltés: 7 dígitos y una letra en el patrón especificado
  
Nacionales no Maltés y entidades de Maltés: 9 dígitos
  
### <a name="pattern"></a>Patrón

Nacionales de Malta: 7 dígitos y una letra
  
-  Siete dígitos  
    
- Una letra (no distingue entre mayúsculas y minúsculas)
    
Nacionales no Maltés y entidades de Maltés: 9 dígitos
  
-  Nueve dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_malta_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
n.º de taxis
  
número de identificación fiscal
  
Nº identificación impto.
  
numru TAT-taxxa
  
identificador TAT-taxxa
  
numru ta ' identifikazzjoni TAT-taxxa
  
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

Nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_netherlands_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

número de identificación fiscal de países bajos
  
identificación de impuestos de países bajos
  
número de identificación fiscal de Netherland
  
identificación de impuestos de Netherland
  
número de identificación fiscal
  
identificador fiscal holandés
  
número de identificación fiscal holandes
  
tax id
  
n.º de identificador de impuesto
  
número de impuesto
  
impto.
  
Tax
  
/
  
/
  
NIF-Países Bajos
  
estaño de Netherland
  
último países de la identificatienummer
  
identificatienummerto de furgoneta
  
identificatienummer en último lugar
  
último países de la identificatie
  
último identificador de Nummer de países bajos
  
Países Bajos belastingnummer
  
BTW Nummer
  
Nederlandse de la última identificatie
  
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

Once dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Once dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_poland_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
taxno #
  
taxnumber #
  
taxnumber
  
NIP
  
NIP #
  
tax id
  
n.º de identificador de impuesto
  
identificador NIP
  
número de identificador de NIP
  
número de identificación fiscal
  
Nº identificación impto.
  
número de IVA
  
n.º de IVA
  
vatno #
  
NIF
  
n.º de ID de IVA
  
numerar identyfikacji podatkowej
  
Polski número de identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formato

Nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_portugal_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

número de impuesto
  
Nº de impuestos
  
taxno #
  
taxnumber #
  
taxnumber
  
NIF
  
NIF
  
fiscal numero
  
número de identificação fiscal
  
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_romania_eu_tax_file_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_romania_eu_tax_file_number` palabra clave de. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id
  
número de identificación fiscal
  
n.º de archivo de impuestos
  
tax file number
  
Nº de impuestos
  
número de impuesto
  
n.º de taxis
  
taxno #
  
ID-ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

10 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_slovakia_eu_tax_file_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovakia_eu_tax_file_number` palabra clave de. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id
  
número de identificación fiscal
  
ID de estaño
  
n.º de estaño
  
ID de estaño de eslovaco
  
/
  
n.º de archivo de impuestos
  
tax file number
  
Nº de impuestos
  
número de impuesto
  
n.º de taxis
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

Ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovenia_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id
  
número de identificación fiscal
  
ID de estaño
  
n.º de estaño
  
ID de estaño de esloveno
  
/
  
n.º de archivo de impuestos
  
tax file number
  
Nº de impuestos
  
número de impuesto
  
n.º de taxis
  
taxno #
  
identifikacijska številka Davka
  
davčna številka
  
številka davčne datoteke
  
## <a name="spain"></a>España

### <a name="format"></a>Formato

Siete u ocho dígitos y una o dos letras en el patrón especificado
  
### <a name="pattern"></a>Patrón

Personas físicas españolas con una tarjeta de identidad nacional de España:
  
-  Ocho dígitos 
    
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Spaniards no residente sin una tarjeta de identidad nacional de España
  
- Una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)
    
- Siete dígitos 
    
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:
  
- Una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)
    
-  Siete dígitos  
    
- Una letra mayúscula (distingue entre mayúsculas y minúsculas)
    
Foreigners con un número de identificación de un extranjero
  
- Una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas) 
    
- Siete dígitos 
    
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Foreigners sin un número de identificación de un extranjero
  
- Una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas) 
    
- Siete dígitos 
    
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_spain_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id
  
número de identificación fiscal
  
identificador CIF
  
n.º CIF
  
identificador CIF en Español
  
precio
  
n.º de archivo de impuestos
  
Número CIF en Español
  
tax file number
  
Número CIF de Español
  
Nº de impuestos
  
número de impuesto
  
n.º de taxis
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de impuesto corporativo
  
número de identificación fiscal
  
Número CIF
  
cifnúmero #
  
## <a name="sweden"></a>Suecia

### <a name="format"></a>Formato

Diez dígitos y un símbolo en el patrón especificado
  
### <a name="pattern"></a>Patrón

Diez dígitos y un símbolo:
  
-  Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
    
- Un signo más, un signo menos o una barra diagonal inversa
    
- Tres dígitos que hacen que el número de identificación sea único donde: 
    
  - Para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero
    
  - El dígito en la novena posición indica el género, ya sea impar o incluso para hembras
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_sweden_eu_tax_file_number` palabra clave de. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id
  
Nº de identificación fiscal
  
número de identificación fiscal
  
tax identification
  
n.º de identificación fiscal
  
Nº de impuestos
  
Tax
  
n.º de taxis
  
archivo de impuestos
  
Nº archivo impto.
  
número de identificación personal
  
Nummer de identificador de patinaje
  
Identifikation de patinaje
  
personnummer
  
## <a name="uk"></a>LIBRA

### <a name="format"></a>Formato

Referencia fiscal única (UTR): 10 dígitos sin espacios y delimitadores
  
Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido. Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
### <a name="pattern"></a>Patrón

Referencia de contribuyente única (UTR): 10 dígitos
  
Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido. Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_uk_eu_tax_file_number` palabra clave de. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id
  
Nº de identificación fiscal
  
número de identificación fiscal
  
tax identification
  
n.º de identificación fiscal
  
Nº de impuestos
  
Tax
  
n.º de taxis
  
archivo de impuestos
  
Nº archivo impto.
  
## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

