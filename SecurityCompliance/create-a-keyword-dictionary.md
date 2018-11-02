---
title: Crear un diccionario de palabras clave
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c8a95d1b-c3b6-4613-98ab-0331d1872cf3
description: Para identificar información confidencial, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas. Los diccionarios de palabras clave ofrecen una administración más sencilla de palabras clave y con una escala mucho mayor, admitiendo hasta 100 000 términos por diccionario.
ms.openlocfilehash: 1cf41df5475af7ac5018cd34ea26e66ad5d668ee
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857238"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="ab48d-105">Crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="ab48d-105">Create a keyword dictionary</span></span>

<span data-ttu-id="ab48d-p102">Prevención de pérdida de datos (DLP) en Office 365 puede identificar, supervisar y proteger su información confidencial. Para identificar información confidencial, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas. Los diccionarios de palabras clave ofrecen una administración más sencilla de palabras clave y con una escala mucho mayor, admitiendo hasta 100 000 términos por diccionario.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p102">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information. Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication) or inappropriate or explicit language. While you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them. Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="ab48d-110">Pasos básicos para crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="ab48d-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="ab48d-p103">Las palabras clave del diccionario pueden provenir de una amplia variedad de orígenes, normalmente de un archivo (como una lista en un archivo .csv o .txt), de una lista que escriba directamente en el cmdlet o de un diccionario existente. Al crear un diccionario de palabras clave, siga los mismos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="ab48d-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list), from a list you enter directly in the cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="ab48d-113">**Conéctese a PowerShell del Centro de seguridad y cumplimiento**: vea [este tema](https://docs.microsoft.com/es-ES/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab48d-113">**Connect to Security &amp; Compliance Center PowerShell** - see [this topic](https://docs.microsoft.com/es-ES/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="ab48d-114">**Defina o cargue las palabras clave del origen que quiera usar**: el cmdlet para crear un diccionario de palabras clave acepta una lista separada por comas de palabras clave, por lo que este paso variará ligeramente según el origen de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="ab48d-114">**Define or load your keywords from your intended source** - the cmdlet to create a keyword dictionary accepts a comma-separated list of keywords, so this step will vary slightly depending on where your keywords come from.</span></span> 
    
3. <span data-ttu-id="ab48d-115">**Codifique las palabras clave**: después de cargarlas, se convertirán en una matriz de bytes antes de su importación.</span><span class="sxs-lookup"><span data-stu-id="ab48d-115">**Encode your keywords** - once loaded, they're converted to a byte array before they're imported.</span></span> 
    
4. <span data-ttu-id="ab48d-116">**Cree el diccionario**: seleccione un nombre y una descripción y, después, cree el diccionario.</span><span class="sxs-lookup"><span data-stu-id="ab48d-116">**Create your dictionary** - choose a name and description and create your dictionary.</span></span> 
    
## <a name="create-a-keyword-dictionary-from-a-file"></a><span data-ttu-id="ab48d-117">Crear un diccionario de palabras clave desde un archivo</span><span class="sxs-lookup"><span data-stu-id="ab48d-117">Create a keyword dictionary from a file</span></span>

<span data-ttu-id="ab48d-p104">Con frecuencia, si necesita crear un diccionario de gran tamaño, puede usar palabras clave de un archivo o una lista exportada de otro origen. En este caso, creará un diccionario de palabras clave que contenga una lista de lenguaje inadecuado para supervisarlo en el correo electrónico externo. Primero, necesita [conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/es-ES/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab48d-p104">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You need to first [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/es-ES/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="ab48d-121">Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.</span><span class="sxs-lookup"><span data-stu-id="ab48d-121">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="ab48d-p105">Guarde el archivo de texto con codificación Unicode. En el Bloc de notas \> **Guardar como** \> **Codificación** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p105">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="ab48d-124">Para leer el archivo en una variable, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ab48d-124">Read the file into a variable by running this cmdlet:</span></span>
    
  ```
  $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
  ```

4. <span data-ttu-id="ab48d-125">Para crear el diccionario, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ab48d-125">Create the dictionary by running this cmdlet:</span></span>
    
  ```
  New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
  ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="ab48d-126">Modificar un diccionario de palabras clave existente</span><span class="sxs-lookup"><span data-stu-id="ab48d-126">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="ab48d-p106">Puede que necesite modificar las palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados. En este ejemplo, modificará algunos términos en PowerShell, guardará los términos localmente donde pueda modificarlos en un editor y, después, actualizará los términos anteriores en contexto. Primero, recupere el objeto de diccionario:</span><span class="sxs-lookup"><span data-stu-id="ab48d-p106">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries. In this example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place. First, retrieve the dictionary object:</span></span>
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="ab48d-p107">Al imprimir `$dict`, se mostrarán las distintas variables. Las palabras clave en sí se almacenan en un objeto en el back-end, pero `$dict.KeywordDictionary` contiene una representación de cadena de estas, que usará para modificar el diccionario. Antes de modificar el diccionario, necesita volver a convertir la cadena de términos en una matriz con el método `.split(',')`. Después, eliminará los espacios no deseados entre las palabras clave con el método `.trim()` y dejará únicamente las palabras clave con las que quiera trabajar.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p107">Printing  `$dict` will show the various variables. The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary. Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method. Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="ab48d-p108">Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría exportar fácilmente el diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p108">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="ab48d-p109">En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](https://go.microsoft.com/fwlink/p/?linkid=852620), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p109">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://go.microsoft.com/fwlink/p/?linkid=852620), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="ab48d-p110">Ejecute el comando `$terms` para mostrar la lista de términos actual. El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="ab48d-p110">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="ab48d-140">Ejecute este comando para especificar los términos que quiera quitar:</span><span class="sxs-lookup"><span data-stu-id="ab48d-140">Run this command to specify the terms that you want to remove:</span></span>
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="ab48d-141">Ejecute este comando para quitar los términos de la lista:</span><span class="sxs-lookup"><span data-stu-id="ab48d-141">Run this command to actually remove the terms from the list:</span></span>
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="ab48d-p111">Ejecute el comando `$updatedTerms` para mostrar la lista actualizada de términos. El resultado del comando será parecido a este (se quitaron los términos especificados):</span><span class="sxs-lookup"><span data-stu-id="ab48d-p111">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="ab48d-p112">Ahora, guarde el diccionario localmente y agregue algunos términos más. Puede agregar los términos aquí en PowerShell, pero tendrá que exportar el archivo localmente para asegurarse de que se guarde con la codificación Unicode y que contenga el BOM.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p112">Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.</span></span>
  
<span data-ttu-id="ab48d-146">Para guardar el diccionario localmente, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab48d-146">Save the dictionary locally by running the following:</span></span>
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="ab48d-p113">Ahora, simplemente abra el archivo, agregue los términos adicionales y guárdelo con codificación Unicode (UTF-16). Ahora, cargará los términos actualizados y actualizará el diccionario en contexto.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p113">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="ab48d-p114">Ahora, el diccionario se actualizó en contexto. Tenga en cuenta que el campo `Identity` recibe el nombre del diccionario. Si también quiere cambiar el nombre del diccionario con el cmdlet `set-`, necesita agregar el parámetro `-Name` a los comandos anteriores con el nuevo nombre de diccionario.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p114">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="ab48d-152">Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP</span><span class="sxs-lookup"><span data-stu-id="ab48d-152">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="ab48d-p115">Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia para un tipo de información confidencial personalizado, o bien como tipo de información confidencial en sí. En ambos casos, es necesario [crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento de Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md). Siga las instrucciones del artículo vinculado para crear un tipo de información confidencial. Una vez que tenga el archivo XML, necesitará el identificador GUID del diccionario para poder usarlo.</span><span class="sxs-lookup"><span data-stu-id="ab48d-p115">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves. Both require [creating a custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md). Follow the instructions in the linked article to create a sensitive information type. Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="ab48d-157">Para obtener la identidad del diccionario, ejecute este comando y copie el valor de la propiedad **Identity**:</span><span class="sxs-lookup"><span data-stu-id="ab48d-157">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="ab48d-158">El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="ab48d-158">The output of the command looks like this:</span></span>
  
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

<span data-ttu-id="ab48d-p116">Pegue la identidad en el archivo XML del tipo de información confidencial personalizado y cárguelo. Ahora, el diccionario aparecerá en la lista de tipos de información confidencial y puede usarlo en la directiva (para hacerlo, especifique el número de palabras clave que tienen que coincidir).</span><span class="sxs-lookup"><span data-stu-id="ab48d-p116">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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


