---
title: Establecer opciones de analizar en eDiscovery avanzado de Office 365
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Revise los pasos para configurar las opciones para el proceso de analizar en Office 365 avanzada exhibición de documentos electrónicos, incluidos cerca de duplicados, los subprocesos de correo electrónico y los temas.  '
ms.openlocfilehash: a0ebbadb180321a3094cb1056ed8e0e6500ee66a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536187"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="063b2-103">Establecer opciones de analizar en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="063b2-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="063b2-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="063b2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="063b2-106">En Opciones avanzadas exhibición de documentos electrónicos, establezca las opciones de analizar antes de ejecutar Analyze.</span><span class="sxs-lookup"><span data-stu-id="063b2-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="063b2-107">Establecer las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="063b2-107">Set Analyze options</span></span>

<span data-ttu-id="063b2-p102">Open **preparar \> analizar** \> **el programa de instalación**. Se muestra la siguiente ventana.</span><span class="sxs-lookup"><span data-stu-id="063b2-p102">Open **Prepare \> Analyze** \> **Setup**. The following window is displayed.</span></span>
  
![Establecer las opciones de análisis](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="063b2-p103">**Cerca de duplicados y subprocesos de correo electrónico** Active esta casilla si desea ejecutar el análisis. Se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="063b2-p103">**Near-duplicates and email threads** Check this box if you want to run the analysis. It is selected by default.</span></span> 
  
 <span data-ttu-id="063b2-113">**Similitud de documento** Escriba el valor del umbral Near duplicados o acepte el valor predeterminado de 65%.</span><span class="sxs-lookup"><span data-stu-id="063b2-113">**Document similarity**Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="063b2-p104">**Temas** Active esta casilla para procesar todos los archivos y asignar los temas a ellos. De forma predeterminada, esta casilla de verificación no está seleccionada. Si desea realizar los temas de procesamiento, especifique las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="063b2-p104">**Themes**Check this box to process all files and assign themes to them. By default, this check box is not selected. Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="063b2-p105">**Número máximo de temas** Introduzca o seleccione un valor para el número de temas para crear. El valor predeterminado es 200.</span><span class="sxs-lookup"><span data-stu-id="063b2-p105">**Max number of themes**Enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="063b2-p106">El aumento del número de temas afecta al rendimiento, así como la capacidad de un tema para generalizar. Cuanto mayor sea el número de temas, más granulares son. Por ejemplo, si un conjunto de 50 temas incluye un tema, como "Baloncesto, cambio, cortar, Lakers"; temas de 300 pueden incluir temas independientes: "Cual insta", "Cortar", "Lakers". Si no tenía ningún conocimiento del tema "Baloncesto" y usar esta característica para ECA, vea el tema "Baloncesto" podría ser útil. Sin embargo, si el procesamiento tenía demasiados temas, es posible que vea nunca la palabra "Baloncesto" y no puede saber que cambio y cortar es una buena temas baloncesto para revisar, en lugar de los elementos que vaya de se inicia y se usa de forma.</span><span class="sxs-lookup"><span data-stu-id="063b2-p106">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="063b2-p107">**Temas que se sugiere** Puede sugerir palabras de tema para controlar el procesamiento de temas. Exhibición de documentos electrónicos avanzada se centrarse en estas palabras sugeridas y pruebe a crear uno o varios temas relevantes, en función de la configuración de "Número de temas de Max".</span><span class="sxs-lookup"><span data-stu-id="063b2-p107">**Suggested themes**You can suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="063b2-p108">Por ejemplo, si la palabra sugerida es "computer", y especificó "2" como el "número de temas de Max", intentará avanzada exhibición de documentos electrónicos generar dos temas que se relacionan con la palabra "equipo". Los dos temas podrían ser "software informático" y "hardware del equipo", por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="063b2-p108">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Agregar tema sugerido](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="063b2-129">Para ver, agregar o editar los temas sugeridos, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="063b2-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="063b2-p109">En el panel de **temas que se sugiere** , haga clic en el **complemento**![agregar icono](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icono para agregar un tema. En el panel de **tema sugerido de agregar** , agregue las palabras, separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="063b2-p109">In the **Suggested themes** panel, click the **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme. In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="063b2-132">En **número de temas**, seleccione un valor para determinar el número de temas de exhibición de documentos electrónicos avanzada intentará generar estas palabras (el valor predeterminado es 1 tema).</span><span class="sxs-lookup"><span data-stu-id="063b2-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="063b2-133">Haga clic en **Guardar** y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="063b2-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="063b2-p110">El número total de temas incluye temas sugeridos. Los temas sugeridos total no puede superar los temas totales. Si hay muchos temas sugeridos con respecto a los temas totales, sólo los temas de "nuevos" unos será detectados por el sistema debido a que la mayoría de los temas se dedicarse a temas sugeridos.</span><span class="sxs-lookup"><span data-stu-id="063b2-p110">The total number of themes includes Suggested Themes. The total Suggested Themes cannot exceed the total themes. If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="063b2-137">**Modo** En la lista desplegable, seleccione una opción de **temas** :</span><span class="sxs-lookup"><span data-stu-id="063b2-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="063b2-138">**Crear y aplicar el modelo de**: calcula los temas por modelos de un segmento de los archivos y, a continuación, distribuye los archivos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="063b2-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="063b2-p111">**Crear modelo**: calcula un modelo de temas de un segmento de los archivos. El proceso de aplicación de dividir los archivos se realiza por separado en otro momento.</span><span class="sxs-lookup"><span data-stu-id="063b2-p111">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="063b2-p112">**Aplicar modelo**: esta opción sólo se muestra si un modelo se ha creado anteriormente y todavía no se ha aplicado. Esto dividirá los archivos basándose en los temas.</span><span class="sxs-lookup"><span data-stu-id="063b2-p112">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="063b2-143">También puede [Omitir el conjunto de texto](set-ignore-text-in-advanced-ediscovery.md) y [establecer la configuración avanzada de analizar](set-analyze-advanced-settings-in-advanced-ediscovery.md) para analizar.</span><span class="sxs-lookup"><span data-stu-id="063b2-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="063b2-p113">Una vez haya configurado estas opciones, haga clic en **analizar** para ejecutar. Se muestran [los resultados de la vista de análisis](view-analyze-results-in-advanced-ediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="063b2-p113">After you've set these options, click **Analyze** to run. [View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="063b2-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="063b2-146">See also</span></span>

[<span data-ttu-id="063b2-147">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="063b2-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="063b2-148">Descripción de la similitud de documento</span><span class="sxs-lookup"><span data-stu-id="063b2-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="063b2-149">Omitir el conjunto de texto</span><span class="sxs-lookup"><span data-stu-id="063b2-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="063b2-150">Establecer la configuración avanzada del análisis</span><span class="sxs-lookup"><span data-stu-id="063b2-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="063b2-151">Ver los resultados de análisis</span><span class="sxs-lookup"><span data-stu-id="063b2-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

