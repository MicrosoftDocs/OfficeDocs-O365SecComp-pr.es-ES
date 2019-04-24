---
title: Número de permiso de conducción de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: be9497c325866a670dff8d82b5170f4ca947c4ad
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255778"
---
# <a name="eu-drivers-license-number"></a>Número de permiso de conducción de la UE

En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de. 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_austria_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/>  número de licencia de conducir  <br/> dlno #  <br/> fuhrerschein  <br/> fuhrerschein Republik Osterreich  <br/> |
   
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords__belgium_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> Führerschein-NR  <br/> fuehrerschein-NR  <br/> fuehrerschein-NR  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_bulgaria_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> свидетелство за управление на мпс  <br/> свидетелство за управление на моторно превозно средство  <br/> сумпс  <br/> шофьорска книжка  <br/> |
   
## <a name="croatia"></a>Croacia

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_croatia_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> vozačka Dozvola  <br/> |
   
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

12 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

12 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_cyprus_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> άδεια οδήγησης  <br/> |
   
## <a name="czech-republic"></a>Chequia

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

Ocho letras y dígitos:
  
- Dos letras (sin distinción entre mayúsculas y minúsculas)
    
- Un espacio (opcional) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_czech_republic_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_denmark_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

Dos letras y seis dígitos:
  
-  Las letras "ET" (sin distinción entre mayúsculas y minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_estonia_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

10 dígitos que contienen un guión
  
### <a name="pattern"></a>Patrón

10 dígitos que contienen un guión:
  
-  Seis dígitos 
    
- Un guión
    
-  Cuatro dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_finland_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>Francia

Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_greece_eu_driver's_license_number**|
|:-----|
|Biblioteca  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> δεια οδήγησης  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

Dos letras y seis dígitos:
  
-  Dos letras (sin distinción entre mayúsculas y minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_hungary_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Seis dígitos seguidos de cuatro letras
  
### <a name="pattern"></a>Patrón

Seis dígitos y cuatro letras:
  
- Seis dígitos
    
- Cuatro letras (sin distinción entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_ireland_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>Italia

Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="latvia"></a>Letonia

### <a name="format"></a>Formato

Tres letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

Tres letras y seis dígitos:
  
-  Tres letras (sin distinción entre mayúsculas y minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_latvia_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

 Ocho dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_lithuania_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

Seis dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

 Seis dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_luxemburg_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Combinación de dos caracteres y seis dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

Combinación de dos caracteres y seis dígitos:
  
- Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)
    
- Un espacio (opcional) 
    
- Tres dígitos
    
- Un espacio (opcional) 
    
- Tres dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de. 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_malta_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> liċenzja sewqan  <br/> |
   
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_netherlands_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

14 dígitos que contienen 2 barras diagonales
  
### <a name="pattern"></a>Patrón

14 dígitos y 2 barras diagonales:
  
-  Cinco dígitos 
    
- Una barra diagonal 
    
- Dos dígitos
    
- Una barra diagonal 
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_poland_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> Prawo jazdy  <br/> |
   
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formato

Dos letras seguidas de siete números en el patrón especificado
  
### <a name="pattern"></a>Patrón

Dos letras seguidas de siete números con caracteres especiales:
  
-  Dos letras (sin distinción entre mayúsculas y minúsculas) 
    
- Un guión 
    
- Seis dígitos
    
- Un espacio
    
- Un dígito
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_portugal_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> Carteira de motorista  <br/> |
   
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

Un carácter seguido de ocho dígitos
  
### <a name="pattern"></a>Patrón

Un carácter seguido de ocho dígitos:
  
-  Una letra (no distingue entre mayúsculas y minúsculas) o un dígito 
    
- Ocho dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_romania_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> Perm de conducere  <br/> |
   
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

Un carácter seguido de siete dígitos
  
### <a name="pattern"></a>Patrón

Un carácter seguido de siete dígitos
  
- Una letra (no distingue entre mayúsculas y minúsculas) o un dígito
    
-  Siete dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_slovakia_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_slovenia_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>España

### <a name="format"></a>Formato

Ocho dígitos seguidos de un carácter
  
### <a name="pattern"></a>Patrón

Ocho dígitos seguidos de un carácter:
  
-  Ocho dígitos 
    
- Un dígito o letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_spain_eu_driver's_license_number**|
|:-----|
|dlno #  <br/> listas  <br/> Lic de drivers.  <br/> permiso de conducir  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> driving licence  <br/> driving license  <br/> número de licencia de conductor  <br/> número de licencia de conductor  <br/> número de licencia de drivers  <br/> número de licencia de drivers  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> permiso de conducción  <br/> número de permiso de conducir  <br/> permisos de conducción  <br/> permisos conducción  <br/> número de licencia conducir  <br/> número de cuaderno de conducir  <br/> número conducir de cuaderno  <br/> licenciar conducir  <br/> número de permisos de conducir  <br/> número de permisos conducir  <br/> número permisos conducir  <br/> permisos conducir  <br/> licencia de manejo  <br/> el cuaderno de conducir  <br/> conducir del cuaderno  <br/> |
   
## <a name="sweden"></a>Suecia

### <a name="format"></a>Formato

Diez dígitos que contienen un guión
  
### <a name="pattern"></a>Patrón

Diez dígitos que contienen un guión:
  
-  Seis dígitos 
    
- Un guión
    
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón. 
    
- Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Palabras clave

| |
|**Keywords_sweden_eu_driver's_license_number**|
|:-----|
|listas  <br/> driver license  <br/> número de licencia de conductor  <br/> permiso de conducir  <br/> Lic de drivers.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número de permiso de conducción  <br/> número de permiso de conducción  <br/> número de licencia de conducir  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>LIBRA

Para obtener más información, consulte la sección "Reino Unido. Número de permiso de conducir "en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

