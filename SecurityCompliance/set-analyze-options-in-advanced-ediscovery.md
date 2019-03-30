---
title: Establecer las opciones de análisis en Office 365 Advanced eDiscovery
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Revise los pasos para configurar las opciones del proceso analizar en la exhibición avanzada de documentos electrónicos de Office 365, incluidos los subduplicados, los subprocesos de correo electrónico y los temas.  '
ms.openlocfilehash: 4689638f5cebe2ef17fcea5a13ff06edc29e5930
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30998533"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="0079f-103">Establecer las opciones de análisis en Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0079f-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="0079f-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="0079f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="0079f-106">En la exhibición avanzada de documentos electrónicos, establezca las opciones de análisis antes de ejecutar Analyze.</span><span class="sxs-lookup"><span data-stu-id="0079f-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="0079f-107">Establecer opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="0079f-107">Set Analyze options</span></span>

<span data-ttu-id="0079f-108">Abra \*\*preparar \> \*\* la \> **instalación**de Analyze.</span><span class="sxs-lookup"><span data-stu-id="0079f-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="0079f-109">Se muestra la siguiente ventana.</span><span class="sxs-lookup"><span data-stu-id="0079f-109">The following window is displayed.</span></span>
  
![Establecer las opciones de análisis](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="0079f-111">**Casi duplicados y subprocesos de correo electrónico** Active esta casilla si desea ejecutar el análisis.</span><span class="sxs-lookup"><span data-stu-id="0079f-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="0079f-112">Está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0079f-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="0079f-113">**Similitud de documentos** Especifique el valor de umbral Near-Duplicates o acepte el valor predeterminado de 65%.</span><span class="sxs-lookup"><span data-stu-id="0079f-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="0079f-114">**Temas** Active esta casilla para procesar todos los archivos y asignarles temas.</span><span class="sxs-lookup"><span data-stu-id="0079f-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="0079f-115">De forma predeterminada, esta casilla de verificación no está activada.</span><span class="sxs-lookup"><span data-stu-id="0079f-115">By default, this check box is not selected.</span></span> <span data-ttu-id="0079f-116">Especifique las siguientes opciones si desea realizar el procesamiento de temas.</span><span class="sxs-lookup"><span data-stu-id="0079f-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="0079f-117">**Número máximo de temas** Escriba o seleccione un valor para el número de temas que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="0079f-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="0079f-118">El valor predeterminado es 200.</span><span class="sxs-lookup"><span data-stu-id="0079f-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0079f-119">El aumento del número de temas afecta al rendimiento, así como la capacidad de un tema de generalizar.</span><span class="sxs-lookup"><span data-stu-id="0079f-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="0079f-120">Cuanto mayor sea el número de temas, más granular serán.</span><span class="sxs-lookup"><span data-stu-id="0079f-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="0079f-121">Por ejemplo, si un conjunto de 50 temas incluye un tema como "baloncesto, podas, Clippers, Lagoros"; 300 temas pueden incluir temas separados: "", "," podadoras "," lago ".</span><span class="sxs-lookup"><span data-stu-id="0079f-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="0079f-122">Si no ha tenido conocimiento del tema "baloncesto" y usa esta característica para ECA, puede resultar útil ver el tema "baloncesto".</span><span class="sxs-lookup"><span data-stu-id="0079f-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="0079f-123">Sin embargo, si el procesamiento tenía demasiados temas, es posible que nunca vea la palabra "baloncesto" y que no sepa que las pausas y las Clippers son buenos temas de baloncesto que revisar, en lugar de que se inician y se usan para el pelo.</span><span class="sxs-lookup"><span data-stu-id="0079f-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="0079f-124">**Temas sugeridos** Puede sugerir palabras del tema para controlar el procesamiento de temas.</span><span class="sxs-lookup"><span data-stu-id="0079f-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="0079f-125">EDiscovery avanzado se centrará en estas palabras sugeridas y intentará crear uno o más temas relevantes, en función de la configuración del "número máximo de temas".</span><span class="sxs-lookup"><span data-stu-id="0079f-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="0079f-126">Por ejemplo, si la palabra sugerida es "equipo" y ha especificado "2" como "número máximo de temas", la exhibición avanzada de documentos electrónicos intentará generar dos temas relacionados con la palabra "equipo".</span><span class="sxs-lookup"><span data-stu-id="0079f-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="0079f-127">Por ejemplo, los dos temas podrían ser "software de equipo" y "hardware de equipo".</span><span class="sxs-lookup"><span data-stu-id="0079f-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Agregar tema sugerido](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="0079f-129">Para ver, agregar o editar los temas sugeridos, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="0079f-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="0079f-130">En el panel **temas sugeridos** , haga clic en el](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icono **Agregar** ![icono Agregar para agregar un tema.</span><span class="sxs-lookup"><span data-stu-id="0079f-130">In the **Suggested themes** panel, click the **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="0079f-131">En el panel **Agregar tema sugerido** , agregue las palabras separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="0079f-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="0079f-132">En **número de temas**, seleccione un valor para determinar el número de temas que la exhibición avanzada de documentos electrónicos intentará generar para estas palabras (el valor predeterminado es 1 tema).</span><span class="sxs-lookup"><span data-stu-id="0079f-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="0079f-133">Haga clic en **Guardar** y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0079f-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0079f-134">El número total de temas incluye temas sugeridos.</span><span class="sxs-lookup"><span data-stu-id="0079f-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="0079f-135">El total de temas sugeridos no puede exceder el total de los temas.</span><span class="sxs-lookup"><span data-stu-id="0079f-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="0079f-136">Si hay muchos temas sugeridos en relación con el total de los temas, el sistema detectará solo unos pocos temas "nuevos", ya que la mayoría de los temas se dedicará a temas sugeridos.</span><span class="sxs-lookup"><span data-stu-id="0079f-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="0079f-137">**Modo** En la lista desplegable, seleccione una opción de **temas** :</span><span class="sxs-lookup"><span data-stu-id="0079f-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="0079f-138">**Crear y aplicar modelo**: calcula los temas por modelos de un segmento de los archivos y, a continuación, distribuye los archivos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="0079f-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="0079f-139">**Create Model**: calcula un modelo de temas a partir de un segmento de los archivos.</span><span class="sxs-lookup"><span data-stu-id="0079f-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="0079f-140">El proceso de aplicar divisiones de archivos se realiza por separado en otro momento.</span><span class="sxs-lookup"><span data-stu-id="0079f-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="0079f-141">**Aplicar modelo**: esta opción solo se muestra si un modelo se ha creado anteriormente y todavía no se ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="0079f-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="0079f-142">Se dividirán los archivos según los temas.</span><span class="sxs-lookup"><span data-stu-id="0079f-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="0079f-143">También puede [establecer omitir texto](set-ignore-text-in-advanced-ediscovery.md) y [establecer la configuración avanzada de análisis](set-analyze-advanced-settings-in-advanced-ediscovery.md) para analizar.</span><span class="sxs-lookup"><span data-stu-id="0079f-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="0079f-144">Una vez establecidas estas opciones, haga clic en **analizar** para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="0079f-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="0079f-145">Se muestran [los resultados de la vista analizar](view-analyze-results-in-advanced-ediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="0079f-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0079f-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="0079f-146">See also</span></span>

[<span data-ttu-id="0079f-147">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="0079f-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0079f-148">Descripción de la similitud de documentos</span><span class="sxs-lookup"><span data-stu-id="0079f-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0079f-149">Establecer omitir texto</span><span class="sxs-lookup"><span data-stu-id="0079f-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0079f-150">Establecer la configuración avanzada del análisis</span><span class="sxs-lookup"><span data-stu-id="0079f-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0079f-151">Ver los resultados del análisis</span><span class="sxs-lookup"><span data-stu-id="0079f-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

