---
title: Buscar y encontrar datos personales
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
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Obtenga información sobre cómo buscar y encontrar datos personales en Office 365.
ms.openlocfilehash: d83e37db57443580e74b42e7b9bc89d440bf5319
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272405"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="ebc77-103">Buscar y encontrar datos personales</span><span class="sxs-lookup"><span data-stu-id="ebc77-103">Search for and find personal data</span></span>

<span data-ttu-id="ebc77-104">Los datos personales se definen muy globalmente en el RGPD como los datos que se refieren a una persona física identificada o identificable que reside de la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="ebc77-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="ebc77-105">Artículo 4: definiciones</span><span class="sxs-lookup"><span data-stu-id="ebc77-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="ebc77-106">“datos personales” se refiere a cualquier información sobre una persona física identificada o identificable (“interesado”); una persona identificable natural es una que puede identificarse, directa o indirectamente, especialmente con referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más elementos específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona natural;</span><span class="sxs-lookup"><span data-stu-id="ebc77-106">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="ebc77-107">Este artículo explica cómo buscar datos personales almacenados en SharePoint Online y OneDrive para la Empresa (que incluye los sitios de todos los grupos de Office 365 y Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="ebc77-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Office 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="ebc77-p101">Buscar datos personales sujetos al RGPD depende de usar tipos de información confidencial en Office 365. Estos definen cómo el proceso automatizado reconoce tipos específicos de información, como números de tarjetas de crédito y números de la Seguridad Social. En este momento, los tipos no pueden usarse para buscar datos en buzones de Exchange en reposo. Sin embargo, sí pueden utilizarse con directivas de prevención de pérdida de datos para buscar datos personales en correo en tránsito.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p101">Finding personal data subject to GDPR relies on using sensitive information types in Office 365. These define how the automated process recognizes specific information types such as health service numbers and credit card numbers. At this time these cannot be used to find data in Exchange mailboxes at rest. However, sensitive information types can be used with data loss prevention policies to find personal data in mail while in transit.</span></span>

<span data-ttu-id="ebc77-112">Aunque actualmente no puede usarse la Búsqueda de contenido para buscar datos personales almacenados en los buzones de Exchange Online, pueden usarse los tipos de información confidencial que establece para que el RGPD busque y proteja información personal cuando se envía por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ebc77-112">So, while you can’t currently use Content Search to find personal data at rest in Exchange Online mailboxes, you can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="ebc77-113">Usar la Búsqueda de contenido para buscar datos personales</span><span class="sxs-lookup"><span data-stu-id="ebc77-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="ebc77-p102">Microsoft recomienda un enfoque de tres fases para buscar datos personales en Office 365. El resto de este tema proporciona una guía para cada una de estas fases.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ebc77-116"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="ebc77-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="ebc77-117"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="ebc77-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ebc77-118">1. Buscar tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="ebc77-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="ebc77-p103">Empiece con tipos de información confidencial para buscar datos personales. Cree una consulta de búsqueda de contenido para cada tipo de información confidencial. Ejecute la consulta y analice los resultados.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="ebc77-122">Si es necesario, agregue parámetros a la consulta para reducir los falsos positivos:</span><span class="sxs-lookup"><span data-stu-id="ebc77-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="ebc77-123">Intervalo de recuento</span><span class="sxs-lookup"><span data-stu-id="ebc77-123">Count range</span></span></li>
    <li><span data-ttu-id="ebc77-124">Intervalo de confianza</span><span class="sxs-lookup"><span data-stu-id="ebc77-124">Confidence range</span></span></li>
    <li><span data-ttu-id="ebc77-125">Otras propiedades u operadores para consultas más complejas</span><span class="sxs-lookup"><span data-stu-id="ebc77-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="ebc77-126">Si es necesario, modifique el tipo de información confidencial para mejorar la precisión de su organización:</span><span class="sxs-lookup"><span data-stu-id="ebc77-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="ebc77-127">Ajuste el nivel de confianza directamente en los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="ebc77-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="ebc77-128">Agregue palabras clave.</span><span class="sxs-lookup"><span data-stu-id="ebc77-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="ebc77-129">Ajuste los requisitos de proximidad de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="ebc77-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ebc77-130">2. Usar el Lenguaje de consulta de palabras clave (KQL) para buscar datos personales adicionales en su entorno</span><span class="sxs-lookup"><span data-stu-id="ebc77-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="ebc77-131">Para buscar datos que no se incluyen en los tipos de información confidencial, use el lenguaje de consulta KQL para desarrollar consultas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ebc77-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="ebc77-132">Compruebe los resultados de estas búsquedas y ajuste la cadena de consulta KQL hasta obtener el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="ebc77-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ebc77-133">3. Crear nuevos tipos de información confidencial mediante las consultas KQL</span><span class="sxs-lookup"><span data-stu-id="ebc77-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="ebc77-p104">Después de optimizar las consultas KQL para encontrar los datos de destino, cree nuevos tipos de información confidencial mediante las consultas. Luego puede usar estos tipos de información confidencial con la Búsqueda de contenido, en las directivas DLP y otras herramientas, y en otras consultas KQL.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ebc77-p105">Próximamente, podrá crear y modificar tipos de información confidencial en una nueva interfaz de usuario en el Centro de seguridad y cumplimiento. Puede ver los resultados coincidentes dinámicamente y ajustar los tipos de información confidencial para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p105">Coming soon — You'll be able to create and modify sensitive information types in a new user interface in the Security and Compliance Center. You can dynamically see matching results and tune sensitive information types to meet your needs.</span></span>

## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="ebc77-138">Buscar tipos de información confidencial con la Búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="ebc77-138">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="ebc77-p106">Comience a buscar información personal mediante los tipos de información confidencial que se incluyen con Office 365. Se muestran en el Centro de seguridad y cumplimiento en Clasificación.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p106">Begin searching for personal data by using the sensitive information types that are included with Office 365. These are listed in the Security and Compliance Center under Classification.</span></span>

<span data-ttu-id="ebc77-p107">Este tema contiene una lista de tipos de información confidencial actuales que se aplican a los ciudadanos de la Unión Europea. Úselos como punto de partida. Compruebe el Centro de seguridad y cumplimiento para ver si hay adiciones que pueden ayudarle con el cumplimiento del RGPD.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p107">This topic includes a list of current sensitive information types that apply to citizens in the European Union. Use these as a starting point. Check Security and Compliance Center frequently for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="ebc77-144">Consulte este artículo: [Qué buscan los tipos de información confidencial](https://support.office.com/es-ES/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span><span class="sxs-lookup"><span data-stu-id="ebc77-144">Also see this article: [List of sensitive information types and what each one looks for](https://support.office.com/es-ES/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span></span>

<span data-ttu-id="ebc77-p108">Los tipos de información confidencial definen cómo el proceso automático reconoce tipos de información específicos como números de cuentas bancarias, números de la Seguridad Social y números de tarjeta de crédito. Los tipos de información confidencial también se conocen como condiciones. Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función. Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial. El nivel de confianza y la proximidad también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p108">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="ebc77-150">En este momento, los tipos de información confidencial no pueden usarse para buscar datos almacenados en buzones.</span><span class="sxs-lookup"><span data-stu-id="ebc77-150">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="ebc77-151">Usar la Búsqueda de contenido con tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="ebc77-151">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ebc77-152"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="ebc77-152"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="ebc77-153"><strong>Más información</strong></span><span class="sxs-lookup"><span data-stu-id="ebc77-153"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="ebc77-154">Vaya a Búsqueda de contenido en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ebc77-154">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="ebc77-155">En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** &gt; **Búsqueda de contenido**.</span><span class="sxs-lookup"><span data-stu-id="ebc77-155">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="ebc77-156">Consulte <a href="https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Ejecutar una Búsqueda de contenido en el Centro de seguridad y cumplimiento de Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="ebc77-156">See <a href="https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ebc77-157">Crear un nuevo elemento de búsqueda para cada tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="ebc77-157">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="ebc77-158">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebc77-158">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="ebc77-159">SensitiveType:”&lt;tipo&gt;”</span><span class="sxs-lookup"><span data-stu-id="ebc77-159">SensitiveType:”&lt;type&gt;”</span></span></p>
</blockquote>
<p><span data-ttu-id="ebc77-160">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ebc77-160">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="ebc77-161">SensitiveType:&quot;Número de pasaporte de Francia&quot;</span><span class="sxs-lookup"><span data-stu-id="ebc77-161">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="ebc77-p109">Establezca el ámbito de la búsqueda a SharePoint (incluye OneDrive para la Empresa). Asegúrese de que la sintaxis es exacta y no hay errores tipográficos o espacios adicionales.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p109">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="ebc77-164">Consulte <a href="https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Crear una consulta para buscar datos confidenciales almacenados en los sitios</a>.</span><span class="sxs-lookup"><span data-stu-id="ebc77-164">See <a href="https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ebc77-165">Revise los resultados de cada búsqueda</span><span class="sxs-lookup"><span data-stu-id="ebc77-165">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="ebc77-166">Busque estos tipos de problemas para determinar si la precisión de la consulta es adecuada:</span><span class="sxs-lookup"><span data-stu-id="ebc77-166">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="ebc77-167">Muchos falsos positivos</span><span class="sxs-lookup"><span data-stu-id="ebc77-167">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="ebc77-168">Faltan de instancias de datos conocidas</span><span class="sxs-lookup"><span data-stu-id="ebc77-168">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="ebc77-169">Consulte <a href="https://support.office.com/en-us/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Exportar resultados de búsqueda desde el Centro de seguridad y cumplimiento de Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="ebc77-169">See <a href="https://support.office.com/en-us/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Export Content Search results from the Office 365 Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="ebc77-170">Nota: si usa Mozilla Firefox o Chrome, es posible que primero deba descargar los informes con Internet Explorer o Edge para instalar el complemento necesario.</span><span class="sxs-lookup"><span data-stu-id="ebc77-170">Note: if you’re using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="ebc77-171">Tipos de información confidencial para datos de ciudadanos de la UE</span><span class="sxs-lookup"><span data-stu-id="ebc77-171">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="ebc77-p110">Empiece con estos tipos de información confidencial. Pronto se añadirán muchos más tipos de información confidencial para datos personales en países de la UE.</span><span class="sxs-lookup"><span data-stu-id="ebc77-p110">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="ebc77-174">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="ebc77-174">Belgium National Number</span></span>
>
> <span data-ttu-id="ebc77-175">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="ebc77-175">Credit Card Number</span></span>
>
> <span data-ttu-id="ebc77-176">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="ebc77-176">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="ebc77-177">Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="ebc77-177">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="ebc77-178">Número de tarjeta de identidad nacional checa</span><span class="sxs-lookup"><span data-stu-id="ebc77-178">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="ebc77-179">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="ebc77-179">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="ebc77-180">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="ebc77-180">EU Debit Card Number</span></span>
>
> <span data-ttu-id="ebc77-181">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="ebc77-181">Finland National ID</span></span>
>
> <span data-ttu-id="ebc77-182">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="ebc77-182">Finland Passport Number</span></span>
>
> <span data-ttu-id="ebc77-183">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="ebc77-183">France Driver's License Number</span></span>
>
> <span data-ttu-id="ebc77-184">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="ebc77-184">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="ebc77-185">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="ebc77-185">France Passport Number</span></span>
>
> <span data-ttu-id="ebc77-186">Número de la Seguridad Social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="ebc77-186">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="ebc77-187">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="ebc77-187">German Driver’s License Number</span></span>
>
> <span data-ttu-id="ebc77-188">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="ebc77-188">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="ebc77-189">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="ebc77-189">German Passport Number</span></span>
>
> <span data-ttu-id="ebc77-190">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="ebc77-190">Greece National ID Card</span></span>
>
> <span data-ttu-id="ebc77-191">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="ebc77-191">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="ebc77-192">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="ebc77-192">IP Address</span></span>
>
> <span data-ttu-id="ebc77-193">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="ebc77-193">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="ebc77-194">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="ebc77-194">Italy’s Driver’s License Number</span></span>
>
> <span data-ttu-id="ebc77-195">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="ebc77-195">Netherlands Citizen’s Service (BSN) Number</span></span>
>
> <span data-ttu-id="ebc77-196">Número de identidad de Noruega</span><span class="sxs-lookup"><span data-stu-id="ebc77-196">Norway Identity Number</span></span>
>
> <span data-ttu-id="ebc77-197">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="ebc77-197">Poland Identity Card</span></span>
>
> <span data-ttu-id="ebc77-198">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="ebc77-198">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="ebc77-199">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="ebc77-199">Poland Passport</span></span>
>
> <span data-ttu-id="ebc77-200">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="ebc77-200">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="ebc77-201">Número de la Seguridad Social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="ebc77-201">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="ebc77-202">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="ebc77-202">Sweden National ID</span></span>
>
> <span data-ttu-id="ebc77-203">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="ebc77-203">Sweden Passport Number</span></span>
>
> <span data-ttu-id="ebc77-p111">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ebc77-p111">U.K. Driver’s License Number</span></span>
>
> <span data-ttu-id="ebc77-p112">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ebc77-p112">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="ebc77-p113">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ebc77-p113">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="ebc77-p114">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="ebc77-p114">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="ebc77-p115">Número de pasaporte EE. UU./Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ebc77-p115">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="ebc77-214">Agregue parámetros a una consulta de tipo de información confidencial para afinar los resultados</span><span class="sxs-lookup"><span data-stu-id="ebc77-214">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="ebc77-215">Puede agregar estos parámetros a una consulta de tipo de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="ebc77-215">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="ebc77-216">Intervalo de recuento: define el número de repeticiones de información confidencial que un documento debe contener antes de que se incluya en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="ebc77-216">Count range — define the number of occurrences of sensitive information a document needs to contain before it’s included in the query results.</span></span>

-   <span data-ttu-id="ebc77-217">Intervalo de confianza: el nivel de confianza con el que el tipo confidencial detectado coincide en realidad, por ejemplo 85 (85 %).</span><span class="sxs-lookup"><span data-stu-id="ebc77-217">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="ebc77-218">Sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ebc77-218">Syntax:</span></span>

-   <span data-ttu-id="ebc77-219">SensitiveType:"\<tipo\>|\<intervalo de recuento\>|\<intervalo de confianza\>"</span><span class="sxs-lookup"><span data-stu-id="ebc77-219">SensitiveType:”\<type\>|\<count range\>|\<confidence range\>”</span></span>

<span data-ttu-id="ebc77-220">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="ebc77-220">Examples:</span></span>

-   <span data-ttu-id="ebc77-221">SensitiveType:"Número de tarjeta de crédito | 5" (devuelve únicamente los documentos que contienen exactamente cinco números de tarjeta de crédito)</span><span class="sxs-lookup"><span data-stu-id="ebc77-221">SensitiveType:“Credit Card Number|5” (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="ebc77-p116">SensitiveType:"Número de tarjeta de crédito | \*| 85... " (el intervalo de confianza es 85 % o superior)</span><span class="sxs-lookup"><span data-stu-id="ebc77-p116">SensitiveType:“Credit Card Number|\*|85..” (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="ebc77-224">Nota: "SensitiveType" distingue mayúsculas de minúsculas, pero el resto de la consulta no.</span><span class="sxs-lookup"><span data-stu-id="ebc77-224">Note: “SensitiveType” is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="ebc77-p117">También puede usar propiedades y operadores para mostrar cómo puede refinar las consultas. Para obtener más información y ejemplos, consulte [Crear una consulta para buscar datos confidenciales almacenados en los sitios](https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span><span class="sxs-lookup"><span data-stu-id="ebc77-p117">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span></span>
