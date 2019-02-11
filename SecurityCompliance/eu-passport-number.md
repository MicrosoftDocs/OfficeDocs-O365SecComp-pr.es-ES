---
title: Número de cuenta de Passport de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de la UE Passport número. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 7a7fc1ff826aab4096c46535686eb0fd68173c6f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "25840329"
---
# <a name="eu-passport-number"></a>Número de cuenta de Passport de la UE

En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de la UE Passport número. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Una letra seguida de un espacio opcional y siete dígitos
  
### <a name="pattern"></a>Patrón

Una combinación de una letra, siete dígitos y un espacio:
  
- Una letra (no distingue entre mayúsculas y minúsculas)
    
- Un espacio (opcional)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_austria_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_austria_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte austriaco  <br/> cuenta de Passport no  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

Dos letras seguidas por seis dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras y seguido de seis dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_belgium_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_belgium_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte belga  <br/> cuenta de Passport no  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_bulgaria_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_bulgaria_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte búlgaro  <br/> cuenta de Passport no  <br/> НОМЕР НА ПАСПОРТА  <br/> |
   
## <a name="croatia"></a>Croacia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_croatia_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_croatia_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte croata  <br/> cuenta de Passport no  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

Una letra seguida de 6-8 dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Una letra seguida de seis a ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_cyprus_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_cyprus_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de cuenta de passport chipriota  <br/> cuenta de Passport no  <br/> ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ  <br/> |
   
## <a name="czech-republic"></a>República Checa

### <a name="format"></a>Formato

Ocho dígitos sin espacios o delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos sin espacios o delimitadores
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_czech_republic_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_czech_republic_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte checo  <br/> cuenta de Passport no  <br/> pas cestovní  <br/> PAS  <br/> |
   
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_denmark_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_denmark_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte danés  <br/> cuenta de Passport no  <br/> PAS  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Una letra seguida de siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Una letra seguida de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_estonia_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_estonia_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte estonio  <br/> cuenta de Passport no  <br/> eesti kodaniku pasada  <br/> |
   
## <a name="finland"></a>Finlandia

Para obtener información detallada, vea la sección "Número de pasaporte Finlandia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Para obtener información detallada, vea la sección "Número de pasaporte Francia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener información detallada, vea la sección "Número de pasaporte Alemania" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_greece_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_greece_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte griega  <br/> cuenta de Passport no  <br/> ΔΙΑΒΑΤΗΡΙΟ  <br/> |
   
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Dos letras seguidas por seis o siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas por seis o siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_hungary_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_hungary_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte húngaro  <br/> cuenta de Passport no  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_ireland_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_ireland_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte irlandés  <br/> cuenta de Passport no  <br/> PAS  <br/> passport  <br/> passeport  <br/> numero de passeport  <br/> |
   
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_italy_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_italy_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|número de pasaporte italiano  <br/> Repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> número de cuenta de Passport  <br/> numero de passaporto italiana  <br/> numero de passaporto  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>Letonia

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_latvia_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_latvia_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte letón  <br/> cuenta de Passport no  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Ocho dígitos o letras sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos o letras (no entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_lithuania_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_lithuania_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de cuenta de passport lithunian  <br/> cuenta de Passport no  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

Ocho dígitos o letras sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos o letras (no entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_nation_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_nation_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte letón  <br/> cuenta de Passport no  <br/> passnummer  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Siete dígitos sin espacios o delimitadores
  
### <a name="pattern"></a>Patrón

 Siete dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_malta_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte Maltés  <br/> cuenta de Passport no  <br/> numru horizontal-passaport  <br/> |
   
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

Nueve letras o dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Nueve letras o dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_netherlands_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_netherlands_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|número de pasaporte neerlandés  <br/> número de cuenta de Passport  <br/> número de cuenta de passport (Países Bajos)  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>Polonia

Para obtener información detallada, vea la sección "Número de pasaporte Polonia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formato

Una letra seguida de seis dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Una letra seguida de seis dígitos:
  
- Una letra (no distingue entre mayúsculas y minúsculas)
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_portugal_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_portugal_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte portugués  <br/> cuenta de Passport no  <br/> número passaporte  <br/> |
   
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

Ocho o nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Ocho o nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_romania_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_romania_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de pasaporte rumano  <br/> cuenta de Passport no  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

Un dígito o letra seguido de siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Un dígito o letra (no entre mayúsculas y minúsculas) seguido de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovakia_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovakia_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de cuenta de passport eslovaco  <br/> cuenta de Passport no  <br/> Číslo pasu  <br/> |
   
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas de siete dígitos:
  
- La letra "P"
    
- Una letra en mayúsculas
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovenia_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovenia_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|número de cuenta de Passport  <br/> número de cuenta de passport esloveno  <br/> cuenta de Passport no  <br/> Lista de potnega številka  <br/> |
   
## <a name="spain"></a>España

### <a name="format"></a>Formato

Una combinación de ocho o nueve caracteres de letras y números sin espacios ni los delimitadores
  
### <a name="pattern"></a>Patrón

Una combinación de ocho o nueve caracteres de letras y números:
  
-  Dos dígitos o letras 
    
- Un dígito o letra (opcional)
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_spain_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_spain_eu_passport_number` se encuentra. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|passport  <br/> cuenta de passport de España  <br/> libro de Passport  <br/> número de cuenta de Passport  <br/> cuenta de Passport no  <br/> Libreta pasaporte  <br/> número pasaporte  <br/> España pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>Suecia

Para obtener información detallada, vea la sección "Número de pasaporte Suecia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="uk"></a>REINO UNIDO

Para obtener información detallada, vea la sección "Número de pasaporte de Estados Unidos / Reino Unido" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Recursos adicionales

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

