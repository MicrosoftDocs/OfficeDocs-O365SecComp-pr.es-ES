---
title: Número de licencia del controlador de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecta el tipo de información confidencial de número de licencia del controlador de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536159"
---
# <a name="eu-drivers-license-number"></a>Número de licencia del controlador de la UE

En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecta el tipo de información confidencial de número de licencia del controlador de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Ocho dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_austria_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_austria_eu_driver's_license_number` se encuentra. 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_austria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> permiso de conducir  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/>  número de licencia de fuerzas  <br/> dlno #  <br/> fuhrerschein  <br/> fuhrerschein República osterreich  <br/> |
   
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formato

10 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_belgium_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_belgium_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords__belgium_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein n  <br/> fuehrerschein n  <br/> fuehrerschein n  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_bulgaria_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_bulgaria_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_bulgaria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС  <br/> СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО  <br/> СУМПС  <br/> ШОФЬОРСКА КНИЖКА  <br/> |
   
## <a name="croatia"></a>Croacia

### <a name="format"></a>Formato

Ocho dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_croatia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_croatia_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_croatia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formato

12 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

12 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_cyprus_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_cyprus_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_cyprus_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> |
   
## <a name="czech-republic"></a>República Checa

### <a name="format"></a>Formato

Dos letras seguidas por seis dígitos
  
### <a name="pattern"></a>Patrón

Ocho letras y dígitos:
  
- Dos letras (no distingue mayúsculas de minúsculas)
    
- Un espacio (opcional) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_czech_republic_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_czech_republic_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_czech_republic_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> Řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formato

Ocho dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_denmark_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_denmark_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_denmark_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Dos letras seguidas por seis dígitos
  
### <a name="pattern"></a>Patrón

Dos letras y seis dígitos:
  
-  Las letras "ET" (no distingue mayúsculas de minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_estonia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_estonia_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_estonia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> 
permis de conduire  <br/> |
   
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

10 dígitos que contienen un guión
  
### <a name="pattern"></a>Patrón

10 dígitos que contiene un guión:
  
-  Seis dígitos 
    
- Un guion
    
-  Cuatro dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_finland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_finland_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_finland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>Francia

Para obtener información detallada, vea la sección "Número de licencia del controlador de Francia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemania

Para obtener información detallada, vea la sección "Número de licencia del controlador alemán" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_greece_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_greece_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_greece_eu_driver's_license_number**|
|:-----|
|dlL #  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> ΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>Hungría

### <a name="format"></a>Formato

Dos letras seguidas por seis dígitos
  
### <a name="pattern"></a>Patrón

Dos letras y seis dígitos:
  
-  Dos letras (no distingue mayúsculas de minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_hungary_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_hungary_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_hungary_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Seis dígitos seguidos de cuatro letras
  
### <a name="pattern"></a>Patrón

Seis dígitos y cuatro letras:
  
- Seis dígitos
    
- Cuatro letras (no distingue mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_ireland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_ireland_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_ireland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>Italia

Para obtener información detallada, vea la sección "Número de licencia del controlador de Italia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="latvia"></a>Letonia

### <a name="format"></a>Formato

Tres letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

Tres letras y seis dígitos:
  
-  Tres letras (no distingue mayúsculas de minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_latvia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_latvia_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_latvia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Ocho dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

 Ocho dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_lithuania_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_lithuania_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_lithuania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>Luxemburgo

### <a name="format"></a>Formato

Seis dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

 Seis dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_luxemburg_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_luxemburg_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_luxemburg_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Combinación de dos caracteres y seis dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

Combinación de dos caracteres y seis dígitos:
  
- Dos caracteres (dígitos o letras, no distingue mayúsculas de minúsculas)
    
- Un espacio (opcional) 
    
- Tres dígitos
    
- Un espacio (opcional) 
    
- Tres dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_malta_eu_driver's_license_number` se encuentra. 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_malta_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> tareas de liċenzja-sewqan  <br/> |
   
## <a name="netherlands"></a>Países Bajos

### <a name="format"></a>Formato

10 dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_netherlands_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_netherlands_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_netherlands_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> 
permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

14 dígitos que contiene 2 barras diagonales
  
### <a name="pattern"></a>Patrón

14 dígitos y barras 2 diagonales:
  
-  Cinco dígitos 
    
- Una barra diagonal 
    
- Dos dígitos
    
- Una barra diagonal 
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_poland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_poland_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_poland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formato

Dos letras seguidas por un siete números en el patrón especificado
  
### <a name="pattern"></a>Patrón

Dos letras seguidas por siete números con caracteres especiales:
  
-  Dos letras (no distingue mayúsculas de minúsculas) 
    
- Un guión 
    
- Seis dígitos
    
- Un espacio
    
- Un dígito
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_portugal_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_portugal_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_portugal_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>Rumania

### <a name="format"></a>Formato

Un carácter seguido de ocho dígitos
  
### <a name="pattern"></a>Patrón

Un carácter seguido de ocho dígitos:
  
-  Una letra (no distingue mayúsculas de minúsculas) o un dígito 
    
- Ocho dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_romania_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_romania_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_romania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> Permis de conducere  <br/> |
   
## <a name="slovakia"></a>Eslovaquia

### <a name="format"></a>Formato

Un carácter seguido de siete dígitos
  
### <a name="pattern"></a>Patrón

Un carácter seguido de siete dígitos
  
- Una letra (no distingue mayúsculas de minúsculas) o un dígito
    
-  Siete dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovakia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovakia_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_slovakia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>Eslovenia

### <a name="format"></a>Formato

Nueve dígitos sin espacios y los delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovenia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovenia_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_slovenia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>España

### <a name="format"></a>Formato

Ocho dígitos seguidos de un carácter
  
### <a name="pattern"></a>Patrón

Ocho dígitos seguidos de un carácter:
  
-  Ocho dígitos 
    
- Un dígito o letra (no distingue mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_spain_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_spain_eu_driver's_license_number**|
|:-----|
|dlno #  <br/> dl#  <br/> lic de controladores.  <br/> licencia de controlador  <br/> permiso de conducción  <br/> drivers licence  <br/> permiso de conducir  <br/> permiso de conducir  <br/> permiso de conducción  <br/> driving licence
  <br/> licencia fuerzas  <br/> número de licencia del controlador  <br/> número de licencia del controlador  <br/> número de solicitudes de certificado de controladores  <br/> número de licencia de controladores  <br/> número de la licencia del controlador  <br/> número de licencia del controlador  <br/> número de permiso de conducir  <br/> número de licencia de fuerzas  <br/> que manejan el permiso  <br/> número del permiso de fuerzas  <br/> permiso de conducción  <br/> conducción de permiso  <br/> número licencia conducir  <br/> número de cuaderno de conducir  <br/> número cuaderno conducir  <br/> licencia conducir  <br/> número de permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> el cuaderno de conducir  <br/> Cuaderno conducir  <br/> |
   
## <a name="sweden"></a>Suecia

### <a name="format"></a>Formato

Diez dígitos que contiene un guión
  
### <a name="pattern"></a>Patrón

Diez dígitos que contiene un guión:
  
-  Seis dígitos 
    
- Un guion
    
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_sweden_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_sweden_eu_driver's_license_number` se encuentra. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_sweden_eu_driver's_license_number**|
|:-----|
|dl#  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> licencia de controlador  <br/> lic de controladores.  <br/> permiso de conducir  <br/> drivers licence  <br/> permiso de conducción  <br/> número de licencia del controlador  <br/> número de la licencia del controlador  <br/> número de licencia de fuerzas  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>REINO UNIDO

Para obtener información detallada, vea la sección "Número de licencia del Reino Unido conductor" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

