---
title: Crear un tipo de información confidencial personalizada en el Centro de seguridad y cumplimiento.
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo crear, modificar, quitar y probar tipos personalizados de información confidencial para DLP en la interfaz gráfica de usuario del Centro de seguridad y cumplimiento.
ms.openlocfilehash: 62a08b4978e7e962f46a1de43c3d3160a44dd46e
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230904"
---
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="54d63-103">Crear un tipo de información confidencial personalizada en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="54d63-103">See Create a custom sensitive information type in Security & Compliance Center PowerShell.</span></span>

## <a name="summary"></a><span data-ttu-id="54d63-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="54d63-104">Summary</span></span>

<span data-ttu-id="54d63-105">Lea este artículo para crear un[tipo personalizado de información confidencial ](custom-sensitive-info-types.md)en el centro de cumplimiento y de seguridad ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="54d63-105">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="54d63-106">Los tipos de información confidencial personalizados se agregan al paquete de reglas denominado Microsoft.SCCManaged.CustomRulePack `Microsoft.SCCManaged.CustomRulePack`.</span><span class="sxs-lookup"><span data-stu-id="54d63-106">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="54d63-107">También puede crear tipos de información confidencial con PowerShell y usar las funciones de coincidencia de datos exacta.</span><span class="sxs-lookup"><span data-stu-id="54d63-107">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="54d63-108">Para obtener más información sobre estos métodos, vea:</span><span class="sxs-lookup"><span data-stu-id="54d63-108">To learn more about those methods, see:</span></span>
- <span data-ttu-id="54d63-109">[Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimientol](create-a-custom-sensitive-information-type-in-scc-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="54d63-109">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>
- <span data-ttu-id="54d63-110">[Cree un tipo de información confidencial personalizada para DLP con Exact Data Match (EDM) ](create-custom-sensitive-info-type-edm.md)</span><span class="sxs-lookup"><span data-stu-id="54d63-110">See [Create a custom sensitive information type with Exact Data Match based classification (Preview)](create-custom-sensitive-info-type-edm.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="54d63-111">Antes de empezar...</span><span class="sxs-lookup"><span data-stu-id="54d63-111">Before you begin</span></span>

- <span data-ttu-id="54d63-112">La organización debe tener una suscripción a, como Office 365 Enterprise, que incluye la prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="54d63-112">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="54d63-113">[Ver Política de Mensajería y Servicio de ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)</span><span class="sxs-lookup"><span data-stu-id="54d63-113">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="54d63-p104">Para usar los tipos personalizados de información confidencial, es necesario estar familiarizado con el uso de expresiones regulares (regex). Para obtener más información sobre el motor Boost.RegEx (anteriormente denominado RegEx++) usado para procesar el texto, vea [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="54d63-p104">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="54d63-p105">Los servicios de soporte técnico y atención al cliente de Microsoft no pueden proporcionarle definiciones personalizadas de coincidencia de contenido (mediante la creación de clasificaciones personalizadas o patrones de expresiones regulares). Los ingenieros de soporte técnico pueden proporcionar soporte limitado para la característica (por ejemplo, pueden proporcionar patrones de expresiones regulares de ejemplo con fines de prueba, o bien ayudarle en la solución de problemas de un patrón de expresión regular existente que no se desencadene del modo previsto), pero no pueden ofrecer garantías de que cualquier desarrollo de coincidencia de contenido personalizado se adapte a sus requisitos u obligaciones.</span><span class="sxs-lookup"><span data-stu-id="54d63-p105">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="54d63-p106">DLP usa el rastreador de búsqueda para identificar y clasificar información confidencial en sitios de SharePoint Online OneDrive para la Empresa. Para identificar el nuevo tipo personalizado de información confidencial en contenido existente, es necesario volver a rastrear el contenido. El contenido se vuelve a rastrear basándose en una programación, pero puede volverlo a rastrear de forma manual para una colección de sitios, una lista o una biblioteca. Para obtener más información, vea [Solicitar de forma manual el rastreo y la nueva indexación de un sitio, biblioteca o lista](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="54d63-p106">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="54d63-122">Crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="54d63-122">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="54d63-123">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="54d63-123">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="54d63-124">Las opciones pueden entenderse fácilmente y se explican en la página asociada del asistente:</span><span class="sxs-lookup"><span data-stu-id="54d63-124">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="54d63-125">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="54d63-125">**Name**</span></span>

- <span data-ttu-id="54d63-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="54d63-126">**Description**</span></span>

- <span data-ttu-id="54d63-127">**Proximidad**</span><span class="sxs-lookup"><span data-stu-id="54d63-127">**Proximity**</span></span>

- <span data-ttu-id="54d63-128">**Nivel de confianza**</span><span class="sxs-lookup"><span data-stu-id="54d63-128">**Confidence level**</span></span>

- <span data-ttu-id="54d63-129">**Elemento de patrón principal** (palabras clave, expresión regular o diccionario)</span><span class="sxs-lookup"><span data-stu-id="54d63-129">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="54d63-130">Opcional: **elementos de patrón complementarios** (palabras clave, expresión regular o diccionario) y un valor correspondiente de **Costo mínimo**.</span><span class="sxs-lookup"><span data-stu-id="54d63-130">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="54d63-p107">Imagine el escenario siguiente: quiere usar un tipo personalizado de información confidencial que detecte números de empleado de nueve dígitos en el contenido, así como las palabras clave “id. de empleado” e “identificación”. Para crear este tipo personalizado de información confidencial, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="54d63-p107">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="54d63-133">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="54d63-133">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Ubicación de los tipos de información confidencial y el botón Crear](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="54d63-135">En la página **Seleccionar un nombre y una descripción**, escriba los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d63-135">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="54d63-136">**Nombre**: id. de empleado.</span><span class="sxs-lookup"><span data-stu-id="54d63-136">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="54d63-137">**Descripción**: detectar números de id. de empleados de Contoso de nueve dígitos.</span><span class="sxs-lookup"><span data-stu-id="54d63-137">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Página de Nombre y descripción](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="54d63-139">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="54d63-139">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="54d63-140">En la página **Requisitos de coincidencia**, haga clic en **Agregar un elemento** y configure las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d63-140">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="54d63-141">**Detectar contenido que contenga**:</span><span class="sxs-lookup"><span data-stu-id="54d63-141">**Detect content containing**:</span></span>
 
      <span data-ttu-id="54d63-p108">a. Haga clic en **Cualquiera de estos** y seleccione **Expresión regular**.</span><span class="sxs-lookup"><span data-stu-id="54d63-p108">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="54d63-p109">b. En el cuadro de expresión regular, escriba `(\s)(\d{9})(\s)` (números de nueve dígitos rodeados por espacios en blanco).</span><span class="sxs-lookup"><span data-stu-id="54d63-p109">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="54d63-146">**Elementos complementarios**: haga clic en **Agregar elementos complementarios** y seleccione **Contiene esta lista de palabras clave**.</span><span class="sxs-lookup"><span data-stu-id="54d63-146">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="54d63-147">En el área **Contiene esta lista de palabras clave**, configure las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d63-147">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="54d63-148">**Lista de palabras clave**: escriba el valor “empleado,id.,identificación”.</span><span class="sxs-lookup"><span data-stu-id="54d63-148">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="54d63-149">**Recuento mínimo**: deje el valor predeterminado (1).</span><span class="sxs-lookup"><span data-stu-id="54d63-149">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="54d63-150">No modifique el valor predeterminado de **Nivel de confianza** (60).</span><span class="sxs-lookup"><span data-stu-id="54d63-150">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="54d63-151">No modifique el valor predeterminado de **Proximidad de caracteres** (300).</span><span class="sxs-lookup"><span data-stu-id="54d63-151">Leave the default **Character proximity** value 300.</span></span>

    ![Página Requisitos de coincidencia](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="54d63-153">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="54d63-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="54d63-154">En la página **Revisar y finalizar**, revise la configuración y, después, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="54d63-154">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Página Revisar y finalizar](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="54d63-p110">En la página siguiente, puede probar el nuevo tipo personalizado de información confidencial haciendo clic en **Sí**. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center). Para probar la regla más tarde, haga clic en **No**.</span><span class="sxs-lookup"><span data-stu-id="54d63-p110">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Página de recomendación de prueba](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="54d63-160">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="54d63-160">How do you know this worked?</span></span>

<span data-ttu-id="54d63-161">Para comprobar si un tipo de información confidencial se creó correctamente, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="54d63-161">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="54d63-162">Vaya a **Clasificaciones** \> **Tipos de información confidencial** y asegúrese de que en la lista se muestre el nuevo tipo personalizado de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="54d63-162">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="54d63-p111">Pruebe el nuevo tipo personalizado de información confidencial. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="54d63-p111">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="54d63-165">Modificar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="54d63-165">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="54d63-166">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="54d63-166">**Notes**:</span></span>

- <span data-ttu-id="54d63-p112">Solo se pueden modificar los tipos personalizados de información confidencial; no se pueden modificar los tipos de información confidencial integrados. Pero puede usar PowerShell para exportar los tipos personalizados de información confidencial integrados, personalizarlos y, después, importarlos como tipos personalizados de información confidencial. Para obtener más información, vea [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="54d63-p112">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="54d63-p113">Solo puede modificar los tipos de información confidencial personalizados que creó en la interfaz de usuario. Si ha usado el [procedimiento de PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) para importar un paquete de reglas de tipo de información confidencial, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="54d63-p113">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="54d63-172">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial**, seleccione el tipo personalizado de información confidencial que quiera modificar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54d63-172">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Ubicación de los tipos de información confidencial y el botón Editar](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="54d63-p114">Verá las mismas opciones disponibles que al crear el tipo personalizado de información confidencial en el Centro de seguridad y cumplimiento. Para obtener más información, vea [Crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="54d63-p114">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="54d63-176">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="54d63-176">How do you know this worked?</span></span>

<span data-ttu-id="54d63-177">Para comprobar si un tipo de información confidencial se modificó correctamente, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="54d63-177">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="54d63-178">Vaya a **Clasificaciones** \> **Tipos de información confidencial** para comprobar las propiedades del tipo personalizado de información confidencial modificado.</span><span class="sxs-lookup"><span data-stu-id="54d63-178">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="54d63-p115">Pruebe el tipo personalizado de información confidencial modificado. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="54d63-p115">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="54d63-181">Quitar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="54d63-181">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="54d63-182">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="54d63-182">**Notes**:</span></span>

- <span data-ttu-id="54d63-183">Solo se pueden quitar los tipos personalizados de información confidencial; no se pueden quitar los tipos de información confidencial integrados.</span><span class="sxs-lookup"><span data-stu-id="54d63-183">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="54d63-184">Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="54d63-184">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="54d63-185">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y seleccione uno o más tipos personalizados de información confidencial que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="54d63-185">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="54d63-186">En el control flotante, haga clic en **Eliminar** (o en **Eliminar tipos de información confidencial**, si seleccionó más de uno).</span><span class="sxs-lookup"><span data-stu-id="54d63-186">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Ubicación de los tipos de información confidencial y el botón Eliminar](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="54d63-188">Haga clic en **Sí** en el mensaje de advertencia que se muestre.</span><span class="sxs-lookup"><span data-stu-id="54d63-188">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="54d63-189">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="54d63-189">How do you know this worked?</span></span>

<span data-ttu-id="54d63-190">Para comprobar si un tipo personalizado de información confidencial se quitó correctamente, vaya a **Clasificaciones** \> **Tipos de información confidencial** y asegúrese de que el tipo personalizado de información confidencial ya no se muestre en la lista.</span><span class="sxs-lookup"><span data-stu-id="54d63-190">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="54d63-191">Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="54d63-191">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="54d63-192">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="54d63-192">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="54d63-p116">Seleccione uno o más tipos personalizados de información confidencial que quiera probar. En el control flotante que se abra, haga clic en **Probar tipo** (o en **Probar tipos de información confidencial**, si seleccionó un más de uno).</span><span class="sxs-lookup"><span data-stu-id="54d63-p116">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Ubicación de los tipos de información confidencial y el botón Tipo de prueba](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="54d63-196">En la página **Cargar archivo para probar** que se abre, cargue un documento para realizar la prueba (puede arrastrar y colocar un archivo, o bien puede hacer clic en **Examinar** y seleccionar un archivo).</span><span class="sxs-lookup"><span data-stu-id="54d63-196">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Página Cargar archivo para probar](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="54d63-198">Haga clic en el botón **Probar** para probar el documento y ver si hay coincidencias de patrones en el archivo.</span><span class="sxs-lookup"><span data-stu-id="54d63-198">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="54d63-199">En la página **Resultados de la coincidencia**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="54d63-199">On the **Match results** page, click **Finish**.</span></span>

    ![Resultados de la coincidencia](media/scc-cust-sens-info-type-test-results.png)