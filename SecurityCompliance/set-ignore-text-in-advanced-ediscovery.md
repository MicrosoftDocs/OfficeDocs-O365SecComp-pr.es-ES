---
title: Establecer la opción de omitir el texto para analizar en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Obtenga información sobre cómo definir la regla para omitir texto específico cuando use los módulos Analyze y Process en Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 3a4c1d17a9a56d3018509a8dcfd6b49abb951676
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214250"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="4a018-103">Establecer la opción de omitir el texto para analizar en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="4a018-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="4a018-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="4a018-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="4a018-p102">La característica omitir texto se puede aplicar a todos los módulos avanzados de eDiscovery (o a cualquiera de ellos): analizar (casi duplicados, subProcesos de correo electrónico, temas) y relevancia. El texto omitido no aparecerá en los archivos que se muestren en relevancia y el análisis o cálculos descartará el texto omitido.</span><span class="sxs-lookup"><span data-stu-id="4a018-p102">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance. Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="4a018-p103">Si la característica de omitir texto se ha definido previamente para los módulos que ya se han ejecutado, la configuración de omitir texto ahora estará protegida contra modificaciones. Sin embargo, la característica de omisión de texto para el módulo de relevancia todavía puede cambiarse en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="4a018-p103">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified. However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="4a018-110">Cómo omitir los filtros de texto que se aplican</span><span class="sxs-lookup"><span data-stu-id="4a018-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="4a018-p104">Se aplican varios filtros de omitir texto en el orden en que se especificaron. Para cambiar el orden en el que se aplican, se deben eliminar y volver a especificar en el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="4a018-p104">Multiple Ignore Text filters are applied in the order that they were entered. To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="4a018-113">Por ejemplo, si el contenido de texto es: "DAVE BOB ALICE CAROL Eva", a continuación se muestran ejemplos de omitir las entradas de texto y los resultados:</span><span class="sxs-lookup"><span data-stu-id="4a018-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="4a018-114">**Omitir entradas de texto**</span><span class="sxs-lookup"><span data-stu-id="4a018-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="4a018-115">**Resultados**</span><span class="sxs-lookup"><span data-stu-id="4a018-115">**Results**</span></span> <br/> |
|<span data-ttu-id="4a018-116">"ALICIA", "BOB CAROL"</span><span class="sxs-lookup"><span data-stu-id="4a018-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="4a018-117">"DAVE EVA"</span><span class="sxs-lookup"><span data-stu-id="4a018-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="4a018-118">"ALICIA", "BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="4a018-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="4a018-119">"EVA BOB CAROL EVA"</span><span class="sxs-lookup"><span data-stu-id="4a018-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="4a018-120">La segunda omisión de la entrada de texto no se implementa porque no se encuentra la cadena como tal después de que se haya aplicado el primer texto ignore.</span><span class="sxs-lookup"><span data-stu-id="4a018-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="4a018-121">Usar expresiones regulares al definir omitir texto</span><span class="sxs-lookup"><span data-stu-id="4a018-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="4a018-p105">Las expresiones regulares se pueden usar al definir omitir texto. A continuación, se muestran ejemplos de sintaxis y uso de expresiones regulares:</span><span class="sxs-lookup"><span data-stu-id="4a018-p105">Regular expressions are supported for use when defining Ignore Text. The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="4a018-124">Para quitar (omitir) el texto desde el principio hasta el final de una línea:</span><span class="sxs-lookup"><span data-stu-id="4a018-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="4a018-125">donde "begin" es la ocurrencia inicial de esta cadena en la línea.</span><span class="sxs-lookup"><span data-stu-id="4a018-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="4a018-126">Por ejemplo, para el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="4a018-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="4a018-127">**"Es la primera oración y primera línea**</span><span class="sxs-lookup"><span data-stu-id="4a018-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="4a018-128">**Es la segunda oración y segunda línea "**</span><span class="sxs-lookup"><span data-stu-id="4a018-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="4a018-129">primero la expresión regular (.\*) $ dará como resultado:</span><span class="sxs-lookup"><span data-stu-id="4a018-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="4a018-130">**"Esto es**</span><span class="sxs-lookup"><span data-stu-id="4a018-130">**"This is**</span></span>
    
    <span data-ttu-id="4a018-131">**Es la segunda oración y segunda línea "**</span><span class="sxs-lookup"><span data-stu-id="4a018-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="4a018-132">Para quitar avisos de declinación de responsabilidad e instrucciones legales insertadas automáticamente al final de los subprocesos de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="4a018-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="4a018-133">donde "begin" y "End" son cadenas únicas al principio y al final de un párrafo de texto ajustado.</span><span class="sxs-lookup"><span data-stu-id="4a018-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="4a018-134">Por ejemplo, la siguiente expresión regular quitará los avisos de declinación de responsabilidad y las instrucciones legales que estaban en el hilo de correo electrónico entre las cadenas de inicio y finalización:</span><span class="sxs-lookup"><span data-stu-id="4a018-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="4a018-135">**Este mensaje contiene información confidencial (. | \s)\*si se requiere la comprobación, solicite una copia impresa de la versión**</span><span class="sxs-lookup"><span data-stu-id="4a018-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="4a018-136">Para quitar un aviso de declinación de responsabilidades (incluidos los caracteres especiales):</span><span class="sxs-lookup"><span data-stu-id="4a018-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="4a018-137">Por ejemplo, para el texto siguiente (con la declinación de responsabilidades representada aquí por x):</span><span class="sxs-lookup"><span data-stu-id="4a018-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="4a018-138">**/\*\ Este mensaje contiene información confidencial. XXXX XXXX**</span><span class="sxs-lookup"><span data-stu-id="4a018-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="4a018-139">**XXXX XXXX XXXX XXXX XXXX XXXX XXXX**</span><span class="sxs-lookup"><span data-stu-id="4a018-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="4a018-140">\**XXXX XXXX si es necesario realizar una comprobación, solicite una copia impresa de la versión. /\*\**</span><span class="sxs-lookup"><span data-stu-id="4a018-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="4a018-141">la expresión regular para quitar el aviso de declinación de responsabilidades anterior debería ser:</span><span class="sxs-lookup"><span data-stu-id="4a018-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="4a018-142">**\/\\*\\Este mensaje contiene información\.confidencial (. | \s)\* si se requiere la comprobación, solicite una copia impresa de\. la versión\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="4a018-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="4a018-143">Reglas de expresiones regulares:</span><span class="sxs-lookup"><span data-stu-id="4a018-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="4a018-144">Los caracteres que no forman parte del alfabeto excepto los espacios, "_" y "-" deben ir precedidos de "\".</span><span class="sxs-lookup"><span data-stu-id="4a018-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="4a018-145">El campo eExpression normal puede tener una longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="4a018-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="4a018-146">Para obtener una explicación y una sintaxis detallada de las expresiones regulares, vea: [referencia rápida del lenguaje de expresiones regulares](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a018-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="4a018-147">Definir la regla de omisión de texto</span><span class="sxs-lookup"><span data-stu-id="4a018-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="4a018-148">En la sección **omitir texto** de la pestaña **administrar \> \> opciones** de análisis, haga clic **+** en el icono para agregar una regla.</span><span class="sxs-lookup"><span data-stu-id="4a018-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="4a018-149">En el cuadro de diálogo **Agregar y omitir texto** , en el campo **nombre** , escriba un nombre para la regla de omitir texto.</span><span class="sxs-lookup"><span data-stu-id="4a018-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![Agregar texto omitido](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="4a018-p106">En el cuadro de **texto** , escriba el texto que se va a omitir. El campo de texto permite un número de caracteres ilimitado.</span><span class="sxs-lookup"><span data-stu-id="4a018-p106">In the **Text** box, type the text to be ignored. The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4a018-153">Como se muestra en la ventana anterior, haga clic en **bombilla** para ver instrucciones de sintaxis comunes para la regla de omitir texto.</span><span class="sxs-lookup"><span data-stu-id="4a018-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="4a018-154">Active la casilla de verificación **distinguir mayúsculas** de minúsculas, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="4a018-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="4a018-155">En la lista **aplicar a** , seleccione los módulos avanzados de eDiscovery en los que desea aplicar la definición.</span><span class="sxs-lookup"><span data-stu-id="4a018-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="4a018-p107">Si desea una ejecución de prueba en texto de ejemplo, escriba ejemplo de texto en el cuadro de texto de **entrada** y haga clic en **prueba**. Los resultados se muestran en el cuadro de texto de **salida** .</span><span class="sxs-lookup"><span data-stu-id="4a018-p107">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**. The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="4a018-p108">Haga clic en **Aceptar** para guardar la regla de omisión de texto. Se muestra la regla definida por omitir texto.</span><span class="sxs-lookup"><span data-stu-id="4a018-p108">Click **OK** to save the Ignore Text rule. The defined Ignore Text rule is displayed.</span></span> 
    
    ![Establecer el nombre del texto omitido](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="4a018-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a018-161">See also</span></span>

[<span data-ttu-id="4a018-162">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="4a018-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4a018-163">Descripción de la similitud de documentos</span><span class="sxs-lookup"><span data-stu-id="4a018-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4a018-164">Configuración de las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="4a018-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4a018-165">Configuración de la configuración avanzada de análisis</span><span class="sxs-lookup"><span data-stu-id="4a018-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4a018-166">Visualización de los resultados del análisis</span><span class="sxs-lookup"><span data-stu-id="4a018-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

