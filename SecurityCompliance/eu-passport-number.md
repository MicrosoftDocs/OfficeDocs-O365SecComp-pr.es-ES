---
title: Número de pasaporte de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: c46f683bd1baf651bcf13c1766dfff3cb953b341
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218270"
---
# <a name="eu-passport-number"></a>Número de pasaporte de la UE

En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
  
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
  
- La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte austriaco  <br/> n.º de pasaporte  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras y seguidas de seis dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte belga  <br/> n.º de pasaporte  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte búlgaro  <br/> n.º de pasaporte  <br/> номер на паспорта  <br/> |
   
## <a name="croatia"></a>Croacia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de croata  <br/> n.º de pasaporte  <br/> Broj putovnice  <br/> |
   
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

Una letra seguida de 6-8 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Una letra seguida de seis a ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de Chipre  <br/> n.º de pasaporte  <br/> αριθμό διαβατηρίου  <br/> |
   
## <a name="czech-republic"></a>Chequia

### <a name="format"></a>Formato

Ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos sin espacios ni delimitadores
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte Checo  <br/> n.º de pasaporte  <br/> Cestovní PAS  <br/> PAS  <br/> |
   
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte danés  <br/> n.º de pasaporte  <br/> PAS  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Una letra seguida de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Una letra seguida de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de estonio  <br/> n.º de pasaporte  <br/> Eesti kodaniku Pass  <br/> |
   
## <a name="finland"></a>Finlandia

Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener más información, consulte la sección "número de pasaporte de Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte griego  <br/> n.º de pasaporte  <br/> διαβατηριο  <br/> |
   
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas por seis o siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte Húngaro  <br/> n.º de pasaporte  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte irlandés  <br/> n.º de pasaporte  <br/> PAS  <br/> passport  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte Italiano  <br/> Repubblica Italiana Passaporto  <br/> Passaporto  <br/> Passaporto italiana  <br/> número de pasaporte  <br/> italiana Passaporto numero  <br/> Passaporto numero  <br/> numéro passeport Italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>Letonia

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de letón  <br/> n.º de pasaporte  <br/> Pase numurs  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Ocho dígitos o letras sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de lithunian  <br/> n.º de pasaporte  <br/> numeración paso  <br/> |
   
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

Ocho dígitos o letras sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de letón  <br/> n.º de pasaporte  <br/> passnummer  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

 Siete dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de Maltés  <br/> n.º de pasaporte  <br/> numru tal-passaport  <br/> |
   
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

Nueve letras o dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Nueve letras o dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte holandés  <br/> número de pasaporte  <br/> número de pasaporte de Holanda  <br/> Nederlanden paspoort Nummer  <br/> paspoort  <br/> Nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>Polonia

Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formato

Una letra seguida de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Una letra seguida de seis dígitos:
  
- Una letra (no distingue entre mayúsculas y minúsculas)
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de Portugués  <br/> n.º de pasaporte  <br/> número Passaporte  <br/> |
   
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

Ocho o nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Ocho o nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de rumano  <br/> n.º de pasaporte  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de eslovaco  <br/> n.º de pasaporte  <br/> číslo Pasu  <br/> |
   
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas de siete dígitos:
  
- La letra "P"
    
- Una letra mayúscula
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de. 
    
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
|número de pasaporte  <br/> número de pasaporte de esloveno  <br/> n.º de pasaporte  <br/> številka potnega lista  <br/> |
   
## <a name="spain"></a>España

### <a name="format"></a>Formato

Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Una combinación de letras y números de ocho o nueve caracteres:
  
-  Dos dígitos o letras 
    
- Un dígito o letra (opcional)
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de. 
    
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
|passport  <br/> pasaporte de España  <br/> libro de Passport  <br/> número de pasaporte  <br/> n.º de pasaporte  <br/> libreta pasaporte  <br/> número pasaporte  <br/> España pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>Suecia

Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="uk"></a>LIBRA

Para obtener más información, consulte la sección "número de pasaporte de Estados Unidos/Reino Unido" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Consulte también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

