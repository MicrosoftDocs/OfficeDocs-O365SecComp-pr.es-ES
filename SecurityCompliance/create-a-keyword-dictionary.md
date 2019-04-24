---
title: Crear un diccionario de palabras clave
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/11/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Para identificar información confidencial, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas. Los diccionarios de palabras clave ofrecen una administración más sencilla de palabras clave y con una escala mucho mayor, admitiendo hasta 100 000 términos por diccionario.
ms.openlocfilehash: 142f471d80c7278cabd4c437f0ae0ee9af3ff219
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258168"
---
# <a name="create-a-keyword-dictionary"></a>Crear un diccionario de palabras clave

La prevención de pérdida de datos (DLP) en Office 365 puede identificar, supervisar y proteger la información confidencial. La identificación de información confidencial a veces requiere la búsqueda de palabras clave, especialmente al identificar contenido genérico (como la comunicación relacionada con el cuidado de la salud) o un lenguaje inadecuado o explícito. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave tienen un tamaño limitado y requieren modificar el XML para crearlas o editarlas. Los diccionarios de palabras clave proporcionan una administración más sencilla de las palabras clave y en una escala mucho mayor, que admiten hasta 100.000 términos por Diccionario.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Pasos básicos para crear un diccionario de palabras clave

Las palabras clave del diccionario pueden provenir de una amplia variedad de orígenes, normalmente de un archivo (como una lista en un archivo .csv o .txt), importadas en el servicio o por el cmdlet de PowerShell, de una lista que escriba directamente en el cmdlet de PowerShell o de un diccionario existente. Al crear un diccionario de palabras clave, siga los mismos pasos principales:
  
1. Use el **centro de seguridad & cumplimiento** ([https://protection.office.com](https://protection.office.com)) o conéctese a **PowerShell &amp; del centro de seguridad y cumplimiento de Office 365**.
    
2. **Defina o cargue las palabras clave del origen deseado**. El asistente y el cmdlet aceptan una lista separada por comas de palabras clave para crear un diccionario de palabras clave personalizado, por lo que este paso variará ligeramente en función de la procedencia de las palabras clave. Una vez cargadas, se codificarán y convertirán en una matriz de bytes antes de su importación.
    
3. **Cree su Diccionario**. Elija un nombre y una descripción y cree su Diccionario.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Crear un diccionario de palabras clave mediante el centro de seguridad & cumplimiento

Siga estos pasos para crear e importar palabras clave para un diccionario personalizado:

1. Conéctese al centro de cumplimiento de seguridad[https://protection.office.com](https://protection.office.com)& ().

2. Vaya a **Clasificaciones > Tipos de información confidencial**.

3. Seleccione **Crear** y escriba un **Nombre** y **Descripción** para el tipo de información confidencial, a continuación, seleccione **Siguiente**

4. Seleccione **Agregar un elemento** y seleccione **Diccionario (palabras clave grandes)** en la lista desplegable **Detectar contenido que contenga**.

5. Seleccione **Agregar un diccionario**

6. En el control de Búsqueda, seleccione **Puede crear nuevos diccionarios de palabras clave aquí**.

7. Escriba un **Nombre** para el diccionario personalizado.

8. Seleccione **Importar** y seleccione **Desde texto** o **Desde csv** según el tipo de archivo de palabras clave.

9. En el cuadro de diálogo, seleccione el archivo de palabras clave del equipo o de los recursos compartidos de su red local y, después, seleccione **Abrir**.

10. Seleccione **Guardar**, después, seleccione el diccionario personalizado de la lista **Diccionarios de palabras clave**.

11. Seleccione **Agregar** y, después, seleccione **Siguiente**.

12. Revise y finalice las selecciones de tipo de información confidencial y seleccione **Finalizar**.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Crear un diccionario de palabras clave desde un archivo con PowerShell

A menudo, cuando es necesario crear un diccionario de gran tamaño, se usan palabras clave de un archivo o una lista exportada desde otro origen. En este caso, creará un diccionario de palabras clave que contiene una lista de idiomas inapropiados para filtrar el correo electrónico externo. Primero debe [conectarse a PowerShell del centro de &amp; seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
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

Es posible que tenga que modificar palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados. Actualmente, solo puede actualizar un diccionario personalizado de palabras clave con PowerShell. 

Por ejemplo, modificaremos algunos términos en PowerShell, guardaremos los términos localmente donde podrá modificarlos en un editor y, a continuación, actualizar los términos anteriores en su lugar. 

En primer lugar, recupere el objeto de diccionario:
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

La `$dict` impresión mostrará las distintas variables. Las palabras clave en sí se almacenan en un objeto en el `$dict.KeywordDictionary` back-end, pero contienen una representación de cadena de ellas que usará para modificar el diccionario. 

Antes de modificar el diccionario, debe volver a convertir la cadena de términos en una matriz con el `.split(',')` método. A continuación, limpiará los espacios no deseados entre las palabras clave con `.trim()` el método, dejando solo las palabras clave con las que trabajar. 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría exportar fácilmente el diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.
  
En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.
  
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

Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia de un tipo personalizado de información confidencial, o bien como un tipo de información confidencial. Ambos requieren que se cree un [tipo personalizado de información confidencial](create-a-custom-sensitive-information-type-in-scc-powershell.md). Siga las instrucciones del artículo vinculado para crear un tipo de información confidencial. Una vez que tenga el XML, necesitará el identificador de GUID para que el Diccionario lo use.
  
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


