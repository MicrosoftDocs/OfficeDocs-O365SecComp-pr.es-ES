---
title: Diseño de un esquema de clasificación de datos personales
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Determine si su organización va a implementar etiquetas como parte de su plan de RGPD.
ms.openlocfilehash: 6886adaa09599b32eb2f3084efdea06fd5794af0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243478"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="4381b-103">Diseño de un esquema de clasificación de datos personales</span><span class="sxs-lookup"><span data-stu-id="4381b-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="4381b-p101">Los artículos anteriores de esta serie se centran en el uso de tipos de información confidencial para identificar datos personales que están sujetos al RGPD. Los tipos de información confidencial son una forma de clasificación. Esta puede ser toda la clasificación que necesita. Sin embargo, muchas organizaciones implementan una estrategia de gobierno de datos más amplia con etiquetas. Use este tema para decidir si también quiere implementar etiquetas como parte de su plan de RGPD. Si lo hace, este tema proporciona algunas directrices y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4381b-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="4381b-p102">Nota: Definir un esquema de clasificación de una organización y configurar directivas, etiquetas y condiciones requiere una cuidadosa planificación y preparación. Es importante tener en cuenta que este no es un proceso de TI. Asegúrese de trabajar con el equipo legal y de cumplimiento para desarrollar un esquema de clasificación y etiquetado de los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4381b-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It is important to realize that this is not an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization’s data.</span></span>

## <a name="decide-if-you-are-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="4381b-113">Decidir si debe utilizar etiquetas además de tipos de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="4381b-113">Decide if you are using labels in addition to sensitive data types</span></span>

<span data-ttu-id="4381b-p103">Puede tomar uno de los dos métodos para la clasificación de información personal en Office 365. Puede usar cualquiera de estos para protección de RGPD. Si decide usar solo los tipos de información confidencial para clasificación, puede omitir el resto de este tema.</span><span class="sxs-lookup"><span data-stu-id="4381b-p103">You can take one of two approaches for classification in Office 365 for personal information. Either of these can be used for GDPR protection. If decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="4381b-117">Elija una de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="4381b-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-office-365-sensitive-information-types"></a><span data-ttu-id="4381b-118">Opción 1: Usar solo los tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="4381b-118">Option 1: Use only Office 365 sensitive information types</span></span>

-   <span data-ttu-id="4381b-119">Los tipos de información confidencial funcionan correctamente para identificar y proteger datos personales sujetos al RGPD y otros tipos de normas.</span><span class="sxs-lookup"><span data-stu-id="4381b-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

-   <span data-ttu-id="4381b-120">Estos son más fáciles de usar si su organización ya no tiene o no va a implementar un plan de gobierno de datos más amplio con etiquetas.</span><span class="sxs-lookup"><span data-stu-id="4381b-120">These are simpler to use if your organization doesn’t already have or plan to implement a broader data governance plan using labels.</span></span>

-   <span data-ttu-id="4381b-121">Estas funcionan con reglas DLP (como sucede con las etiquetas de retención).</span><span class="sxs-lookup"><span data-stu-id="4381b-121">These work with DLP rules (so do retention labels).</span></span>

-   <span data-ttu-id="4381b-122">Los tipos de información confidencial funcionan con Cloud App Security para que pueda detectar información confidencial en otras aplicaciones SaaS.</span><span class="sxs-lookup"><span data-stu-id="4381b-122">Sensitive information types work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--retention-labels"></a><span data-ttu-id="4381b-123">Opción 2: Usar tipos de información confidencial y etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="4381b-123">Option 2: Use sensitive information types + retention labels</span></span>

-   <span data-ttu-id="4381b-124">Necesitará los tipos de información confidencial para aplicar automáticamente etiquetas a datos personales que están sujetos al RGPD, por lo que son un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="4381b-124">You’ll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

-   <span data-ttu-id="4381b-125">Usar etiquetas de retención le permite incluir información personal que está sujeta al RGPD en un plan de gobierno de datos más amplio para su organización.</span><span class="sxs-lookup"><span data-stu-id="4381b-125">Using retention labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>



## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="4381b-126">Desarrollar un esquema de etiqueta que incluya datos personales</span><span class="sxs-lookup"><span data-stu-id="4381b-126">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="4381b-p104">Antes de usar las capacidades técnicas para aplicar protección y etiquetas, primero trabaje en toda la organización para definir un esquema de clasificación. Es posible que su organización ya tenga un esquema de clasificación, lo que facilitará agregar datos personales. En este tema se incluye un esquema de clasificación de ejemplo. Puede usarlo como punto de partida, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4381b-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="4381b-131">Introducción</span><span class="sxs-lookup"><span data-stu-id="4381b-131">Getting started</span></span>

<span data-ttu-id="4381b-p105">Para empezar, decida el número y los nombres de las etiquetas que va a implementar. Hágalo sin preocuparse sobre la tecnología que debe usar y cómo se aplicarán las etiquetas. Aplique este esquema de forma universal en su organización, incluyendo a los datos que se encuentran en almacenamiento local y en otros servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="4381b-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="4381b-135">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4381b-135">Recommendations</span></span> 

<span data-ttu-id="4381b-136">Al diseñar e implementar directivas, etiquetas y condiciones, tenga en cuenta estas recomendaciones:</span><span class="sxs-lookup"><span data-stu-id="4381b-136">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

-   <span data-ttu-id="4381b-p106">Use el esquema de clasificación existente (si corresponde): muchas organizaciones ya usan algún tipo de clasificación de datos. Evalúe con cuidado el esquema de la etiqueta existente y, si es posible, úselo tal como está. El uso de etiquetas que son reconocibles para el usuario final impulsará la adopción.</span><span class="sxs-lookup"><span data-stu-id="4381b-p106">Use existing classification schema (if any) — Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end-user will drive adoption.</span></span>

-   <span data-ttu-id="4381b-p107">Comience con directivas y etiquetas predeterminadas: todas las soluciones incluyen un conjunto de directivas y etiquetas predefinidas. Evalúelas detenidamente teniendo en cuenta los requisitos legales y empresariales y considere usarlas en lugar de crear nuevas.</span><span class="sxs-lookup"><span data-stu-id="4381b-p107">Start with default policies and labels — All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organizations legal and business requirements and consider using them instead of creating new ones.</span></span>

-   <span data-ttu-id="4381b-p108">Comience con poco: no hay prácticamente ningún límite en el número de etiquetas que se pueden crear. Sin embargo, grandes cantidades de etiquetas y etiquetas secundarias afectarán negativamente la adopción. Si tiene demasiadas opciones, es casi como si no tuviese ninguna opción en absoluto.</span><span class="sxs-lookup"><span data-stu-id="4381b-p108">Start small — There is virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often means no choice at all.</span></span>

-   <span data-ttu-id="4381b-145">Use escenarios y casos de uso: identifique los casos de uso comunes dentro de la organización y use los escenarios que se derivan del RGPD para comprobar si la configuración de etiqueta y clasificación prevista funcionará en la práctica.</span><span class="sxs-lookup"><span data-stu-id="4381b-145">Use scenarios and use cases — Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

-   <span data-ttu-id="4381b-p109">Plantéese cada solicitud para una nueva etiqueta, ¿cada escenario o caso de uso necesita una nueva etiqueta o podemos usar las que ya tenemos? Mantener el número de etiquetas al mínimo mejora la adopción.</span><span class="sxs-lookup"><span data-stu-id="4381b-p109">Question every request for a new label, does every scenario or use case really need a new label or can we use what we already have? Keeping the number of labels to a minimum improves adoption.</span></span>

-   <span data-ttu-id="4381b-p110">Use subetiquetas para departamentos clave: algunos departamentos tendrán necesidades específicas que requerirán etiquetas específicas. Defina estas etiquetas como subetiquetas de una etiqueta existente y considere el uso de directivas de ámbito asignadas a grupos de usuarios en lugar de globalmente.</span><span class="sxs-lookup"><span data-stu-id="4381b-p110">Use sub-labels for key departments, some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

-   <span data-ttu-id="4381b-p111">Considere usar directivas de ámbito: las directivas destinadas a subconjuntos de usuarios evitarán una "sobrecarga de etiquetas". Una directiva de ámbito permite asignar etiquetas específicas de roles o departamentos específica (sub-) solo a empleados que trabajan para ese departamento concreto.</span><span class="sxs-lookup"><span data-stu-id="4381b-p111">Consider scoped policies, polices targeted at subsets of users will prevent "label overload". A scoped policy enables assigning role or department specific (sub-)labels to just employees that work for that specific department.</span></span>

-   <span data-ttu-id="4381b-p112">Use nombres de etiqueta significativo: se recomienda no usar argot, estándares o acrónimos como nombres de etiqueta. Intente usar nombres adecuados para el usuario final para mejorar la adopción. En lugar de usar etiquetas como PII, PCI, HIPAA, LBI, MBI y HBI considere nombres como No laborable, General, Confidencial y Extremadamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="4381b-p112">Use meaningful label names, it is recommended not to use jargon, standards or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI and HBI consider names like Non-Business, Public, General, Confidential and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="4381b-155">Ejemplo de esquema de clasificación</span><span class="sxs-lookup"><span data-stu-id="4381b-155">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4381b-156"><strong>Nombre de etiqueta</strong></span><span class="sxs-lookup"><span data-stu-id="4381b-156"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="4381b-157"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="4381b-157"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4381b-158">Personal</span><span class="sxs-lookup"><span data-stu-id="4381b-158">Personal</span></span></td>
<td align="left"><span data-ttu-id="4381b-159">Datos no empresariales, únicamente para uso personal.</span><span class="sxs-lookup"><span data-stu-id="4381b-159">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4381b-160">Público</span><span class="sxs-lookup"><span data-stu-id="4381b-160">Public</span></span></td>
<td align="left"><span data-ttu-id="4381b-161">Datos profesionales preparados y aprobados específicamente para consumo público.</span><span class="sxs-lookup"><span data-stu-id="4381b-161">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4381b-162">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="4381b-162">Customer data</span></span></td>
<td align="left"><span data-ttu-id="4381b-p113">Datos profesionales que contienen información de identificación personal. Algunos ejemplos son números de tarjeta de crédito, números de cuentas bancarias y números de la Seguridad Social.</span><span class="sxs-lookup"><span data-stu-id="4381b-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4381b-165">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="4381b-165">HR data</span></span></td>
<td align="left"><span data-ttu-id="4381b-166">Datos de recursos humanos sobre los empleados de Contoso, como datos de número de empleado y salario.</span><span class="sxs-lookup"><span data-stu-id="4381b-166">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4381b-167">Confidencial</span><span class="sxs-lookup"><span data-stu-id="4381b-167">Confidential</span></span></td>
<td align="left"><span data-ttu-id="4381b-p114">Datos empresariales confidenciales que podrían causar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: contratos, informes de seguridad, resúmenes de previsión y datos de la cuenta de ventas.</span><span class="sxs-lookup"><span data-stu-id="4381b-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4381b-170">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="4381b-170">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="4381b-p115">Datos empresariales extremadamente confidenciales que podrían provocar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: información de empleados y clientes, contraseñas, código fuente e informes financieros previamente anunciados.</span><span class="sxs-lookup"><span data-stu-id="4381b-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="4381b-173">Definir un criterio de búsqueda y de taxonomía en todas las etiquetas</span><span class="sxs-lookup"><span data-stu-id="4381b-173">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="4381b-p116">Tras desarrollar un esquema de clasificación de la organización, el siguiente paso es desarrollar criterios de búsqueda y de taxonomía para buscar datos. Para los datos personales, ya ha completado este trabajo mediante la identificación de tipos de información confidencial y también al personalizar o crear nuevos tipos de información confidencial en su entorno.</span><span class="sxs-lookup"><span data-stu-id="4381b-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you’ve already completed this work by identifying sensitive information types and also by customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="4381b-p117">La siguiente tabla proporciona un esquema de ejemplo, taxonomía y criterios de búsqueda de una organización. Las etiquetas están ordenadas por nivel de confidencialidad de menos confidenciales a más confidenciales para asegurar que los datos que coincidan con varias condiciones de etiqueta se asignan la etiqueta adecuada.</span><span class="sxs-lookup"><span data-stu-id="4381b-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="4381b-178">Nota: El ejemplo de configuración se proporciona únicamente con fines ilustrativos y no está pensado como guía de implementación o referencia.</span><span class="sxs-lookup"><span data-stu-id="4381b-178">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="4381b-179">Lo más importante es asegurarse de que el trabajo que dedica para clasificar los datos personales para cumplimiento de RGPD se adaptan a los objetivos de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="4381b-179">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="4381b-180">Esquema de ejemplo, taxonomía y criterios de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4381b-180">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4381b-181"><strong>Etiqueta</strong></span><span class="sxs-lookup"><span data-stu-id="4381b-181"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="4381b-182"><strong>Taxonomía</strong></span><span class="sxs-lookup"><span data-stu-id="4381b-182"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="4381b-183"><strong>Método</strong></span><span class="sxs-lookup"><span data-stu-id="4381b-183"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="4381b-184"><strong>Sintaxis de búsqueda</strong></span><span class="sxs-lookup"><span data-stu-id="4381b-184"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4381b-185">Personal</span><span class="sxs-lookup"><span data-stu-id="4381b-185">Personal</span></span></td>
<td align="left"><span data-ttu-id="4381b-186">Documentos etiquetados manualmente como personales por el usuario final.</span><span class="sxs-lookup"><span data-stu-id="4381b-186">Documents manually labelled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="4381b-187">Manual</span><span class="sxs-lookup"><span data-stu-id="4381b-187">Manual</span></span></td>
<td align="left"><span data-ttu-id="4381b-188">Documentos etiquetados manualmente como personales por el usuario final.</span><span class="sxs-lookup"><span data-stu-id="4381b-188">Documents manually labelled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4381b-189">Público</span><span class="sxs-lookup"><span data-stu-id="4381b-189">Public</span></span></td>
<td align="left"><span data-ttu-id="4381b-190">Documentos que contienen la frase “Aprobado para publicación ##/####” (que no distingue mayúsculas de minúsculas) donde # representa cualquier dígito.</span><span class="sxs-lookup"><span data-stu-id="4381b-190">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="4381b-191">KQL</span><span class="sxs-lookup"><span data-stu-id="4381b-191">KQL</span></span></p>
<p><span data-ttu-id="4381b-192">RegEx</span><span class="sxs-lookup"><span data-stu-id="4381b-192">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="4381b-193">KQL: aprobado para publicación\*</span><span class="sxs-lookup"><span data-stu-id="4381b-193">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="4381b-194">RegEx: (?i)(\bAprobado para publicación \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="4381b-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4381b-195">Datos del cliente</span><span class="sxs-lookup"><span data-stu-id="4381b-195">Customer data</span></span></td>
<td align="left"><span data-ttu-id="4381b-196">Tipos de información confidencial para datos de ciudadanos de la UE.</span><span class="sxs-lookup"><span data-stu-id="4381b-196">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="4381b-197">Tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4381b-197">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4381b-198">Recursos humanos: datos de empleado</span><span class="sxs-lookup"><span data-stu-id="4381b-198">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="4381b-199">Documentos que incluyan el id. de empleado (que distingue entre mayúsculas y minúsculas) en el formato CONTOSO-9##### donde # representa cualquier dígito.</span><span class="sxs-lookup"><span data-stu-id="4381b-199">Documents that include the case sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="4381b-200">KQL</span><span class="sxs-lookup"><span data-stu-id="4381b-200">KQL</span></span></p>
<p><span data-ttu-id="4381b-201">RegEx</span><span class="sxs-lookup"><span data-stu-id="4381b-201">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="4381b-202">KQL: CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="4381b-202">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="4381b-203">RegEx: (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="4381b-203">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4381b-204">Recursos humanos: datos de sueldo</span><span class="sxs-lookup"><span data-stu-id="4381b-204">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="4381b-205">Los documentos que incluyen la palabra clave Contoso (no distingue mayúsculas de minúsculas) y la palabra clave compensación o salario (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4381b-205">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="4381b-206">KQL</span><span class="sxs-lookup"><span data-stu-id="4381b-206">KQL</span></span></p>
<p><span data-ttu-id="4381b-207">RegEx</span><span class="sxs-lookup"><span data-stu-id="4381b-207">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="4381b-208">KQL: Contoso Y (Salario O Compensación)</span><span class="sxs-lookup"><span data-stu-id="4381b-208">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="4381b-209">RegEx: (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="4381b-209">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4381b-210">Confidencial</span><span class="sxs-lookup"><span data-stu-id="4381b-210">Confidential</span></span></td>
<td align="left"><span data-ttu-id="4381b-211">Documentos que contienen la frase Confidencial de Contoso (no distingue mayúsculas de minúsculas).</span><span class="sxs-lookup"><span data-stu-id="4381b-211">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="4381b-212">KQL</span><span class="sxs-lookup"><span data-stu-id="4381b-212">KQL</span></span></p>
<p><span data-ttu-id="4381b-213">RegEx</span><span class="sxs-lookup"><span data-stu-id="4381b-213">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="4381b-214">KQL: Confidencial de Contoso</span><span class="sxs-lookup"><span data-stu-id="4381b-214">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="4381b-215">RegEx: (?i)(\bConfidencial de Contoso\b)</span><span class="sxs-lookup"><span data-stu-id="4381b-215">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4381b-216">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="4381b-216">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="4381b-217">Documentos que incluyen la frase Secreto de Contoso (distingue mayúsculas de minúsculas) o Secreto-C#### donde # representa cualquier dígito.</span><span class="sxs-lookup"><span data-stu-id="4381b-217">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="4381b-218">KQL</span><span class="sxs-lookup"><span data-stu-id="4381b-218">KQL</span></span></p>
<p><span data-ttu-id="4381b-219">RegEx</span><span class="sxs-lookup"><span data-stu-id="4381b-219">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="4381b-220">KQL: Secreto de Contoso O Secreto-C\*</span><span class="sxs-lookup"><span data-stu-id="4381b-220">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="4381b-221">RegEx: (?i)(\bSecreto de Contoso\b)|(\bSecreto-C\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="4381b-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
