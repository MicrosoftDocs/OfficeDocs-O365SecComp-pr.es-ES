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
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="4cb2f-105">Crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="4cb2f-105">Create a keyword dictionary</span></span>

<span data-ttu-id="4cb2f-106">La prevención de pérdida de datos (DLP) en Office 365 puede identificar, supervisar y proteger la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-106">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information.</span></span> <span data-ttu-id="4cb2f-107">La identificación de información confidencial a veces requiere la búsqueda de palabras clave, especialmente al identificar contenido genérico (como la comunicación relacionada con el cuidado de la salud) o un lenguaje inadecuado o explícito.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-107">Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="4cb2f-108">Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave tienen un tamaño limitado y requieren modificar el XML para crearlas o editarlas.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-108">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="4cb2f-109">Los diccionarios de palabras clave proporcionan una administración más sencilla de las palabras clave y en una escala mucho mayor, que admiten hasta 100.000 términos por Diccionario.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-109">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="4cb2f-110">Pasos básicos para crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="4cb2f-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="4cb2f-p103">Las palabras clave del diccionario pueden provenir de una amplia variedad de orígenes, normalmente de un archivo (como una lista en un archivo .csv o .txt), importadas en el servicio o por el cmdlet de PowerShell, de una lista que escriba directamente en el cmdlet de PowerShell o de un diccionario existente. Al crear un diccionario de palabras clave, siga los mismos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="4cb2f-113">Use el **centro de seguridad & cumplimiento** ([https://protection.office.com](https://protection.office.com)) o conéctese a **PowerShell &amp; del centro de seguridad y cumplimiento de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-113">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Office 365 Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="4cb2f-114">**Defina o cargue las palabras clave del origen deseado**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-114">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="4cb2f-115">El asistente y el cmdlet aceptan una lista separada por comas de palabras clave para crear un diccionario de palabras clave personalizado, por lo que este paso variará ligeramente en función de la procedencia de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-115">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="4cb2f-116">Una vez cargadas, se codificarán y convertirán en una matriz de bytes antes de su importación.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-116">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="4cb2f-117">**Cree su Diccionario**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-117">**Create your dictionary**.</span></span> <span data-ttu-id="4cb2f-118">Elija un nombre y una descripción y cree su Diccionario.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-118">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="4cb2f-119">Crear un diccionario de palabras clave mediante el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4cb2f-119">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="4cb2f-120">Siga estos pasos para crear e importar palabras clave para un diccionario personalizado:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-120">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="4cb2f-121">Conéctese al centro de cumplimiento de seguridad[https://protection.office.com](https://protection.office.com)& ().</span><span class="sxs-lookup"><span data-stu-id="4cb2f-121">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="4cb2f-122">Vaya a **Clasificaciones > Tipos de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-122">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="4cb2f-123">Seleccione **Crear** y escriba un **Nombre** y **Descripción** para el tipo de información confidencial, a continuación, seleccione **Siguiente**</span><span class="sxs-lookup"><span data-stu-id="4cb2f-123">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="4cb2f-124">Seleccione **Agregar un elemento** y seleccione **Diccionario (palabras clave grandes)** en la lista desplegable **Detectar contenido que contenga**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-124">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="4cb2f-125">Seleccione **Agregar un diccionario**</span><span class="sxs-lookup"><span data-stu-id="4cb2f-125">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="4cb2f-126">En el control de Búsqueda, seleccione **Puede crear nuevos diccionarios de palabras clave aquí**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-126">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="4cb2f-127">Escriba un **Nombre** para el diccionario personalizado.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-127">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="4cb2f-128">Seleccione **Importar** y seleccione **Desde texto** o **Desde csv** según el tipo de archivo de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-128">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="4cb2f-129">En el cuadro de diálogo, seleccione el archivo de palabras clave del equipo o de los recursos compartidos de su red local y, después, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-129">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="4cb2f-130">Seleccione **Guardar**, después, seleccione el diccionario personalizado de la lista **Diccionarios de palabras clave**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-130">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="4cb2f-131">Seleccione **Agregar** y, después, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-131">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="4cb2f-132">Revise y finalice las selecciones de tipo de información confidencial y seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-132">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="4cb2f-133">Crear un diccionario de palabras clave desde un archivo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cb2f-133">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="4cb2f-134">A menudo, cuando es necesario crear un diccionario de gran tamaño, se usan palabras clave de un archivo o una lista exportada desde otro origen.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-134">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="4cb2f-135">En este caso, creará un diccionario de palabras clave que contiene una lista de idiomas inapropiados para filtrar el correo electrónico externo.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-135">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="4cb2f-136">Primero debe [conectarse a PowerShell del centro de &amp; seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="4cb2f-136">You must first [connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="4cb2f-137">Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-137">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="4cb2f-p107">Guarde el archivo de texto con codificación Unicode. En el Bloc de notas \> **Guardar como** \> **Codificación** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="4cb2f-140">Para leer el archivo en una variable, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-140">Read the file into a variable by running this cmdlet:</span></span>
    
    ```
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="4cb2f-141">Para crear el diccionario, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-141">Create the dictionary by running this cmdlet:</span></span>
    
    ```
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="4cb2f-142">Modificar un diccionario de palabras clave existente</span><span class="sxs-lookup"><span data-stu-id="4cb2f-142">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="4cb2f-143">Es posible que tenga que modificar palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-143">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="4cb2f-144">Actualmente, solo puede actualizar un diccionario personalizado de palabras clave con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-144">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="4cb2f-145">Por ejemplo, modificaremos algunos términos en PowerShell, guardaremos los términos localmente donde podrá modificarlos en un editor y, a continuación, actualizar los términos anteriores en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-145">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="4cb2f-146">En primer lugar, recupere el objeto de diccionario:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-146">First, retrieve the dictionary object:</span></span>
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="4cb2f-147">La `$dict` impresión mostrará las distintas variables.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-147">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="4cb2f-148">Las palabras clave en sí se almacenan en un objeto en el `$dict.KeywordDictionary` back-end, pero contienen una representación de cadena de ellas que usará para modificar el diccionario.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-148">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="4cb2f-149">Antes de modificar el diccionario, debe volver a convertir la cadena de términos en una matriz con el `.split(',')` método.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-149">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="4cb2f-150">A continuación, limpiará los espacios no deseados entre las palabras clave con `.trim()` el método, dejando solo las palabras clave con las que trabajar.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-150">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="4cb2f-p111">Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría exportar fácilmente el diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="4cb2f-p112">En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="4cb2f-p113">Ejecute el comando `$terms` para mostrar la lista de términos actual. El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="4cb2f-157">Ejecute este comando para especificar los términos que quiera quitar:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-157">Run this command to specify the terms that you want to remove:</span></span>
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="4cb2f-158">Ejecute este comando para quitar los términos de la lista:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-158">Run this command to actually remove the terms from the list:</span></span>
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="4cb2f-p114">Ejecute el comando `$updatedTerms` para mostrar la lista actualizada de términos. El resultado del comando será parecido a este (se quitaron los términos especificados):</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="4cb2f-p115">Ahora, guarde el diccionario localmente y agregue algunos términos más. Puede agregar los términos aquí en PowerShell, pero tendrá que exportar el archivo localmente para asegurarse de que se guarde con la codificación Unicode y que contenga el BOM.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p115">Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.</span></span>
  
<span data-ttu-id="4cb2f-163">Para guardar el diccionario localmente, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-163">Save the dictionary locally by running the following:</span></span>
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="4cb2f-p116">Ahora, simplemente abra el archivo, agregue los términos adicionales y guárdelo con codificación Unicode (UTF-16). Ahora, cargará los términos actualizados y actualizará el diccionario en contexto.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p116">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="4cb2f-p117">Ahora, el diccionario se actualizó en contexto. Tenga en cuenta que el campo `Identity` recibe el nombre del diccionario. Si también quiere cambiar el nombre del diccionario con el cmdlet `set-`, necesita agregar el parámetro `-Name` a los comandos anteriores con el nuevo nombre de diccionario.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p117">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="4cb2f-169">Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP</span><span class="sxs-lookup"><span data-stu-id="4cb2f-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="4cb2f-170">Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia de un tipo personalizado de información confidencial, o bien como un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="4cb2f-171">Ambos requieren que se cree un [tipo personalizado de información confidencial](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4cb2f-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="4cb2f-172">Siga las instrucciones del artículo vinculado para crear un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="4cb2f-173">Una vez que tenga el XML, necesitará el identificador de GUID para que el Diccionario lo use.</span><span class="sxs-lookup"><span data-stu-id="4cb2f-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="4cb2f-174">Para obtener la identidad del diccionario, ejecute este comando y copie el valor de la propiedad **Identity**:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="4cb2f-175">El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4cb2f-175">The output of the command looks like this:</span></span>
  
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

<span data-ttu-id="4cb2f-p119">Pegue la identidad en el archivo XML del tipo de información confidencial personalizado y cárguelo. Ahora, el diccionario aparecerá en la lista de tipos de información confidencial y puede usarlo en la directiva (para hacerlo, especifique el número de palabras clave que tienen que coincidir).</span><span class="sxs-lookup"><span data-stu-id="4cb2f-p119">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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


