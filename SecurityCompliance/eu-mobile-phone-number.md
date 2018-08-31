---
title: Número de teléfono móvil de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 555e7675-2ae8-42d1-9b8e-2c8f8cd21337
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial de número de teléfono móvil de la UE.
ms.openlocfilehash: d0818759dae8ed86cc9aef6f7fad48cbd2acf24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536101"
---
# <a name="eu-mobile-phone-number"></a>Número de teléfono móvil de la UE

Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial de número de teléfono móvil de la UE. 
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Dígitos sin longitud estándar
  
### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_austria_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_austria_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_austria_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_mobile_number"/>
          <Match idRef="Keywords_austria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_austria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a>Bélgica

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_belgium_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_belgium_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_belgium_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_mobile_number"/>
          <Match idRef="Keywords_belgium_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_belgium_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="bulgaria"></a>Bulgaria

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_bulgaria_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_bulgaria_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_bulgaria_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_mobile_number"/>
          <Match idRef="Keywords_bulgaria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_bulgaria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="croatia"></a>Croacia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_croatia_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_croatia_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_croatia_eu_mobile_number` se encuentra. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_mobile_number"/>
          <Match idRef="Keywords_croatia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_croatia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="cyprus"></a>Chipre

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_cyprus_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_cyprus_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_cyprus_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_mobile_number"/>
          <Match idRef="Keywords_cyprus_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_cyprus_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="czech-republic"></a>República Checa

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_czech_republic_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_czech_republic_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_czech_republic_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_mobile_number"/>
          <Match idRef="Keywords_czech_republic_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_czech_republic_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="denmark"></a>Dinamarca

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_denmark_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_denmark_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_denmark_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_mobile_number"/>
          <Match idRef="Keywords_denmark_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_denmark_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="estonia"></a>Estonia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_estonia_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_estonia_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_estonia_eu_mobile_number` se encuentra. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_mobile_number"/>
          <Match idRef="Keywords_estonia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_estonia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="finland"></a>Finlandia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_finland_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_finland_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_finland_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_mobile_number"/>
          <Match idRef="Keywords_finland_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_finland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="france"></a>Francia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_france_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_france_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_france_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_mobile_number"/>
          <Match idRef="Keywords_france_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_france_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="germany"></a>Alemania

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_germany_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_germany_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_germany_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_mobile_number"/>
          <Match idRef="Keywords_germany_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_germany_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="greece"></a>Grecia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_greece_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_greece_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_greece_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_mobile_number"/>
          <Match idRef="Keywords_greece_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_greece_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="hungary"></a>Hungría

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_hungary_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_hungary_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_hungary_eu_mobile_number` se encuentra. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_mobile_number"/>
          <Match idRef="Keywords_hungary_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_hungary_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="ireland"></a>Irlanda

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_ireland_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_ireland_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_ireland_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_mobile_number"/>
          <Match idRef="Keywords_ireland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_ireland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="italy"></a>Italia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_italy_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_italy_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_italy_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_mobile_number"/>
          <Match idRef="Keywords_italy_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_italy_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="latvia"></a>Letonia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_latvia_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_latvia_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_latvia_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_mobile_number"/>
          <Match idRef="Keywords_latvia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_latvia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="lithuania"></a>Lituania

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_lithuania_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_lithuania_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_lithuania_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_mobile_number"/>
          <Match idRef="Keywords_lithuania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_lithuania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="luxemburg"></a>Luxemburgo

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_luxumburg_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_luxumburg_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_luxumburg_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxumburg_eu_mobile_number"/>
          <Match idRef="Keywords_luxumburg_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_luxumburg_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="malta"></a>Malta

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_malta_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_malta_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_mobile_number"/>
          <Match idRef="Keywords_malta_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_malta_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="netherlands"></a>Países Bajos

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_netherlands_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_netherlands_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_netherlands_eu_mobile_number` se encuentra. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_mobile_number"/>
          <Match idRef="Keywords_netherlands_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_netherlands_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="poland"></a>Polonia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_poland_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_poland_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_poland_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_mobile_number"/>
          <Match idRef="Keywords_poland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_poland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="portugal"></a>Portugal

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_portugal_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_portugal_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_portugal_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_mobile_number"/>
          <Match idRef="Keywords_portugal_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_portugal_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="romania"></a>Rumania

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_romania_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_romania_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_romania_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_mobile_number"/>
          <Match idRef="Keywords_romania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_romania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovakia"></a>Eslovaquia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovakia_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_slovakia_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovakia_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_mobile_number"/>
          <Match idRef="Keywords_slovakia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovakia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovenia"></a>Eslovenia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovenia_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_slovenia_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_slovenia_eu_mobile_number` se encuentra. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_mobile_number"/>
          <Match idRef="Keywords_slovenia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovenia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="spain"></a>España

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_spain_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_spain_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_spain_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_mobile_number"/>
          <Match idRef="Keywords_spain_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_spain_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="sweden"></a>Suecia

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_sweden_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_sweden_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_sweden_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_mobile_number"/>
          <Match idRef="Keywords_sweden_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_sweden_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="uk"></a>REINO UNIDO

### <a name="pattern"></a>Patrón

-  Dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_uk_eu_mobile_number` busca contenido que coincide con el patrón. 
    
- La expresión regular `Regex_uk_eu_formatted_mobile_number` busca contenido que coincide con el patrón. 
    
- Una palabra clave de `Keywords_uk_eu_mobile_number` se encuentra. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_mobile_number"/>
          <Match idRef="Keywords_uk_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_uk_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="see-also"></a>Vea también

[Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

