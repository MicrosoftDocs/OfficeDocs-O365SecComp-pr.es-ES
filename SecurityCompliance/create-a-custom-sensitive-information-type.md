---
title: Crear un tipo personalizado de información confidencial
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo crear, modificar, quitar y probar tipos personalizados de información confidencial para DLP en la interfaz gráfica de usuario del Centro de seguridad y cumplimiento.
ms.openlocfilehash: de7bbc8ee624fe9468dc64a9811db31d529984bf
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258348"
---
# <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="497ff-103">Crear un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="497ff-103">Create a custom sensitive information type</span></span>

<span data-ttu-id="497ff-p101">Prevención de pérdida de datos (DLP) de Office 365 incluye muchos [tipos de información confidencial](what-the-sensitive-information-types-look-for.md) integrados preparados para usarlos en las directivas DLP. Estos tipos integrados pueden ayudar a identificar y proteger números de tarjeta de crédito, cuentas bancarias, números de pasaporte y mucho más.</span><span class="sxs-lookup"><span data-stu-id="497ff-p101">Data loss prevention (DLP) in Office 365 includes many built-in [sensitive information types](what-the-sensitive-information-types-look-for.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 

<span data-ttu-id="497ff-106">Pero, si necesita identificar y proteger otro tipo de información confidencial, como el id. de empleado o números de proyecto que usen un formato específico para su organización, puede crear un tipo personalizado de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="497ff-106">But if you need to identify and protect a different type of sensitive information (for example, employee IDs or project numbers that uses a format specific to your organization) you can create a custom sensitive information type.</span></span>

<span data-ttu-id="497ff-107">Estas son las partes básicas de un tipo personalizado de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="497ff-107">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="497ff-108">**Patrón principal**: números de id. de empleado, números de proyecto, etc. Suele identificarse mediante una expresión regular (regex), pero también puede ser una lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="497ff-108">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="497ff-p102">**Evidencia adicional**: imagine que busca un número de id. de empleado de nueve dígitos. No todos los números de nueve dígitos son números de id. de empleado, pero puede buscar texto adicional (palabras clave como “empleado”, “identificación” o “id.”, o bien otros patrones de texto basados en expresiones regulares). Esta evidencia complementaria (también conocida como _evidencia_ _corroborativa_) incrementa la probabilidad de que el número de nueve dígitos encontrado en el contenido sea realmente un número de id. de empleado.</span><span class="sxs-lookup"><span data-stu-id="497ff-p102">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="497ff-p103">**Proximidad de caracteres**: tiene sentido que, cuanto más próximos estén entre sí el patrón principal y la evidencia complementaria, más probabilidades habrá de que el contenido detectado sea lo que busca. Puede especificar la distancia de caracteres entre el patrón principal y la evidencia complementaria (también conocida como _ventana de proximidad_), como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="497ff-p103">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagrama de evidencia corroborativa y ventana de proximidad](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="497ff-p104">**Nivel de confianza**: cuantas más evidencias complementarias tenga, mayor será la probabilidad de que una coincidencia contenga la información confidencial que busca. Puede asignar mayores niveles de confianza a las coincidencias detectadas mediante el uso de más evidencias.</span><span class="sxs-lookup"><span data-stu-id="497ff-p104">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="497ff-p105">Cuando esté conforme, un patrón devolverá un recuento y un nivel de confianza, que podrá usar en las condiciones de las directivas DLP. Al agregar a una directiva DLP una condición para detectar un tipo de información confidencial, puede editar el recuento y el nivel de confianza, como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="497ff-p105">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Opciones de precisión de coincidencia y recuento de instancias](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

<span data-ttu-id="497ff-120">Para crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento, use una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="497ff-120">To create custom sensitive information types in the Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="497ff-p106">**Interfaz de usuario**: este método es más sencillo y rápido, pero tiene menos opciones de configuración que si usa PowerShell. En el resto de este tema, se describen estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="497ff-p106">**Use the UI**: This method is easier and faster, but you have less configuration options than PowerShell. The rest of this topic describes these procedures.</span></span>

- <span data-ttu-id="497ff-p107">**PowerShell**: para usar este método, primero tiene que crear un archivo XML (denominado _paquete de reglas_) que contiene uno o más tipos de información confidencial y, después, usará PowerShell para importar el paquete de reglas (importar el paquete de reglas es complicado en comparación con la creación del paquete de reglas). Este método es mucho más complejo que si se usa la interfaz de usuario, pero ofrece más opciones de configuración. Para obtener instrucciones, vea [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="497ff-p107">**Use PowerShell**: This method requires that you first create an XML file (called a _rule package_) that contains one or more sensitive information types, and then you use PowerShell to import the rule package (importing the rule package is trivial compared to creating the rule package. This method is much more complex than the UI, but you have more configuration options. For instructions, see [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

<span data-ttu-id="497ff-126">En la tabla siguiente, se describen las principales diferencias:</span><span class="sxs-lookup"><span data-stu-id="497ff-126">The key differences are described in the following table:</span></span>

|<span data-ttu-id="497ff-127">**Tipos personalizados de información confidencial en la interfaz de usuario**</span><span class="sxs-lookup"><span data-stu-id="497ff-127">**Custom sensitive information types in the UI**</span></span>|<span data-ttu-id="497ff-128">**Tipos personalizados de información confidencial en PowerShell**</span><span class="sxs-lookup"><span data-stu-id="497ff-128">**Custom sensitive information types in PowerShell**</span></span>|
|:-----|:-----|
|<span data-ttu-id="497ff-129">El nombre y la descripción están en un idioma.</span><span class="sxs-lookup"><span data-stu-id="497ff-129">Name and Description are in one language.</span></span>|<span data-ttu-id="497ff-130">Admite varios idiomas para Nombre y Descripción.</span><span class="sxs-lookup"><span data-stu-id="497ff-130">Supports multiple languages for Name and Description.</span></span>|
|<span data-ttu-id="497ff-131">Es compatible con un patrón.</span><span class="sxs-lookup"><span data-stu-id="497ff-131">Supports one pattern.</span></span>|<span data-ttu-id="497ff-132">Es compatible con varios patrones.</span><span class="sxs-lookup"><span data-stu-id="497ff-132">Supports multiple patterns.</span></span>|
|<span data-ttu-id="497ff-133">Las evidencias complementarias pueden ser:</span><span class="sxs-lookup"><span data-stu-id="497ff-133">Supporting evidence can be:</span></span> <br/><span data-ttu-id="497ff-134">• Expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="497ff-134">• Regular expressions</span></span> <br/><span data-ttu-id="497ff-135">• Palabras clave</span><span class="sxs-lookup"><span data-stu-id="497ff-135">• Keywords</span></span> <br/><span data-ttu-id="497ff-136">• Diccionarios de palabras clave</span><span class="sxs-lookup"><span data-stu-id="497ff-136">• Keyword dictionaries</span></span>|<span data-ttu-id="497ff-137">Las evidencias complementarias pueden ser:</span><span class="sxs-lookup"><span data-stu-id="497ff-137">Supporting evidence can be:</span></span> <br/><span data-ttu-id="497ff-138">• Expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="497ff-138">• Regular expressions</span></span> <br/><span data-ttu-id="497ff-139">• Palabras clave</span><span class="sxs-lookup"><span data-stu-id="497ff-139">• Keywords</span></span> <br/><span data-ttu-id="497ff-140">• Diccionarios de palabras clave</span><span class="sxs-lookup"><span data-stu-id="497ff-140">• Keyword dictionaries</span></span> <br/><span data-ttu-id="497ff-141">• [Funciones de DLP integradas](what-the-dlp-functions-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="497ff-141">• [Built-in DLP functions](what-the-dlp-functions-look-for.md)</span></span>|
|<span data-ttu-id="497ff-142">Los tipos de información confidencial personalizados se agregan al paquete de reglas denominado Microsoft.SCCManaged.CustomRulePack</span><span class="sxs-lookup"><span data-stu-id="497ff-142">Custom sensitive information types are added to the rule package named Microsoft.SCCManaged.CustomRulePack</span></span>|<span data-ttu-id="497ff-143">Puede crear hasta 10 paquetes de reglas que contengan tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="497ff-143">You can create up to 10 rule packages that contain custom sensitive information types.</span></span>|
|<span data-ttu-id="497ff-144">La coincidencia de patrones necesita la detección del patrón principal y todas las evidencias complementarias (se usa el operador AND implícito).</span><span class="sxs-lookup"><span data-stu-id="497ff-144">Pattern match requires the detection of the primary pattern and all supporting evidence (the implicit AND operator is used).</span></span>|<span data-ttu-id="497ff-145">La coincidencia de patrones necesita la detección del patrón principal y una cantidad configurable de evidencias complementarias (pueden usarse los operadores AND y OR implícitos).</span><span class="sxs-lookup"><span data-stu-id="497ff-145">Pattern match requires the detection of the primary pattern and a configurable amount of supporting evidence (implicit AND and OR operators can be used).</span></span>|

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="497ff-146">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="497ff-146">What do you need to know before you begin?</span></span>

- <span data-ttu-id="497ff-147">Para abrir el Centro de seguridad y cumplimiento, vea [Ir al Centro de seguridad y cumplimiento](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="497ff-147">To open the Security & Compliance Center, see [Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="497ff-p108">Para usar los tipos personalizados de información confidencial, es necesario estar familiarizado con el uso de expresiones regulares (regex). Para obtener más información sobre el motor Boost.RegEx (anteriormente denominado RegEx++) usado para procesar el texto, vea [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="497ff-p108">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="497ff-p109">Los servicios de soporte técnico y atención al cliente de Microsoft no pueden proporcionarle definiciones personalizadas de coincidencia de contenido (mediante la creación de clasificaciones personalizadas o patrones de expresiones regulares). Los ingenieros de soporte técnico pueden proporcionar soporte limitado para la característica (por ejemplo, pueden proporcionar patrones de expresiones regulares de ejemplo con fines de prueba, o bien ayudarle en la solución de problemas de un patrón de expresión regular existente que no se desencadene del modo previsto), pero no pueden ofrecer garantías de que cualquier desarrollo de coincidencia de contenido personalizado se adapte a sus requisitos u obligaciones.</span><span class="sxs-lookup"><span data-stu-id="497ff-p109">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="497ff-p110">DLP usa el rastreador de búsqueda para identificar y clasificar información confidencial en sitios de SharePoint Online OneDrive para la Empresa. Para identificar el nuevo tipo personalizado de información confidencial en contenido existente, es necesario volver a rastrear el contenido. El contenido se vuelve a rastrear basándose en una programación, pero puede volverlo a rastrear de forma manual para una colección de sitios, una lista o una biblioteca. Para obtener más información, vea [Solicitar de forma manual el rastreo y la nueva indexación de un sitio, biblioteca o lista](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="497ff-p110">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="497ff-156">Crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="497ff-156">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="497ff-157">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="497ff-157">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="497ff-158">Las opciones pueden entenderse fácilmente y se explican en la página asociada del asistente:</span><span class="sxs-lookup"><span data-stu-id="497ff-158">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="497ff-159">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="497ff-159">**Name**</span></span>

- <span data-ttu-id="497ff-160">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="497ff-160">**Description**</span></span>

- <span data-ttu-id="497ff-161">**Proximidad**</span><span class="sxs-lookup"><span data-stu-id="497ff-161">**Proximity**</span></span>

- <span data-ttu-id="497ff-162">**Nivel de confianza**</span><span class="sxs-lookup"><span data-stu-id="497ff-162">**Confidence level**</span></span>

- <span data-ttu-id="497ff-163">**Elemento de patrón principal** (palabras clave, expresión regular o diccionario)</span><span class="sxs-lookup"><span data-stu-id="497ff-163">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="497ff-164">Opcional: **elementos de patrón complementarios** (palabras clave, expresión regular o diccionario) y un valor correspondiente de **Costo mínimo**.</span><span class="sxs-lookup"><span data-stu-id="497ff-164">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="497ff-p111">Imagine el escenario siguiente: quiere usar un tipo personalizado de información confidencial que detecte números de empleado de nueve dígitos en el contenido, así como las palabras clave “id. de empleado” e “identificación”. Para crear este tipo personalizado de información confidencial, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="497ff-p111">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="497ff-167">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="497ff-167">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Ubicación de los tipos de información confidencial y el botón Crear](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="497ff-169">En la página **Seleccionar un nombre y una descripción**, escriba los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="497ff-169">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="497ff-170">**Nombre**: id. de empleado.</span><span class="sxs-lookup"><span data-stu-id="497ff-170">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="497ff-171">**Descripción**: detectar números de id. de empleados de Contoso de nueve dígitos.</span><span class="sxs-lookup"><span data-stu-id="497ff-171">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Página de Nombre y descripción](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="497ff-173">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="497ff-173">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="497ff-174">En la página **Requisitos de coincidencia**, haga clic en **Agregar un elemento** y configure las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="497ff-174">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="497ff-175">**Detectar contenido que contenga**:</span><span class="sxs-lookup"><span data-stu-id="497ff-175">**Detect content containing**:</span></span>
 
      <span data-ttu-id="497ff-p112">a. Haga clic en **Cualquiera de estos** y seleccione **Expresión regular**.</span><span class="sxs-lookup"><span data-stu-id="497ff-p112">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="497ff-p113">b. En el cuadro de expresión regular, escriba `(\s)(\d{9})(\s)` (números de nueve dígitos rodeados por espacios en blanco).</span><span class="sxs-lookup"><span data-stu-id="497ff-p113">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="497ff-180">**Elementos complementarios**: haga clic en **Agregar elementos complementarios** y seleccione **Contiene esta lista de palabras clave**.</span><span class="sxs-lookup"><span data-stu-id="497ff-180">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="497ff-181">En el área **Contiene esta lista de palabras clave**, configure las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="497ff-181">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="497ff-182">**Lista de palabras clave**: escriba el valor “empleado,id.,identificación”.</span><span class="sxs-lookup"><span data-stu-id="497ff-182">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="497ff-183">**Recuento mínimo**: deje el valor predeterminado (1).</span><span class="sxs-lookup"><span data-stu-id="497ff-183">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="497ff-184">No modifique el valor predeterminado de **Nivel de confianza** (60).</span><span class="sxs-lookup"><span data-stu-id="497ff-184">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="497ff-185">No modifique el valor predeterminado de **Proximidad de caracteres** (300).</span><span class="sxs-lookup"><span data-stu-id="497ff-185">Leave the default **Character proximity** value 300.</span></span>

    ![Página Requisitos de coincidencia](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="497ff-187">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="497ff-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="497ff-188">En la página **Revisar y finalizar**, revise la configuración y, después, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="497ff-188">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Página Revisar y finalizar](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="497ff-p114">En la página siguiente, puede probar el nuevo tipo personalizado de información confidencial haciendo clic en **Sí**. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center). Para probar la regla más tarde, haga clic en **No**.</span><span class="sxs-lookup"><span data-stu-id="497ff-p114">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Página de recomendación de prueba](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="497ff-194">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="497ff-194">How do you know this worked?</span></span>

<span data-ttu-id="497ff-195">Para comprobar si un tipo de información confidencial se creó correctamente, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="497ff-195">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="497ff-196">Vaya a **Clasificaciones** \> **Tipos de información confidencial** y asegúrese de que en la lista se muestre el nuevo tipo personalizado de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="497ff-196">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="497ff-p115">Pruebe el nuevo tipo personalizado de información confidencial. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="497ff-p115">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="497ff-199">Modificar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="497ff-199">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="497ff-200">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="497ff-200">**Notes**:</span></span>

- <span data-ttu-id="497ff-p116">Solo se pueden modificar los tipos personalizados de información confidencial; no se pueden modificar los tipos de información confidencial integrados. Pero puede usar PowerShell para exportar los tipos personalizados de información confidencial integrados, personalizarlos y, después, importarlos como tipos personalizados de información confidencial. Para obtener más información, vea [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="497ff-p116">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="497ff-p117">Solo puede modificar los tipos de información confidencial personalizados que creó en la interfaz de usuario. Si ha usado el [procedimiento de PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) para importar un paquete de reglas de tipo de información confidencial, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="497ff-p117">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="497ff-206">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial**, seleccione el tipo personalizado de información confidencial que quiera modificar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="497ff-206">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Ubicación de los tipos de información confidencial y el botón Editar](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="497ff-p118">Verá las mismas opciones disponibles que al crear el tipo personalizado de información confidencial en el Centro de seguridad y cumplimiento. Para obtener más información, vea [Crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="497ff-p118">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="497ff-210">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="497ff-210">How do you know this worked?</span></span>

<span data-ttu-id="497ff-211">Para comprobar si un tipo de información confidencial se modificó correctamente, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="497ff-211">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="497ff-212">Vaya a **Clasificaciones** \> **Tipos de información confidencial** para comprobar las propiedades del tipo personalizado de información confidencial modificado.</span><span class="sxs-lookup"><span data-stu-id="497ff-212">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="497ff-p119">Pruebe el tipo personalizado de información confidencial modificado. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="497ff-p119">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="497ff-215">Quitar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="497ff-215">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="497ff-216">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="497ff-216">**Notes**:</span></span>

- <span data-ttu-id="497ff-217">Solo se pueden quitar los tipos personalizados de información confidencial; no se pueden quitar los tipos de información confidencial integrados.</span><span class="sxs-lookup"><span data-stu-id="497ff-217">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="497ff-218">Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="497ff-218">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="497ff-219">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y seleccione uno o más tipos personalizados de información confidencial que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="497ff-219">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="497ff-220">En el control flotante, haga clic en **Eliminar** (o en **Eliminar tipos de información confidencial**, si seleccionó más de uno).</span><span class="sxs-lookup"><span data-stu-id="497ff-220">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Ubicación de los tipos de información confidencial y el botón Eliminar](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="497ff-222">Haga clic en **Sí** en el mensaje de advertencia que se muestre.</span><span class="sxs-lookup"><span data-stu-id="497ff-222">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="497ff-223">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="497ff-223">How do you know this worked?</span></span>

<span data-ttu-id="497ff-224">Para comprobar si un tipo personalizado de información confidencial se quitó correctamente, vaya a **Clasificaciones** \> **Tipos de información confidencial** y asegúrese de que el tipo personalizado de información confidencial ya no se muestre en la lista.</span><span class="sxs-lookup"><span data-stu-id="497ff-224">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="497ff-225">Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="497ff-225">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="497ff-226">En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="497ff-226">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="497ff-p120">Seleccione uno o más tipos personalizados de información confidencial que quiera probar. En el control flotante que se abra, haga clic en **Probar tipo** (o en **Probar tipos de información confidencial**, si seleccionó un más de uno).</span><span class="sxs-lookup"><span data-stu-id="497ff-p120">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Ubicación de los tipos de información confidencial y el botón Tipo de prueba](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="497ff-230">En la página **Cargar archivo para probar** que se abre, cargue un documento para realizar la prueba (puede arrastrar y colocar un archivo, o bien puede hacer clic en **Examinar** y seleccionar un archivo).</span><span class="sxs-lookup"><span data-stu-id="497ff-230">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Página Cargar archivo para probar](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="497ff-232">Haga clic en el botón **Probar** para probar el documento y ver si hay coincidencias de patrones en el archivo.</span><span class="sxs-lookup"><span data-stu-id="497ff-232">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="497ff-233">En la página **Resultados de la coincidencia**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="497ff-233">On the **Match results** page, click **Finish**.</span></span>

    ![Resultados de la coincidencia](media/scc-cust-sens-info-type-test-results.png)