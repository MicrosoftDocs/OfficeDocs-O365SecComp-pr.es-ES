---
title: Establecer la opción de omitir el texto para analizar en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Obtenga información sobre cómo definir la regla para omitir el texto específico al utilizar los módulos de proceso y analizar en la exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536239"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2e81d-103">Establecer la opción de omitir el texto para analizar en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2e81d-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="2e81d-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2e81d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2e81d-p102">La característica de omitir el texto se puede aplicar a todos o cualquiera de los siguientes módulos de exhibición de documentos electrónicos avanzada: analizar (cerca de duplicados, subprocesos de correo electrónico, los temas) y la relevancia. Texto omitido no aparecerán en los archivos que se muestran en la relevancia y los cálculos de análisis descartará el texto omitido.</span><span class="sxs-lookup"><span data-stu-id="2e81d-p102">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance. Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="2e81d-p103">Si la característica de omitir el texto se ha definido previamente para los módulos que ya ha ejecutado, la opción Omitir texto ahora estará protegida frente a la modificación. Sin embargo, aún puede cambiarse la característica de omitir el texto para el módulo de la relevancia en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="2e81d-p103">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified. However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="2e81d-110">Cómo se aplican los filtros de omitir texto</span><span class="sxs-lookup"><span data-stu-id="2e81d-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="2e81d-p104">Varios filtros de omitir texto se aplican en el orden en que se escribieron. Para cambiar el orden en que se aplican, debe eliminar y volver a escribir en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="2e81d-p104">Multiple Ignore Text filters are applied in the order that they were entered. To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="2e81d-113">Por ejemplo, si el contenido de texto es: "EVA de CAROL de ALICE para BOB de DAVE", los siguientes son ejemplos de entradas de omitir el texto y los resultados:</span><span class="sxs-lookup"><span data-stu-id="2e81d-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2e81d-114">**Omitir las entradas de texto**</span><span class="sxs-lookup"><span data-stu-id="2e81d-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="2e81d-115">**Resultados**</span><span class="sxs-lookup"><span data-stu-id="2e81d-115">**Results**</span></span> <br/> |
|<span data-ttu-id="2e81d-116">"ALICE", "BOB ANA"</span><span class="sxs-lookup"><span data-stu-id="2e81d-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="2e81d-117">"DAVE EVA"</span><span class="sxs-lookup"><span data-stu-id="2e81d-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="2e81d-118">"ALICE", "BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="2e81d-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="2e81d-119">"DAVE BOB CAROL EVA"</span><span class="sxs-lookup"><span data-stu-id="2e81d-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="2e81d-120">No se implementa la segunda entrada de texto omitir debido a que la cadena no se encuentra como tal, una vez que se ha aplicado el primer texto omitir.</span><span class="sxs-lookup"><span data-stu-id="2e81d-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="2e81d-121">Usar expresiones regulares al definir Omitir texto</span><span class="sxs-lookup"><span data-stu-id="2e81d-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="2e81d-p105">Expresiones regulares compatibles para su uso al definir Omitir texto. Los siguientes son ejemplos de uso y la sintaxis de expresión regular:</span><span class="sxs-lookup"><span data-stu-id="2e81d-p105">Regular expressions are supported for use when defining Ignore Text. The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="2e81d-124">Para quitar (omitir) el texto de inicio hasta el final de una línea:</span><span class="sxs-lookup"><span data-stu-id="2e81d-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="2e81d-125">donde "Begin" es la aparición de esta cadena en la línea inicial.</span><span class="sxs-lookup"><span data-stu-id="2e81d-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="2e81d-126">Por ejemplo, para el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="2e81d-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="2e81d-127">**"Ésta es la primera oración y primera línea**</span><span class="sxs-lookup"><span data-stu-id="2e81d-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="2e81d-128">**Ésta es la segunda oración y la segunda línea"**</span><span class="sxs-lookup"><span data-stu-id="2e81d-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="2e81d-129">la expresión Regular first(.\*) $ dará como resultado:</span><span class="sxs-lookup"><span data-stu-id="2e81d-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="2e81d-130">**"Ésta es la**</span><span class="sxs-lookup"><span data-stu-id="2e81d-130">**"This is**</span></span>
    
    <span data-ttu-id="2e81d-131">**Ésta es la segunda oración y la segunda línea"**</span><span class="sxs-lookup"><span data-stu-id="2e81d-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="2e81d-132">Para quitar la declinación de responsabilidades y legales instrucciones que se insertan automáticamente al final de subprocesos de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="2e81d-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="2e81d-133">donde "Begin" y "End" son cadenas únicas al principio y al final de un párrafo de texto ajustado.</span><span class="sxs-lookup"><span data-stu-id="2e81d-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="2e81d-134">Por ejemplo, la siguiente expresión regular quitará declinación de responsabilidades y declaraciones legales que estaban en el subproceso de correo electrónico entre las cadenas Begin y End:</span><span class="sxs-lookup"><span data-stu-id="2e81d-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="2e81d-135">**Este mensaje contiene información confidencial (. | \s)\*si es necesario la verificación por favor, solicitar una versión de la copia impresa**</span><span class="sxs-lookup"><span data-stu-id="2e81d-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="2e81d-136">Para quitar una renuncia de responsabilidad (incluidos los caracteres especiales):</span><span class="sxs-lookup"><span data-stu-id="2e81d-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="2e81d-137">Por ejemplo, para el siguiente texto (con la declinación de responsabilidades aquí representado por x):</span><span class="sxs-lookup"><span data-stu-id="2e81d-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="2e81d-138">**/\*\ Este mensaje contiene información confidencial. xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="2e81d-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="2e81d-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="2e81d-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="2e81d-140">\**Si es necesario, la verificación: xxxx xxxx solicita una versión de la copia impresa. /\*\**</span><span class="sxs-lookup"><span data-stu-id="2e81d-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="2e81d-141">debe ser la expresión regular para quitar la declinación de responsabilidades anterior:</span><span class="sxs-lookup"><span data-stu-id="2e81d-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="2e81d-142">**\/\\*\\Este mensaje contiene información confidencial\.(. | \s)\* si es necesario la verificación por favor, solicitar una versión de la copia impresa\.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="2e81d-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="2e81d-143">Reglas de expresión regular:</span><span class="sxs-lookup"><span data-stu-id="2e81d-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="2e81d-144">Todos los caracteres que no forman parte del alfabeto excepto espacios, "_" y "-" debe ir precedido por "\".</span><span class="sxs-lookup"><span data-stu-id="2e81d-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="2e81d-145">El campo eExpression regular puede ser una longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="2e81d-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="2e81d-146">Para obtener una explicación y detallada sobre la sintaxis de expresiones regulares, consulte: [Lenguaje de expresiones regulares - referencia rápida](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2e81d-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="2e81d-147">Definir la regla de omitir texto</span><span class="sxs-lookup"><span data-stu-id="2e81d-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="2e81d-148">En la **administrar \> analizar \> analizar las opciones de** ficha, en la sección **Omitir texto** , haga clic en el **+** icono para agregar una regla.</span><span class="sxs-lookup"><span data-stu-id="2e81d-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="2e81d-149">En el cuadro de diálogo **Agregar texto omitir** , en el campo **nombre** , escriba un nombre para la regla de texto omitir.</span><span class="sxs-lookup"><span data-stu-id="2e81d-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![Agregar texto omitido](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="2e81d-p106">En el cuadro de **texto** , escriba el texto que se pasen por alto. El campo de texto permite a un número ilimitado de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2e81d-p106">In the **Text** box, type the text to be ignored. The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="2e81d-153">Tal como se muestra en la ventana anterior, haga clic en la **bombilla** para ver las instrucciones de sintaxis comunes para la regla de texto omitir.</span><span class="sxs-lookup"><span data-stu-id="2e81d-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="2e81d-154">Seleccione la casilla de verificación **distinguir mayúsculas de minúsculas** , si así lo desea.</span><span class="sxs-lookup"><span data-stu-id="2e81d-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="2e81d-155">En la lista **aplicar a** , seleccione los módulos de exhibición de documentos electrónicos avanzada en el que se va a aplicar la definición.</span><span class="sxs-lookup"><span data-stu-id="2e81d-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="2e81d-p107">Si desea que una ejecución de prueba en el texto de ejemplo, escriba el texto de ejemplo en el cuadro de texto de **entrada** y haga clic en **probar**. Los resultados se muestran en el cuadro de texto de **salida** .</span><span class="sxs-lookup"><span data-stu-id="2e81d-p107">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**. The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="2e81d-p108">Haga clic en **Aceptar** para guardar la regla Omitir texto. Se muestra la regla de omitir texto definida.</span><span class="sxs-lookup"><span data-stu-id="2e81d-p108">Click **OK** to save the Ignore Text rule. The defined Ignore Text rule is displayed.</span></span> 
    
    ![Establecer el nombre del texto omitido](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="2e81d-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e81d-161">See also</span></span>

[<span data-ttu-id="2e81d-162">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2e81d-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2e81d-163">Descripción de la similitud de documento</span><span class="sxs-lookup"><span data-stu-id="2e81d-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2e81d-164">Configurar las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="2e81d-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2e81d-165">Análisis de la opción Configuración avanzada</span><span class="sxs-lookup"><span data-stu-id="2e81d-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2e81d-166">Ver los resultados del análisis</span><span class="sxs-lookup"><span data-stu-id="2e81d-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

