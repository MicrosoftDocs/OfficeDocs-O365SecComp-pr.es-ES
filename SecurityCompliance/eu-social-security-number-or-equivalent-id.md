---
title: Número de la seguridad social de la UE o identificador equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154492"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>Número de la seguridad social de la UE o identificador equivalente

En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de la seguridad social (SSN) o del identificador equivalente de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

10 dígitos en el formato especificado
  
### <a name="pattern"></a>Patrón

10 dígitos:
  
-  Tres dígitos que corresponden a un número de serie 
    
- Un dígito de control
    
- Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_austria_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

n.º de seguridad social
  
social security number
  
social security code
  
número de seguro
  
SSN austriaco
  
SSN
  
SSN
  
código de seguro
  
número de código de seguro
  
socialsecurityno#
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_belgium_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

número nacional belga
  
número nacional
  
social security number
  
nationalnumber#
  
SSN
  
SSN
  
nationalnumber
  
bnn#
  
bnn
  
número de identificación personal
  
personalidnumber#
  
numéro nacional
  
numéro de sécurité
  
numéro d'assuré
  
Nacional del identificador
  
identifiantnational#
  
numéronational#
  
## <a name="croatia"></a>Croacia

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
  
- La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_croatia_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

número de identificación personal
  
número de ciudadano principal
  
national identification number
  
social security number
  
nationalnumber#
  
SSN
  
SSN
  
nationalnumber
  
bnn#
  
bnn
  
número de identificación personal
  
personalidnumber#
  
OIB
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>Chequia

### <a name="format"></a>Formato

Diez dígitos y una barra diagonal inversa en el patrón especificado
  
### <a name="pattern"></a>Patrón

Diez dígitos y una barra diagonal inversa:
  
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD): 
    
- Una barra diagonal inversa
    
- Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha.
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_czech_republic_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

número de nacimiento
  
national identification number
  
número de identificación personal
  
social security number
  
nationalnumber#
  
SSN
  
SSN
  
número nacional
  
número de identificación personal
  
personalidnumber#
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Diez dígitos y un guión en el patrón especificado
  
### <a name="pattern"></a>Patrón

Diez dígitos y un guión:
  
- Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
    
- Un guión 
    
- Cuatro dígitos que corresponden a un número de secuencia
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_denmark_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

número de identificación personal
  
national identification number
  
social security number
  
nationalnumber#
  
SSN
  
SSN
  
número nacional
  
número de identificación personal
  
personalidnumber#
  
CPR-Nummer
  
personnummer
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinación de 11 caracteres en el formato especificado
  
### <a name="pattern"></a>Patrón

Una combinación de 11 caracteres en el formato especificado:
  
-  Seis dígitos 
    
- Una instancia de una de las siguientes opciones:
    
  - Símbolo más
    
  - Símbolo menos
    
  - La letra "A" (sin distinción entre mayúsculas y minúsculas)
    
- Tres dígitos
    
- Una letra o un dígito
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_finland_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

identification number
  
identificador personal
  
número de identidad
  
número de identificación nacional finlandesa
  
personalidnumber#
  
national identification number
  
número de identificador
  
n.º de identificación nacional
  
número de identificación nacional
  
identificador no
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti numero
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero#
  
kansallisen tunnistenumero
  
tunnusnumero
  
kansallinen tunnus numero
  
hetu
  
## <a name="france"></a>Francia

Para obtener más información, consulte la sección "número de la seguridad social de Francia (INSEE)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener más información, consulte la sección "número de tarjeta de identidades Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Para obtener más información, consulte la sección "tarjeta de identificación nacional de Grecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_hungary_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

número de la seguridad social húngara
  
social security number
  
NúmeroSeguridadSocial
  
hssn#
  
socialsecuritynno
  
hssn
  
taj
  
taj#
  
SSN
  
SSN
  
n.º de seguridad social
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>Portugal

Para obtener más información, consulte la sección "número de tarjeta de ciudadano de Portugal" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="spain"></a>España

Para obtener más información, consulte la sección "número de la seguridad social de España (SSN)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="sweden"></a>Suecia

### <a name="format"></a>Formato

12 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

12 dígitos:
  
-  Ocho dígitos que corresponden a la fecha de nacimiento (AAAAMMDD) 
    
- Tres dígitos que corresponden a un número de serie en el que: 
    
  - El último dígito del número de serie indica el sexo por la asignación de un número impar para macho y un número par para hembras
    
  - Hasta 1990, la asignación de número de serie que se corresponde con el condado en el que nació el portador del número o (si nació antes de 1947) donde estuvo viviendo, de acuerdo con los registros fiscales, el 1 de enero de 1947, con un código especial (por lo general, 9 como el séptimo dígito) para immigrants 
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_sweden_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

número de identificación personal
  
identification number
  
número de identificación personal
  
n.º de identidad
  
n.º de identificación
  
n.º de identificación personal
  
identificador personnummer
  
personligt ID-Nummer
  
unikt ID-Nummer
  
personnummer
  
identifikationsnumret
  
personnummer#
  
identifikationsnumret#
  
## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

