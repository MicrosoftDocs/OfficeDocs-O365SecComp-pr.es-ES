---
title: Personalizar o crear un nuevo tipo de información confidencial
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Aprenda a modificar o crear nuevos tipos de información confidencial de Office 365 para RGPD.
ms.openlocfilehash: 756c68c2270f010d229c65fe9f9829356b661972
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220140"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a><span data-ttu-id="4898e-103">Personalizar o crear un nuevo tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4898e-103">Customize or create a new sensitive information type</span></span>

<span data-ttu-id="4898e-104">En este artículo se proporcionan tres ejemplos para ilustrar cómo modificar o crear nuevos tipos de información confidencial de Office 365 para RGPD.</span><span class="sxs-lookup"><span data-stu-id="4898e-104">This article provides three examples to demonstrate how to modify or create new Office 365 sensitive information types for GDPR.</span></span>

- <span data-ttu-id="4898e-105">Modificar un tipo de información confidencial existente: número de tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="4898e-105">Modify an existing sensitive information type — EU Debit Card Number</span></span>

- <span data-ttu-id="4898e-106">Crear un nuevo tipo de información confidencial: dirección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="4898e-106">Create a new sensitive information type — email address</span></span>

- <span data-ttu-id="4898e-107">Crear un nuevo tipo de información confidencial con archivo XML de ejemplo: número de cliente de Contoso</span><span class="sxs-lookup"><span data-stu-id="4898e-107">Create a new sensitive information type with example XML file — Contoso customer number</span></span>

<span data-ttu-id="4898e-108">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="4898e-108">Also see:</span></span>

- [<span data-ttu-id="4898e-109">Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="4898e-109">Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [<span data-ttu-id="4898e-110">Personalizar un tipo de información confidencial integrado</span><span class="sxs-lookup"><span data-stu-id="4898e-110">Customize a built-in sensitive information type</span></span>](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a><span data-ttu-id="4898e-111">Modificar un tipo de información confidencial para mejorar la precisión</span><span class="sxs-lookup"><span data-stu-id="4898e-111">Modify a sensitive information type to improve accuracy</span></span>

<span data-ttu-id="4898e-112">Si usa la Búsqueda de contenido para buscar datos personales con tipos de información confidencial y no obtiene los resultados esperados o la búsqueda devuelve demasiados falsos positivos, considere la posibilidad de modificar el tipo de información confidencial para que funcione mejor con su entorno.</span><span class="sxs-lookup"><span data-stu-id="4898e-112">If you’re using Content Search to search for personal data using sensitive information types and you’re not returning the expected results, or the query returns too many false positives, consider modifying the sensitive information type to work better with your environment.</span></span>

<span data-ttu-id="4898e-p101">El procedimiento recomendado al crear o personalizar un tipo de información confidencial es crear un tipo de información confidencial nuevo basado en otro existente, asignándole un nombre e identificadores únicos. Por ejemplo, si desea ajustar los parámetros del tipo de información confidencial "Número de tarjeta de débito de la UE", podría asignar a su copia de la regla el nombre "Tarjeta de débito de la UE mejorada" para distinguirla del original.</span><span class="sxs-lookup"><span data-stu-id="4898e-p101">The best practice when creating or customizing a sensitive information type is to create a new sensitive information type based on an existing one, giving it a unique name and identifiers. For example, if you wish to adjust the parameters of the “EU Debit Card Number” sensitive information type, you could name your copy of that rule “EU Debit Card Enhanced” to distinguish it from the original.</span></span>

<span data-ttu-id="4898e-p102">En el nuevo tipo de información confidencial, simplemente modifique los valores que desea cambiar para mejorar la precisión. Una vez haya terminado, cargue el nuevo tipo de información confidencial y cree una nueva regla DLP (o modifique una existente) para usar el nuevo tipo de información confidencial que acaba de agregar. Pueden ser necesarios varios intentos para modificar la precisión de los tipos de información confidencial, por lo que si conserva una copia del tipo original, podrá volver a él si es necesario en el futuro.</span><span class="sxs-lookup"><span data-stu-id="4898e-p102">In your new sensitive information type, simply modify the values you wish to change to improve its accuracy. Once complete, upload your new sensitive information type and create a new DLP rule (or modify an existing one) to use the new sensitive information type you just added. Modifying the accuracy of sensitive information types might require some trial and error, so maintaining a copy of the original type allows you to fall back to it if required in the future.</span></span>

<span data-ttu-id="4898e-118">Para personalizar un tipo de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="4898e-118">To customize a sensitive information type:</span></span>

1.  <span data-ttu-id="4898e-119">Exporte el paquete de reglas de Microsoft existentes de tipos de información confidencial integradas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4898e-119">Export the existing Microsoft Rule Package of built in sensitive information types in Office 365.</span></span>

2.  <span data-ttu-id="4898e-120">Cambie el nombre de este archivo XML y ábralo en el editor de XML.</span><span class="sxs-lookup"><span data-stu-id="4898e-120">Rename this XML file and open it in your favorite XML editor.</span></span>

3.  <span data-ttu-id="4898e-121">Aísle el tipo de información confidencial y quite todos los demás.</span><span class="sxs-lookup"><span data-stu-id="4898e-121">Isolate the sensitive information type and remove all others.</span></span>

4.  <span data-ttu-id="4898e-122">Use PowerShell para generar dos nuevos GUID para el tipo de información confidencial que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="4898e-122">Use PowerShell to generate two new GUIDs for the sensitive information type you are modifying.</span></span>

5.  <span data-ttu-id="4898e-123">Modificar el Id. y otros elementos básicos para que el tipo de información confidencial sea único (esto incluye reemplazar dos GUID con los nuevos que generó).</span><span class="sxs-lookup"><span data-stu-id="4898e-123">Modify the ID and other basic elements so the sensitive information type is unique (this includes replacing two GUIDs with the new ones you generated).</span></span>

6.  <span data-ttu-id="4898e-124">Ajuste los requisitos de coincidencia para mejorar la precisión.</span><span class="sxs-lookup"><span data-stu-id="4898e-124">Tune the match requirements to improve accuracy.</span></span>

    1.  <span data-ttu-id="4898e-125">Modificaciones de proximidad: modifique la proximidad del patrón de caracteres para ampliar o reducir la ventana en la que deben encontrarse palabras clave por el tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4898e-125">Proximity modifications — Modify the character pattern proximity to expand or shrink the window in which keywords must be found around the sensitive information type.</span></span>

    2.  <span data-ttu-id="4898e-p103">Modificaciones de palabra clave: agregue palabras clave a uno de los elementos \<palabra clave\> para proporcionar al tipo de información confidencial evidencias de corroboración más específicas que debe buscar para señalar una coincidencia en esta regla, o quite palabras clave que causan falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="4898e-p103">Keyword modifications — Add keywords to one of the \<Keywords\> element in order to provide our sensitive information type more specific corroborative evidence to search for in order to signal a match on this rule. Or remove keywords that are causing false positives.</span></span>

    3.  <span data-ttu-id="4898e-128">Modificaciones de confianza: modifique la confianza con la que el tipo de información confidencial debe coincidir con los criterios especificados en la definición antes de que se señale e informe de una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="4898e-128">Confidence modifications — Modify the confidence with which the sensitive information type must match the criteria specified in its definition before a match is signaled and reported.</span></span>

7.  <span data-ttu-id="4898e-129">Cargue el nuevo tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4898e-129">Upload the new sensitive information type.</span></span>

8.  <span data-ttu-id="4898e-p104">Vuelva a rastrear el contenido para identificar la información confidencial. Consulte [Solicitar de forma manual que se rastree y se actualice el índice de un sitio](https://support.office.com/es-ES/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).</span><span class="sxs-lookup"><span data-stu-id="4898e-p104">Recrawl your content to identify the sensitive information. See [Manually request crawling and re-indexing of a site](https://support.office.com/es-ES/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).</span></span>

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a><span data-ttu-id="4898e-132">Ejemplo: modificar el tipo de información confidencial “número de tarjeta de débito de la UE”</span><span class="sxs-lookup"><span data-stu-id="4898e-132">Example: modify the ‘EU Debit Card Number’ sensitive information type</span></span>

<span data-ttu-id="4898e-p105">Mejorar la precisión de reglas DLP en todos los sistemas necesita pruebas con un conjunto de datos de ejemplo y puede requerir de ajustes mediante pruebas y modificaciones repetitivas. Este ejemplo muestra las modificaciones al tipo de información confidencial "Número de tarjeta de débito de la UE" para mejorar su precisión.</span><span class="sxs-lookup"><span data-stu-id="4898e-p105">Improving the accuracy of DLP rules in any system requires testing against a sample data set, and may require fine tuning through repetitive modifications and tests. This example demonstrates modifications to the ‘EU Debit Card Number’ sensitive information type to improve its accuracy.</span></span>

<span data-ttu-id="4898e-p106">Al buscar un número de tarjeta de débito de la UE en nuestro ejemplo, ese números e define estrictamente como 16 dígitos con un patrón complejo y está sujeto a la validación de la suma de comprobación. No se puede modificar este modelo debido a la definición de cadena del tipo de información confidencial. Sin embargo, pueden hacerse los siguientes ajustes para mejorar la precisión de la forma en que la DLP de Office 365 busca este tipo de información confidencial en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4898e-p106">When searching for an EU Debit Card Number in our example, the definition of that number is strictly defined as 16 digits using a complex pattern, and being subject to the validation of a checksum. We cannot alter this pattern due to the string definition of this sensitive information type. However, we can make the following adjustments to improve the accuracy of how Office 365 DLP finds this sensitive information type within Office 365.</span></span>

### <a name="proximity-modification"></a><span data-ttu-id="4898e-138">Modificación de proximidad</span><span class="sxs-lookup"><span data-stu-id="4898e-138">Proximity modification</span></span>

<span data-ttu-id="4898e-p107">Reduciremos la ventana modificando el valor patternProximity en el elemento \<Entidad\> de 300 a 150 caracteres. Esto significa que la evidencia de corroboración, o las palabras clave, deben estar más cerca de nuestro tipo de información confidencial para señalar a una coincidencia con esta regla.</span><span class="sxs-lookup"><span data-stu-id="4898e-p107">We'll shrink the window by modifying the patternProximity value in our \<Entity\> element from 300 to 150 characters. This means that our corroborative evidence, or our keywords, must be closer to our sensitive information type in order to signal a match on this rule.</span></span>

<span data-ttu-id="4898e-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="4898e-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

### <a name="keyword-modifications"></a><span data-ttu-id="4898e-142">Modificaciones de palabras clave</span><span class="sxs-lookup"><span data-stu-id="4898e-142">Keyword modifications</span></span>

<span data-ttu-id="4898e-p108">Algunas palabras clave podrían provocar falsos positivos. Así pues, es posible que desee quitar palabras clave. Estas son las palabras clave en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4898e-p108">Some keywords might cause false positives to occur. As a result you might want to remove keywords. Here are the keywords for this example::</span></span>

<span data-ttu-id="4898e-146">\<Keyword id="palabra clave\_tarjeta\_términos\_dict"\></span><span class="sxs-lookup"><span data-stu-id="4898e-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span></span>

<span data-ttu-id="4898e-147">\<Group\></span><span class="sxs-lookup"><span data-stu-id="4898e-147">\<Group\></span></span>

<span data-ttu-id="4898e-148">\<Term\>tarjeta corporativa\</Term\></span><span class="sxs-lookup"><span data-stu-id="4898e-148">\<Term\>corporate card\</Term\></span></span>

<span data-ttu-id="4898e-149">\<Term\>tarjeta de la organización\</Term\></span><span class="sxs-lookup"><span data-stu-id="4898e-149">\<Term\>organization card\</Term\></span></span>

<span data-ttu-id="4898e-150">\<Term\>n.º de cuenta\</Term\></span><span class="sxs-lookup"><span data-stu-id="4898e-150">\<Term\>acct nbr\</Term\></span></span>

<span data-ttu-id="4898e-151">\<Term\>núm. de cuenta\</Term\></span><span class="sxs-lookup"><span data-stu-id="4898e-151">\<Term\>acct num\</Term\></span></span>

<span data-ttu-id="4898e-152">\<Term\>nº de cuenta\</Term\></span><span class="sxs-lookup"><span data-stu-id="4898e-152">\<Term\>acct no\</Term\></span></span>

<span data-ttu-id="4898e-153">…</span><span class="sxs-lookup"><span data-stu-id="4898e-153">…</span></span>

<span data-ttu-id="4898e-154">\</Group\></span><span class="sxs-lookup"><span data-stu-id="4898e-154">\</Group\></span></span>

<span data-ttu-id="4898e-155">\</Keyword\></span><span class="sxs-lookup"><span data-stu-id="4898e-155">\</Keyword\></span></span>

### <a name="confidence-modifications"></a><span data-ttu-id="4898e-156">Modificaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="4898e-156">Confidence modifications</span></span>

<span data-ttu-id="4898e-p109">Si quita palabras clave de la definición, normalmente querrá ajustar el nivel de confianza que tiene en que se ha encontrado este tipo de información confidencial reduciendo este valor. El nivel predeterminado del tipo número de tarjeta de débito de la UE es 85.</span><span class="sxs-lookup"><span data-stu-id="4898e-p109">If you remove keywords from the definition, you would typically want to adjust how confident you are that this sensitive information type was found by lowering this value. The default level for EU Debit Card Number type is 85.</span></span>

<span data-ttu-id="4898e-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="4898e-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

<span data-ttu-id="4898e-160">\<Pattern confidenceLevel= "85"\></span><span class="sxs-lookup"><span data-stu-id="4898e-160">\<Pattern confidenceLevel="85"\></span></span>

<span data-ttu-id="4898e-161">…</span><span class="sxs-lookup"><span data-stu-id="4898e-161">…</span></span>

<span data-ttu-id="4898e-162">\</Pattern\></span><span class="sxs-lookup"><span data-stu-id="4898e-162">\</Pattern\></span></span>

<span data-ttu-id="4898e-163">\</Entity\></span><span class="sxs-lookup"><span data-stu-id="4898e-163">\</Entity\></span></span>

## <a name="create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="4898e-164">Crear un nuevo tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4898e-164">Create a new custom sensitive information type</span></span>

<span data-ttu-id="4898e-165">Para crear un nuevo tipo de información confidencial, empiece con una búsqueda de contenido para:</span><span class="sxs-lookup"><span data-stu-id="4898e-165">To create a new custom sensitive information type, start by using Content Search to:</span></span>

-   <span data-ttu-id="4898e-166">Optimizar una consulta KQL</span><span class="sxs-lookup"><span data-stu-id="4898e-166">Optimize a KQL query</span></span>

-   <span data-ttu-id="4898e-167">Ver que palabras clave son más útiles</span><span class="sxs-lookup"><span data-stu-id="4898e-167">See which keywords are most useful</span></span>

<span data-ttu-id="4898e-p110">Utilice los resultados para crear un nuevo tipo de información confidencial. Optimice el nuevo tipo de información confidencial en su entorno.</span><span class="sxs-lookup"><span data-stu-id="4898e-p110">Use these results to create a new sensitive information type. Then optimize the new sensitive information type for your environment.</span></span>

<span data-ttu-id="4898e-p111">Nota: Próximamente se añadirán muchos nuevos tipos de información confidencial para datos personales de países de la UE. Si necesita crear nuevos tipos de información confidencial, comience por datos personalizados para su entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="4898e-p111">Note: Many new sensitive information types are coming soon for personal data in EU countries. If you need to create new sensitive information types, begin by targeting data that is custom to your environment.</span></span>

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a><span data-ttu-id="4898e-172">Paso 1: Use palabras clave y consultas KQL para buscar datos adicionales en su entorno</span><span class="sxs-lookup"><span data-stu-id="4898e-172">Step 1 — Use KQL queries and key words to find additional data in your environment</span></span>

<span data-ttu-id="4898e-p112">Es posible que deba crear consultas adicionales para buscar datos personales que están sujeta al RGPD. La Búsqueda de contenido usa el lenguaje de consulta de palabras clave (KQL) para buscar datos. La mayoría de la información confidencial no se detecta con precisión solo con KQL sin tipos de información confidencial. Por lo tanto, el objetivo es probar y optimizar las cadenas KQL con la Búsqueda de contenido y después usarlas para crear y ajustar los nuevos tipos de información confidencial que pueden proporcionar mayor precisión.</span><span class="sxs-lookup"><span data-stu-id="4898e-p112">You might need to create additional queries to find personal data that is subject to GDPR. Content Search uses Keyword Query Language (KQL) to find data. Most sensitive data can’t be accurately detected using just KQL without sensitive information types. So the goal is to test and optimize KQL strings using Content Search and then use these to create and tune new sensitive information types where you can achieve even greater accuracy.</span></span>

<span data-ttu-id="4898e-177">Use estos recursos para formular y optimizar consultas con KQL:</span><span class="sxs-lookup"><span data-stu-id="4898e-177">Use these resources to formulate and optimize queries using KQL:</span></span>

-   [<span data-ttu-id="4898e-178">Referencia de la sintaxis del lenguaje de consultas de palabras clave (KQL) (DMC)</span><span class="sxs-lookup"><span data-stu-id="4898e-178">Keyword Query Language (KQL) syntax reference (DMC)</span></span>](https://docs.microsoft.com/es-ES/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

-   [<span data-ttu-id="4898e-179">Ejecutar una búsqueda de contenido en el Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="4898e-179">Run a Content Search in the Office 365 Security & Compliance Center</span></span>](https://support.office.com/es-ES/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) 

<span data-ttu-id="4898e-p113">La Búsqueda de contenido proporciona otro recurso para ayudarle a desarrollar consultas KQL y tipos de información confidencial: palabras clave. ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente qué palabras clave son las más (y menos) eficaces. Para obtener más información acerca de las estadísticas de búsqueda, consulte [Ver las estadísticas de palabra clave de resultados de búsqueda de contenido](https://support.office.com/es-ES/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).</span><span class="sxs-lookup"><span data-stu-id="4898e-p113">Content Search provides another resource to help you develop KQL queries and sensitive information types — keywords. Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. For more information about search statistics, see [View keyword statistics for Content Search results](https://support.office.com/es-ES/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).</span></span>

<span data-ttu-id="4898e-p114">Las palabras clave en cada fila están conectadas mediante el operador O en la consulta de búsqueda que se crea. También puede usar una frase de palabras clave (entre paréntesis) en una fila.</span><span class="sxs-lookup"><span data-stu-id="4898e-p114">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span>

<span data-ttu-id="4898e-187">Para obtener más información, consulte [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](https://support.office.com/es-ES/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).</span><span class="sxs-lookup"><span data-stu-id="4898e-187">For more information, see [Keyword queries and search conditions for Content Search](https://support.office.com/es-ES/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).</span></span>

### <a name="exampleusing-content-search-to-identify-email-addresses"></a><span data-ttu-id="4898e-188">Ejemplo: usar la Búsqueda de contenido para identificar direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="4898e-188">Example—Using Content Search to identify email addresses</span></span>

<span data-ttu-id="4898e-p115">Se considera que las direcciones de correo electrónico son información confidencial relacionada con temas de datos. Este es un ejemplo sencillo para demostrar cómo puede ayudar Búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="4898e-p115">Email addresses are considered sensitive information related to data subjects. This is a simple example to demonstrate how Content Search can help.</span></span>

<span data-ttu-id="4898e-p116">No se pueden usar conjuntamente KQL y palabras clave. Use estas herramientas por separado para afinar la consulta y determinar las palabras clave que pueden ser útiles en los tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4898e-p116">KQL and keywords can’t be used together. Use these tools separately to hone your query and determine keywords that might be useful in sensitive information types.</span></span>

### <a name="kql-query"></a><span data-ttu-id="4898e-193">Consulta KQL</span><span class="sxs-lookup"><span data-stu-id="4898e-193">KQL query</span></span>

<span data-ttu-id="4898e-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span><span class="sxs-lookup"><span data-stu-id="4898e-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span></span>

<span data-ttu-id="4898e-195">Notas:</span><span class="sxs-lookup"><span data-stu-id="4898e-195">Notes:</span></span>

-   <span data-ttu-id="4898e-196">Puede usar CERCA y OCERCA para búsquedas de proximidad.</span><span class="sxs-lookup"><span data-stu-id="4898e-196">You can use NEAR and ONEAR for proximity searches.</span></span>

-   <span data-ttu-id="4898e-197">Desafortunadamente, KQL no admite consultas con la clase Regex (por ejemplo: IdRef = "Regex\_dirección\_de correo")</span><span class="sxs-lookup"><span data-stu-id="4898e-197">Unfortunately, KQL doesn’t support queries with the Regex Class (ex: IdRef="Regex\_email\_address")</span></span>

### <a name="keywords"></a><span data-ttu-id="4898e-198">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4898e-198">Keywords</span></span>

<span data-ttu-id="4898e-p117">Escriba cada palabra clave en una línea independiente. Palabras clave de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4898e-p117">Enter each keyword on a separate line. Example keywords:</span></span>

-   <span data-ttu-id="4898e-201">dirección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="4898e-201">email address</span></span>

-   <span data-ttu-id="4898e-202">correo</span><span class="sxs-lookup"><span data-stu-id="4898e-202">mail</span></span>

-   <span data-ttu-id="4898e-203">contacto</span><span class="sxs-lookup"><span data-stu-id="4898e-203">contact</span></span>

-   <span data-ttu-id="4898e-204">remitente</span><span class="sxs-lookup"><span data-stu-id="4898e-204">sender</span></span>

-   <span data-ttu-id="4898e-205">destinatario</span><span class="sxs-lookup"><span data-stu-id="4898e-205">recipient</span></span>

-   <span data-ttu-id="4898e-206">cc</span><span class="sxs-lookup"><span data-stu-id="4898e-206">cc</span></span>

-   <span data-ttu-id="4898e-207">cco</span><span class="sxs-lookup"><span data-stu-id="4898e-207">bcc</span></span>

<span data-ttu-id="4898e-208">En este ejemplo, es posible que descubra que las palabras clave no son necesarias y generan una gran cantidad de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="4898e-208">In this example, you might learn the keywords are not necessary and produce a lot of false positive results.</span></span>

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="4898e-209">Paso 2: Crear un nuevo tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4898e-209">Step 2 — Create a new custom sensitive information type</span></span>

<span data-ttu-id="4898e-p118">Después de usar consultas KQL y palabras clave para identificar información confidencial, úselas para crear nuevos tipos de información confidencial. En muchos casos, necesitará la sofisticación de los tipos de información confidencial para alcanzar el nivel correcto de precisión. Después puede usar estos tipos de información confidencial con la Búsqueda de contenido, en las directivas DLP y otras herramientas y en otras consultas KQL.</span><span class="sxs-lookup"><span data-stu-id="4898e-p118">After using KQL queries and keywords to identify sensitive information, use these to create new custom sensitive information types. In many cases, you’ll require the sophistication of sensitive information types to achieve the right level of accuracy. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span>

<span data-ttu-id="4898e-p119">El procedimiento recomendado es crear un nuevo tipo de información confidencial basado en otro existente. Use el mismo proceso descrito anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="4898e-p119">The best practice is to create a new sensitive information type based on an existing one. Use the same process described earlier in this article.</span></span>

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a><span data-ttu-id="4898e-215">Ejemplo: Crear un nuevo tipo de información confidencial para: direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="4898e-215">Example — Create a new sensitive information for email addresses</span></span> 

<span data-ttu-id="4898e-p120">Seguiremos con la dirección de correo electrónico como ejemplo porque es sencillo. En la siguiente tabla se detallan las modificaciones que se recomiendan para un nuevo tipo de información confidencial de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4898e-p120">We’ll continue with the email address as an example because it’s simple. The following table details the modifications recommended for a new email sensitive information type.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4898e-218"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="4898e-218"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="4898e-219"><strong>Modificación</strong></span><span class="sxs-lookup"><span data-stu-id="4898e-219"><strong>Modification </strong></span></span></th>
<th align="left"><span data-ttu-id="4898e-220"><strong>Sintaxis XML de ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="4898e-220"><strong>Example XML syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4898e-221">1</span><span class="sxs-lookup"><span data-stu-id="4898e-221">1</span></span></td>
<td align="left"><span data-ttu-id="4898e-222">Establezca la propiedad IdRef</span><span class="sxs-lookup"><span data-stu-id="4898e-222">Set the IdRef property</span></span>
<p><span data-ttu-id="4898e-p121">En el elemento &lt;Entidad&gt;, modifique el elemento &lt;IdMatch&gt; para que su propiedad idRef sea igual a un valor único. Este valor apuntará a un elemento que define la expresión regular para buscar direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4898e-p121">Within the &lt;Entity&gt; element, modify the &lt;IdMatch&gt; element so that its idRef property is = to a unique value. This value will point to an element that defines our regular expression to find email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="4898e-225">IdRef=&quot;Regex_email_address&quot;</span><span class="sxs-lookup"><span data-stu-id="4898e-225">IdRef=&quot;Regex_email_address&quot;</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4898e-226">2</span><span class="sxs-lookup"><span data-stu-id="4898e-226">2</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-227">Atributo de proximidad</span><span class="sxs-lookup"><span data-stu-id="4898e-227">Proximity attribute</span></span></p>
<p><span data-ttu-id="4898e-228">Empezaremos con un valor patternProximity en el elemento &lt;Entidad&gt; de 300.</span><span class="sxs-lookup"><span data-stu-id="4898e-228">We'll start with a patternProximity value in our &lt;Entity&gt; element of 300.</span></span></p></td>
<td align="left"><span data-ttu-id="4898e-229">patternsProximity=&quot;300&quot;</span><span class="sxs-lookup"><span data-stu-id="4898e-229">patternsProximity=&quot;300&quot;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4898e-230">3</span><span class="sxs-lookup"><span data-stu-id="4898e-230">3</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-231">Nivel de confianza</span><span class="sxs-lookup"><span data-stu-id="4898e-231">Confidence level</span></span></p>
<p><span data-ttu-id="4898e-p122">Establezca la propiedad recommendedConfidence en un valor que sienta que representará la confianza de encontrar una coincidencia exacta. Probablemente esto requiera realizar pruebas con un conjunto de datos representativo para obtener un resultado exacto. Como una configuración inicial, establezca este valor en 75.</span><span class="sxs-lookup"><span data-stu-id="4898e-p122">Set the recommendedConfidence property to a value you feel will represent the confidence of finding an accurate match. This will likely require testing with a representative data set to get an accurate result. As an initial setting, set this value to 75.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4898e-235">recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-235">recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="4898e-236">El XML resultante de estos tres primeros elementos combinado tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4898e-236">The resulting XML for these first three elements combined looks like this:</span></span></p>
<p><span data-ttu-id="4898e-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="4898e-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="4898e-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span></span></p>
<p><span data-ttu-id="4898e-240">&lt;Any minMatches=&quot;1&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-240">&lt;Any minMatches=&quot;1&quot;&gt;</span></span></p>
<p><span data-ttu-id="4898e-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span></span></p>
<p><span data-ttu-id="4898e-242">&lt;/Any&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-242">&lt;/Any&gt;</span></span></p>
<p><span data-ttu-id="4898e-243">&lt;/Pattern&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-243">&lt;/Pattern&gt;</span></span></p>
<p><span data-ttu-id="4898e-244">&lt;/Entity&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-244">&lt;/Entity&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4898e-245">4</span><span class="sxs-lookup"><span data-stu-id="4898e-245">4</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-246">Elemento Regex</span><span class="sxs-lookup"><span data-stu-id="4898e-246">Regex element</span></span></p>
<p><span data-ttu-id="4898e-247">Agregue un nuevo elemento &lt;Regex&gt; situado inmediatamente por debajo del elemento &lt;Entidad&gt; que defina la expresión regular que se usa para identificar la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4898e-247">Add a new &lt;Regex&gt; element immediately be below the &lt;Entity&gt; elements that defines the regular expression used to identify email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="4898e-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4898e-249">5</span><span class="sxs-lookup"><span data-stu-id="4898e-249">5</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-250">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4898e-250">Keywords</span></span></p>
<p><span data-ttu-id="4898e-p123">Agregue un nuevo elemento &lt;Palabra clave&gt; después del elemento &lt;Regex&gt; que defina la lista de direcciones de correo electrónico. Asegúrese de que el valor de Id. del elemento &lt;Palabra clave&gt; coincida con el valor &lt;Match idRef&gt; el elemento &lt;Entity&gt;&lt;Pattern&gt;. Puede seguir agregando sus propias palabras clave si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4898e-p123">Add a new &lt;Keyword&gt; element below the &lt;Regex&gt; element that defines list of email address related keywords. Ensure that the id value for the &lt;Keyword&gt; element matches the &lt;Match idRef&gt; value in the &lt;Entity&gt;&lt;Pattern&gt; element. You may continue to add your own keywords if needed.</span></span></p>
<p><span data-ttu-id="4898e-p124">Es probable que no sea necesario que las palabras clave se incluyan en un tipo de información confidencial de correo electrónico. Estas se proporcionan como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4898e-p124">Keywords are likely not necessary to include in an email sensitive information type. These are provided as an example.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4898e-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span></span></p>
<p><span data-ttu-id="4898e-257">&lt;Group&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-257">&lt;Group&gt;</span></span></p>
<p><span data-ttu-id="4898e-258">&lt;Term&gt;correo electrónico&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-258">&lt;Term&gt;email&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="4898e-259">&lt;Term&gt;dirección de correo electrónico&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-259">&lt;Term&gt;email address&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="4898e-260">&lt;Term&gt;contacto&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-260">&lt;Term&gt;contact&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="4898e-261">&lt;/Group&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-261">&lt;/Group&gt;</span></span></p>
<p><span data-ttu-id="4898e-262">&lt;/Keyword&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-262">&lt;/Keyword&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4898e-263">6</span><span class="sxs-lookup"><span data-stu-id="4898e-263">6</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-264">Elemento LocalizedStrings</span><span class="sxs-lookup"><span data-stu-id="4898e-264">LocalizedStrings element</span></span></p>
<p><span data-ttu-id="4898e-265">En el elemento &lt;LocalizedStrings&gt;&lt;Resource&gt; asegúrese de que tiene un nombre único que identifica el tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4898e-265">In the &lt;LocalizedStrings&gt;&lt;Resource&gt; element ensure that you have a unique name that identifies your sensitive information type.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4898e-266">&lt;LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-266">&lt;LocalizedStrings&gt;</span></span></p>
<p><span data-ttu-id="4898e-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span></span></p>
<p><span data-ttu-id="4898e-268">&lt;Name default=&quot;true&quot; langcode=&quot;es-es&quot;&gt;Dirección de correo electrónico&lt;/Name&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span></span></p>
<p><span data-ttu-id="4898e-269">&lt;Description default=&quot;true&quot; langcode=&quot;es-es&quot;&gt;Detecta direcciones de correo electrónico.&lt;/Description&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span></span></p>
<p><span data-ttu-id="4898e-270">&lt;/Resource&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-270">&lt;/Resource&gt;</span></span></p>
<p><span data-ttu-id="4898e-271">&lt;/LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="4898e-271">&lt;/LocalizedStrings&gt;</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a><span data-ttu-id="4898e-272">Crear un nuevo tipo de información confidencial con PowerShell y archivo XML de ejemplo: número de cliente de Contoso</span><span class="sxs-lookup"><span data-stu-id="4898e-272">Create a new sensitive information type with example PowerShell and XML file — Contoso customer number</span></span>

<span data-ttu-id="4898e-p125">Contoso usa un número de clientes de Contoso (CCN) para identificar a cada cliente en la base de datos de cliente. Un CCN consta de la siguiente taxonomía:</span><span class="sxs-lookup"><span data-stu-id="4898e-p125">Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following taxonomy:</span></span>

-   <span data-ttu-id="4898e-p126">Dos dígitos para representar el año en que se creó el registro. Contoso fue fundado en 2002, por lo tanto, el valor mínimo posible sería 02.</span><span class="sxs-lookup"><span data-stu-id="4898e-p126">Two digits to represent the year that the record was created. Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>

-   <span data-ttu-id="4898e-p127">Tres dígitos para representar la agencia asociada que creó el registro. Los posibles valores de agencia están comprendidos entre 000 y 999.</span><span class="sxs-lookup"><span data-stu-id="4898e-p127">Three digits to represent the partner agency that created the record. Possible agency values range from 000 to 999.</span></span>

-   <span data-ttu-id="4898e-p128">Un carácter alfa para representar la línea de negocio. Los valores posibles son a-z y debe distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4898e-p128">An alpha character to represent the line of business. Possible values are a-z and should be case insensitive.</span></span>

-   <span data-ttu-id="4898e-p129">Un número de serie de cuatro dígitos. Los posibles valores de número de serie están comprendidos entre 0000 y 9999.</span><span class="sxs-lookup"><span data-stu-id="4898e-p129">A four-digit serial number. Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="4898e-283">CNN de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4898e-283">Example CCNs:</span></span>

> <span data-ttu-id="4898e-284">15080P9562</span><span class="sxs-lookup"><span data-stu-id="4898e-284">15080P9562</span></span>
>
> <span data-ttu-id="4898e-285">14040O1119</span><span class="sxs-lookup"><span data-stu-id="4898e-285">14040O1119</span></span>
>
> <span data-ttu-id="4898e-286">15020J8317</span><span class="sxs-lookup"><span data-stu-id="4898e-286">15020J8317</span></span>
>
> <span data-ttu-id="4898e-287">14050E2330</span><span class="sxs-lookup"><span data-stu-id="4898e-287">14050E2330</span></span>
>
> <span data-ttu-id="4898e-288">16050E2166</span><span class="sxs-lookup"><span data-stu-id="4898e-288">16050E2166</span></span>
>
> <span data-ttu-id="4898e-289">17040O1118</span><span class="sxs-lookup"><span data-stu-id="4898e-289">17040O1118</span></span>

<span data-ttu-id="4898e-290">Contoso siempre hace referencia a los clientes utilizando un CCN en la correspondencia interna, la correspondencia externa, los documentos, etc. Les gustaría crear un tipo de información confidencial para detectar el uso de CCN en Office 365 para poder aplicar protección al uso de esta forma de datos personales.</span><span class="sxs-lookup"><span data-stu-id="4898e-290">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, etc. They would like to create a custom sensitive information type to detect the use of CCN in Office 365 so that they may apply protection to the use of this form of personal data.</span></span>

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a><span data-ttu-id="4898e-291">Crear un nuevo tipo de información confidencial para el número de cliente de Contoso</span><span class="sxs-lookup"><span data-stu-id="4898e-291">Create a new sensitive information type for Contoso customer number</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4898e-292"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="4898e-292"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="4898e-293"><strong>Acción</strong></span><span class="sxs-lookup"><span data-stu-id="4898e-293"><strong>Action </strong></span></span></th>
<th align="left"><span data-ttu-id="4898e-294"><strong>Resultado</strong></span><span class="sxs-lookup"><span data-stu-id="4898e-294"><strong>Result</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4898e-295">1</span><span class="sxs-lookup"><span data-stu-id="4898e-295">1</span></span></td>
<td align="left"><span data-ttu-id="4898e-296">Contoso usa PowerShell y Búsqueda de contenido para buscar documentos que coinciden con un conjunto de ejemplo de CCN.</span><span class="sxs-lookup"><span data-stu-id="4898e-296">Contoso uses PowerShell and Content Search to find documents that match an example set of CCNs.</span></span></td>
<td align="left">

<p><span data-ttu-id="4898e-297">#Conectar al Centro de seguridad y &amp; cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="4898e-297">#Connect to Office 365 Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="4898e-298">$adminUser = &quot;juanc@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="4898e-298">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="4898e-299">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="4898e-299">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="4898e-300">#Crear &amp; iniciar una búsqueda de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4898e-300">#Create &amp; start search for sample data</span></span></p>
<p><span data-ttu-id="4898e-301">$searchName = &quot;Búsqueda de información de cliente de ejemplo&quot;</span><span class="sxs-lookup"><span data-stu-id="4898e-301">$searchName = &quot;Sample Customer Information Search&quot;</span></span></p>
<p><span data-ttu-id="4898e-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span><span class="sxs-lookup"><span data-stu-id="4898e-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span></span></p>
<p><span data-ttu-id="4898e-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span><span class="sxs-lookup"><span data-stu-id="4898e-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span></span></p>
<p><span data-ttu-id="4898e-304">Start-ComplianceSearch -Identity $searchName</span><span class="sxs-lookup"><span data-stu-id="4898e-304">Start-ComplianceSearch -Identity $searchName</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4898e-305">2</span><span class="sxs-lookup"><span data-stu-id="4898e-305">2</span></span></td>
<td align="left"><span data-ttu-id="4898e-p130">Contoso analiza los resultados. Cada vez que se usó el CCN, se usó una fecha con formato de la UE y también se usaron alguna de estas palabras clave en una proximidad de 300 caracteres.</span><span class="sxs-lookup"><span data-stu-id="4898e-p130">Contoso analyzes the results. Every time the CCN was used, an EU formatted date was used and one of these keywords were also used within a proximity of 300 characters.</span></span></td>
<td align="left"><span data-ttu-id="4898e-308">número de cliente, nº de cliente, # de cliente, #cliente, cliente de Contoso</span><span class="sxs-lookup"><span data-stu-id="4898e-308">customer number, customer no, customer #, customer#, Contoso customer</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4898e-309">3</span><span class="sxs-lookup"><span data-stu-id="4898e-309">3</span></span></td>
<td align="left"><span data-ttu-id="4898e-310">Contoso desarrollo el siguiente patrón de expresiones regulares (RegEx) para identificar sus CCN.</span><span class="sxs-lookup"><span data-stu-id="4898e-310">Contoso developed the following Regular Expression (RegEx) pattern to identify their CCN.</span></span></td>
<td align="left"><span data-ttu-id="4898e-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="4898e-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4898e-312">4</span><span class="sxs-lookup"><span data-stu-id="4898e-312">4</span></span></td>
<td align="left"><span data-ttu-id="4898e-313">Contoso desarrolló el siguiente patrón de expresiones regulares (RegEx) para identificar las fechas de la UE en los formatos utilizados por sus diferentes filiales.</span><span class="sxs-lookup"><span data-stu-id="4898e-313">Contoso developed the following Regular Expression (RegEx) pattern to identify EU dates in the formats used by their various subsidiaries.</span></span></td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4898e-314">5</span><span class="sxs-lookup"><span data-stu-id="4898e-314">5</span></span></td>
<td align="left"><span data-ttu-id="4898e-315">Contoso usa PowerShell para generar los tres GUID únicos.</span><span class="sxs-lookup"><span data-stu-id="4898e-315">Contoso uses PowerShell to generate three unique GUIDs.</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-316">#Generar un GUID único para el Id. de RulePack, el Id. de Publisher y el Id. de Entidad</span><span class="sxs-lookup"><span data-stu-id="4898e-316">#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</span></span></p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4898e-317">6</span><span class="sxs-lookup"><span data-stu-id="4898e-317">6</span></span></td>
<td align="left"><span data-ttu-id="4898e-318">Contoso define los siguientes parámetros para la regla de tipo de elemento confidencial.</span><span class="sxs-lookup"><span data-stu-id="4898e-318">Contoso defines the following parameters for their sensitive item type rule.</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-319">Nombre: Número de cliente de Contoso (CCN)</span><span class="sxs-lookup"><span data-stu-id="4898e-319">Name: Contoso Customer Number (CCN)</span></span></p>
<p><span data-ttu-id="4898e-320">Descripción: Número de cliente de Contoso (CCN) que busca palabras clave adicionales y fechas con formato de la UE</span><span class="sxs-lookup"><span data-stu-id="4898e-320">Description: Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4898e-321">7</span><span class="sxs-lookup"><span data-stu-id="4898e-321">7</span></span></td>
<td align="left"><span data-ttu-id="4898e-322">Contoso crea un archivo XML para un nuevo tipo de información confidencial para detectar un número de cliente de Contoso (CCN) y lo guarda en un sistema de archivos local como C:\Scripts\ContosoCCN.xml con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4898e-322">Contoso creates an XML file for a new sensitive information type to detect a Contoso Customer Number (CCN) and saves this to a local file system as C:\Scripts\ContosoCCN.xml in with UTF-8 encoding.</span></span></td>
<td align="left"><span data-ttu-id="4898e-323">Consulte el archivo XML después de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="4898e-323">See the XML file below this table.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4898e-324">8</span><span class="sxs-lookup"><span data-stu-id="4898e-324">8</span></span></td>
<td align="left"><span data-ttu-id="4898e-325">Contoso crea el tipo de información confidencial con el siguiente PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4898e-325">Contoso creates the custom sensitive information type with the following PowerShell.</span></span></td>
<td align="left"><p><span data-ttu-id="4898e-326">#Conectar al Centro de seguridad y &amp; cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="4898e-326">#Connect to Office 365 Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="4898e-327">$adminUser = &quot;juanc@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="4898e-327">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="4898e-328">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="4898e-328">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="4898e-329">#Crear el nuevo tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4898e-329">#Create new Sensitive Information Type</span></span></p>
<p><span data-ttu-id="4898e-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span><span class="sxs-lookup"><span data-stu-id="4898e-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a><span data-ttu-id="4898e-331">Archivo XML de ejemplo para el nuevo tipo de información confidencial (paso 7)</span><span class="sxs-lookup"><span data-stu-id="4898e-331">Example XML file for the new sensitive information type (step 7)</span></span>
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
