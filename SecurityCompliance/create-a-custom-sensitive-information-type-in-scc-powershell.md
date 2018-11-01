---
title: Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento de Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 82c382a5-b6db-44fd-995d-b333b3c7fc30
description: Aprenda a crear e importar un tipo de información confidencial personalizada para DLP en el Centro de seguridad y cumplimiento de Office 365.
ms.openlocfilehash: 46e3e0cc502eb6135e18c30df3d96ec2e083b54c
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "25866060"
---
# <a name="create-a-custom-sensitive-information-type-in-office-365-security--compliance-center-powershell"></a><span data-ttu-id="80864-103">Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="80864-103">Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="80864-p101">La función Prevención de pérdida de datos (DLP) de Office 365 incluye distintos [tipos de información confidencial](what-the-sensitive-information-types-look-for.md) preparados para usarlos en directivas DLP. Estos tipos integrados pueden ayudarle a identificar y proteger números de tarjetas de crédito, cuentas bancarias, pasaportes y mucho más.</span><span class="sxs-lookup"><span data-stu-id="80864-p101">Data loss prevention (DLP) in Office 365 includes many [sensitive information types](what-the-sensitive-information-types-look-for.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 
  
<span data-ttu-id="80864-p102">Sin embargo, si tiene que identificar y proteger otro tipo de información confidencial (por ejemplo, un id. de empleado que usa un formato específico de su organización), puede crear un tipo personalizado de información confidencial. Los tipos de información confidencial se definen en un archivo XML denominado _paquete de reglas_.</span><span class="sxs-lookup"><span data-stu-id="80864-p102">But if you need to identify and protect a different type of sensitive information - for example, an employee ID that uses a format specific to your organization - you can create a custom sensitive information type. A sensitive information type is defined in an XML file called a rule package.</span></span>
  
<span data-ttu-id="80864-p103">En este tema, se muestra cómo crear un archivo XML donde se define su propio tipo personalizado de información confidencial. Necesita saber cómo crear una expresión regular. Por ejemplo, en este tema se crea un tipo personalizado de información confidencial que identifica un id. de empleado. Puede usar este XML de ejemplo como punto de inicio para crear su propio archivo XML.</span><span class="sxs-lookup"><span data-stu-id="80864-p103">This topic shows you how to create an XML file that defines your own custom sensitive information type. You need to know how to create a regular expression. As an example, this topic creates a custom sensitive information type that identifies an employee ID. You can use this example XML as a starting point for your own XML file.</span></span>
  
<span data-ttu-id="80864-p104">Después de crear un archivo XML con formato correcto, puede cargarlo en Office 365 mediante PowerShell de Office 365. Después, ya estará listo para usar su propio tipo personalizado de información confidencial en sus directivas DLP y comprobar si detecta la información confidencial del modo previsto.</span><span class="sxs-lookup"><span data-stu-id="80864-p104">After you've created a well-formed XML file, you can upload it to Office 365 by using PowerShell. Then you're ready to use your custom sensitive information type in your DLP policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="80864-p105">También puede crear tipos personalizados de información confidencial menos complejos en la interfaz de usuario del Centro de seguridad y cumplimiento. Para obtener más información, vea [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="80864-p105">You can also create less complex custom sensitive information types in the Security & Compliance Center UI. For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="80864-116">Declinación de responsabilidades importante</span><span class="sxs-lookup"><span data-stu-id="80864-116">Important disclaimer</span></span>

<span data-ttu-id="80864-p106">Debido a las varianzas de los entornos de cliente y los requisitos de coincidencia de contenido, el Soporte técnico de Microsoft no puede ayudar a proporcionar definiciones de contenido coincidente personalizadas: por ejemplo, definir clasificaciones personalizadas o patrones de expresiones regulares (conocidas como “RegEx”). Para el desarrollo, las pruebas y la depuración de contenido coincidente personalizado, los clientes de Office 365 tendrán que basarse en recursos de TI internos o usar un recurso externo de consultoría como los Servicios de Consultoría de Microsoft (MCS). Los ingenieros de soporte técnico pueden proporcionar soporte técnico limitado para la característica, pero no pueden garantizar que cualquier desarrollo personalizado de contenido coincidente cumplirá los requisitos y obligaciones del cliente. Pueden proporcionarse modelos de expresiones regulares de muestra con fines de prueba como ejemplo del tipo de asistencia que se puede proporcionar, o el servicio de soporte técnico puede ayudarle a solucionar problemas de un diseño RegEx existente que no se desencadena como se esperaba con un único ejemplo de contenido específico.</span><span class="sxs-lookup"><span data-stu-id="80864-p106">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions – e.g. defining custom classifications or regular expression patterns (“RegEx”). For custom content-matching development, testing, and debugging, Office 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS).  Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer’s requirements or obligations.  As an example of the type of support which can be provided, sample regular expression patterns may be provided for testing purposes. Or support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

 <span data-ttu-id="80864-122">Para obtener más información sobre el motor de RegEx de .NET que se usa para el procesamiento de texto, vea la documentación en [Expresiones regulares de .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="80864-122">For additional information on the .NET regex engine that's used for processing the text, see the documentaiton on [Regular Expressions in .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).</span></span>
    
## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="80864-123">XML de ejemplo de un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="80864-123">Sample XML of a rule package</span></span>

<span data-ttu-id="80864-p107">Este es el XML de ejemplo del paquete de reglas que crearemos en este tema. Los elementos y los atributos se explican en las secciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="80864-p107">Here's the sample XML of the rule package that we'll create in this topic. Elements and attributes are explained in the sections below.</span></span>
  
```
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
    <Version build="0" major="1" minor="0" revision="0"/>
    <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
    <Details defaultLangCode="en-us">
        <LocalizedDetails langcode="en-us">
            <PublisherName>Contoso</PublisherName>
            <Name>Employee ID Custom Rule Pack</Name>
            <Description>
            This rule package contains the custom Employee ID entity.
            </Description>
        </LocalizedDetails>
    </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
    <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="70">
        <Pattern confidenceLevel="60">
            <IdMatch idRef="Regex_employee_id"/>
        </Pattern>
        <Pattern confidenceLevel="70">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
        </Pattern>
        <Pattern confidenceLevel="80">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
            <Any minMatches="1">
                <Match idRef="Keyword_badge" minCount="2"/>
                <Match idRef="Keyword_employee"/>
            </Any>
            <Any minMatches="0" maxMatches="0">
                <Match idRef="Keyword_false_positives_local"/>
                <Match idRef="Keyword_false_positives_intl"/>
            </Any>
        </Pattern>
    </Entity>
    <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
    <Keyword id="Keyword_employee">
        <Group matchStyle="word">
            <Term>Identification</Term>
            <Term>Contoso Employee</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_badge">
        <Group matchStyle="string">
            <Term>card</Term>
            <Term>badge</Term>
            <Term caseSensitive="true">ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_local">
        <Group matchStyle="word">
            <Term>credit card</Term>
            <Term>national ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_intl">
        <Group matchStyle="word">
            <Term>identity card</Term>
            <Term>national ID</Term>
            <Term>EU debit card</Term>
        </Group>
    </Keyword>
    <LocalizedStrings>
        <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
            <Name default="true" langcode="en-us">Employee ID</Name>
            <Description default="true" langcode="en-us">
            A custom classification for detecting Employee IDs.
            </Description>
            <Name default="true" langcode="de-de">Name for German locale</Name>
            <Description default="true" langcode="de-de">
            Description for German locale.
            </Description>
        </Resource>
    </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="80864-p108">¿Cuáles son sus requisitos clave? [Elementos Rule, Entity y Pattern]</span><span class="sxs-lookup"><span data-stu-id="80864-p108">What are your key requirements? [Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="80864-128">Antes de empezar, resulta útil comprender la estructura básica del esquema XML de una regla y cómo puede usar esta estructura para definir su tipo personalizado de información confidencial de forma que identifique el contenido adecuado.</span><span class="sxs-lookup"><span data-stu-id="80864-128">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="80864-p109">Una regla define una o más entidades (tipos de información confidencial) y, a su vez, cada entidad define uno o más patrones. Un patrón es lo que DLP busca al evaluar contenido, como correos electrónicos y documentos.</span><span class="sxs-lookup"><span data-stu-id="80864-p109">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns. A pattern is what DLP looks for when it evaluates content such as email and documents.</span></span>
  
<span data-ttu-id="80864-p110">Nota rápida sobre terminología: Si está familiarizado con las directivas DLP, ya sabrá que una directiva contiene una o más reglas compuestas por condiciones y acciones. Pero, en este tema, en el marcado XML se usa el término "regla" para identificar los patrones que definen una entidad, que también se conoce como tipo de información confidencial. Por lo tanto, cuando vea el término "regla" en este tema, piense en una entidad o un tipo de información confidencial, no en condiciones y acciones.</span><span class="sxs-lookup"><span data-stu-id="80864-p110">(A quick note on terminology - if you're familiar with DLP policies, you know that a policy contains one or more rules comprised of conditions and actions. However, in this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type. So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.)</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="80864-134">Escenario más sencillo: entidad con un patrón</span><span class="sxs-lookup"><span data-stu-id="80864-134">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="80864-p111">Este es el escenario más sencillo. Quiere usar una directiva DLP para identificar contenido donde haya presente un id. de empleado de su organización, que tiene un formato de número de nueve dígitos. Por lo tanto, el patrón hace referencia a una expresión regular contenida en la regla que identifica números de nueve dígitos. Cualquier contenido donde haya presente un número de nueve dígitos cumplirá con el patrón.</span><span class="sxs-lookup"><span data-stu-id="80864-p111">Here's the simplest scenario. You want your DLP policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number. So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers. Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![Diagrama de una entidad con un patrón](media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="80864-140">Pero, aunque es sencillo, este patrón puede identificar un gran número de falsos positivos si coincide con contenido donde aparezcan números de nueve dígitos que no sean necesariamente id. de empleado.</span><span class="sxs-lookup"><span data-stu-id="80864-140">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="80864-141">Escenario más común: entidad con varios patrones</span><span class="sxs-lookup"><span data-stu-id="80864-141">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="80864-142">Por este motivo, es más común definir una entidad con más de un patrón, donde los patrones identifican pruebas complementarias (como una palabra clave o una fecha), además de la entidad (como un número de nueve dígitos).</span><span class="sxs-lookup"><span data-stu-id="80864-142">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="80864-143">Por ejemplo, para incrementar la probabilidad de identificar contenido donde haya un id. de empleado, puede definir un patrón que también identifique una fecha de contratación y, además, definir otro patrón que identifique una fecha de contratación y una palabra clave (como "Id. de empleado"), además del número de nueve dígitos.</span><span class="sxs-lookup"><span data-stu-id="80864-143">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![Diagrama de una entidad con varios patrones](media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="80864-145">Debe tener en cuenta un par de aspectos importantes de esta estructura:</span><span class="sxs-lookup"><span data-stu-id="80864-145">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="80864-p112">Los patrones que necesitan más pruebas tienen un mayor nivel de confianza. Esto es útil porque, cuando más tarde use este tipo de información confidencial en una directiva DLP, podrá usar acciones más restrictivas (como bloquear contenido) solo con las coincidencias de mayor confianza y, además, podrá usar acciones menos restrictivas (como el envío de notificaciones) con las coincidencias de menor confianza.</span><span class="sxs-lookup"><span data-stu-id="80864-p112">Patterns that require more evidence have a higher confidence level. This is useful because when you later use this sensitive information type in a DLP policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>
    
- <span data-ttu-id="80864-p113">Los elementos IdMatch y Match complementarios hacen referencia a expresiones regulares y palabras clave que, en realidad, son elementos secundarios del elemento Rule, no del elemento Pattern. El elemento Pattern hace referencia a estos elementos complementarios, pero se incluye en el elemento Rule. Esto quiere decir que varias entidades y patrones pueden hacer referencia a una única definición de un elemento complementario, como una expresión regular o una lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="80864-p113">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern. These supporting elements are referenced by the Pattern but included in the Rule. This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>
    
## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="80864-p114">¿Qué entidad necesita identificar? [elemento Entity, atributo id.]</span><span class="sxs-lookup"><span data-stu-id="80864-p114">What entity do you need to identify? [Entity element, id attribute]</span></span>

<span data-ttu-id="80864-p115">Una entidad es un tipo de información confidencial (como un número de tarjeta de crédito) que tiene un patrón bien definido. Cada entidad tiene un GUID único como su id.</span><span class="sxs-lookup"><span data-stu-id="80864-p115">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern. Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="80864-155">Asignar un nombre a la entidad y generar su GUID</span><span class="sxs-lookup"><span data-stu-id="80864-155">Name the entity and generate its GUID</span></span>

<span data-ttu-id="80864-p116">Agregue los elementos Rules y Entity. Después, agregue un comentario que contenga el nombre de la entidad personalizada (en este ejemplo, "Id. de empleado"). Más tarde, agregará el nombre de la entidad a la sección de cadenas localizadas, y ese nombre es lo que se mostrará en la interfaz de usuario al crear una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="80864-p116">Add the Rules and Entity elements. Then add a comment that contains the name of your custom entity - in this example, Employee ID. Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a DLP policy.</span></span>
  
<span data-ttu-id="80864-p117">Después, genere un GUID para la entidad. Hay varias formas de generar GUID, pero puede hacerlo fácilmente en PowerShell si escribe lo siguiente: [guid]::NewGuid(). Más tarde, también agregará el GUID de la entidad a la sección de cadenas localizadas.</span><span class="sxs-lookup"><span data-stu-id="80864-p117">Next, generate a GUID for your entity. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid(). Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![Marcado XML donde se muestran los elementos Rules y Entity](media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="80864-p118">¿Qué patrón quiere hacer coincidir? [Elemento Pattern, elemento IdMatch, elemento Regex]</span><span class="sxs-lookup"><span data-stu-id="80864-p118">What pattern do you want to match? [Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="80864-p119">El patrón contiene la lista de lo que busca el tipo de información confidencial. Esta lista puede contener expresiones regulares, palabras clave y funciones integradas (que realizan tareas como ejecutar expresiones regulares para encontrar fechas o direcciones). Los tipos de información confidencial pueden tener varios patrones con confianzas únicas.</span><span class="sxs-lookup"><span data-stu-id="80864-p119">The pattern contains the list of what the sensitive information type is looking for. This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses). Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="80864-p120">Lo que tienen en común todos los patrones siguientes es que hacen referencia a la misma expresión regular, que busca un número de nueve dígitos (\d{9}) rodeado de espacios en blanco (\s) … (\s). El elemento IdMatch hace referencia a esta expresión regular y es el requisito común para todos los patrones que buscan la entidad Id. de empleado. IdMatch es el identificador que el patrón intenta hacer coincidir, como un id. de empleado, un número de tarjeta de crédito o un número del seguro social. Un elemento Pattern necesita tener exactamente un elemento IdMatch.</span><span class="sxs-lookup"><span data-stu-id="80864-p120">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) … (\s). This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity. IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number. A Pattern element must have exactly one IdMatch element.</span></span>
  
![Marcado XML donde se muestran varios elementos Pattern que hacen referencia a un único elemento Regex](media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="80864-p121">Cuando se cumpla un patrón, este devolverá un recuento y un nivel de confianza que puede usar en las condiciones de la directiva DLP. Al agregar a una directiva DLP una condición para detectar un tipo de información confidencial, puede editar el recuento y el nivel de confianza, como se muestra aquí. El nivel de confianza (que también se denomina "precisión de coincidencia") se explica más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="80864-p121">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![Opciones de precisión de coincidencia y recuento de instancias](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="80864-p122">Al crear una expresión regular, tenga en cuenta que pueden producirse algunos problemas. Por ejemplo, si escribe y carga una expresión regular que identifica demasiado contenido, esto podría afectar al rendimiento. Para obtener más información sobre estos posibles problemas, vea la sección posterior [Posibles problemas de validación](#potential-validation-issues-to-be-aware-of).</span><span class="sxs-lookup"><span data-stu-id="80864-p122">When you create your regular expression, keep in mind that there are potential issues to be aware of. For example, if you write and upload a regex that identifies too much content, this can impact performance. To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="80864-p123">¿Quiere exigir más pruebas? [Elemento Match, atributo minCount]</span><span class="sxs-lookup"><span data-stu-id="80864-p123">Do you want to require additional evidence? [Match element, minCount attribute]</span></span>

<span data-ttu-id="80864-183">Además del elemento IdMatch, un patrón puede usar el elemento Match para exigir pruebas complementarias adicionales, como una palabra clave, una expresión regular, una fecha o una dirección.</span><span class="sxs-lookup"><span data-stu-id="80864-183">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="80864-p124">En un elemento Pattern, se pueden incluir varios elementos Match, ya sea directamente en el elemento Pattern, o bien en combinación con el elemento Any. Los elementos Match se combinan mediante un operador AND implícito; todos los elementos Match tienen que cumplirse para que el patrón encuentre una coincidencia. Puede usar el elemento Any para introducir los operadores AND u OR (encontrará más información en una sección posterior).</span><span class="sxs-lookup"><span data-stu-id="80864-p124">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element. Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched. You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="80864-p125">Puede usar el atributo minCount opcional para especificar el número de instancias que necesita encontrar una coincidencia por cada uno de los elementos Match. Por ejemplo, puede especificar que un patrón se cumpla únicamente cuando se encuentren, como mínimo, dos palabras clave de una lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="80864-p125">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements. For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![Marcado XML donde se muestra el elemento Match con el atributo minOccurs](media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="80864-190">Palabras clave [elementos Keyword, Group y Term, atributos matchStyle y caseSensitive]</span><span class="sxs-lookup"><span data-stu-id="80864-190">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="80864-p126">Al identificar información confidencial (como un id. de empleado), es habitual exigir palabras clave como pruebas corroboradoras. Por ejemplo, además de hacer coincidir un número de nueve dígitos, puede que quiera buscar palabras como "tarjeta", "identificación" o "id.". Para hacerlo, use el elemento Keyword. El elemento Keyword tiene un atributo "id." al que puede hacerse referencia mediante varios elementos Match en varios patrones o entidades.</span><span class="sxs-lookup"><span data-stu-id="80864-p126">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence. For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID". To do this, you use the Keyword element. The Keyword element has an id attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="80864-p127">Las palabras clave se incluyen como una lista de elementos Term en un elemento Group. El elemento Group tiene un atributo matchStyle con dos valores posibles:</span><span class="sxs-lookup"><span data-stu-id="80864-p127">Keywords are included as a list of Term elements in a Group element. The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="80864-p128">**matchStyle="word"** El tipo de coincidencia "word" identifica palabras completas rodeadas por espacios en blanco u otros delimitadores. Siempre tiene que usar "word", excepto si necesita hacer coincidir partes de palabras o hacer coincidir palabras en idiomas asiáticos.</span><span class="sxs-lookup"><span data-stu-id="80864-p128">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters. You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="80864-p129">**matchStyle="string"** El tipo de coincidencia "string" identifica cadenas, sin importar el contenido que aparezca alrededor. Por ejemplo, "as" coincidirá con "asa" y con "alias". Use "string" solo cuando necesite hacer coincidir palabras asiáticas, o bien si la palabra clave puede incluirse como parte de otras cadenas.</span><span class="sxs-lookup"><span data-stu-id="80864-p129">**matchStyle="string"** String match identifies strings no matter what they're surrounded by. For example, "id" will match "bid" and "idea". Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="80864-202">Por último, puede usar el atributo caseSensitive del elemento Term para especificar que el contenido tiene que coincidir exactamente con la palabra clave, incluidas las letras en minúscula y mayúscula.</span><span class="sxs-lookup"><span data-stu-id="80864-202">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![Marcado XML donde se muestran elementos Match que hacen referencia palabras clave](media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="80864-204">Expresiones regulares [elemento Regex]</span><span class="sxs-lookup"><span data-stu-id="80864-204">Regular expressions [Regex element]</span></span>

<span data-ttu-id="80864-p130">En este ejemplo, la entidad Id. de empleado ya usa el elemento IdMatch para hacer referencia a una expresión regular para el patrón (un número de nueve dígitos rodeado de espacios en blanco). Además, un patrón puede usar un elemento Match para hacer referencia a un elemento Regex adicional con el fin de identificar pruebas corroboradoras, como un número de cinco o nueve dígitos con el formato de un código postal de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="80864-p130">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern - a nine-digit number surrounded by whitespace. In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="80864-207">Patrones adicionales, como fechas o direcciones [funciones integradas]</span><span class="sxs-lookup"><span data-stu-id="80864-207">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="80864-p131">Además de los tipos de información confidencial integrados, en DLP también se incluyen funciones integradas que pueden identificar pruebas corroboradoras, como una fecha con formato de Estados Unidos, una fecha con formato de la UE, una fecha de expiración o una dirección de Estados Unidos. DLP no permite cargar sus propias funciones personalizadas; pero, al crear un tipo personalizado de información confidencial, la entidad puede hacer referencia a las funciones integradas.</span><span class="sxs-lookup"><span data-stu-id="80864-p131">In addition to the built-in sensitive information types, DLP also includes built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address. DLP does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="80864-210">Por ejemplo, una tarjeta de identificación de empleado contiene una fecha de contratación, por lo que esta entidad personalizada puede usar la función integrada `Func_us_date` para identificar una fecha en el formato usado normalmente en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="80864-210">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="80864-211">Para obtener más información, vea [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="80864-211">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![Marcado XML donde se muestra el elemento Match que hace referencia a una función integrada](media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="80864-213">Diferentes combinaciones de pruebas [elemento Any, atributos minMatches y maxMatches]</span><span class="sxs-lookup"><span data-stu-id="80864-213">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="80864-p132">En un elemento Pattern, todos los elementos IdMatch y Match se combinan mediante un operador AND implícito (todas las coincidencias tienen que cumplirse para que el patrón se cumpla). Pero puede crear una lógica de coincidencia más flexible mediante el elemento Any para agrupar elementos Match. Por ejemplo, puede usar el elemento Any para que coincida con todos los elementos Match secundarios, con ninguno o con un subconjunto exacto.</span><span class="sxs-lookup"><span data-stu-id="80864-p132">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator - all of the matches must be satisfied before the pattern can be satisfied. However, you can create more flexible matching logic by using the Any element to group Match elements. For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="80864-p133">El elemento Any tiene los atributos opcionales minMatches y maxMatches, que puede usar para definir cuántos de los elementos Match secundarios han de cumplirse para que el patrón coincida. Tenga en cuenta que estos atributos definen el número de elementos Match que han de cumplirse, no el número de instancias de pruebas encontradas para las coincidencias. Para definir un número mínimo de instancias para una coincidencia específica (como dos palabras clave de una lista), use el atributo minCount para un elemento Match (ver arriba).</span><span class="sxs-lookup"><span data-stu-id="80864-p133">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched. Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches. To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="80864-220">Coincidir como mínimo con un elemento Match secundario</span><span class="sxs-lookup"><span data-stu-id="80864-220">Match at least one child Match element</span></span>

<span data-ttu-id="80864-p134">Si quiere exigir que solo tenga que cumplirse un número mínimo de elementos Match, puede usar el atributo minMatches. En realidad, estos elementos Match se combinan mediante un operador OR implícito. Este elemento Any se cumple si se encuentra una fecha con formato de Estados Unidos o una palabra clave de alguna de las listas.</span><span class="sxs-lookup"><span data-stu-id="80864-p134">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute. In effect, these Match elements are joined by an implicit OR operator. This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>
  
![Marcado XML donde se muestra el elemento Any con el atributo minMatches](media/385db1b1-571b-4a05-81b3-db28f5099c17.png)
  
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="80864-225">Coincidir un subconjunto exacto de elementos Match secundarios</span><span class="sxs-lookup"><span data-stu-id="80864-225">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="80864-p135">Si quiere exigir que se cumpla un número exacto de elementos Match, puede establecer los atributos minMatches y maxMatches en el mismo valor. Este elemento Any solo se cumple si se encuentra exactamente una fecha o palabra clave (si se encuentra más de una, el patrón no coincidirá).</span><span class="sxs-lookup"><span data-stu-id="80864-p135">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value. This Any element is satisfied only if exactly one date or keyword is found - any more than that, and the pattern won't be matched.</span></span>
  
![Marcado XML donde se muestra el elemento Any con los atributos minMatches y maxMatches](media/97b10002-7781-42e8-ac5a-20ad8c5a887e.png)
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="80864-229">Ninguna coincidencia de elementos Match secundarios</span><span class="sxs-lookup"><span data-stu-id="80864-229">Match none of children Match elements</span></span>

<span data-ttu-id="80864-p136">Si quiere exigir la ausencia de pruebas específicas para que se cumpla un patrón, puede establecer los atributos minMatches y maxMatches en 0. Esto puede resultar útil si tiene una lista de palabras clave u otras pruebas que es probable que indiquen un falso positivo.</span><span class="sxs-lookup"><span data-stu-id="80864-p136">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0. This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="80864-p137">Por ejemplo, la entidad Id. de empleado busca la palabra clave "tarjeta", ya que puede hacer referencia a una "tarjeta de identificación". Pero, si la palabra "tarjeta" solo aparece en la frase "tarjeta de crédito", es poco probable que "tarjeta" en este contenido signifique "tarjeta de identificación". Por lo tanto, puede agregar "tarjeta de crédito" con una palabra clave a una lista de términos que quiera excluir para impedir que se cumpla el patrón.</span><span class="sxs-lookup"><span data-stu-id="80864-p137">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card". However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card". So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
![Marcado XML donde se muestra el valor cero del atributo maxMatches](media/f81d44e5-3db8-48a8-8919-f483a386afdf.png)
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="80864-p138">¿Cuál es la proximidad con que la entidad tiene que aparecer junto a otra prueba? [Atributo patternsProximity]</span><span class="sxs-lookup"><span data-stu-id="80864-p138">How close to the entity must the other evidence be? [patternsProximity attribute]</span></span>

<span data-ttu-id="80864-p139">El tipo de información confidencial busca un patrón que represente un id. de empleado y, como parte de ese patrón, también busca pruebas corroboradoras, como una palabra clave (por ejemplo, "id."). Cuanto más cerca se encuentre esta prueba, más probable es que el patrón sea el id. de empleado adecuado. Puede determinar la proximidad de otras pruebas en el patrón con la entidad mediante el atributo patternsProximity obligatorio del elemento Entity.</span><span class="sxs-lookup"><span data-stu-id="80864-p139">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID". It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID. You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![Marcado XML donde se muestra el atributo patternsProximity](media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="80864-p140">Por cada patrón en la entidad, el valor del atributo patternsProximity define la distancia (en caracteres Unicode) desde la ubicación de IdMatch para el resto de las coincidencias especificadas para ese patrón. La ventana de proximidad se ancla mediante la ubicación IdMatch, con la ventana extendiéndose hacia la izquierda y la derecha de la ubicación IdMatch.</span><span class="sxs-lookup"><span data-stu-id="80864-p140">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern. The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![Diagrama de la ventana de proximidad](media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="80864-p141">En el ejemplo siguiente, se muestra cómo la ventana de proximidad afecta a la coincidencia de patrones donde el elemento IdMatch de la entidad personalizada "Id. de empleado" exige como mínimo una coincidencia corroboradora de una palabra clave o fecha. Solo ID1 coincide porque, en el caso de ID2 e ID3, en la ventana de proximidad no se encuentra ninguna prueba corroboradora, o bien se encuentra una parcial.</span><span class="sxs-lookup"><span data-stu-id="80864-p141">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date. Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![Diagrama de prueba corroboradora y ventana de proximidad](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="80864-p142">Tenga en cuenta que, en el caso del correo electrónico, el cuerpo del mensaje y los datos adjuntos se consideran elementos independientes. Esto significa que la ventana de proximidad no se extiende más allá del final de cada uno de estos elementos. Por cada elemento (datos adjuntos o cuerpo), tanto idMatch como la prueba corroboradora necesitan residir en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="80864-p142">Note that for email, the message body and each attachment are treated as separate items. This means that the proximity window does not extend beyond the end of each of these items. For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="80864-p143">¿Cuáles son los niveles de confianza adecuados para diferentes patrones? [Atributo confidenceLevel, atributo recommendedConfidence]</span><span class="sxs-lookup"><span data-stu-id="80864-p143">What are the right confidence levels for different patterns? [confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="80864-p144">Cuantas más pruebas necesite un patrón, más seguro estará de que se haya identificado una entidad real (como un id. de empleado) cuando coincida el patrón. Por ejemplo, tendrá más confianza en un patrón que necesite un número de identificación de nueve dígitos, una fecha de contratación y una palabra clave a muy poca distancia, que en un patrón que solo necesite un número de identificación de nueve dígitos.</span><span class="sxs-lookup"><span data-stu-id="80864-p144">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched. For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="80864-p145">El elemento Pattern tiene un atributo confidenceLevel obligatorio. Piense en el valor de confidenceLevel (un entero entre 1 y 100) como un id. único para cada patrón de una entidad (los patrones de una entidad necesitan tener asignados distintos niveles de confianza). El valor preciso del entero no importa: solo tiene que elegir números que tengan sentido para el equipo de cumplimiento. Después de cargar el tipo personalizado de información confidencial y crear una directiva DLP, puede hacer referencia a esos niveles de confianza en las condiciones de las reglas que cree.</span><span class="sxs-lookup"><span data-stu-id="80864-p145">The Pattern element has a required confidenceLevel attribute. You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity - the patterns in an entity must have different confidence levels that you assign. The precise value of the integer doesn't matter - simply pick numbers that make sense to your compliance team. After you upload your custom sensitive information type and then create a DLP policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![Marcado XML donde se muestran los elementos Pattern con distintos valores para el atributo confidenceLevel](media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
<span data-ttu-id="80864-p146">Además del atributo confidenceLevel para cada elemento Pattern, el elemento Entity tiene un atributo recommendedConfidence. El atributo de confianza recomendado se puede identificar como el nivel de confianza predeterminado para la regla. Al crear una regla en una directiva DLP, si no especifica un nivel de confianza para la regla que se usará, esa regla coincidirá según el nivel de confianza recomendado para la entidad.</span><span class="sxs-lookup"><span data-stu-id="80864-p146">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute. The recommended confidence attribute can be thought of as the default confidence level for the rule. When you create a rule in a DLP policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span>
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-security-amp-compliance-center-localizedstrings-element"></a><span data-ttu-id="80864-p147">¿Quiere admitir otros idiomas en la interfaz de usuario del Centro de seguridad y cumplimiento? [Elemento LocalizedStrings]</span><span class="sxs-lookup"><span data-stu-id="80864-p147">Do you want to support other languages in the UI of the Security &amp; Compliance Center? [LocalizedStrings element]</span></span>

<span data-ttu-id="80864-p148">Si el equipo de cumplimiento usa el Centro de seguridad y cumplimiento de Office 365 para crear directivas DLP en distintas configuraciones regionales y diferentes idiomas, puede proporcionar versiones localizadas del nombre y la descripción del tipo personalizado de información confidencial. Cuando el equipo de cumplimiento use Office 365 en un idioma admitido, verán el nombre localizado en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="80864-p148">If your compliance team uses the Office 365 Security &amp; Compliance Center to create DLP policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type. When your compliance team uses Office 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![Opciones de precisión de coincidencia y recuento de instancias](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="80864-p149">El elemento Rules necesita contener un elemento LocalizedStrings, que contiene un elemento Resource que hace referencia al GUID de la entidad personalizada. A su vez, cada elemento Resource contiene uno o más elementos Name y Description, y cada uno usa el atributo langcode para especificar una cadena localizada para un idioma específico.</span><span class="sxs-lookup"><span data-stu-id="80864-p149">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity. In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![Marcado XML donde se muestra el contenido del elemento LocalizedStrings](media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="80864-p150">Tenga en cuenta que las cadenas localizadas solo se usan para mostrar el tipo personalizado de información confidencial en la interfaz de usuario del Centro de seguridad y cumplimiento. No se pueden usar cadenas localizadas para proporcionar otras versiones localizadas de una lista de palabras clave o una expresión regular.</span><span class="sxs-lookup"><span data-stu-id="80864-p150">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Security &amp; Compliance Center. You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="80864-273">Otro marcado de paquete de reglas [GUID de RulePack]</span><span class="sxs-lookup"><span data-stu-id="80864-273">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="80864-p151">Por último, el principio de cada elemento RulePackage contiene información general que necesita rellenar. Puede usar el siguiente marcado como una plantilla y reemplazar los marcadores de posición "…" con su propia información.</span><span class="sxs-lookup"><span data-stu-id="80864-p151">Finally, the beginning of each RulePackage contains some general information that you need to fill in. You can use the following markup as a template and replace the ". . ." placeholders with your own info.</span></span>
  
<span data-ttu-id="80864-p152">Aún más importante, necesita generar un GUID para el elemento RulePack. Anteriormente, ha generado un GUID para la entidad (se trata de un GUID secundario para el elemento RulePack). Hay varias formas de generar GUID, pero puede hacerlo fácilmente en PowerShell si escribe lo siguiente: [guid]::NewGuid().</span><span class="sxs-lookup"><span data-stu-id="80864-p152">Most importantly, you'll need to generate a GUID for the RulePack. Above, you generated a GUID for the entity; this is a second GUID for the RulePack. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="80864-p153">El elemento Version también es importante. Al cargar por primera vez un paquete de reglas, Office 365 anota el número de versión. Si posteriormente actualiza el paquete de reglas y carga una nueva versión, asegúrese de actualizar el número de versión (de lo contrario, Office 365 no implementará el paquete de reglas).</span><span class="sxs-lookup"><span data-stu-id="80864-p153">The Version element is also important. When you upload your rule package for the first time, Office 365 notes the version number. Later, if you update the rule package and upload a new version, make sure to update the version number or Office 365 won't deploy the rule package.</span></span>
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    . . .
 </Rules>
</RulePackage>

```

<span data-ttu-id="80864-285">Una vez completado, el elemento RulePack será parecido a este.</span><span class="sxs-lookup"><span data-stu-id="80864-285">When complete, your RulePack element should look like this.</span></span>
  
![Marcado XML donde se muestra el elemento RulePack](media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="80864-287">Cambios para Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80864-287">Changes for Exchange Online</span></span>

<span data-ttu-id="80864-p154">Anteriormente, puede que haya usado PowerShell de Exchange Online para importar tipos personalizados de información confidencial para DLP. Ahora, dichos tipos se pueden usar tanto en el Centro de administración de Exchange como en el Centro de seguridad y cumplimiento. Como parte de esta mejora, necesita usar el símbolo del sistema de PowerShell del Centro de seguridad y cumplimiento para importar los tipos personalizados de información confidencial (ya no se pueden importar desde Exchange PowerShell). Los tipos mencionados seguirán funcionando como hasta ahora; pero puede que los cambios realizados en los tipos personalizados de información confidencial del Centro de seguridad y cumplimiento tarden hasta una hora en aparecer en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="80864-p154">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP. Now your custom sensitive information types can be used in both the Exchange Admin Center and the Security &amp; Compliance Center. As part of this improvement, you should use Security &amp; Compliance Center PowerShell to import your custom sensitive information types - you can't import them from the Exchange PowerShell anymore. Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Security &amp; Compliance Center to appear in the Exchange Admin Center.</span></span>
  
<span data-ttu-id="80864-p155">Tenga en cuenta que, en el Centro de seguridad y cumplimiento, se usa el cmdlet `DlpSensitiveInformationTypeRulePackage` para cargar un paquete de reglas. Anteriormente, en el Centro de administración de Exchange, se usaba el cmdlet `ClassificationRuleCollection`.</span><span class="sxs-lookup"><span data-stu-id="80864-p155">Note that in the Security &amp; Compliance Center, you use the  `DlpSensitiveInformationTypeRulePackage` cmdlet to upload a rule package. Previously, in the Exchange Admin Center, you used the  `ClassificationRuleCollection` cmdlet.</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="80864-294">Cargar un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="80864-294">Upload your rule package</span></span>

<span data-ttu-id="80864-295">Para cargar un paquete de reglas, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="80864-295">To upload your rule package, do the following.</span></span>
  
1. <span data-ttu-id="80864-296">Guárdelo como un archivo .xml con codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="80864-296">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="80864-297">Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="80864-297">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. <span data-ttu-id="80864-298">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="80864-298">Use the following syntax:</span></span>

    ```
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte)
    ```

    <span data-ttu-id="80864-299">En este ejemplo se carga el archivo XML de Unicode denominado MyNewRulePack.xml desde C:\Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="80864-299">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

    ```
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte)
    ```

    <span data-ttu-id="80864-300">Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="80864-300">For detailed syntax and parameter information, see [New-OrganizationRelationship](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage).</span></span>

5. <span data-ttu-id="80864-301">Para comprobar que ha creado correctamente un nuevo tipo de información confidencial, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="80864-301">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="80864-302">Ejecute el siguiente comando y compruebe que aparece el nuevo paquete de reglas:</span><span class="sxs-lookup"><span data-stu-id="80864-302">Run the following command and verify the new rule package is listed:</span></span>

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ``` 

  - <span data-ttu-id="80864-303">Ejecute el siguiente comando y compruebe que aparece el nuevo tipo de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="80864-303">Run the following command and verify the sensitive information type is listed:</span></span>

    ```
    Get-DlpSensitiveInformationType
    ``` 

    <span data-ttu-id="80864-304">Para los tipos personalizados de información confidencial, el valor de propiedad de Publisher no será Microsoft Corporation, sino otro.</span><span class="sxs-lookup"><span data-stu-id="80864-304">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

  - <span data-ttu-id="80864-305">Reemplace \<Nombre\> con el valor de nombre del tipo de información confidencial (por ejemplo, Id. de empleado) y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="80864-305">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the following command:</span></span>

    ```
    Get-DlpSensitiveInformationType -Identity "<Name>"
    ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="80864-306">Posibles problemas de validación</span><span class="sxs-lookup"><span data-stu-id="80864-306">Potential validation issues to be aware of</span></span>

<span data-ttu-id="80864-p156">Al cargar un archivo XML de paquete de reglas, el sistema valida el código XML y comprueba si hay patrones incorrectos conocidos y problemas de rendimiento obvios. Estos son algunos de los problemas conocidos (la validación comprueba las expresiones regulares):</span><span class="sxs-lookup"><span data-stu-id="80864-p156">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues. Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="80864-309">No puede empezar ni terminar con el alternador "|", que coincide con todo, ya que se considera una coincidencia vacía.</span><span class="sxs-lookup"><span data-stu-id="80864-309">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
    <span data-ttu-id="80864-310">Por ejemplo, "|a" o "b|" no superarán la validación.</span><span class="sxs-lookup"><span data-stu-id="80864-310">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="80864-311">No puede empezar ni terminar con un patrón ".{0,m}", ya que no tiene ninguna finalidad funcional y solo perjudica al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="80864-311">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
    <span data-ttu-id="80864-312">Por ejemplo, ".{0,50}ASDF" o "ASDF.{0,50}" no superarán la validación.</span><span class="sxs-lookup"><span data-stu-id="80864-312">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="80864-313">No puede tener ".{0,m}" o "{1,m}" en grupos, ni tampoco ".\*" o ".+" en grupos.</span><span class="sxs-lookup"><span data-stu-id="80864-313">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
    <span data-ttu-id="80864-314">Por ejemplo, "(.{0,50000})" no superará la validación.</span><span class="sxs-lookup"><span data-stu-id="80864-314">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="80864-315">No puede tener ningún carácter con los repetidores "{0,m}" o "{1,m}" en grupos.</span><span class="sxs-lookup"><span data-stu-id="80864-315">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
    <span data-ttu-id="80864-316">Por ejemplo, "(a\*)" no superará la validación.</span><span class="sxs-lookup"><span data-stu-id="80864-316">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="80864-317">No puede empezar ni terminar con ".{1,m}" (en su lugar, use simplemente ".").</span><span class="sxs-lookup"><span data-stu-id="80864-317">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
    <span data-ttu-id="80864-318">Por ejemplo, ".{1,m}asdf" no superará la validación; en su lugar, use ".asdf".</span><span class="sxs-lookup"><span data-stu-id="80864-318">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="80864-319">No puede tener un repetidor no enlazado (como "\*" o "+") en un grupo.</span><span class="sxs-lookup"><span data-stu-id="80864-319">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
    <span data-ttu-id="80864-320">Por ejemplo, "(xx)\*" y "(xx)+" no superarán la validación.</span><span class="sxs-lookup"><span data-stu-id="80864-320">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
    
<span data-ttu-id="80864-321">Si un tipo personalizado de información confidencial contiene un problema que puede afectar al rendimiento, no se cargará y es posible que se muestre uno de estos mensajes de error:</span><span class="sxs-lookup"><span data-stu-id="80864-321">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="80864-322">**Cuantificadores genéricos que coinciden con más de un contenido de lo esperado (por ejemplo, "+", "\*")**</span><span class="sxs-lookup"><span data-stu-id="80864-322">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="80864-323">**Aserciones de búsqueda anticipada y posterior**</span><span class="sxs-lookup"><span data-stu-id="80864-323">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="80864-324">**Agrupación compleja en conjunto con cuantificadores generales**</span><span class="sxs-lookup"><span data-stu-id="80864-324">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="80864-325">Volver a rastrear el contenido para identificar la información confidencial</span><span class="sxs-lookup"><span data-stu-id="80864-325">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="80864-p157">DLP usa el rastreador de búsqueda para identificar y clasificar información confidencial en el contenido del sitio. El contenido de sitios de OneDrive para la Empresa y SharePoint Online se vuelve a rastrear automáticamente cada vez que se actualiza. Pero, para identificar el nuevo tipo personalizado de información confidencial en todo el contenido existente, es necesario volver a rastrear ese contenido.</span><span class="sxs-lookup"><span data-stu-id="80864-p157">DLP uses the search crawler to identify and classify sensitive information in site content. Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated. But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="80864-329">En Office 365, no se puede solicitar de forma manual un nuevo rastreo de todo un espacio empresarial, pero puede hacerlo para una colección de sitios, una lista o una biblioteca (vea [Solicitar de forma manual un rastreo y volver a indexar un sitio, una biblioteca o una lista](https://support.office.com/article/9afa977d-39de-4321-b4ca-8c7c7e6d264e)).</span><span class="sxs-lookup"><span data-stu-id="80864-329">In Office 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library - see [Manually request crawling and re-indexing of a site, a library or a list](https://support.office.com/article/9afa977d-39de-4321-b4ca-8c7c7e6d264e).</span></span>
  
## <a name="remove-a-custom-sensitive-information-type"></a><span data-ttu-id="80864-330">Eliminación de un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="80864-330">Remove a custom sensitive information type</span></span>

<span data-ttu-id="80864-331">**Nota**: antes el quitar un tipo personalizado de información confidencial, asegúrese de que ninguna directiva DLP ni las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) sigan haciendo referencia al tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="80864-331">**Note**: Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

<span data-ttu-id="80864-332">En PowerShell del Centro de seguridad y cumplimiento, hay dos métodos para quitar los tipos personalizados de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="80864-332">In Security & Compliance Center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="80864-p158">**Quite los tipos personalizados de información confidencial individuales**: use el método documentado en [Modificar un tipo personalizado de información confidencial](#modify-a-custom-sensitive-information-type). Exporte el paquete de reglas personalizado que contiene el tipo de información confidencial, quite el tipo de información confidencial del archivo XML e importe el archivo XML actualizado en el paquete de reglas personalizado existente.</span><span class="sxs-lookup"><span data-stu-id="80864-p158">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type). You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="80864-335">**Quitar un paquete de reglas personalizado y todos los tipos de información confidencial que contiene**: este método se documenta en esta sección.</span><span class="sxs-lookup"><span data-stu-id="80864-335">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

1. [<span data-ttu-id="80864-336">Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="80864-336">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=799771)

2. <span data-ttu-id="80864-337">Para quitar un paquete de reglas personalizado, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="80864-337">To remove a custom rule package, use the following syntax:</span></span>

    ```
    Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
    ```

    <span data-ttu-id="80864-338">Puede usar el valor de nombre (en cualquier idioma) o el valor (GUID) `RulePack id` para identificar el paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="80864-338">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

    <span data-ttu-id="80864-339">En este ejemplo se quita el paquete de reglas denominado "Paquete de reglas personalizado de Id. de empleado".</span><span class="sxs-lookup"><span data-stu-id="80864-339">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

    ```
       Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
    ```

    <span data-ttu-id="80864-340">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="80864-340">For detailed syntax and parameter information, see [Remove-OrganizationRelationship](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="80864-341">Para comprobar que ha quitado correctamente un nuevo tipo personalizado de información confidencial, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="80864-341">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="80864-342">Ejecute el siguiente comando y compruebe que ya no aparece el nuevo paquete de reglas:</span><span class="sxs-lookup"><span data-stu-id="80864-342">From the exsdkExMSH, run the following command and verify that the rule you remove is no longer listed:</span></span>

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ``` 

  - <span data-ttu-id="80864-343">Ejecute el siguiente comando y compruebe que ya no aparecen los tipos de información confidencial en el paquete de reglas que ha quitado:</span><span class="sxs-lookup"><span data-stu-id="80864-343">Run the following command and verify the sensitive information types in the removed rule package are no longer listed:</span></span>

    ```
    Get-DlpSensitiveInformationType
    ``` 

    <span data-ttu-id="80864-344">Para los tipos personalizados de información confidencial, el valor de propiedad de Publisher no será Microsoft Corporation, sino otro.</span><span class="sxs-lookup"><span data-stu-id="80864-344">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

  - <span data-ttu-id="80864-345">Reemplace \<Nombre\> con el valor de nombre del tipo de información confidencial (por ejemplo, Id. de empleado) y ejecute el comando siguiente para comprobar que el tipo de información confidencial ya no aparece: </span><span class="sxs-lookup"><span data-stu-id="80864-345">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the following command to verify the sensitive information type is no longer listed:</span></span>

    ```
    Get-DlpSensitiveInformationType -Identity "<Name>"
    ```

## <a name="modify-a-custom-sensitive-information-type"></a><span data-ttu-id="80864-346">Modificación de un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="80864-346">Remove a custom sensitive information type</span></span>

<span data-ttu-id="80864-347">Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80864-347">In Security & Compliance Center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="80864-348">Exporte el paquete de reglas existente que contiene el tipo de información confidencial a un archivo XML (o, si lo tiene, use el archivo XML existente).</span><span class="sxs-lookup"><span data-stu-id="80864-348">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span> 

2. <span data-ttu-id="80864-349">Modifique el tipo personalizado de información confidencial en el archivo XML exportado.</span><span class="sxs-lookup"><span data-stu-id="80864-349">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="80864-350">Importe el archivo XML actualizado en el paquete de reglas existentes.</span><span class="sxs-lookup"><span data-stu-id="80864-350">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="80864-351">Para conectarse a PowerShell del Centro de seguridad y cumplimiento, vea [Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](http://go.microsoft.com/fwlink/p/?LinkID=799771).</span><span class="sxs-lookup"><span data-stu-id="80864-351">To connect to Security & Compliance Center PowerShell, see [Connect to Office 365 Security & Compliance Center PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

#### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="80864-352">Paso 1: exportar el paquete de reglas existentes a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="80864-352">Step 1: Export the existing rule package to an XML file</span></span>

<span data-ttu-id="80864-353">**Nota**: si tiene una copia del archivo XML (si, por ejemplo, lo acaba de crear y de importar), puede saltar al paso siguiente para modificar el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="80864-353">**Note**: If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="80864-354">Si aún no lo sabe, ejecute el comando siguiente para buscar el nombre del paquete de reglas personalizado:</span><span class="sxs-lookup"><span data-stu-id="80864-354">If you don't already know it, run the following command to find the name of the custom rule package:</span></span>

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ```

    <span data-ttu-id="80864-p159">**Nota**: el paquete de reglas integradas que contiene los tipos de información confidencial integrados se denomina paquete de reglas de Microsoft. El paquete de reglas que contiene los tipos personalizados de información confidencial que creó en la interfaz de usuario del Centro de seguridad y cumplimiento se llama Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="80864-p159">**Note**: The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Security & Compliance Center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="80864-357">Use la siguiente sintaxis para almacenar el paquete de reglas personalizado a una variable:</span><span class="sxs-lookup"><span data-stu-id="80864-357">Use the following syntax to store the custom rule package to a variable:</span></span>

    ```
    $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
    ```

   <span data-ttu-id="80864-358">Por ejemplo, si el paquete de reglas se llama "Paquete de reglas personalizado de Id. de empleado", ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="80864-358">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following command:</span></span>

    ```
    $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
    ```

3. <span data-ttu-id="80864-359">Use la siguiente sintaxis para exportar el paquete de reglas personalizado a un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="80864-359">Use the following syntax to export the custom rule package to an XML file:</span></span>

    ```
    Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
    ```

    <span data-ttu-id="80864-360">En este ejemplo se exporta el paquete de reglas para el archivo denominado ExportedRulePackage.xml en la carpeta C:\Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="80864-360">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

    ```
    Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
    ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="80864-361">Paso 2: modificar el tipo de información confidencial en el archivo XML exportado</span><span class="sxs-lookup"><span data-stu-id="80864-361">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="80864-362">Anteriormente en este tema se describen los tipos de información confidencial en el archivo XML y otros elementos del archivo.</span><span class="sxs-lookup"><span data-stu-id="80864-362">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="80864-363">Paso 3: importar el archivo XML actualizado en el paquete de reglas existentes</span><span class="sxs-lookup"><span data-stu-id="80864-363">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="80864-364">Para importar el archivo XML actualizado en el paquete de reglas existentes, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="80864-364">To import the updated XML back into the existing rule package, use the following syntax:</span></span>

```
Set-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity" -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte)
```

<span data-ttu-id="80864-365">Puede usar el Valor de nombre o el valor (GUID) `RulePack id` para identificar el paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="80864-365">You can use the Name value or the `RulePack id` (GUID) value to identify the rule package.</span></span>

<span data-ttu-id="80864-366">En este ejemplo se carga el archivo XML Unicode actualizado denominado MyUpdatedRulePack.xml desde C:\Mis documentos en el paquete de reglas existente denominado "Paquete de reglas personalizado de Id. de empleado".</span><span class="sxs-lookup"><span data-stu-id="80864-366">This example uploads the updated Unicode XML file named MyUpdatedRulePack.xml from C:\My Documents into the existing rule package named "Employee ID Custom Rule Pack".</span></span>

```
Set-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack" -FileData (Get-Content -Path "C:\My Documents\MyUpdatedRulePack.xml" -Encoding Byte)
```

<span data-ttu-id="80864-367">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="80864-367">For detailed syntax and parameter information, see [Set-PublicFolderMigrationRequest](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage) and Resume-PublicFolderMigrationRequest.</span></span>

## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="80864-368">Referencia: Definición de esquema XML de paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="80864-368">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="80864-369">Puede copiar este marcado, guardarlo como un archivo XSD y usarlo para validar el archivo XML del paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="80864-369">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
```
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce" 
           xmlns:xs="http://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>        
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>

```

## <a name="more-information"></a><span data-ttu-id="80864-370">Más información</span><span class="sxs-lookup"><span data-stu-id="80864-370">More information</span></span>

- [<span data-ttu-id="80864-371">Información general sobre las directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="80864-371">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="80864-372">Información que buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="80864-372">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="80864-373">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="80864-373">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    

