---
title: Buscar y encontrar datos personales
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Obtenga información sobre cómo buscar y encontrar datos personales en Office 365.
ms.openlocfilehash: b63cf930a38feab6df815b5350d60184a6339927
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158522"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="dcb70-103">Buscar y encontrar datos personales</span><span class="sxs-lookup"><span data-stu-id="dcb70-103">Search for and find personal data</span></span>

<span data-ttu-id="dcb70-104">Los datos personales se definen muy globalmente en el RGPD como los datos que se refieren a una persona física identificada o identificable que reside de la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="dcb70-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="dcb70-105">Artículo 4: definiciones</span><span class="sxs-lookup"><span data-stu-id="dcb70-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="dcb70-106">“datos personales” se refiere a cualquier información sobre una persona física identificada o identificable (“interesado”); una persona identificable natural es una que puede identificarse, directa o indirectamente, especialmente con referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más elementos específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona natural;</span><span class="sxs-lookup"><span data-stu-id="dcb70-106">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="dcb70-107">Este artículo explica cómo buscar datos personales almacenados en SharePoint Online y OneDrive para la Empresa (que incluye los sitios de todos los grupos de Office 365 y Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="dcb70-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Office 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="dcb70-p101">Buscar datos personales sujetos al RGPD depende de usar tipos de información confidencial en Office 365. Estos definen cómo el proceso automatizado reconoce tipos específicos de información, como números de tarjetas de crédito y números de la Seguridad Social. En este momento, los tipos no pueden usarse para buscar datos en buzones de Exchange en reposo. Sin embargo, sí pueden utilizarse con directivas de prevención de pérdida de datos para buscar datos personales en correo en tránsito.</span><span class="sxs-lookup"><span data-stu-id="dcb70-p101">Finding personal data subject to GDPR relies on using sensitive information types in Office 365. These define how the automated process recognizes specific information types such as health service numbers and credit card numbers. At this time these cannot be used to find data in Exchange mailboxes at rest. However, sensitive information types can be used with data loss prevention policies to find personal data in mail while in transit.</span></span>

<span data-ttu-id="dcb70-112">Aunque actualmente no puede usarse la Búsqueda de contenido para buscar datos personales almacenados en los buzones de Exchange Online, pueden usarse los tipos de información confidencial que establece para que el RGPD busque y proteja información personal cuando se envía por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dcb70-112">So, while you can’t currently use Content Search to find personal data at rest in Exchange Online mailboxes, you can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="dcb70-113">Usar la Búsqueda de contenido para buscar datos personales</span><span class="sxs-lookup"><span data-stu-id="dcb70-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="dcb70-p102">Microsoft recomienda un enfoque de tres fases para buscar datos personales en Office 365. El resto de este tema proporciona una guía para cada una de estas fases.</span><span class="sxs-lookup"><span data-stu-id="dcb70-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dcb70-116"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="dcb70-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="dcb70-117"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="dcb70-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcb70-118">1. Buscar tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="dcb70-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcb70-p103">Empiece con tipos de información confidencial para buscar datos personales. Cree una consulta de búsqueda de contenido para cada tipo de información confidencial. Ejecute la consulta y analice los resultados.</span><span class="sxs-lookup"><span data-stu-id="dcb70-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="dcb70-122">Si es necesario, agregue parámetros a la consulta para reducir los falsos positivos:</span><span class="sxs-lookup"><span data-stu-id="dcb70-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="dcb70-123">Intervalo de recuento</span><span class="sxs-lookup"><span data-stu-id="dcb70-123">Count range</span></span></li>
    <li><span data-ttu-id="dcb70-124">Intervalo de confianza</span><span class="sxs-lookup"><span data-stu-id="dcb70-124">Confidence range</span></span></li>
    <li><span data-ttu-id="dcb70-125">Otras propiedades u operadores para consultas más complejas</span><span class="sxs-lookup"><span data-stu-id="dcb70-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="dcb70-126">Si es necesario, modifique el tipo de información confidencial para mejorar la precisión de su organización:</span><span class="sxs-lookup"><span data-stu-id="dcb70-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="dcb70-127">Ajuste el nivel de confianza directamente en los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="dcb70-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="dcb70-128">Agregue palabras clave.</span><span class="sxs-lookup"><span data-stu-id="dcb70-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="dcb70-129">Ajuste los requisitos de proximidad de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="dcb70-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcb70-130">2. Usar el Lenguaje de consulta de palabras clave (KQL) para buscar datos personales adicionales en su entorno</span><span class="sxs-lookup"><span data-stu-id="dcb70-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcb70-131">Para buscar datos que no se incluyen en los tipos de información confidencial, use el lenguaje de consulta KQL para desarrollar consultas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="dcb70-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="dcb70-132">Compruebe los resultados de estas búsquedas y ajuste la cadena de consulta KQL hasta obtener el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="dcb70-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcb70-133">3. Crear nuevos tipos de información confidencial mediante las consultas KQL</span><span class="sxs-lookup"><span data-stu-id="dcb70-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="dcb70-p104">Después de optimizar las consultas KQL para encontrar los datos de destino, cree nuevos tipos de información confidencial mediante las consultas. Luego puede usar estos tipos de información confidencial con la Búsqueda de contenido, en las directivas DLP y otras herramientas, y en otras consultas KQL.</span><span class="sxs-lookup"><span data-stu-id="dcb70-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="dcb70-136">Buscar tipos de información confidencial con la Búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="dcb70-136">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="dcb70-137">Comience a buscar información personal mediante los tipos de información confidencial que se incluyen con Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcb70-137">Begin searching for personal data by using the sensitive information types that are included with Office 365.</span></span> <span data-ttu-id="dcb70-138">Se muestran en el Centro de seguridad y cumplimiento en Clasificación.</span><span class="sxs-lookup"><span data-stu-id="dcb70-138">These are listed under Classification in the security center and compliance center.</span></span>

<span data-ttu-id="dcb70-139">Este tema contiene una lista de algunos tipos de información confidencial que se aplican a los ciudadanos de la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="dcb70-139">This topic includes a list of some sensitive information types that apply to citizens in the European Union.</span></span> <span data-ttu-id="dcb70-140">Consulte el centro de seguridad o en el centro de cumplimiento para agregar nuevos tipos que pueden ayudarle con el cumplimiento del RGPD.</span><span class="sxs-lookup"><span data-stu-id="dcb70-140">Check the security center or the compliance center for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="dcb70-141">Consulte este artículo: [Qué buscan los tipos de información confidencial](https://support.office.com/es-ES/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span><span class="sxs-lookup"><span data-stu-id="dcb70-141">Also see this article: [List of sensitive information types and what each one looks for](https://support.office.com/en-us/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span></span>

<span data-ttu-id="dcb70-p107">Los tipos de información confidencial definen cómo el proceso automático reconoce tipos de información específicos como números de cuentas bancarias, números de la Seguridad Social y números de tarjeta de crédito. Los tipos de información confidencial también se conocen como condiciones. Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función. Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial. El nivel de confianza y la proximidad también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="dcb70-p107">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="dcb70-147">En este momento, los tipos de información confidencial no pueden usarse para buscar datos almacenados en buzones.</span><span class="sxs-lookup"><span data-stu-id="dcb70-147">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="dcb70-148">Usar la Búsqueda de contenido con tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="dcb70-148">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dcb70-149"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="dcb70-149"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="dcb70-150"><strong>Más información</strong></span><span class="sxs-lookup"><span data-stu-id="dcb70-150"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="dcb70-151">Vaya a Búsqueda de contenido en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="dcb70-151">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcb70-152">En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** &gt; **Búsqueda de contenido**.</span><span class="sxs-lookup"><span data-stu-id="dcb70-152">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="dcb70-153">Consulte <a href="https://support.office.com/es-ES/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Ejecutar una Búsqueda de contenido en el Centro de seguridad y cumplimiento de Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="dcb70-153">See <a href="https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcb70-154">Crear un nuevo elemento de búsqueda para cada tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="dcb70-154">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcb70-155">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="dcb70-155">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="dcb70-156">SensitiveType:”&lt;tipo&gt;”</span><span class="sxs-lookup"><span data-stu-id="dcb70-156">SensitiveType:”&lt;type&gt;”</span></span></p>
</blockquote>
<p><span data-ttu-id="dcb70-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dcb70-157">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="dcb70-158">SensitiveType:&quot;Número de pasaporte de Francia&quot;</span><span class="sxs-lookup"><span data-stu-id="dcb70-158">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="dcb70-p108">Establezca el ámbito de la búsqueda a SharePoint (incluye OneDrive para la Empresa). Asegúrese de que la sintaxis es exacta y no hay errores tipográficos o espacios adicionales.</span><span class="sxs-lookup"><span data-stu-id="dcb70-p108">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="dcb70-161">Consulte <a href="https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Crear una consulta para buscar datos confidenciales almacenados en los sitios</a>.</span><span class="sxs-lookup"><span data-stu-id="dcb70-161">See <a href="https://support.office.com/en-us/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcb70-162">Revise los resultados de cada búsqueda</span><span class="sxs-lookup"><span data-stu-id="dcb70-162">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcb70-163">Busque estos tipos de problemas para determinar si la precisión de la consulta es adecuada:</span><span class="sxs-lookup"><span data-stu-id="dcb70-163">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="dcb70-164">Muchos falsos positivos</span><span class="sxs-lookup"><span data-stu-id="dcb70-164">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="dcb70-165">Faltan de instancias de datos conocidas</span><span class="sxs-lookup"><span data-stu-id="dcb70-165">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="dcb70-166">Consulte <a href="https://support.office.com/es-ES/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Exportar resultados de búsqueda desde el Centro de seguridad y cumplimiento de Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="dcb70-166">See <a href="https://support.office.com/en-us/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Export Content Search results from the Office 365 Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="dcb70-167">Nota: si usa Mozilla Firefox o Chrome, es posible que primero deba descargar los informes con Internet Explorer o Edge para instalar el complemento necesario.</span><span class="sxs-lookup"><span data-stu-id="dcb70-167">Note: if you’re using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="dcb70-168">Tipos de información confidencial para datos de ciudadanos de la UE</span><span class="sxs-lookup"><span data-stu-id="dcb70-168">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="dcb70-p109">Empiece con estos tipos de información confidencial. Pronto se añadirán muchos más tipos de información confidencial para datos personales en países de la UE.</span><span class="sxs-lookup"><span data-stu-id="dcb70-p109">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="dcb70-171">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="dcb70-171">Belgium National Number</span></span>
>
> <span data-ttu-id="dcb70-172">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="dcb70-172">Credit Card Number</span></span>
>
> <span data-ttu-id="dcb70-173">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="dcb70-173">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="dcb70-174">Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="dcb70-174">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="dcb70-175">Número de tarjeta de identidad nacional checa</span><span class="sxs-lookup"><span data-stu-id="dcb70-175">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="dcb70-176">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="dcb70-176">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="dcb70-177">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="dcb70-177">EU Debit Card Number</span></span>
>
> <span data-ttu-id="dcb70-178">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="dcb70-178">Finland National ID</span></span>
>
> <span data-ttu-id="dcb70-179">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="dcb70-179">Finland Passport Number</span></span>
>
> <span data-ttu-id="dcb70-180">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="dcb70-180">France Driver's License Number</span></span>
>
> <span data-ttu-id="dcb70-181">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="dcb70-181">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="dcb70-182">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="dcb70-182">France Passport Number</span></span>
>
> <span data-ttu-id="dcb70-183">Número de la Seguridad Social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="dcb70-183">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="dcb70-184">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="dcb70-184">German Driver’s License Number</span></span>
>
> <span data-ttu-id="dcb70-185">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="dcb70-185">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="dcb70-186">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="dcb70-186">German Passport Number</span></span>
>
> <span data-ttu-id="dcb70-187">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="dcb70-187">Greece National ID Card</span></span>
>
> <span data-ttu-id="dcb70-188">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="dcb70-188">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="dcb70-189">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="dcb70-189">IP Address</span></span>
>
> <span data-ttu-id="dcb70-190">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="dcb70-190">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="dcb70-191">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="dcb70-191">Italy’s Driver’s License Number</span></span>
>
> <span data-ttu-id="dcb70-192">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="dcb70-192">Netherlands Citizen’s Service (BSN) Number</span></span>
>
> <span data-ttu-id="dcb70-193">Número de identidad de Noruega</span><span class="sxs-lookup"><span data-stu-id="dcb70-193">Norway Identity Number</span></span>
>
> <span data-ttu-id="dcb70-194">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="dcb70-194">Poland Identity Card</span></span>
>
> <span data-ttu-id="dcb70-195">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="dcb70-195">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="dcb70-196">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="dcb70-196">Poland Passport</span></span>
>
> <span data-ttu-id="dcb70-197">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="dcb70-197">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="dcb70-198">Número de la Seguridad Social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="dcb70-198">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="dcb70-199">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="dcb70-199">Sweden National ID</span></span>
>
> <span data-ttu-id="dcb70-200">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="dcb70-200">Sweden Passport Number</span></span>
>
> <span data-ttu-id="dcb70-p110">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="dcb70-p110">U.K. Driver’s License Number</span></span>
>
> <span data-ttu-id="dcb70-p111">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="dcb70-p111">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="dcb70-p112">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="dcb70-p112">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="dcb70-p113">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="dcb70-p113">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="dcb70-p114">Número de pasaporte EE. UU./Reino Unido</span><span class="sxs-lookup"><span data-stu-id="dcb70-p114">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="dcb70-211">Agregue parámetros a una consulta de tipo de información confidencial para afinar los resultados</span><span class="sxs-lookup"><span data-stu-id="dcb70-211">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="dcb70-212">Puede agregar estos parámetros a una consulta de tipo de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="dcb70-212">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="dcb70-213">Intervalo de recuento: define el número de repeticiones de información confidencial que un documento debe contener antes de que se incluya en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="dcb70-213">Count range — define the number of occurrences of sensitive information a document needs to contain before it’s included in the query results.</span></span>

-   <span data-ttu-id="dcb70-214">Intervalo de confianza: el nivel de confianza con el que el tipo confidencial detectado coincide en realidad, por ejemplo 85 (85 %).</span><span class="sxs-lookup"><span data-stu-id="dcb70-214">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="dcb70-215">Sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dcb70-215">Syntax:</span></span>

-   <span data-ttu-id="dcb70-216">SensitiveType:"\<tipo\>|\<intervalo de recuento\>|\<intervalo de confianza\>"</span><span class="sxs-lookup"><span data-stu-id="dcb70-216">SensitiveType:”\<type\>|\<count range\>|\<confidence range\>”</span></span>

<span data-ttu-id="dcb70-217">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="dcb70-217">Examples:</span></span>

-   <span data-ttu-id="dcb70-218">SensitiveType:"Número de tarjeta de crédito | 5" (devuelve únicamente los documentos que contienen exactamente cinco números de tarjeta de crédito)</span><span class="sxs-lookup"><span data-stu-id="dcb70-218">SensitiveType:“Credit Card Number|5” (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="dcb70-p115">SensitiveType:"Número de tarjeta de crédito | \*| 85... " (el intervalo de confianza es 85 % o superior)</span><span class="sxs-lookup"><span data-stu-id="dcb70-p115">SensitiveType:“Credit Card Number|\*|85..” (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="dcb70-221">Nota: "SensitiveType" distingue mayúsculas de minúsculas, pero el resto de la consulta no.</span><span class="sxs-lookup"><span data-stu-id="dcb70-221">Note: “SensitiveType” is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="dcb70-p116">También puede usar propiedades y operadores para mostrar cómo puede refinar las consultas. Para obtener más información y ejemplos, consulte [Crear una consulta para buscar datos confidenciales almacenados en los sitios](https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span><span class="sxs-lookup"><span data-stu-id="dcb70-p116">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://support.office.com/en-us/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span></span>
