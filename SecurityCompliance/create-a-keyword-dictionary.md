---
title: Crear un diccionario de palabras clave
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Para identificar información confidencial, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas. Los diccionarios de palabras clave ofrecen una administración más sencilla de palabras clave y con una escala mucho mayor, admitiendo hasta 100 000 términos por diccionario.
ms.openlocfilehash: 8e115c0feddbd55a498db3481e6ad4bc7ebb07e7
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638917"
---
# <a name="create-a-keyword-dictionary"></a>Crear un diccionario de palabras clave

Prevención de pérdida de datos (DLP) en Office 365 puede identificar, supervisar y proteger su información confidencial. Para identificar información confidencial, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas. Los diccionarios de palabras clave ofrecen una administración más sencilla de palabras clave y con una escala mucho mayor, admitiendo hasta 100 000 términos por diccionario.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Pasos básicos para crear un diccionario de palabras clave

Las palabras clave del diccionario pueden provenir de una amplia variedad de orígenes, normalmente de un archivo (como una lista en un archivo .csv o .txt), de una lista que escriba directamente en el cmdlet o de un diccionario existente. Al crear un diccionario de palabras clave, siga los mismos pasos principales:
  
1. **Conéctese a PowerShell del Centro de seguridad y cumplimiento**: vea [este tema](https://docs.microsoft.com/es-ES/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
    
2. **Defina o cargue las palabras clave del origen que quiera usar**: el cmdlet para crear un diccionario de palabras clave acepta una lista separada por comas de palabras clave, por lo que este paso variará ligeramente según el origen de las palabras clave. 
    
3. **Codifique las palabras clave**: después de cargarlas, se convertirán en una matriz de bytes antes de su importación. 
    
4. **Cree el diccionario**: seleccione un nombre y una descripción y, después, cree el diccionario. 
    
## <a name="create-a-keyword-dictionary-from-a-file"></a>Crear un diccionario de palabras clave desde un archivo

Con frecuencia, si necesita crear un diccionario de gran tamaño, puede usar palabras clave de un archivo o una lista exportada de otro origen. En este caso, creará un diccionario de palabras clave que contenga una lista de lenguaje inadecuado para supervisarlo en el correo electrónico externo. Primero, necesita [conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/es-ES/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.
    
2. Guarde el archivo de texto con codificación Unicode. En el Bloc de notas \> **Guardar como** \> **Codificación** \> **Unicode**.
    
3. Para leer el archivo en una variable, ejecute este cmdlet:
    
  ```
  $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
  ```

4. Para crear el diccionario, ejecute este cmdlet:
    
  ```
  New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
  ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Modificar un diccionario de palabras clave existente

Puede que necesite modificar las palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados. En este ejemplo, modificará algunos términos en PowerShell, guardará los términos localmente donde pueda modificarlos en un editor y, después, actualizará los términos anteriores en contexto. Primero, recupere el objeto de diccionario:
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

Al imprimir `$dict`, se mostrarán las distintas variables. Las palabras clave en sí se almacenan en un objeto en el back-end, pero `$dict.KeywordDictionary` contiene una representación de cadena de estas, que usará para modificar el diccionario. Antes de modificar el diccionario, necesita volver a convertir la cadena de términos en una matriz con el método `.split(',')`. Después, eliminará los espacios no deseados entre las palabras clave con el método `.trim()` y dejará únicamente las palabras clave con las que quiera trabajar. 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría exportar fácilmente el diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.
  
En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](https://go.microsoft.com/fwlink/p/?linkid=852620), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.
  
Ejecute el comando `$terms` para mostrar la lista de términos actual. El resultado del comando tiene este aspecto: 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

Ejecute este comando para especificar los términos que quiera quitar:
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

Ejecute este comando para quitar los términos de la lista:
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Ejecute el comando `$updatedTerms` para mostrar la lista actualizada de términos. El resultado del comando será parecido a este (se quitaron los términos especificados): 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

Ahora, guarde el diccionario localmente y agregue algunos términos más. Puede agregar los términos aquí en PowerShell, pero tendrá que exportar el archivo localmente para asegurarse de que se guarde con la codificación Unicode y que contenga el BOM.
  
Para guardar el diccionario localmente, ejecute lo siguiente:
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

Ahora, simplemente abra el archivo, agregue los términos adicionales y guárdelo con codificación Unicode (UTF-16). Ahora, cargará los términos actualizados y actualizará el diccionario en contexto.
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Ahora, el diccionario se actualizó en contexto. Tenga en cuenta que el campo `Identity` recibe el nombre del diccionario. Si también quiere cambiar el nombre del diccionario con el cmdlet `set-`, necesita agregar el parámetro `-Name` a los comandos anteriores con el nuevo nombre de diccionario. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP

Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia para un tipo de información confidencial personalizado, o bien como tipo de información confidencial en sí. En ambos casos, es necesario [crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento de Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md). Siga las instrucciones del artículo vinculado para crear un tipo de información confidencial. Una vez que tenga el archivo XML, necesitará el identificador GUID del diccionario para poder usarlo.
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Para obtener la identidad del diccionario, ejecute este comando y copie el valor de la propiedad **Identity**: 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

El resultado del comando tiene este aspecto:
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

Pegue la identidad en el archivo XML del tipo de información confidencial personalizado y cárguelo. Ahora, el diccionario aparecerá en la lista de tipos de información confidencial y puede usarlo en la directiva (para hacerlo, especifique el número de palabras clave que tienen que coincidir).
  
```
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```


