---
title: Identificador de número de seguridad Social de la UE o equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial del número de seguridad Social de la UE o identificador equivalente. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536077"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>Identificador de número de seguridad Social de la UE o equivalente

En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de la UE número de seguridad Social (SSN) o identificador equivalente. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

10 dígitos en el formato especificado
  
### <a name="pattern"></a>Patrón

10 dígitos:
  
-  Tres dígitos que se corresponden con un número de serie 
    
- Dígito de un control
    
- Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_austria_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

seguridad social no
  
social security number

  

social security code
  
número de seguro
  
ssn austriaco
  
ssn #
  
ssn
  
código de seguro
  
código seguro #
  
socialsecurityno #
  
sozialversicherungsnummer
  
Soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

11 dígitos sin espacios o delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_belgium_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

número nacional belga
  
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
  
numéro nacional
  
numéro de sécurité

  
d. numéro' proceder
  
por parte nacional
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>Croacia

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
  
- La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_croatia_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

número de identificación personal
  
número de ciudadanos maestra
  
número de identificación nacional
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
número de identificación personal
  
personalidnumber #
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>República Checa

### <a name="format"></a>Formato

Diez dígitos y una barra diagonal inversa en el patrón especificado
  
### <a name="pattern"></a>Patrón

Diez dígitos y una barra diagonal inversa:
  
- Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD): 
    
- Una barra diagonal inversa
    
- Tres dígitos que se corresponden con un número de serie que separa a las personas nacidas en la misma fecha
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_czech_republic_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

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
  
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Diez dígitos y un guión en el patrón especificado
  
### <a name="pattern"></a>Patrón

Diez dígitos y un guión:
  
- Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA) 
    
- Un guión 
    
- Cuatro dígitos que se corresponden con un número de secuencia
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_denmark_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

número de identificación personal
  
número de identificación nacional
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
número nacional
  
número de identificación personal
  
personalidnumber #
  
rcp nummer
  
personnummer
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinación de caracteres de 11 en el formato especificado
  
### <a name="pattern"></a>Patrón

Una combinación de caracteres de 11 en el formato especificado:
  
-  Seis dígitos 
    
- Una instancia de uno de los siguientes:
    
  - Además de símbolo
    
  - Signo menos
    
  - La letra "A" (no distingue mayúsculas de minúsculas)
    
- Tres dígitos
    
- Una letra o un dígito
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_finland_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

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
  
hetu
  
## <a name="france"></a>Francia

Para obtener información detallada, vea la sección "Francia número de seguridad Social (INSEE)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener información detallada, vea la sección "Número de tarjeta de identidad de Alemania" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Para obtener información detallada, vea la sección "tarjeta de identificación nacional Grecia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_hungary_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

número de la seguridad social húngaro
  
social security number

  
NúmeroSeguridadSocial #
  
hssn #
  
socialsecuritynno
  
hssn
  
taj
  
taj #
  
ssn
  
ssn #
  
seguridad social no
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
Magiar áfa szám
  
## <a name="portugal"></a>Portugal

Para obtener información detallada, vea la sección "Número de tarjeta de Portugal ciudadanos" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="spain"></a>España

Para obtener información detallada, vea la sección "España número de seguridad Social (SSN)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="sweden"></a>Suecia

### <a name="format"></a>Formato

12 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

12 dígitos:
  
-  Ocho dígitos que se corresponden con la fecha de nacimiento (aaaammdd) 
    
- Tres dígitos que se corresponden con un número de serie donde: 
    
  - El último dígito en el número de serie indica género por la asignación de un número impar para hombre y un número par de hembra
    
  - Hasta 1990, la asignación del número de serie correspondía a la provincia donde surgió el portador del número o (si nacimiento antes de 1947) donde éste tenía ha viva, según los registros de impuestos, en el 1 de enero de 1947, con un código especial (normalmente 9 como el dígito 7) para inmigrantes 
    
- Dígito de un control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_sweden_eu_ssn_or_equivalent` se encuentra. 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

número de identificación personal
  
identification number

  
un identificador personal no
  
identidad no
  
identificación no
  
identificación personal no
  
identificador de personnummer
  
identificador de personligt-nummer
  
identificador de unikt-nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

