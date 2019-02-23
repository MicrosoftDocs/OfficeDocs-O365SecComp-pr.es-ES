---
title: Qué buscan los tipos de información confidencial
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye 80 tipos de información confidencial listos para que pueda usarlos en las directivas de DLP. En este tema se enumeran todos estos tipos de información confidencial y se muestra el aspecto de una directiva DLP cuando detecta cada tipo.
ms.openlocfilehash: 17fb0b8d745168f8000fba9e6fc42f3c255a1937
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216360"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="72dfe-104">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="72dfe-104">What the sensitive information types look for</span></span>

<span data-ttu-id="72dfe-p102">La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP. En este tema se enumeran todos estos tipos de información confidencial y se muestra el aspecto de una directiva DLP cuando detecta cada tipo. Un patrón que puede identificarse mediante una expresión regular o una función define un tipo de información confidencial. Además, las evidencias confirmativas, como las palabras clave y las sumas de comprobación, se pueden usar para identificar un tipo de información confidencial. El nivel de confianza y la proximidad también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="72dfe-110">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="72dfe-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-111">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-111">Format</span></span>

<span data-ttu-id="72dfe-112">9 dígitos, que pueden tener un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-113">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-113">Pattern</span></span>

<span data-ttu-id="72dfe-114">Con formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-114">Formatted:</span></span>
- <span data-ttu-id="72dfe-115">Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="72dfe-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="72dfe-116">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-116">A hyphen</span></span>
- <span data-ttu-id="72dfe-117">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-117">Four digits</span></span>
- <span data-ttu-id="72dfe-118">Un guión</span><span class="sxs-lookup"><span data-stu-id="72dfe-118">A hyphen</span></span>
- <span data-ttu-id="72dfe-119">Un dígito</span><span class="sxs-lookup"><span data-stu-id="72dfe-119">A digit</span></span>

<span data-ttu-id="72dfe-120">Sin formato: 9 dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="72dfe-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="72dfe-121">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-121">Checksum</span></span>

<span data-ttu-id="72dfe-122">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-123">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-123">Definition</span></span>

<span data-ttu-id="72dfe-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-125">La función Func_aba_routing encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-126">Se encuentra una palabra clave de Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="72dfe-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="72dfe-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="72dfe-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="72dfe-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="72dfe-129">aba</span><span class="sxs-lookup"><span data-stu-id="72dfe-129">aba</span></span>
- <span data-ttu-id="72dfe-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="72dfe-130">aba #</span></span>
- <span data-ttu-id="72dfe-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="72dfe-131">aba routing #</span></span>
- <span data-ttu-id="72dfe-132">número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="72dfe-132">aba routing number</span></span>
- <span data-ttu-id="72dfe-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="72dfe-133">aba#</span></span>
- <span data-ttu-id="72dfe-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="72dfe-134">abarouting#</span></span>
- <span data-ttu-id="72dfe-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="72dfe-135">aba number</span></span>
- <span data-ttu-id="72dfe-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="72dfe-136">abaroutingnumber</span></span>
- <span data-ttu-id="72dfe-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="72dfe-137">american bank association routing #</span></span>
- <span data-ttu-id="72dfe-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="72dfe-138">american bank association routing number</span></span>
- <span data-ttu-id="72dfe-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="72dfe-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="72dfe-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="72dfe-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="72dfe-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="72dfe-141">bank routing number</span></span>
- <span data-ttu-id="72dfe-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="72dfe-142">bankrouting#</span></span>
- <span data-ttu-id="72dfe-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="72dfe-143">bankroutingnumber</span></span>
- <span data-ttu-id="72dfe-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="72dfe-144">routing transit number</span></span>
- <span data-ttu-id="72dfe-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="72dfe-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="72dfe-146">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="72dfe-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-147">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-147">Format</span></span>

<span data-ttu-id="72dfe-148">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="72dfe-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-149">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-149">Pattern</span></span>

<span data-ttu-id="72dfe-150">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-150">Eight digits:</span></span>
- <span data-ttu-id="72dfe-151">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-151">Two digits</span></span>
- <span data-ttu-id="72dfe-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="72dfe-152">A period</span></span>
- <span data-ttu-id="72dfe-153">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-153">Three digits</span></span>
- <span data-ttu-id="72dfe-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="72dfe-154">A period</span></span>
- <span data-ttu-id="72dfe-155">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-156">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-156">Checksum</span></span>

<span data-ttu-id="72dfe-157">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-158">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-158">Definition</span></span>

<span data-ttu-id="72dfe-159">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-160">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-161">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="72dfe-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="72dfe-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="72dfe-164">Número de identidad nacional de Argentina
</span><span class="sxs-lookup"><span data-stu-id="72dfe-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="72dfe-165">Identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-165">Identity</span></span> 
- <span data-ttu-id="72dfe-166">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="72dfe-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="72dfe-167">DNI</span></span> 
- <span data-ttu-id="72dfe-168">Registro Nacional de NIC de personas</span><span class="sxs-lookup"><span data-stu-id="72dfe-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="72dfe-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="72dfe-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="72dfe-170">Registro nacional de las personas
</span><span class="sxs-lookup"><span data-stu-id="72dfe-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="72dfe-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="72dfe-171">Identidad</span></span> 
- <span data-ttu-id="72dfe-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="72dfe-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="72dfe-173">Número de cuenta bancaria de Australia</span><span class="sxs-lookup"><span data-stu-id="72dfe-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-174">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-174">Format</span></span>

<span data-ttu-id="72dfe-175">De 6 a 10 dígitos con o sin número de sucursal bancaria de estado</span><span class="sxs-lookup"><span data-stu-id="72dfe-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-176">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-176">Pattern</span></span>

<span data-ttu-id="72dfe-p103">El número de cuenta es de 6-10 dígitos. Número de sucursal estatal del Banco de Australia:</span><span class="sxs-lookup"><span data-stu-id="72dfe-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="72dfe-179">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-179">Three digits</span></span> 
- <span data-ttu-id="72dfe-180">Un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-180">A hyphen</span></span> 
- <span data-ttu-id="72dfe-181">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-182">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-182">Checksum</span></span>

<span data-ttu-id="72dfe-183">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-184">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-184">Definition</span></span>

<span data-ttu-id="72dfe-185">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-186">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="72dfe-187">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="72dfe-188">La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="72dfe-189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-190">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="72dfe-191">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="72dfe-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="72dfe-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="72dfe-194">swift bank code</span></span>
- <span data-ttu-id="72dfe-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="72dfe-195">correspondent bank</span></span>
- <span data-ttu-id="72dfe-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="72dfe-196">base currency</span></span>
- <span data-ttu-id="72dfe-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="72dfe-197">usa account</span></span>
- <span data-ttu-id="72dfe-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="72dfe-198">holder address</span></span>
- <span data-ttu-id="72dfe-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="72dfe-199">bank address</span></span>
- <span data-ttu-id="72dfe-200">
information account</span><span class="sxs-lookup"><span data-stu-id="72dfe-200">information account</span></span>
- <span data-ttu-id="72dfe-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="72dfe-201">fund transfers</span></span>
- <span data-ttu-id="72dfe-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="72dfe-202">bank charges</span></span>
- <span data-ttu-id="72dfe-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="72dfe-203">bank details</span></span>
- <span data-ttu-id="72dfe-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="72dfe-204">banking information</span></span>
- <span data-ttu-id="72dfe-205">
full names</span><span class="sxs-lookup"><span data-stu-id="72dfe-205">full names</span></span>
- <span data-ttu-id="72dfe-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="72dfe-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="72dfe-207">Número de licencia de conducción de Australia</span><span class="sxs-lookup"><span data-stu-id="72dfe-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-208">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-208">Format</span></span>

<span data-ttu-id="72dfe-209">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-210">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-210">Pattern</span></span>

<span data-ttu-id="72dfe-211">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="72dfe-212">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-213">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-213">Two digits</span></span> 
- <span data-ttu-id="72dfe-214">Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="72dfe-215">O bien</span><span class="sxs-lookup"><span data-stu-id="72dfe-215">OR</span></span>

- <span data-ttu-id="72dfe-216">1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-217">4-9 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-217">4-9 digits</span></span>

<span data-ttu-id="72dfe-218">O bien</span><span class="sxs-lookup"><span data-stu-id="72dfe-218">OR</span></span>

- <span data-ttu-id="72dfe-219">Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-220">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-220">Checksum</span></span>

<span data-ttu-id="72dfe-221">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-222">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-222">Definition</span></span>

<span data-ttu-id="72dfe-223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-224">La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-225">Se encuentra una palabra clave de Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="72dfe-226">No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="72dfe-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="72dfe-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="72dfe-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="72dfe-229">international driving permits</span></span>
- <span data-ttu-id="72dfe-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="72dfe-230">australian automobile association</span></span>
- <span data-ttu-id="72dfe-231">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="72dfe-231">international driving permit</span></span>
- <span data-ttu-id="72dfe-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="72dfe-232">DriverLicence</span></span>
- <span data-ttu-id="72dfe-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="72dfe-233">DriverLicences</span></span>
- <span data-ttu-id="72dfe-234">Lic del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-234">Driver Lic</span></span>
- <span data-ttu-id="72dfe-235">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-235">Driver Licence</span></span>
- <span data-ttu-id="72dfe-236">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-236">Driver Licences</span></span>
- <span data-ttu-id="72dfe-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-237">DriversLic</span></span>
- <span data-ttu-id="72dfe-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="72dfe-238">DriversLicence</span></span>
- <span data-ttu-id="72dfe-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="72dfe-239">DriversLicences</span></span>
- <span data-ttu-id="72dfe-240">Lic de los drivers</span><span class="sxs-lookup"><span data-stu-id="72dfe-240">Drivers Lic</span></span>
- <span data-ttu-id="72dfe-241">Controladores conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-241">Drivers Lics</span></span>
- <span data-ttu-id="72dfe-242">Licencia de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-242">Drivers Licence</span></span>
- <span data-ttu-id="72dfe-243">Licencias de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-243">Drivers Licences</span></span>
- <span data-ttu-id="72dfe-244">N.º carné</span><span class="sxs-lookup"><span data-stu-id="72dfe-244">Driver'Lic</span></span>
- <span data-ttu-id="72dfe-245">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="72dfe-245">Driver'Lics</span></span>
- <span data-ttu-id="72dfe-246">N.º carné</span><span class="sxs-lookup"><span data-stu-id="72dfe-246">Driver'Licence</span></span>
- <span data-ttu-id="72dfe-247">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="72dfe-247">Driver'Licences</span></span>
- <span data-ttu-id="72dfe-248">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-248">Driver' Lic</span></span>
- <span data-ttu-id="72dfe-249">Controlador de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-249">Driver' Lics</span></span>
- <span data-ttu-id="72dfe-250">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-250">Driver' Licence</span></span>
- <span data-ttu-id="72dfe-251">Licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-251">Driver' Licences</span></span>
- <span data-ttu-id="72dfe-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-252">Driver'sLic</span></span>
- <span data-ttu-id="72dfe-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="72dfe-253">Driver'sLics</span></span>
- <span data-ttu-id="72dfe-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="72dfe-254">Driver'sLicence</span></span>
- <span data-ttu-id="72dfe-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="72dfe-255">Driver'sLicences</span></span>
- <span data-ttu-id="72dfe-256">Lic del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-256">Driver's Lic</span></span>
- <span data-ttu-id="72dfe-257">Conducción del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-257">Driver's Lics</span></span>
- <span data-ttu-id="72dfe-258">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-258">Driver's Licence</span></span>
- <span data-ttu-id="72dfe-259">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-259">Driver's Licences</span></span>
- <span data-ttu-id="72dfe-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-260">DriverLic#</span></span>
- <span data-ttu-id="72dfe-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-261">DriverLics#</span></span>
- <span data-ttu-id="72dfe-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="72dfe-262">DriverLicence#</span></span>
- <span data-ttu-id="72dfe-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="72dfe-263">DriverLicences#</span></span>
- <span data-ttu-id="72dfe-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="72dfe-264">Driver Lic#</span></span>
- <span data-ttu-id="72dfe-265">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-265">Driver Lics#</span></span>
- <span data-ttu-id="72dfe-266">N.º de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-266">Driver Licence#</span></span>
- <span data-ttu-id="72dfe-267">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-267">Driver Licences#</span></span>
- <span data-ttu-id="72dfe-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-268">DriversLic#</span></span>
- <span data-ttu-id="72dfe-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-269">DriversLics#</span></span>
- <span data-ttu-id="72dfe-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="72dfe-270">DriversLicence#</span></span>
- <span data-ttu-id="72dfe-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="72dfe-271">DriversLicences#</span></span>
- <span data-ttu-id="72dfe-272">N.º de Lic de los conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-272">Drivers Lic#</span></span>
- <span data-ttu-id="72dfe-273">Controladores conducción #</span><span class="sxs-lookup"><span data-stu-id="72dfe-273">Drivers Lics#</span></span>
- <span data-ttu-id="72dfe-274">N.º de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-274">Drivers Licence#</span></span>
- <span data-ttu-id="72dfe-275">N.º de licencias de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-275">Drivers Licences#</span></span>
- <span data-ttu-id="72dfe-276">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-276">Driver'Lic#</span></span>
- <span data-ttu-id="72dfe-277">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-277">Driver'Lics#</span></span>
- <span data-ttu-id="72dfe-278">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-278">Driver'Licence#</span></span>
- <span data-ttu-id="72dfe-279">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-279">Driver'Licences#</span></span>
- <span data-ttu-id="72dfe-280">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-280">Driver' Lic#</span></span>
- <span data-ttu-id="72dfe-281">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-281">Driver' Lics#</span></span>
- <span data-ttu-id="72dfe-282">N.º de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-282">Driver' Licence#</span></span>
- <span data-ttu-id="72dfe-283">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-283">Driver' Licences#</span></span>
- <span data-ttu-id="72dfe-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-284">Driver'sLic#</span></span>
- <span data-ttu-id="72dfe-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-285">Driver'sLics#</span></span>
- <span data-ttu-id="72dfe-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="72dfe-286">Driver'sLicence#</span></span>
- <span data-ttu-id="72dfe-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="72dfe-287">Driver'sLicences#</span></span>
- <span data-ttu-id="72dfe-288">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-288">Driver's Lic#</span></span>
- <span data-ttu-id="72dfe-289">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-289">Driver's Lics#</span></span>
- <span data-ttu-id="72dfe-290">Número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-290">Driver's Licence#</span></span>
- <span data-ttu-id="72dfe-291">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="72dfe-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="72dfe-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="72dfe-293">aaa</span><span class="sxs-lookup"><span data-stu-id="72dfe-293">aaa</span></span>
- <span data-ttu-id="72dfe-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-294">DriverLicense</span></span>
- <span data-ttu-id="72dfe-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-295">DriverLicenses</span></span>
- <span data-ttu-id="72dfe-296">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-296">Driver License</span></span>
- <span data-ttu-id="72dfe-297">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-297">Driver Licenses</span></span>
- <span data-ttu-id="72dfe-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-298">DriversLicense</span></span>
- <span data-ttu-id="72dfe-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-299">DriversLicenses</span></span>
- <span data-ttu-id="72dfe-300">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-300">Drivers License</span></span>
- <span data-ttu-id="72dfe-301">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-301">Drivers Licenses</span></span>
- <span data-ttu-id="72dfe-302">Conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-302">Driver'License</span></span>
- <span data-ttu-id="72dfe-303">Conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-303">Driver'Licenses</span></span>
- <span data-ttu-id="72dfe-304">Licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-304">Driver' License</span></span>
- <span data-ttu-id="72dfe-305">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-305">Driver' Licenses</span></span>
- <span data-ttu-id="72dfe-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-306">Driver'sLicense</span></span>
- <span data-ttu-id="72dfe-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-307">Driver'sLicenses</span></span>
- <span data-ttu-id="72dfe-308">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-308">Driver's License</span></span>
- <span data-ttu-id="72dfe-309">Licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-309">Driver's Licenses</span></span>
- <span data-ttu-id="72dfe-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-310">DriverLicense#</span></span>
- <span data-ttu-id="72dfe-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-311">DriverLicenses#</span></span>
- <span data-ttu-id="72dfe-312">N.º de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-312">Driver License#</span></span>
- <span data-ttu-id="72dfe-313">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-313">Driver Licenses#</span></span>
- <span data-ttu-id="72dfe-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-314">DriversLicense#</span></span>
- <span data-ttu-id="72dfe-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-315">DriversLicenses#</span></span>
- <span data-ttu-id="72dfe-316">N.º de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-316">Drivers License#</span></span>
- <span data-ttu-id="72dfe-317">N.º de licencias de impulsores</span><span class="sxs-lookup"><span data-stu-id="72dfe-317">Drivers Licenses#</span></span>
- <span data-ttu-id="72dfe-318">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-318">Driver'License#</span></span>
- <span data-ttu-id="72dfe-319">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-319">Driver'Licenses#</span></span>
- <span data-ttu-id="72dfe-320">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-320">Driver' License#</span></span>
- <span data-ttu-id="72dfe-321">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-321">Driver' Licenses#</span></span>
- <span data-ttu-id="72dfe-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-322">Driver'sLicense#</span></span>
- <span data-ttu-id="72dfe-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="72dfe-324">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-324">Driver's License#</span></span>
- <span data-ttu-id="72dfe-325">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="72dfe-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="72dfe-326">Número de cuenta médica de Australia</span><span class="sxs-lookup"><span data-stu-id="72dfe-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-327">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-327">Format</span></span>

<span data-ttu-id="72dfe-328">Entre 10 y 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-329">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-329">Pattern</span></span>

<span data-ttu-id="72dfe-330">Entre 10 y 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-330">10-11 digits:</span></span>
- <span data-ttu-id="72dfe-331">el primer dígito está en el intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="72dfe-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="72dfe-332">El noveno dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="72dfe-333">El décimo dígito es el dígito de emisión</span><span class="sxs-lookup"><span data-stu-id="72dfe-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="72dfe-334">El undécimo dígito (opcional) es el número individual</span><span class="sxs-lookup"><span data-stu-id="72dfe-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-335">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-335">Checksum</span></span>

<span data-ttu-id="72dfe-336">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-337">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-337">Definition</span></span>

<span data-ttu-id="72dfe-338">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-339">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-340">Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="72dfe-341">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-341">The checksum passes.</span></span>

<span data-ttu-id="72dfe-342">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-343">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-344">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-344">The checksum passes.</span></span>

```
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-345">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="72dfe-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="72dfe-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="72dfe-347">bank account details</span></span>
- <span data-ttu-id="72dfe-348">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="72dfe-348">medicare payments</span></span>
- <span data-ttu-id="72dfe-349">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="72dfe-349">mortgage account</span></span>
- <span data-ttu-id="72dfe-350">
bank payments</span><span class="sxs-lookup"><span data-stu-id="72dfe-350">bank payments</span></span>
- <span data-ttu-id="72dfe-351">
information branch</span><span class="sxs-lookup"><span data-stu-id="72dfe-351">information branch</span></span>
- <span data-ttu-id="72dfe-352">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="72dfe-352">credit card loan</span></span>
- <span data-ttu-id="72dfe-353">
department of human services</span><span class="sxs-lookup"><span data-stu-id="72dfe-353">department of human services</span></span>
- <span data-ttu-id="72dfe-354">servicio local</span><span class="sxs-lookup"><span data-stu-id="72dfe-354">local service</span></span>
- <span data-ttu-id="72dfe-355">

medicare</span><span class="sxs-lookup"><span data-stu-id="72dfe-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="72dfe-356">Número de pasaporte de Australia</span><span class="sxs-lookup"><span data-stu-id="72dfe-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-357">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-357">Format</span></span>

<span data-ttu-id="72dfe-358">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-359">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-359">Pattern</span></span>

<span data-ttu-id="72dfe-360">Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-361">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-361">Checksum</span></span>

<span data-ttu-id="72dfe-362">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-363">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-363">Definition</span></span>

<span data-ttu-id="72dfe-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-365">La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-366">Se encuentra una palabra clave de Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="72dfe-367">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="72dfe-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-368">Keyword_passport</span></span>

- <span data-ttu-id="72dfe-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-369">Passport Number</span></span>
- <span data-ttu-id="72dfe-370">
Passport No</span><span class="sxs-lookup"><span data-stu-id="72dfe-370">Passport No</span></span>
- <span data-ttu-id="72dfe-371">Passport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-371">Passport #</span></span>
- <span data-ttu-id="72dfe-372">Passport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-372">Passport#</span></span>
- <span data-ttu-id="72dfe-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="72dfe-373">PassportID</span></span>
- <span data-ttu-id="72dfe-374">Passportno
</span><span class="sxs-lookup"><span data-stu-id="72dfe-374">Passportno</span></span>
- <span data-ttu-id="72dfe-375">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-375">passportnumber</span></span>
- <span data-ttu-id="72dfe-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="72dfe-376">パスポート</span></span>
- <span data-ttu-id="72dfe-377">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-377">パスポート番号</span></span>
- <span data-ttu-id="72dfe-378">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-378">パスポートのNum</span></span>
- <span data-ttu-id="72dfe-379">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-379">パスポート ＃</span></span> 
- <span data-ttu-id="72dfe-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="72dfe-380">Numéro de passeport</span></span>
- <span data-ttu-id="72dfe-381">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="72dfe-381">Passeport n °</span></span>
- <span data-ttu-id="72dfe-382">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="72dfe-382">Passeport Non</span></span>
- <span data-ttu-id="72dfe-383">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-383">Passeport #</span></span>
- <span data-ttu-id="72dfe-384">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-384">Passeport#</span></span>
- <span data-ttu-id="72dfe-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="72dfe-385">PasseportNon</span></span>
- <span data-ttu-id="72dfe-386">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="72dfe-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="72dfe-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="72dfe-388">passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-388">passport</span></span>
- <span data-ttu-id="72dfe-389">
passport details</span><span class="sxs-lookup"><span data-stu-id="72dfe-389">passport details</span></span>
- <span data-ttu-id="72dfe-390">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="72dfe-390">immigration and citizenship</span></span>
- <span data-ttu-id="72dfe-391">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="72dfe-391">commonwealth of australia</span></span>
- <span data-ttu-id="72dfe-392">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="72dfe-392">department of immigration</span></span>
- <span data-ttu-id="72dfe-393">
residential address</span><span class="sxs-lookup"><span data-stu-id="72dfe-393">residential address</span></span>
- <span data-ttu-id="72dfe-394">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="72dfe-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="72dfe-395">visa
</span><span class="sxs-lookup"><span data-stu-id="72dfe-395">visa</span></span>
- <span data-ttu-id="72dfe-396">
national identity card</span><span class="sxs-lookup"><span data-stu-id="72dfe-396">national identity card</span></span>
- <span data-ttu-id="72dfe-397">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="72dfe-397">passport number</span></span>
- <span data-ttu-id="72dfe-398">
travel document</span><span class="sxs-lookup"><span data-stu-id="72dfe-398">travel document</span></span>
- <span data-ttu-id="72dfe-399">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="72dfe-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="72dfe-400">Número de archivo de impuestos de Australia</span><span class="sxs-lookup"><span data-stu-id="72dfe-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-401">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-401">Format</span></span>

<span data-ttu-id="72dfe-402">Entre 8 y 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-403">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-403">Pattern</span></span>

<span data-ttu-id="72dfe-404">8-9 dígitos que normalmente se presentan con espacios como sigue:</span><span class="sxs-lookup"><span data-stu-id="72dfe-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="72dfe-405">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-405">Three digits</span></span> 
- <span data-ttu-id="72dfe-406">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="72dfe-406">An optional space</span></span> 
- <span data-ttu-id="72dfe-407">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-407">Three digits</span></span> 
- <span data-ttu-id="72dfe-408">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="72dfe-408">An optional space</span></span> 
- <span data-ttu-id="72dfe-409">2-3 dígitos donde el último dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-410">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-410">Checksum</span></span>

<span data-ttu-id="72dfe-411">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-412">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-412">Definition</span></span>

<span data-ttu-id="72dfe-413">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-414">La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-415">No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="72dfe-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="72dfe-416">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-416">The checksum passes.</span></span>

```
    <!-- Australia Tax File Number -->
<Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
    
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_Australia_Tax_File_Number" />
          <Match idRef="Keyword_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="72dfe-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="72dfe-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="72dfe-419">australian business number</span></span>
- <span data-ttu-id="72dfe-420">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="72dfe-420">marginal tax rate</span></span>
- <span data-ttu-id="72dfe-421">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="72dfe-421">medicare levy</span></span>
- <span data-ttu-id="72dfe-422">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="72dfe-422">portfolio number</span></span>
- <span data-ttu-id="72dfe-423">
service veterans</span><span class="sxs-lookup"><span data-stu-id="72dfe-423">service veterans</span></span>
- <span data-ttu-id="72dfe-424">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="72dfe-424">withholding tax</span></span>
- <span data-ttu-id="72dfe-425">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="72dfe-425">individual tax return</span></span>
- <span data-ttu-id="72dfe-426">

tax file number</span><span class="sxs-lookup"><span data-stu-id="72dfe-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="72dfe-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="72dfe-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="72dfe-428">00000000</span><span class="sxs-lookup"><span data-stu-id="72dfe-428">00000000</span></span>
- <span data-ttu-id="72dfe-429">11111111</span><span class="sxs-lookup"><span data-stu-id="72dfe-429">11111111</span></span>
- <span data-ttu-id="72dfe-430">22222222</span><span class="sxs-lookup"><span data-stu-id="72dfe-430">22222222</span></span>
- <span data-ttu-id="72dfe-431">33333333</span><span class="sxs-lookup"><span data-stu-id="72dfe-431">33333333</span></span>
- <span data-ttu-id="72dfe-432">44444444</span><span class="sxs-lookup"><span data-stu-id="72dfe-432">44444444</span></span>
- <span data-ttu-id="72dfe-433">55555555</span><span class="sxs-lookup"><span data-stu-id="72dfe-433">55555555</span></span>
- <span data-ttu-id="72dfe-434">66666666</span><span class="sxs-lookup"><span data-stu-id="72dfe-434">66666666</span></span>
- <span data-ttu-id="72dfe-435">77777777</span><span class="sxs-lookup"><span data-stu-id="72dfe-435">77777777</span></span>
- <span data-ttu-id="72dfe-436">88888888</span><span class="sxs-lookup"><span data-stu-id="72dfe-436">88888888</span></span>
- <span data-ttu-id="72dfe-437">99999999</span><span class="sxs-lookup"><span data-stu-id="72dfe-437">99999999</span></span>
- <span data-ttu-id="72dfe-438">000000000</span><span class="sxs-lookup"><span data-stu-id="72dfe-438">000000000</span></span>
- <span data-ttu-id="72dfe-439">111111111</span><span class="sxs-lookup"><span data-stu-id="72dfe-439">111111111</span></span>
- <span data-ttu-id="72dfe-440">222222222</span><span class="sxs-lookup"><span data-stu-id="72dfe-440">222222222</span></span>
- <span data-ttu-id="72dfe-441">333333333</span><span class="sxs-lookup"><span data-stu-id="72dfe-441">333333333</span></span>
- <span data-ttu-id="72dfe-442">444444444</span><span class="sxs-lookup"><span data-stu-id="72dfe-442">444444444</span></span>
- <span data-ttu-id="72dfe-443">555555555</span><span class="sxs-lookup"><span data-stu-id="72dfe-443">555555555</span></span>
- <span data-ttu-id="72dfe-444">666666666</span><span class="sxs-lookup"><span data-stu-id="72dfe-444">666666666</span></span>
- <span data-ttu-id="72dfe-445">777777777</span><span class="sxs-lookup"><span data-stu-id="72dfe-445">777777777</span></span>
- <span data-ttu-id="72dfe-446">888888888</span><span class="sxs-lookup"><span data-stu-id="72dfe-446">888888888</span></span>
- <span data-ttu-id="72dfe-447">999999999</span><span class="sxs-lookup"><span data-stu-id="72dfe-447">999999999</span></span>
- <span data-ttu-id="72dfe-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="72dfe-448">0000000000</span></span>
- <span data-ttu-id="72dfe-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="72dfe-449">1111111111</span></span>
- <span data-ttu-id="72dfe-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="72dfe-450">2222222222</span></span>
- <span data-ttu-id="72dfe-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="72dfe-451">3333333333</span></span>
- <span data-ttu-id="72dfe-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="72dfe-452">4444444444</span></span>
- <span data-ttu-id="72dfe-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="72dfe-453">5555555555</span></span>
- <span data-ttu-id="72dfe-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="72dfe-454">6666666666</span></span>
- <span data-ttu-id="72dfe-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="72dfe-455">7777777777</span></span>
- <span data-ttu-id="72dfe-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="72dfe-456">8888888888</span></span>
- <span data-ttu-id="72dfe-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="72dfe-457">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="72dfe-458">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="72dfe-458">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-459">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-459">Format</span></span>

<span data-ttu-id="72dfe-460">11 dígitos más delimitadores</span><span class="sxs-lookup"><span data-stu-id="72dfe-460">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-461">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-461">Pattern</span></span>

<span data-ttu-id="72dfe-462">11 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="72dfe-462">11 digits plus delimiters:</span></span>
- <span data-ttu-id="72dfe-463">Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-463">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="72dfe-464">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-464">A hyphen</span></span> 
- <span data-ttu-id="72dfe-465">Tres dígitos secuenciales (impares para hombres, pares para mujeres) </span><span class="sxs-lookup"><span data-stu-id="72dfe-465">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="72dfe-466">Un punto</span><span class="sxs-lookup"><span data-stu-id="72dfe-466">A period</span></span> 
- <span data-ttu-id="72dfe-467">Dos dígitos que son un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-467">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-468">Checksum</span></span>

<span data-ttu-id="72dfe-469">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-469">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-470">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-470">Definition</span></span>

<span data-ttu-id="72dfe-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-472">La función Func_belgium_national_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-472">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-473">Se encuentra una palabra clave de Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-473">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="72dfe-474">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-474">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-475">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-475">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="72dfe-476">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-476">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="72dfe-477">Identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-477">Identity</span></span>
- <span data-ttu-id="72dfe-478">Registration</span><span class="sxs-lookup"><span data-stu-id="72dfe-478">Registration</span></span>
- <span data-ttu-id="72dfe-479">Identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-479">Identification</span></span> 
- <span data-ttu-id="72dfe-480">ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-480">ID</span></span> 
- <span data-ttu-id="72dfe-481">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="72dfe-481">Identiteitskaart</span></span>
- <span data-ttu-id="72dfe-482">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="72dfe-482">Registratie nummer</span></span> 
- <span data-ttu-id="72dfe-483">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-483">Identificatie nummer</span></span> 
- <span data-ttu-id="72dfe-484">Identiteit</span><span class="sxs-lookup"><span data-stu-id="72dfe-484">Identiteit</span></span>
- <span data-ttu-id="72dfe-485">Registratie</span><span class="sxs-lookup"><span data-stu-id="72dfe-485">Registratie</span></span>
- <span data-ttu-id="72dfe-486">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="72dfe-486">Identificatie</span></span> 
- <span data-ttu-id="72dfe-487">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="72dfe-487">Carte d’identité</span></span> 
- <span data-ttu-id="72dfe-488">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="72dfe-488">numéro d'immatriculation</span></span>
- <span data-ttu-id="72dfe-489">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="72dfe-489">numéro d'identification</span></span>
- <span data-ttu-id="72dfe-490">
identité
</span><span class="sxs-lookup"><span data-stu-id="72dfe-490">identité</span></span> 
- <span data-ttu-id="72dfe-491">inscription
</span><span class="sxs-lookup"><span data-stu-id="72dfe-491">inscription</span></span> 
- <span data-ttu-id="72dfe-492">Identifikation</span><span class="sxs-lookup"><span data-stu-id="72dfe-492">Identifikation</span></span>
- <span data-ttu-id="72dfe-493">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="72dfe-493">Identifizierung</span></span>
- <span data-ttu-id="72dfe-494">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-494">Identifikationsnummer</span></span>
- <span data-ttu-id="72dfe-495">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="72dfe-495">Personalausweis</span></span>
- <span data-ttu-id="72dfe-496">Registrierung</span><span class="sxs-lookup"><span data-stu-id="72dfe-496">Registrierung</span></span>
- <span data-ttu-id="72dfe-497">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-497">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="72dfe-498">Número CPF de Brasil</span><span class="sxs-lookup"><span data-stu-id="72dfe-498">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-499">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-499">Format</span></span>

<span data-ttu-id="72dfe-500">11 dígitos incluido un dígito de control y que pueden tener o no formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-500">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-501">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-501">Pattern</span></span>

<span data-ttu-id="72dfe-502">Con formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-502">Formatted:</span></span>
- <span data-ttu-id="72dfe-503">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-503">Three digits</span></span> 
- <span data-ttu-id="72dfe-504">Un punto </span><span class="sxs-lookup"><span data-stu-id="72dfe-504">A period</span></span> 
- <span data-ttu-id="72dfe-505">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-505">Three digits</span></span> 
- <span data-ttu-id="72dfe-506">Un punto </span><span class="sxs-lookup"><span data-stu-id="72dfe-506">A period</span></span> 
- <span data-ttu-id="72dfe-507">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-507">Three digits</span></span> 
- <span data-ttu-id="72dfe-508">Un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-508">A hyphen</span></span> 
- <span data-ttu-id="72dfe-509">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-509">Two digits which are check digits</span></span>

<span data-ttu-id="72dfe-510">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-510">Unformatted:</span></span>
- <span data-ttu-id="72dfe-511">11 dígitos, donde los dos últimos dígitos son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-511">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-512">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-512">Checksum</span></span>

<span data-ttu-id="72dfe-513">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-514">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-514">Definition</span></span>

<span data-ttu-id="72dfe-515">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-515">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-516">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-516">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-517">Se encuentra una palabra clave de Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="72dfe-517">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="72dfe-518">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-518">The checksum passes.</span></span>

<span data-ttu-id="72dfe-519">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-519">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-520">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-520">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-521">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-521">The checksum passes.</span></span>

```
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-522">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-522">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="72dfe-523">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="72dfe-523">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="72dfe-524">CPF</span><span class="sxs-lookup"><span data-stu-id="72dfe-524">CPF</span></span>
- <span data-ttu-id="72dfe-525">Identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-525">Identification</span></span>
- <span data-ttu-id="72dfe-526">Registro</span><span class="sxs-lookup"><span data-stu-id="72dfe-526">Registration</span></span>
- <span data-ttu-id="72dfe-527">Ingresos</span><span class="sxs-lookup"><span data-stu-id="72dfe-527">Revenue</span></span>
- <span data-ttu-id="72dfe-528">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="72dfe-528">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="72dfe-529">Imposto
</span><span class="sxs-lookup"><span data-stu-id="72dfe-529">Imposto</span></span> 
- <span data-ttu-id="72dfe-530">Identificação
</span><span class="sxs-lookup"><span data-stu-id="72dfe-530">Identificação</span></span> 
- <span data-ttu-id="72dfe-531">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="72dfe-531">Inscrição</span></span> 
- <span data-ttu-id="72dfe-532">Receita

</span><span class="sxs-lookup"><span data-stu-id="72dfe-532">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="72dfe-533">Número de entidad jurídica de Brasil (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="72dfe-533">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-534">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-534">Format</span></span>

<span data-ttu-id="72dfe-535">14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores</span><span class="sxs-lookup"><span data-stu-id="72dfe-535">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-536">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-536">Pattern</span></span>
<span data-ttu-id="72dfe-537">14 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="72dfe-537">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="72dfe-538">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-538">Two digits</span></span> 
- <span data-ttu-id="72dfe-539">Un punto</span><span class="sxs-lookup"><span data-stu-id="72dfe-539">A period</span></span> 
- <span data-ttu-id="72dfe-540">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-540">Three digits</span></span> 
- <span data-ttu-id="72dfe-541">Un punto </span><span class="sxs-lookup"><span data-stu-id="72dfe-541">A period</span></span> 
- <span data-ttu-id="72dfe-542">Tres dígitos (estos ocho primeros dígitos son el número de registro) </span><span class="sxs-lookup"><span data-stu-id="72dfe-542">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="72dfe-543">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="72dfe-543">A forward slash</span></span> 
- <span data-ttu-id="72dfe-544">Número de sucursal de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-544">Four-digit branch number</span></span> 
- <span data-ttu-id="72dfe-545">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-545">A hyphen</span></span> 
- <span data-ttu-id="72dfe-546">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-546">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-547">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-547">Checksum</span></span>

<span data-ttu-id="72dfe-548">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-549">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-549">Definition</span></span>

<span data-ttu-id="72dfe-550">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-551">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-551">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-552">Se encuentra una palabra clave de Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="72dfe-552">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="72dfe-553">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-553">The checksum passes.</span></span>

<span data-ttu-id="72dfe-554">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-554">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-555">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-555">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-556">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-556">The checksum passes.</span></span>

```
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-557">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-557">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="72dfe-558">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="72dfe-558">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="72dfe-559">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="72dfe-559">CNPJ</span></span> 
- <span data-ttu-id="72dfe-560">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="72dfe-560">CNPJ/MF</span></span> 
- <span data-ttu-id="72dfe-561">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="72dfe-561">CNPJ-MF</span></span> 
- <span data-ttu-id="72dfe-562">Registro nacional de entidades jurídicas
</span><span class="sxs-lookup"><span data-stu-id="72dfe-562">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="72dfe-563">Registro de contribuyentes
</span><span class="sxs-lookup"><span data-stu-id="72dfe-563">Taxpayers Registry</span></span> 
- <span data-ttu-id="72dfe-564">Entidad jurídica
</span><span class="sxs-lookup"><span data-stu-id="72dfe-564">Legal entity</span></span> 
- <span data-ttu-id="72dfe-565">Entidades jurídicas
</span><span class="sxs-lookup"><span data-stu-id="72dfe-565">Legal entities</span></span> 
- <span data-ttu-id="72dfe-566">Estado de registro
</span><span class="sxs-lookup"><span data-stu-id="72dfe-566">Registration Status</span></span> 
- <span data-ttu-id="72dfe-567">Negocio
</span><span class="sxs-lookup"><span data-stu-id="72dfe-567">Business</span></span> 
- <span data-ttu-id="72dfe-568">Company</span><span class="sxs-lookup"><span data-stu-id="72dfe-568">Company</span></span>
- <span data-ttu-id="72dfe-569">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="72dfe-569">CNPJ</span></span> 
- <span data-ttu-id="72dfe-570">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="72dfe-570">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="72dfe-571">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="72dfe-571">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="72dfe-572">CGC
</span><span class="sxs-lookup"><span data-stu-id="72dfe-572">CGC</span></span> 
- <span data-ttu-id="72dfe-573">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="72dfe-573">Pessoa jurídica</span></span> 
- <span data-ttu-id="72dfe-574">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="72dfe-574">Pessoas jurídicas</span></span> 
- <span data-ttu-id="72dfe-575">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="72dfe-575">Situação cadastral</span></span> 
- <span data-ttu-id="72dfe-576">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="72dfe-576">Inscrição</span></span> 
- <span data-ttu-id="72dfe-577">Empresa
</span><span class="sxs-lookup"><span data-stu-id="72dfe-577">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="72dfe-578">Tarjeta de identificación nacional de Brasil (RG)</span><span class="sxs-lookup"><span data-stu-id="72dfe-578">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-579">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-579">Format</span></span>

<span data-ttu-id="72dfe-580">Registro geral (formato anterior): nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-580">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="72dfe-581">Registro de Identidade (RIC) (nuevo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-581">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-582">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-582">Pattern</span></span>

<span data-ttu-id="72dfe-583">Registro de Geral (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="72dfe-583">Registro Geral (old format):</span></span>
- <span data-ttu-id="72dfe-584">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-584">Two digits</span></span> 
- <span data-ttu-id="72dfe-585">Un punto</span><span class="sxs-lookup"><span data-stu-id="72dfe-585">A period</span></span> 
- <span data-ttu-id="72dfe-586">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-586">Three digits</span></span> 
- <span data-ttu-id="72dfe-587">Un punto</span><span class="sxs-lookup"><span data-stu-id="72dfe-587">A period</span></span> 
- <span data-ttu-id="72dfe-588">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-588">Three digits</span></span> 
- <span data-ttu-id="72dfe-589">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-589">A hyphen</span></span> 
- <span data-ttu-id="72dfe-590">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-590">One digit which is a check digit</span></span>

<span data-ttu-id="72dfe-591">Registro de Identidade (RIC) (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="72dfe-591">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="72dfe-592">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-592">10 digits</span></span> 
- <span data-ttu-id="72dfe-593">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-593">A hyphen</span></span> 
- <span data-ttu-id="72dfe-594">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-594">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-595">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-595">Checksum</span></span>

<span data-ttu-id="72dfe-596">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-596">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-597">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-597">Definition</span></span>

<span data-ttu-id="72dfe-598">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-598">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-599">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-599">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-600">Se encuentra una palabra clave de Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="72dfe-600">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="72dfe-601">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-601">The checksum passes.</span></span>

<span data-ttu-id="72dfe-602">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-602">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-603">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-603">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-604">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-604">The checksum passes.</span></span>

```
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-605">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-605">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="72dfe-606">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="72dfe-606">Keyword_brazil_rg</span></span>

<span data-ttu-id="72dfe-607">Cédula de Identidade identidad nacional identificador número de rregistro registro de Iidentidade registro Geral RG (esta palabra clave distingue entre mayúsculas y minúsculas) RIC (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-607">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="72dfe-608">Número de cuenta bancaria de Canadá</span><span class="sxs-lookup"><span data-stu-id="72dfe-608">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-609">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-609">Format</span></span>

<span data-ttu-id="72dfe-610">Siete o doce dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-610">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-611">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-611">Pattern</span></span>

<span data-ttu-id="72dfe-612">El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.</span><span class="sxs-lookup"><span data-stu-id="72dfe-612">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="72dfe-613">Un número de tránsito de cuenta bancaria de Canadá es:</span><span class="sxs-lookup"><span data-stu-id="72dfe-613">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="72dfe-614">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-614">Five digits</span></span> 
- <span data-ttu-id="72dfe-615">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-615">A hyphen</span></span> 
- <span data-ttu-id="72dfe-616">Tres dígitos o</span><span class="sxs-lookup"><span data-stu-id="72dfe-616">Three digits OR</span></span>
- <span data-ttu-id="72dfe-617">Un cero "0" </span><span class="sxs-lookup"><span data-stu-id="72dfe-617">A zero "0"</span></span> 
- <span data-ttu-id="72dfe-618">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-618">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-619">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-619">Checksum</span></span>

<span data-ttu-id="72dfe-620">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-620">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-621">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-621">Definition</span></span>

<span data-ttu-id="72dfe-622">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-622">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-623">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-623">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-624">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-624">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="72dfe-625">La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-625">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="72dfe-626">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-627">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-627">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-628">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-628">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-629">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-629">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="72dfe-630">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-630">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="72dfe-631">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="72dfe-631">canada savings bonds</span></span>
- <span data-ttu-id="72dfe-632">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="72dfe-632">canada revenue agency</span></span>
- <span data-ttu-id="72dfe-633">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="72dfe-633">canadian financial institution</span></span>
- <span data-ttu-id="72dfe-634">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="72dfe-634">direct deposit form</span></span>
- <span data-ttu-id="72dfe-635">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="72dfe-635">canadian citizen</span></span>
- <span data-ttu-id="72dfe-636">
legal representative</span><span class="sxs-lookup"><span data-stu-id="72dfe-636">legal representative</span></span>
- <span data-ttu-id="72dfe-637">
notary public</span><span class="sxs-lookup"><span data-stu-id="72dfe-637">notary public</span></span>
- <span data-ttu-id="72dfe-638">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="72dfe-638">commissioner for oaths</span></span>
- <span data-ttu-id="72dfe-639">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="72dfe-639">child care benefit</span></span>
- <span data-ttu-id="72dfe-640">
universal child care</span><span class="sxs-lookup"><span data-stu-id="72dfe-640">universal child care</span></span>
- <span data-ttu-id="72dfe-641">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="72dfe-641">canada child tax benefit</span></span>
- <span data-ttu-id="72dfe-642">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="72dfe-642">income tax benefit</span></span>
- <span data-ttu-id="72dfe-643">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="72dfe-643">harmonized sales tax</span></span>
- <span data-ttu-id="72dfe-644">social insurance number</span><span class="sxs-lookup"><span data-stu-id="72dfe-644">social insurance number</span></span>
- <span data-ttu-id="72dfe-645">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="72dfe-645">income tax refund</span></span>
- <span data-ttu-id="72dfe-646">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="72dfe-646">child tax benefit</span></span>
- <span data-ttu-id="72dfe-647">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="72dfe-647">territorial payments</span></span>
- <span data-ttu-id="72dfe-648">
institution number</span><span class="sxs-lookup"><span data-stu-id="72dfe-648">institution number</span></span>
- <span data-ttu-id="72dfe-649">
deposit request</span><span class="sxs-lookup"><span data-stu-id="72dfe-649">deposit request</span></span>
- <span data-ttu-id="72dfe-650">
banking information</span><span class="sxs-lookup"><span data-stu-id="72dfe-650">banking information</span></span>
- <span data-ttu-id="72dfe-651">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="72dfe-651">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="72dfe-652">Número de licencia de conductor de Canadá</span><span class="sxs-lookup"><span data-stu-id="72dfe-652">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-653">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-653">Format</span></span>

<span data-ttu-id="72dfe-654">Varía según la provincia</span><span class="sxs-lookup"><span data-stu-id="72dfe-654">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-655">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-655">Pattern</span></span>

<span data-ttu-id="72dfe-656">Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="72dfe-656">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-657">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-657">Checksum</span></span>

<span data-ttu-id="72dfe-658">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-658">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-659">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-659">Definition</span></span>

<span data-ttu-id="72dfe-660">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-660">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-661">La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-661">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-662">Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="72dfe-662">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="72dfe-663">Se encuentra una palabra clave de Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="72dfe-663">A keyword from Keyword_canada_drivers_license is found.</span></span>

```
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-664">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-664">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="72dfe-665">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="72dfe-665">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="72dfe-666">La abreviatura de la provincia, por ejemplo, AB</span><span class="sxs-lookup"><span data-stu-id="72dfe-666">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="72dfe-667">
El nombre de la provincia, por ejemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="72dfe-667">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="72dfe-668">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="72dfe-668">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="72dfe-669">DL</span><span class="sxs-lookup"><span data-stu-id="72dfe-669">DL</span></span>
- <span data-ttu-id="72dfe-670">DLS</span><span class="sxs-lookup"><span data-stu-id="72dfe-670">DLS</span></span>
- <span data-ttu-id="72dfe-671">CDL</span><span class="sxs-lookup"><span data-stu-id="72dfe-671">CDL</span></span>
- <span data-ttu-id="72dfe-672">CDLS</span><span class="sxs-lookup"><span data-stu-id="72dfe-672">CDLS</span></span>
- <span data-ttu-id="72dfe-673">DriverLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-673">DriverLic</span></span>
- <span data-ttu-id="72dfe-674">DriverLics</span><span class="sxs-lookup"><span data-stu-id="72dfe-674">DriverLics</span></span>
- <span data-ttu-id="72dfe-675">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-675">DriverLicense</span></span>
- <span data-ttu-id="72dfe-676">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-676">DriverLicenses</span></span>
- <span data-ttu-id="72dfe-677">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="72dfe-677">DriverLicence</span></span>
- <span data-ttu-id="72dfe-678">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="72dfe-678">DriverLicences</span></span>
- <span data-ttu-id="72dfe-679">Lic del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-679">Driver Lic</span></span>
- <span data-ttu-id="72dfe-680">Controlador conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-680">Driver Lics</span></span>
- <span data-ttu-id="72dfe-681">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-681">Driver License</span></span>
- <span data-ttu-id="72dfe-682">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-682">Driver Licenses</span></span>
- <span data-ttu-id="72dfe-683">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-683">Driver Licence</span></span>
- <span data-ttu-id="72dfe-684">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-684">Driver Licences</span></span>
- <span data-ttu-id="72dfe-685">DriversLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-685">DriversLic</span></span>
- <span data-ttu-id="72dfe-686">DriversLics</span><span class="sxs-lookup"><span data-stu-id="72dfe-686">DriversLics</span></span>
- <span data-ttu-id="72dfe-687">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="72dfe-687">DriversLicence</span></span>
- <span data-ttu-id="72dfe-688">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="72dfe-688">DriversLicences</span></span>
- <span data-ttu-id="72dfe-689">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-689">DriversLicense</span></span>
- <span data-ttu-id="72dfe-690">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-690">DriversLicenses</span></span>
- <span data-ttu-id="72dfe-691">Lic de los drivers</span><span class="sxs-lookup"><span data-stu-id="72dfe-691">Drivers Lic</span></span>
- <span data-ttu-id="72dfe-692">Controladores conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-692">Drivers Lics</span></span>
- <span data-ttu-id="72dfe-693">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-693">Drivers License</span></span>
- <span data-ttu-id="72dfe-694">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-694">Drivers Licenses</span></span>
- <span data-ttu-id="72dfe-695">Licencia de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-695">Drivers Licence</span></span>
- <span data-ttu-id="72dfe-696">Licencias de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-696">Drivers Licences</span></span>
- <span data-ttu-id="72dfe-697">N.º carné</span><span class="sxs-lookup"><span data-stu-id="72dfe-697">Driver'Lic</span></span>
- <span data-ttu-id="72dfe-698">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="72dfe-698">Driver'Lics</span></span>
- <span data-ttu-id="72dfe-699">Conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-699">Driver'License</span></span>
- <span data-ttu-id="72dfe-700">Conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-700">Driver'Licenses</span></span>
- <span data-ttu-id="72dfe-701">N.º carné</span><span class="sxs-lookup"><span data-stu-id="72dfe-701">Driver'Licence</span></span>
- <span data-ttu-id="72dfe-702">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="72dfe-702">Driver'Licences</span></span>
- <span data-ttu-id="72dfe-703">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-703">Driver' Lic</span></span>
- <span data-ttu-id="72dfe-704">Controlador de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-704">Driver' Lics</span></span>
- <span data-ttu-id="72dfe-705">Licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-705">Driver' License</span></span>
- <span data-ttu-id="72dfe-706">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-706">Driver' Licenses</span></span>
- <span data-ttu-id="72dfe-707">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-707">Driver' Licence</span></span>
- <span data-ttu-id="72dfe-708">Licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-708">Driver' Licences</span></span>
- <span data-ttu-id="72dfe-709">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-709">Driver'sLic</span></span>
- <span data-ttu-id="72dfe-710">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="72dfe-710">Driver'sLics</span></span>
- <span data-ttu-id="72dfe-711">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-711">Driver'sLicense</span></span>
- <span data-ttu-id="72dfe-712">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-712">Driver'sLicenses</span></span>
- <span data-ttu-id="72dfe-713">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="72dfe-713">Driver'sLicence</span></span>
- <span data-ttu-id="72dfe-714">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="72dfe-714">Driver'sLicences</span></span>
- <span data-ttu-id="72dfe-715">Lic del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-715">Driver's Lic</span></span>
- <span data-ttu-id="72dfe-716">Conducción del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-716">Driver's Lics</span></span>
- <span data-ttu-id="72dfe-717">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-717">Driver's License</span></span>
- <span data-ttu-id="72dfe-718">Licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-718">Driver's Licenses</span></span>
- <span data-ttu-id="72dfe-719">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-719">Driver's Licence</span></span>
- <span data-ttu-id="72dfe-720">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-720">Driver's Licences</span></span>
- <span data-ttu-id="72dfe-721">Perm de conduire</span><span class="sxs-lookup"><span data-stu-id="72dfe-721">Permis de Conduire</span></span>
- <span data-ttu-id="72dfe-722">id</span><span class="sxs-lookup"><span data-stu-id="72dfe-722">id</span></span>
- <span data-ttu-id="72dfe-723">falta</span><span class="sxs-lookup"><span data-stu-id="72dfe-723">ids</span></span>
- <span data-ttu-id="72dfe-724">
idcard number</span><span class="sxs-lookup"><span data-stu-id="72dfe-724">idcard number</span></span>
- <span data-ttu-id="72dfe-725">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="72dfe-725">idcard numbers</span></span>
- <span data-ttu-id="72dfe-726">
idcard #</span><span class="sxs-lookup"><span data-stu-id="72dfe-726">idcard #</span></span>
- <span data-ttu-id="72dfe-727">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="72dfe-727">idcard #s</span></span>
- <span data-ttu-id="72dfe-728">tarjeta tarjeta</span><span class="sxs-lookup"><span data-stu-id="72dfe-728">idcard card</span></span>
- <span data-ttu-id="72dfe-729">tarjetas tarjeta</span><span class="sxs-lookup"><span data-stu-id="72dfe-729">idcard cards</span></span>
- <span data-ttu-id="72dfe-730">tarjeta</span><span class="sxs-lookup"><span data-stu-id="72dfe-730">idcard</span></span>
- <span data-ttu-id="72dfe-731">identification number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-731">identification number</span></span>
- <span data-ttu-id="72dfe-732">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-732">identification numbers</span></span>
- <span data-ttu-id="72dfe-733">identification #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-733">identification #</span></span>
- <span data-ttu-id="72dfe-734">
identification #s</span><span class="sxs-lookup"><span data-stu-id="72dfe-734">identification #s</span></span>
- <span data-ttu-id="72dfe-735">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-735">identification card</span></span>
- <span data-ttu-id="72dfe-736">tarjetas de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-736">identification cards</span></span>
- <span data-ttu-id="72dfe-737">
identification
</span><span class="sxs-lookup"><span data-stu-id="72dfe-737">identification</span></span> 
- <span data-ttu-id="72dfe-738">DL#</span><span class="sxs-lookup"><span data-stu-id="72dfe-738">DL#</span></span>
- <span data-ttu-id="72dfe-739">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-739">DLS#</span></span> 
- <span data-ttu-id="72dfe-740">CDL#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-740">CDL#</span></span> 
- <span data-ttu-id="72dfe-741">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-741">CDLS#</span></span> 
- <span data-ttu-id="72dfe-742">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-742">DriverLic#</span></span> 
- <span data-ttu-id="72dfe-743">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-743">DriverLics#</span></span> 
- <span data-ttu-id="72dfe-744">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-744">DriverLicense#</span></span> 
- <span data-ttu-id="72dfe-745">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-745">DriverLicenses#</span></span> 
- <span data-ttu-id="72dfe-746">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="72dfe-746">DriverLicence#</span></span> 
- <span data-ttu-id="72dfe-747">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="72dfe-747">DriverLicences#</span></span> 
- <span data-ttu-id="72dfe-748">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="72dfe-748">Driver Lic#</span></span>
- <span data-ttu-id="72dfe-749">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-749">Driver Lics#</span></span> 
- <span data-ttu-id="72dfe-750">N.º de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-750">Driver License#</span></span> 
- <span data-ttu-id="72dfe-751">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-751">Driver Licenses#</span></span> 
- <span data-ttu-id="72dfe-752">N.º de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-752">Driver License#</span></span> 
- <span data-ttu-id="72dfe-753">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-753">Driver Licences#</span></span> 
- <span data-ttu-id="72dfe-754">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-754">DriversLic#</span></span> 
- <span data-ttu-id="72dfe-755">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-755">DriversLics#</span></span> 
- <span data-ttu-id="72dfe-756">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-756">DriversLicense#</span></span> 
- <span data-ttu-id="72dfe-757">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-757">DriversLicenses#</span></span> 
- <span data-ttu-id="72dfe-758">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="72dfe-758">DriversLicence#</span></span> 
- <span data-ttu-id="72dfe-759">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="72dfe-759">DriversLicences#</span></span> 
- <span data-ttu-id="72dfe-760">N.º de Lic de los conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-760">Drivers Lic#</span></span> 
- <span data-ttu-id="72dfe-761">Controladores conducción #</span><span class="sxs-lookup"><span data-stu-id="72dfe-761">Drivers Lics#</span></span> 
- <span data-ttu-id="72dfe-762">N.º de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-762">Drivers License#</span></span> 
- <span data-ttu-id="72dfe-763">N.º de licencias de impulsores</span><span class="sxs-lookup"><span data-stu-id="72dfe-763">Drivers Licenses#</span></span> 
- <span data-ttu-id="72dfe-764">N.º de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-764">Drivers Licence#</span></span> 
- <span data-ttu-id="72dfe-765">N.º de licencias de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-765">Drivers Licences#</span></span> 
- <span data-ttu-id="72dfe-766">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-766">Driver'Lic#</span></span> 
- <span data-ttu-id="72dfe-767">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-767">Driver'Lics#</span></span> 
- <span data-ttu-id="72dfe-768">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-768">Driver'License#</span></span> 
- <span data-ttu-id="72dfe-769">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-769">Driver'Licenses#</span></span> 
- <span data-ttu-id="72dfe-770">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-770">Driver'Licence#</span></span> 
- <span data-ttu-id="72dfe-771">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-771">Driver'Licences#</span></span> 
- <span data-ttu-id="72dfe-772">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-772">Driver' Lic#</span></span> 
- <span data-ttu-id="72dfe-773">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-773">Driver' Lics#</span></span> 
- <span data-ttu-id="72dfe-774">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-774">Driver' License#</span></span> 
- <span data-ttu-id="72dfe-775">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-775">Driver' Licenses#</span></span> 
- <span data-ttu-id="72dfe-776">N.º de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-776">Driver' Licence#</span></span> 
- <span data-ttu-id="72dfe-777">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-777">Driver' Licences#</span></span> 
- <span data-ttu-id="72dfe-778">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-778">Driver'sLic#</span></span> 
- <span data-ttu-id="72dfe-779">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-779">Driver'sLics#</span></span> 
- <span data-ttu-id="72dfe-780">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-780">Driver'sLicense#</span></span> 
- <span data-ttu-id="72dfe-781">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-781">Driver'sLicenses#</span></span> 
- <span data-ttu-id="72dfe-782">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="72dfe-782">Driver'sLicence#</span></span> 
- <span data-ttu-id="72dfe-783">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="72dfe-783">Driver'sLicences#</span></span> 
- <span data-ttu-id="72dfe-784">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-784">Driver's Lic#</span></span> 
- <span data-ttu-id="72dfe-785">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-785">Driver's Lics#</span></span> 
- <span data-ttu-id="72dfe-786">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-786">Driver's License#</span></span> 
- <span data-ttu-id="72dfe-787">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-787">Driver's Licenses#</span></span> 
- <span data-ttu-id="72dfe-788">Número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-788">Driver's Licence#</span></span> 
- <span data-ttu-id="72dfe-789">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-789">Driver's Licences#</span></span> 
- <span data-ttu-id="72dfe-790">Perm de conduire #</span><span class="sxs-lookup"><span data-stu-id="72dfe-790">Permis de Conduire#</span></span> 
- <span data-ttu-id="72dfe-791">identificador</span><span class="sxs-lookup"><span data-stu-id="72dfe-791">id#</span></span> 
- <span data-ttu-id="72dfe-792">falta</span><span class="sxs-lookup"><span data-stu-id="72dfe-792">ids#</span></span> 
- <span data-ttu-id="72dfe-793">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-793">idcard card#</span></span> 
- <span data-ttu-id="72dfe-794">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-794">idcard cards#</span></span> 
- <span data-ttu-id="72dfe-795">idcard#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-795">idcard#</span></span> 
- <span data-ttu-id="72dfe-796">identification card#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-796">identification card#</span></span> 
- <span data-ttu-id="72dfe-797">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-797">identification cards#</span></span> 
- <span data-ttu-id="72dfe-798">identification#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-798">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="72dfe-799">Número de servicio de salud de Canadá</span><span class="sxs-lookup"><span data-stu-id="72dfe-799">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-800">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-800">Format</span></span>

<span data-ttu-id="72dfe-801">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-801">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-802">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-802">Pattern</span></span>

<span data-ttu-id="72dfe-803">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-803">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-804">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-804">Checksum</span></span>

<span data-ttu-id="72dfe-805">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-805">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-806">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-806">Definition</span></span>

<span data-ttu-id="72dfe-807">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-807">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-808">La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-808">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-809">Se encuentra una palabra clave de Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-809">A keyword from Keyword_canada_health_service_number is found.</span></span>

```
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-810">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-810">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="72dfe-811">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-811">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="72dfe-812">personal health number</span><span class="sxs-lookup"><span data-stu-id="72dfe-812">personal health number</span></span>
- <span data-ttu-id="72dfe-813">
patient information</span><span class="sxs-lookup"><span data-stu-id="72dfe-813">patient information</span></span>
- <span data-ttu-id="72dfe-814">servicios de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-814">health services</span></span>
- <span data-ttu-id="72dfe-815">
speciality services</span><span class="sxs-lookup"><span data-stu-id="72dfe-815">speciality services</span></span>
- <span data-ttu-id="72dfe-816">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="72dfe-816">automobile accident</span></span>
- <span data-ttu-id="72dfe-817">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="72dfe-817">patient hospital</span></span>
- <span data-ttu-id="72dfe-818">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="72dfe-818">psychiatrist</span></span>
- <span data-ttu-id="72dfe-819">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="72dfe-819">workers compensation</span></span>
- <span data-ttu-id="72dfe-820">
disability</span><span class="sxs-lookup"><span data-stu-id="72dfe-820">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="72dfe-821">Número de pasaporte de Canadá</span><span class="sxs-lookup"><span data-stu-id="72dfe-821">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-822">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-822">Format</span></span>

<span data-ttu-id="72dfe-823">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-823">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-824">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-824">Pattern</span></span>

<span data-ttu-id="72dfe-825">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-825">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-826">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-826">Checksum</span></span>

<span data-ttu-id="72dfe-827">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-827">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-828">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-828">Definition</span></span>

<span data-ttu-id="72dfe-829">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-829">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-830">La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-830">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-831">Se encuentra una palabra clave de Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="72dfe-831">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

``` 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-832">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-832">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="72dfe-833">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-833">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="72dfe-834">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="72dfe-834">canadian citizenship</span></span>
- <span data-ttu-id="72dfe-835">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-835">canadian passport</span></span>
- <span data-ttu-id="72dfe-836">
passport application</span><span class="sxs-lookup"><span data-stu-id="72dfe-836">passport application</span></span>
- <span data-ttu-id="72dfe-837">
passport photos</span><span class="sxs-lookup"><span data-stu-id="72dfe-837">passport photos</span></span>
- <span data-ttu-id="72dfe-838">
certified translator</span><span class="sxs-lookup"><span data-stu-id="72dfe-838">certified translator</span></span>
- <span data-ttu-id="72dfe-839">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="72dfe-839">canadian citizens</span></span>
- <span data-ttu-id="72dfe-840">
processing times</span><span class="sxs-lookup"><span data-stu-id="72dfe-840">processing times</span></span>
- <span data-ttu-id="72dfe-841">

renewal application</span><span class="sxs-lookup"><span data-stu-id="72dfe-841">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="72dfe-842">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-842">Keyword_passport</span></span>

- <span data-ttu-id="72dfe-843">Passport Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-843">Passport Number</span></span>
- <span data-ttu-id="72dfe-844">
Passport No</span><span class="sxs-lookup"><span data-stu-id="72dfe-844">Passport No</span></span>
- <span data-ttu-id="72dfe-845">Passport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-845">Passport #</span></span>
- <span data-ttu-id="72dfe-846">Passport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-846">Passport#</span></span>
- <span data-ttu-id="72dfe-847">PassportID</span><span class="sxs-lookup"><span data-stu-id="72dfe-847">PassportID</span></span>
- <span data-ttu-id="72dfe-848">Passportno
</span><span class="sxs-lookup"><span data-stu-id="72dfe-848">Passportno</span></span>
- <span data-ttu-id="72dfe-849">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-849">passportnumber</span></span>
- <span data-ttu-id="72dfe-850">パスポート</span><span class="sxs-lookup"><span data-stu-id="72dfe-850">パスポート</span></span>
- <span data-ttu-id="72dfe-851">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-851">パスポート番号</span></span>
- <span data-ttu-id="72dfe-852">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-852">パスポートのNum</span></span>
- <span data-ttu-id="72dfe-853">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-853">パスポート＃</span></span>
- <span data-ttu-id="72dfe-854">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="72dfe-854">Numéro de passeport</span></span>
- <span data-ttu-id="72dfe-855">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="72dfe-855">Passeport n °</span></span>
- <span data-ttu-id="72dfe-856">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="72dfe-856">Passeport Non</span></span>
- <span data-ttu-id="72dfe-857">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-857">Passeport #</span></span>
- <span data-ttu-id="72dfe-858">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-858">Passeport#</span></span>
- <span data-ttu-id="72dfe-859">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="72dfe-859">PasseportNon</span></span>
- <span data-ttu-id="72dfe-860">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="72dfe-860">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="72dfe-861">Número de Identificación Personal de salud en Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="72dfe-861">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-862">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-862">Format</span></span>

<span data-ttu-id="72dfe-863">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-863">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-864">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-864">Pattern</span></span>

<span data-ttu-id="72dfe-865">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-865">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-866">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-866">Checksum</span></span>

<span data-ttu-id="72dfe-867">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-867">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-868">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-868">Definition</span></span>

<span data-ttu-id="72dfe-p104">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón. Se encuentran al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="72dfe-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-871">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-871">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="72dfe-872">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="72dfe-872">Keyword_canada_phin</span></span>

- <span data-ttu-id="72dfe-873">social insurance number</span><span class="sxs-lookup"><span data-stu-id="72dfe-873">social insurance number</span></span>
- <span data-ttu-id="72dfe-874">
health information act</span><span class="sxs-lookup"><span data-stu-id="72dfe-874">health information act</span></span>
- <span data-ttu-id="72dfe-875">
income tax information</span><span class="sxs-lookup"><span data-stu-id="72dfe-875">income tax information</span></span>
- <span data-ttu-id="72dfe-876">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="72dfe-876">manitoba health</span></span>
- <span data-ttu-id="72dfe-877">
health registration</span><span class="sxs-lookup"><span data-stu-id="72dfe-877">health registration</span></span>
- <span data-ttu-id="72dfe-878">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="72dfe-878">prescription purchases</span></span>
- <span data-ttu-id="72dfe-879">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="72dfe-879">benefit eligibility</span></span>
- <span data-ttu-id="72dfe-880">
personal health</span><span class="sxs-lookup"><span data-stu-id="72dfe-880">personal health</span></span>
- <span data-ttu-id="72dfe-881">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="72dfe-881">power of attorney</span></span>
- <span data-ttu-id="72dfe-882">
registration number</span><span class="sxs-lookup"><span data-stu-id="72dfe-882">registration number</span></span>
- <span data-ttu-id="72dfe-883">personal health number</span><span class="sxs-lookup"><span data-stu-id="72dfe-883">personal health number</span></span>
- <span data-ttu-id="72dfe-884">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="72dfe-884">practitioner referral</span></span>
- <span data-ttu-id="72dfe-885">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="72dfe-885">wellness professional</span></span>
- <span data-ttu-id="72dfe-886">
patient referral</span><span class="sxs-lookup"><span data-stu-id="72dfe-886">patient referral</span></span>
- <span data-ttu-id="72dfe-887">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="72dfe-887">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="72dfe-888">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="72dfe-888">Keyword_canada_provinces</span></span>

- <span data-ttu-id="72dfe-889">Nunavut</span><span class="sxs-lookup"><span data-stu-id="72dfe-889">Nunavut</span></span>
- <span data-ttu-id="72dfe-890">
Quebec</span><span class="sxs-lookup"><span data-stu-id="72dfe-890">Quebec</span></span>
- <span data-ttu-id="72dfe-891">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="72dfe-891">Northwest Territories</span></span>
- <span data-ttu-id="72dfe-892">
Ontario</span><span class="sxs-lookup"><span data-stu-id="72dfe-892">Ontario</span></span>
- <span data-ttu-id="72dfe-893">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="72dfe-893">British Columbia</span></span>
- <span data-ttu-id="72dfe-894">
Alberta</span><span class="sxs-lookup"><span data-stu-id="72dfe-894">Alberta</span></span>
- <span data-ttu-id="72dfe-895">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="72dfe-895">Saskatchewan</span></span>
- <span data-ttu-id="72dfe-896">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="72dfe-896">Manitoba</span></span>
- <span data-ttu-id="72dfe-897">
Yukon</span><span class="sxs-lookup"><span data-stu-id="72dfe-897">Yukon</span></span>
- <span data-ttu-id="72dfe-898">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="72dfe-898">Newfoundland and Labrador</span></span>
- <span data-ttu-id="72dfe-899">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="72dfe-899">New Brunswick</span></span>
- <span data-ttu-id="72dfe-900">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="72dfe-900">Nova Scotia</span></span>
- <span data-ttu-id="72dfe-901">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="72dfe-901">Prince Edward Island</span></span>
- <span data-ttu-id="72dfe-902">Canadá</span><span class="sxs-lookup"><span data-stu-id="72dfe-902">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="72dfe-903">Número de seguridad social de Canadá</span><span class="sxs-lookup"><span data-stu-id="72dfe-903">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-904">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-904">Format</span></span>

<span data-ttu-id="72dfe-905">Nueve dígitos con guiones opcionales o espacios</span><span class="sxs-lookup"><span data-stu-id="72dfe-905">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-906">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-906">Pattern</span></span>

<span data-ttu-id="72dfe-907">Con formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-907">Formatted:</span></span>
- <span data-ttu-id="72dfe-908">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-908">Three digits</span></span> 
- <span data-ttu-id="72dfe-909">Un guión o un espacio </span><span class="sxs-lookup"><span data-stu-id="72dfe-909">A hyphen or space</span></span> 
- <span data-ttu-id="72dfe-910">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-910">Three digits</span></span> 
- <span data-ttu-id="72dfe-911">Un guión o un espacio </span><span class="sxs-lookup"><span data-stu-id="72dfe-911">A hyphen or space</span></span> 
- <span data-ttu-id="72dfe-912">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-912">Three digits</span></span>

<span data-ttu-id="72dfe-913">Sin formato: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-913">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-914">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-914">Checksum</span></span>

<span data-ttu-id="72dfe-915">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-915">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-916">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-916">Definition</span></span>

<span data-ttu-id="72dfe-917">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-917">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-918">La función Func_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-918">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-919">Al menos dos de cualquier combinación de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72dfe-919">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="72dfe-920">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="72dfe-920">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="72dfe-921">Se encuentra una palabra clave de Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="72dfe-921">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="72dfe-922">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-922">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="72dfe-923">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-923">The checksum passes.</span></span>

<span data-ttu-id="72dfe-924">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-924">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-925">La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-925">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-926">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="72dfe-926">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="72dfe-927">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-927">The checksum passes.</span></span>

```
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-928">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-928">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="72dfe-929">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="72dfe-929">Keyword_sin</span></span>

- <span data-ttu-id="72dfe-930">PIN</span><span class="sxs-lookup"><span data-stu-id="72dfe-930">sin</span></span> 
- <span data-ttu-id="72dfe-931">social insurance
</span><span class="sxs-lookup"><span data-stu-id="72dfe-931">social insurance</span></span> 
- <span data-ttu-id="72dfe-932">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="72dfe-932">numero d'assurance sociale</span></span> 
- <span data-ttu-id="72dfe-933">sins
</span><span class="sxs-lookup"><span data-stu-id="72dfe-933">sins</span></span> 
- <span data-ttu-id="72dfe-934">SSN</span><span class="sxs-lookup"><span data-stu-id="72dfe-934">ssn</span></span> 
- <span data-ttu-id="72dfe-935">SSN</span><span class="sxs-lookup"><span data-stu-id="72dfe-935">ssns</span></span> 
- <span data-ttu-id="72dfe-936">seguridad social</span><span class="sxs-lookup"><span data-stu-id="72dfe-936">social security</span></span> 
- <span data-ttu-id="72dfe-937">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="72dfe-937">numero d'assurance social</span></span> 
- <span data-ttu-id="72dfe-938">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="72dfe-938">national identification number</span></span> 
- <span data-ttu-id="72dfe-939">
national id</span><span class="sxs-lookup"><span data-stu-id="72dfe-939">national id</span></span> 
- <span data-ttu-id="72dfe-940">sin#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-940">sin#</span></span> 
- <span data-ttu-id="72dfe-941">soc ins
</span><span class="sxs-lookup"><span data-stu-id="72dfe-941">soc ins</span></span> 
- <span data-ttu-id="72dfe-942">social ins
</span><span class="sxs-lookup"><span data-stu-id="72dfe-942">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="72dfe-943">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="72dfe-943">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="72dfe-944">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-944">driver's license</span></span> 
- <span data-ttu-id="72dfe-945">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-945">drivers license</span></span> 
- <span data-ttu-id="72dfe-946">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-946">driver's licence</span></span> 
- <span data-ttu-id="72dfe-947">drivers licence</span><span class="sxs-lookup"><span data-stu-id="72dfe-947">drivers licence</span></span> 
- <span data-ttu-id="72dfe-948">DOB
</span><span class="sxs-lookup"><span data-stu-id="72dfe-948">DOB</span></span> 
- <span data-ttu-id="72dfe-949">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-949">Birthdate</span></span> 
- <span data-ttu-id="72dfe-950">Cumpleaños </span><span class="sxs-lookup"><span data-stu-id="72dfe-950">Birthday</span></span> 
- <span data-ttu-id="72dfe-951">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-951">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="72dfe-952">Número de tarjeta de identidad de Chile</span><span class="sxs-lookup"><span data-stu-id="72dfe-952">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-953">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-953">Format</span></span>

<span data-ttu-id="72dfe-954">7-8 dígitos más delimitadores, un dígito de control o una letra</span><span class="sxs-lookup"><span data-stu-id="72dfe-954">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-955">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-955">Pattern</span></span>

<span data-ttu-id="72dfe-956">7 u 8 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="72dfe-956">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="72dfe-957">1 o 2 dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-957">1-2 digits</span></span> 
- <span data-ttu-id="72dfe-958">Un punto </span><span class="sxs-lookup"><span data-stu-id="72dfe-958">A period</span></span> 
- <span data-ttu-id="72dfe-959">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-959">Three digits</span></span> 
- <span data-ttu-id="72dfe-960">Un punto</span><span class="sxs-lookup"><span data-stu-id="72dfe-960">A period</span></span> 
- <span data-ttu-id="72dfe-961">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-961">Three digits</span></span> 
- <span data-ttu-id="72dfe-962">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-962">A dash</span></span> 
- <span data-ttu-id="72dfe-963">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-963">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-964">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-964">Checksum</span></span>

<span data-ttu-id="72dfe-965">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-966">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-966">Definition</span></span>

<span data-ttu-id="72dfe-967">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-967">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-968">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-968">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-969">Se encuentra una palabra clave de Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-969">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="72dfe-970">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-970">The checksum passes.</span></span>

<span data-ttu-id="72dfe-971">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-971">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-972">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-972">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-973">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-973">The checksum passes.</span></span>

```
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-974">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-974">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="72dfe-975">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-975">Keyword_chile_id_card</span></span>

- <span data-ttu-id="72dfe-976">Número de identificación nacional
</span><span class="sxs-lookup"><span data-stu-id="72dfe-976">National Identification Number</span></span> 
- <span data-ttu-id="72dfe-977">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-977">Identity card</span></span> 
- <span data-ttu-id="72dfe-978">ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-978">ID</span></span> 
- <span data-ttu-id="72dfe-979">Identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-979">Identification</span></span> 
- <span data-ttu-id="72dfe-980">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="72dfe-980">Rol Único Nacional</span></span> 
- <span data-ttu-id="72dfe-981">REALIZAR</span><span class="sxs-lookup"><span data-stu-id="72dfe-981">RUN</span></span> 
- <span data-ttu-id="72dfe-982">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="72dfe-982">Rol Único Tributario</span></span> 
- <span data-ttu-id="72dfe-983">RUT
</span><span class="sxs-lookup"><span data-stu-id="72dfe-983">RUT</span></span> 
- <span data-ttu-id="72dfe-984">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="72dfe-984">Cédula de Identidad</span></span> 
- <span data-ttu-id="72dfe-985">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="72dfe-985">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="72dfe-986">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="72dfe-986">Tarjeta de identificación</span></span> 
- <span data-ttu-id="72dfe-987">Identificación
</span><span class="sxs-lookup"><span data-stu-id="72dfe-987">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="72dfe-988">	Número de tarjeta de identidad de residente de China (PRC)</span><span class="sxs-lookup"><span data-stu-id="72dfe-988">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-989">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-989">Format</span></span>

<span data-ttu-id="72dfe-990">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-990">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-991">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-991">Pattern</span></span>

<span data-ttu-id="72dfe-992">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-992">18 digits:</span></span>
- <span data-ttu-id="72dfe-993">Seis dígitos que son un código de dirección </span><span class="sxs-lookup"><span data-stu-id="72dfe-993">Six digits which are an address code</span></span> 
- <span data-ttu-id="72dfe-994">Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-994">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="72dfe-995">Tres dígitos que son un código de pedido </span><span class="sxs-lookup"><span data-stu-id="72dfe-995">Three digits which are an order code</span></span> 
- <span data-ttu-id="72dfe-996">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-996">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-997">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-997">Checksum</span></span>

<span data-ttu-id="72dfe-998">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-998">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-999">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-999">Definition</span></span>

<span data-ttu-id="72dfe-1000">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1000">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1001">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1001">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1002">Se encuentra una palabra clave de Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1002">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="72dfe-1003">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1003">The checksum passes.</span></span>

<span data-ttu-id="72dfe-1004">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1005">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1005">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1006">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1006">The checksum passes.</span></span>

```
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1007">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1007">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="72dfe-1008">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="72dfe-1008">Keyword_china_resident_id</span></span>

- <span data-ttu-id="72dfe-1009">Tarjeta de identidad de residente
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1009">Resident Identity Card</span></span> 
- <span data-ttu-id="72dfe-1010">China</span><span class="sxs-lookup"><span data-stu-id="72dfe-1010">PRC</span></span> 
- <span data-ttu-id="72dfe-1011">Tarjeta de identificación nacional
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1011">National Identification Card</span></span> 
- <span data-ttu-id="72dfe-1012">身份证 </span><span class="sxs-lookup"><span data-stu-id="72dfe-1012">身份证</span></span> 
- <span data-ttu-id="72dfe-1013">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="72dfe-1013">居民 身份证</span></span> 
- <span data-ttu-id="72dfe-1014">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1014">居民身份证</span></span> 
- <span data-ttu-id="72dfe-1015">鉴定

</span><span class="sxs-lookup"><span data-stu-id="72dfe-1015">鉴定</span></span> 
- <span data-ttu-id="72dfe-1016">身分證 </span><span class="sxs-lookup"><span data-stu-id="72dfe-1016">身分證</span></span> 
- <span data-ttu-id="72dfe-1017">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="72dfe-1017">居民 身份證</span></span>
- <span data-ttu-id="72dfe-1018">鑑定 </span><span class="sxs-lookup"><span data-stu-id="72dfe-1018">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="72dfe-1019">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1019">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1020">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1020">Format</span></span>

<span data-ttu-id="72dfe-1021">16 dígitos que pueden ser formateados o sin formato (dddddddddddddddd) y deben pasar la prueba Luhn.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1021">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1022">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1022">Pattern</span></span>

<span data-ttu-id="72dfe-1023">Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1023">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1024">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1024">Checksum</span></span>

<span data-ttu-id="72dfe-1025">Sí, la suma de comprobación de Luhn</span><span class="sxs-lookup"><span data-stu-id="72dfe-1025">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1026">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1026">Definition</span></span>

<span data-ttu-id="72dfe-1027">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1027">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1028">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1028">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1029">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1029">One of the following is true:</span></span>
    - <span data-ttu-id="72dfe-1030">Se encuentra una palabra clave de Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1030">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="72dfe-1031">Se encuentra una palabra clave de Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1031">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="72dfe-1032">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1032">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="72dfe-1033">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1033">The checksum passes.</span></span>

<span data-ttu-id="72dfe-1034">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1034">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1035">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1035">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1036">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1036">The checksum passes.</span></span>

```
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1037">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1037">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="72dfe-1038">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="72dfe-1038">Keyword_cc_verification</span></span>

- <span data-ttu-id="72dfe-1039">card verification</span><span class="sxs-lookup"><span data-stu-id="72dfe-1039">card verification</span></span>
- <span data-ttu-id="72dfe-1040">card identification number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1040">card identification number</span></span>
- <span data-ttu-id="72dfe-1041">cvn
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1041">cvn</span></span>
- <span data-ttu-id="72dfe-1042">cid
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1042">cid</span></span>
- <span data-ttu-id="72dfe-1043">CVC2</span><span class="sxs-lookup"><span data-stu-id="72dfe-1043">cvc2</span></span>
- <span data-ttu-id="72dfe-1044">CVV2</span><span class="sxs-lookup"><span data-stu-id="72dfe-1044">cvv2</span></span>
- <span data-ttu-id="72dfe-1045">pin block
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1045">pin block</span></span>
- <span data-ttu-id="72dfe-1046">security code
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1046">security code</span></span>
- <span data-ttu-id="72dfe-1047">security number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1047">security number</span></span>
- <span data-ttu-id="72dfe-1048">security no
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1048">security no</span></span>
- <span data-ttu-id="72dfe-1049">issue number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1049">issue number</span></span>
- <span data-ttu-id="72dfe-1050">issue no
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1050">issue no</span></span>
- <span data-ttu-id="72dfe-1051">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1051">cryptogramme</span></span>
- <span data-ttu-id="72dfe-1052">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1052">numéro de sécurité</span></span>
- <span data-ttu-id="72dfe-1053">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1053">numero de securite</span></span>
- <span data-ttu-id="72dfe-1054">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1054">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="72dfe-1055">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1055">kreditkartenprufnummer</span></span>
- <span data-ttu-id="72dfe-1056">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1056">prüfziffer</span></span>
- <span data-ttu-id="72dfe-1057">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1057">prufziffer</span></span>
- <span data-ttu-id="72dfe-1058">Sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="72dfe-1058">sicherheits Kode</span></span>
- <span data-ttu-id="72dfe-1059">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1059">sicherheitscode</span></span>
- <span data-ttu-id="72dfe-1060">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1060">sicherheitsnummer</span></span>
- <span data-ttu-id="72dfe-1061">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1061">verfalldatum</span></span>
- <span data-ttu-id="72dfe-1062">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1062">codice di verifica</span></span>
- <span data-ttu-id="72dfe-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p105">cod. sicurezza</span></span>
- <span data-ttu-id="72dfe-1065">c.o.d. sicurezza</span><span class="sxs-lookup"><span data-stu-id="72dfe-1065">cod sicurezza</span></span>
- <span data-ttu-id="72dfe-1066">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="72dfe-1066">n autorizzazione</span></span>
- <span data-ttu-id="72dfe-1067">código
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1067">código</span></span>
- <span data-ttu-id="72dfe-1068">codigo
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1068">codigo</span></span>
- <span data-ttu-id="72dfe-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p106">cod. seg</span></span>
- <span data-ttu-id="72dfe-1071">seg de bacalao</span><span class="sxs-lookup"><span data-stu-id="72dfe-1071">cod seg</span></span>
- <span data-ttu-id="72dfe-1072">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1072">código de segurança</span></span>
- <span data-ttu-id="72dfe-1073">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1073">codigo de seguranca</span></span>
- <span data-ttu-id="72dfe-1074">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1074">codigo de segurança</span></span>
- <span data-ttu-id="72dfe-1075">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1075">código de seguranca</span></span>
- <span data-ttu-id="72dfe-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p107">cód. segurança</span></span>
- <span data-ttu-id="72dfe-p108">COD. DQO SEGURANCA. segurança</span><span class="sxs-lookup"><span data-stu-id="72dfe-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="72dfe-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p109">cód. seguranca</span></span>
- <span data-ttu-id="72dfe-1083">Cód segurança</span><span class="sxs-lookup"><span data-stu-id="72dfe-1083">cód segurança</span></span>
- <span data-ttu-id="72dfe-1084">Bacalao SEGURANCA contra reembolso de segurança</span><span class="sxs-lookup"><span data-stu-id="72dfe-1084">cod seguranca cod segurança</span></span>
- <span data-ttu-id="72dfe-1085">Cód SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="72dfe-1085">cód seguranca</span></span>
- <span data-ttu-id="72dfe-1086">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1086">número de verificação</span></span>
- <span data-ttu-id="72dfe-1087">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1087">numero de verificacao</span></span>
- <span data-ttu-id="72dfe-1088">ablauf
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1088">ablauf</span></span>
- <span data-ttu-id="72dfe-1089">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1089">gültig bis</span></span>
- <span data-ttu-id="72dfe-1090">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1090">gültigkeitsdatum</span></span>
- <span data-ttu-id="72dfe-1091">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1091">gultig bis</span></span>
- <span data-ttu-id="72dfe-1092">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1092">gultigkeitsdatum</span></span>
- <span data-ttu-id="72dfe-1093">scadenza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1093">scadenza</span></span>
- <span data-ttu-id="72dfe-1094">data scad
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1094">data scad</span></span>
- <span data-ttu-id="72dfe-1095">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1095">fecha de expiracion</span></span>
- <span data-ttu-id="72dfe-1096">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1096">fecha de venc</span></span>
- <span data-ttu-id="72dfe-1097">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1097">vencimiento</span></span>
- <span data-ttu-id="72dfe-1098">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1098">válido hasta</span></span>
- <span data-ttu-id="72dfe-1099">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1099">valido hasta</span></span>
- <span data-ttu-id="72dfe-1100">vto
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1100">vto</span></span>
- <span data-ttu-id="72dfe-1101">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1101">data de expiração</span></span>
- <span data-ttu-id="72dfe-1102">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1102">data de expiracao</span></span>
- <span data-ttu-id="72dfe-1103">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1103">data em que expira</span></span>
- <span data-ttu-id="72dfe-1104">validade
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1104">validade</span></span>
- <span data-ttu-id="72dfe-1105">valor
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1105">valor</span></span>
- <span data-ttu-id="72dfe-1106">vencimento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1106">vencimento</span></span>
- <span data-ttu-id="72dfe-1107">Venc</span><span class="sxs-lookup"><span data-stu-id="72dfe-1107">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="72dfe-1108">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="72dfe-1108">Keyword_cc_name</span></span>

- <span data-ttu-id="72dfe-1109">amex</span><span class="sxs-lookup"><span data-stu-id="72dfe-1109">amex</span></span>
- <span data-ttu-id="72dfe-1110">
american express</span><span class="sxs-lookup"><span data-stu-id="72dfe-1110">american express</span></span>
- <span data-ttu-id="72dfe-1111">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1111">americanexpress</span></span>
- <span data-ttu-id="72dfe-1112">Régimen</span><span class="sxs-lookup"><span data-stu-id="72dfe-1112">Visa</span></span>
- <span data-ttu-id="72dfe-1113">mastercard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1113">mastercard</span></span>
- <span data-ttu-id="72dfe-1114">master card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1114">master card</span></span>
- <span data-ttu-id="72dfe-1115">
mc
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1115">mc</span></span> 
- <span data-ttu-id="72dfe-1116">mastercards</span><span class="sxs-lookup"><span data-stu-id="72dfe-1116">mastercards</span></span>
- <span data-ttu-id="72dfe-1117">
master cards</span><span class="sxs-lookup"><span data-stu-id="72dfe-1117">master cards</span></span>
- <span data-ttu-id="72dfe-1118">Club de comensal</span><span class="sxs-lookup"><span data-stu-id="72dfe-1118">diner's Club</span></span>
- <span data-ttu-id="72dfe-1119">diners club
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1119">diners club</span></span>
- <span data-ttu-id="72dfe-1120">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1120">dinersclub</span></span>
- <span data-ttu-id="72dfe-1121">discover card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1121">discover card</span></span>
- <span data-ttu-id="72dfe-1122">discovercard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1122">discovercard</span></span>
- <span data-ttu-id="72dfe-1123">discover cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1123">discover cards</span></span>
- <span data-ttu-id="72dfe-1124">JCB</span><span class="sxs-lookup"><span data-stu-id="72dfe-1124">JCB</span></span>
- <span data-ttu-id="72dfe-1125">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1125">japanese card bureau</span></span>
- <span data-ttu-id="72dfe-1126">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1126">carte blanche</span></span>
- <span data-ttu-id="72dfe-1127">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1127">carteblanche</span></span>
- <span data-ttu-id="72dfe-1128">credit card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1128">credit card</span></span>
- <span data-ttu-id="72dfe-1129">CC</span><span class="sxs-lookup"><span data-stu-id="72dfe-1129">cc#</span></span>
- <span data-ttu-id="72dfe-1130"># CC:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1130">cc#:</span></span>
- <span data-ttu-id="72dfe-1131">
expiration date</span><span class="sxs-lookup"><span data-stu-id="72dfe-1131">expiration date</span></span>
- <span data-ttu-id="72dfe-1132">exp date
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1132">exp date</span></span>
- <span data-ttu-id="72dfe-1133">
expiry date</span><span class="sxs-lookup"><span data-stu-id="72dfe-1133">expiry date</span></span>
- <span data-ttu-id="72dfe-1134">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="72dfe-1134">date d’expiration</span></span>
- <span data-ttu-id="72dfe-1135">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="72dfe-1135">date d'exp</span></span>
- <span data-ttu-id="72dfe-1136">
date expiration</span><span class="sxs-lookup"><span data-stu-id="72dfe-1136">date expiration</span></span>
- <span data-ttu-id="72dfe-1137">bank card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1137">bank card</span></span>
- <span data-ttu-id="72dfe-1138">
bankcard</span><span class="sxs-lookup"><span data-stu-id="72dfe-1138">bankcard</span></span>
- <span data-ttu-id="72dfe-1139">card number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1139">card number</span></span>
- <span data-ttu-id="72dfe-1140">card num
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1140">card num</span></span>
- <span data-ttu-id="72dfe-1141">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1141">cardnumber</span></span>
- <span data-ttu-id="72dfe-1142">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1142">cardnumbers</span></span>
- <span data-ttu-id="72dfe-1143">card numbers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1143">card numbers</span></span>
- <span data-ttu-id="72dfe-1144">creditcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1144">creditcard</span></span>
- <span data-ttu-id="72dfe-1145">credit cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1145">credit cards</span></span>
- <span data-ttu-id="72dfe-1146">creditcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1146">creditcards</span></span>
- <span data-ttu-id="72dfe-1147">ccn
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1147">ccn</span></span>
- <span data-ttu-id="72dfe-1148">card holder
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1148">card holder</span></span>
- <span data-ttu-id="72dfe-1149">cardholder
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1149">cardholder</span></span>
- <span data-ttu-id="72dfe-1150">card holders
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1150">card holders</span></span>
- <span data-ttu-id="72dfe-1151">cardholders
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1151">cardholders</span></span>
- <span data-ttu-id="72dfe-1152">check card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1152">check card</span></span>
- <span data-ttu-id="72dfe-1153">checkcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1153">checkcard</span></span>
- <span data-ttu-id="72dfe-1154">check cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1154">check cards</span></span>
- <span data-ttu-id="72dfe-1155">checkcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1155">checkcards</span></span>
- <span data-ttu-id="72dfe-1156">debit card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1156">debit card</span></span>
- <span data-ttu-id="72dfe-1157">debitcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1157">debitcard</span></span>
- <span data-ttu-id="72dfe-1158">debit cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1158">debit cards</span></span>
- <span data-ttu-id="72dfe-1159">debitcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1159">debitcards</span></span>
- <span data-ttu-id="72dfe-1160">atm card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1160">atm card</span></span>
- <span data-ttu-id="72dfe-1161">atmcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1161">atmcard</span></span>
- <span data-ttu-id="72dfe-1162">atm cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1162">atm cards</span></span>
- <span data-ttu-id="72dfe-1163">atmcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1163">atmcards</span></span>
- <span data-ttu-id="72dfe-1164">
enroute</span><span class="sxs-lookup"><span data-stu-id="72dfe-1164">enroute</span></span>
- <span data-ttu-id="72dfe-1165">
en route</span><span class="sxs-lookup"><span data-stu-id="72dfe-1165">en route</span></span>
- <span data-ttu-id="72dfe-1166">card type
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1166">card type</span></span>
- <span data-ttu-id="72dfe-1167">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1167">carte bancaire</span></span>
- <span data-ttu-id="72dfe-1168">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1168">carte de crédit</span></span>
- <span data-ttu-id="72dfe-1169">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1169">carte de credit</span></span>
- <span data-ttu-id="72dfe-1170">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1170">numéro de carte</span></span>
- <span data-ttu-id="72dfe-1171">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1171">numero de carte</span></span>
- <span data-ttu-id="72dfe-1172">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1172">nº de la carte</span></span>
- <span data-ttu-id="72dfe-1173">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1173">nº de carte</span></span>
- <span data-ttu-id="72dfe-1174">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1174">kreditkarte</span></span>
- <span data-ttu-id="72dfe-1175">karte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1175">karte</span></span>
- <span data-ttu-id="72dfe-1176">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1176">karteninhaber</span></span>
- <span data-ttu-id="72dfe-1177">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="72dfe-1177">karteninhabers</span></span>
- <span data-ttu-id="72dfe-1178">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1178">kreditkarteninhaber</span></span>
- <span data-ttu-id="72dfe-1179">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1179">kreditkarteninstitut</span></span>
- <span data-ttu-id="72dfe-1180">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1180">kreditkartentyp</span></span>
- <span data-ttu-id="72dfe-1181">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1181">eigentümername</span></span>
- <span data-ttu-id="72dfe-1182">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1182">kartennr</span></span> 
- <span data-ttu-id="72dfe-1183">kartennummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1183">kartennummer</span></span>
- <span data-ttu-id="72dfe-1184">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1184">kreditkartennummer</span></span>
- <span data-ttu-id="72dfe-1185">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1185">kreditkarten-nummer</span></span>
- <span data-ttu-id="72dfe-1186">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1186">carta di credito</span></span>
- <span data-ttu-id="72dfe-1187">carta credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1187">carta credito</span></span>
- <span data-ttu-id="72dfe-1188">cobro</span><span class="sxs-lookup"><span data-stu-id="72dfe-1188">carta</span></span>
- <span data-ttu-id="72dfe-1189">carta n</span><span class="sxs-lookup"><span data-stu-id="72dfe-1189">n carta</span></span>
- <span data-ttu-id="72dfe-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p110">nr. carta</span></span>
- <span data-ttu-id="72dfe-1192">Carta de NR</span><span class="sxs-lookup"><span data-stu-id="72dfe-1192">nr carta</span></span>
- <span data-ttu-id="72dfe-1193">numero carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1193">numero carta</span></span>
- <span data-ttu-id="72dfe-1194">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1194">numero della carta</span></span>
- <span data-ttu-id="72dfe-1195">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1195">numero di carta</span></span>
- <span data-ttu-id="72dfe-1196">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1196">tarjeta credito</span></span>
- <span data-ttu-id="72dfe-1197">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1197">tarjeta de credito</span></span>
- <span data-ttu-id="72dfe-1198">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1198">tarjeta crédito</span></span>
- <span data-ttu-id="72dfe-1199">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1199">tarjeta de crédito</span></span>
- <span data-ttu-id="72dfe-1200">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1200">tarjeta de atm</span></span>
- <span data-ttu-id="72dfe-1201">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1201">tarjeta atm</span></span>
- <span data-ttu-id="72dfe-1202">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1202">tarjeta debito</span></span>
- <span data-ttu-id="72dfe-1203">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1203">tarjeta de debito</span></span>
- <span data-ttu-id="72dfe-1204">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1204">tarjeta débito</span></span>
- <span data-ttu-id="72dfe-1205">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1205">tarjeta de débito</span></span>
- <span data-ttu-id="72dfe-1206">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1206">nº de tarjeta</span></span>
- <span data-ttu-id="72dfe-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p111">no. de tarjeta</span></span>
- <span data-ttu-id="72dfe-1209">sin tarjeta de</span><span class="sxs-lookup"><span data-stu-id="72dfe-1209">no de tarjeta</span></span>
- <span data-ttu-id="72dfe-1210">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1210">numero de tarjeta</span></span>
- <span data-ttu-id="72dfe-1211">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1211">número de tarjeta</span></span>
- <span data-ttu-id="72dfe-1212">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1212">tarjeta no</span></span>
- <span data-ttu-id="72dfe-1213">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1213">tarjetahabiente</span></span>
- <span data-ttu-id="72dfe-1214">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1214">cartão de crédito</span></span>
- <span data-ttu-id="72dfe-1215">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1215">cartão de credito</span></span>
- <span data-ttu-id="72dfe-1216">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1216">cartao de crédito</span></span>
- <span data-ttu-id="72dfe-1217">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1217">cartao de credito</span></span>
- <span data-ttu-id="72dfe-1218">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1218">cartão de débito</span></span>
- <span data-ttu-id="72dfe-1219">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1219">cartao de débito</span></span>
- <span data-ttu-id="72dfe-1220">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1220">cartão de debito</span></span>
- <span data-ttu-id="72dfe-1221">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1221">cartao de debito</span></span>
- <span data-ttu-id="72dfe-1222">débito automático</span><span class="sxs-lookup"><span data-stu-id="72dfe-1222">débito automático</span></span>
- <span data-ttu-id="72dfe-1223">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1223">debito automatico</span></span>
- <span data-ttu-id="72dfe-1224">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="72dfe-1224">número do cartão</span></span>
- <span data-ttu-id="72dfe-1225">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1225">numero do cartão</span></span> 
- <span data-ttu-id="72dfe-1226">número do cartao</span><span class="sxs-lookup"><span data-stu-id="72dfe-1226">número do cartao</span></span>
- <span data-ttu-id="72dfe-1227">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="72dfe-1227">numero do cartao</span></span>
- <span data-ttu-id="72dfe-1228">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1228">número de cartão</span></span>
- <span data-ttu-id="72dfe-1229">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1229">numero de cartão</span></span>
- <span data-ttu-id="72dfe-1230">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1230">número de cartao</span></span>
- <span data-ttu-id="72dfe-1231">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1231">numero de cartao</span></span>
- <span data-ttu-id="72dfe-1232">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="72dfe-1232">nº do cartão</span></span>
- <span data-ttu-id="72dfe-1233">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1233">nº do cartao</span></span>
- <span data-ttu-id="72dfe-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p112">nº. do cartão</span></span>
- <span data-ttu-id="72dfe-1236">no cartão</span><span class="sxs-lookup"><span data-stu-id="72dfe-1236">no do cartão</span></span>
- <span data-ttu-id="72dfe-1237">no hacer carta</span><span class="sxs-lookup"><span data-stu-id="72dfe-1237">no do cartao</span></span>
- <span data-ttu-id="72dfe-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p113">no. do cartão</span></span>
- <span data-ttu-id="72dfe-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="72dfe-1242">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="72dfe-1242">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1243">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1243">Format</span></span>

<span data-ttu-id="72dfe-1244">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1245">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1245">Pattern</span></span>

<span data-ttu-id="72dfe-1246">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1247">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-1247">Checksum</span></span>

<span data-ttu-id="72dfe-1248">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-1248">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1249">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1249">Definition</span></span>

<span data-ttu-id="72dfe-1250">Una directiva DLP está 75 % segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1251">La función Func_croatia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1251">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1252">Se encuentra una palabra clave de Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1252">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1253">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="72dfe-1254">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-1254">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="72dfe-1255">Tarjeta de identidad croata</span><span class="sxs-lookup"><span data-stu-id="72dfe-1255">Croatian identity card</span></span>
- <span data-ttu-id="72dfe-1256">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="72dfe-1256">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="72dfe-1257">	Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="72dfe-1257">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1258">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1258">Format</span></span>

<span data-ttu-id="72dfe-1259">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1259">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1260">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1260">Pattern</span></span>

<span data-ttu-id="72dfe-1261">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1261">11 digits:</span></span>
- <span data-ttu-id="72dfe-1262">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1262">10 digits</span></span> 
- <span data-ttu-id="72dfe-1263">El dígito final es un dígito de control para el intercambio internacional de datos, se agregan las letras h antes de los once dígitos.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1263">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1264">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1264">Checksum</span></span>

<span data-ttu-id="72dfe-1265">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1265">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1266">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1266">Definition</span></span>

<span data-ttu-id="72dfe-1267">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1267">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1268">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1268">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1269">Se encuentra una palabra clave de Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1269">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="72dfe-1270">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1270">The checksum passes.</span></span>

<span data-ttu-id="72dfe-1271">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1272">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1272">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1273">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1273">The checksum passes.</span></span>

```
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1274">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1274">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="72dfe-1275">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1275">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="72dfe-1276">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="72dfe-1276">Personal Identification Number</span></span>
- <span data-ttu-id="72dfe-1277">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1277">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="72dfe-1278">OIB
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1278">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="72dfe-1279">Número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="72dfe-1279">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1280">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1280">Format</span></span>

<span data-ttu-id="72dfe-1281">Nueve dígitos con barra diagonal (formato antiguo) 10 dígitos con barra diagonal (nuevo formato) opcional</span><span class="sxs-lookup"><span data-stu-id="72dfe-1281">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1282">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1282">Pattern</span></span>

<span data-ttu-id="72dfe-1283">Nueve dígitos (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="72dfe-1283">Nine digits (old format):</span></span>
- <span data-ttu-id="72dfe-1284">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1284">Nine digits</span></span>

<span data-ttu-id="72dfe-1285">O bien</span><span class="sxs-lookup"><span data-stu-id="72dfe-1285">OR</span></span>

- <span data-ttu-id="72dfe-1286">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-1286">Six digits that represent date of birth</span></span>
- <span data-ttu-id="72dfe-1287">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="72dfe-1287">A forward slash</span></span>
- <span data-ttu-id="72dfe-1288">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1288">Three digits</span></span>

<span data-ttu-id="72dfe-1289">10 dígitos (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="72dfe-1289">10 digits (new format):</span></span>
- <span data-ttu-id="72dfe-1290">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1290">10 digits</span></span>

<span data-ttu-id="72dfe-1291">O BIEN</span><span class="sxs-lookup"><span data-stu-id="72dfe-1291">OR</span></span>

- <span data-ttu-id="72dfe-1292">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-1292">Six digits that represent date of birth</span></span>
- <span data-ttu-id="72dfe-1293">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="72dfe-1293">A forward slash</span></span> 
- <span data-ttu-id="72dfe-1294">Cuatro dígitos donde el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-1294">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1295">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1295">Checksum</span></span>

<span data-ttu-id="72dfe-1296">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1296">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1297">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1297">Definition</span></span>

<span data-ttu-id="72dfe-p115">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_czech_id_card encuentra contenido que coincide con el patrón. Se encuentra una palabra clave de Keyword_czech_id_card. La suma de comprobación se supera.</span><span class="sxs-lookup"><span data-stu-id="72dfe-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="72dfe-1301">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1301">Keywords</span></span>

- <span data-ttu-id="72dfe-1302">número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="72dfe-1302">czech personal identity number</span></span>
- <span data-ttu-id="72dfe-1303">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="72dfe-1303">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="72dfe-1304">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="72dfe-1304">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1305">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1305">Format</span></span>

<span data-ttu-id="72dfe-1306">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="72dfe-1306">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1307">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1307">Pattern</span></span>

<span data-ttu-id="72dfe-1308">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1308">10 digits:</span></span>
- <span data-ttu-id="72dfe-1309">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-1309">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="72dfe-1310">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-1310">A hyphen</span></span> 
- <span data-ttu-id="72dfe-1311">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-1311">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1312">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1312">Checksum</span></span>

<span data-ttu-id="72dfe-1313">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1314">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1314">Definition</span></span>

<span data-ttu-id="72dfe-p116">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_denmark_id encuentra contenido que coincide con el patrón. Se encuentra una palabra clave de Keyword_denmark_id. La suma de comprobación se supera.</span><span class="sxs-lookup"><span data-stu-id="72dfe-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1318">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1318">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="72dfe-1319">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="72dfe-1319">Keyword_denmark_id</span></span>

- <span data-ttu-id="72dfe-1320">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="72dfe-1320">Personal Identification Number</span></span>
- <span data-ttu-id="72dfe-1321">CPR</span><span class="sxs-lookup"><span data-stu-id="72dfe-1321">CPR</span></span>
- <span data-ttu-id="72dfe-1322">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="72dfe-1322">Det Centrale Personregister</span></span>
- <span data-ttu-id="72dfe-1323">Personnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1323">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="72dfe-1324">Número de la Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="72dfe-1324">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1325">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1325">Format</span></span>

<span data-ttu-id="72dfe-1326">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1326">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1327">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1327">Pattern</span></span>

<span data-ttu-id="72dfe-1328">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1328">Pattern must include all of the following:</span></span>
- <span data-ttu-id="72dfe-1329">Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1329">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="72dfe-1330">Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1330">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="72dfe-1331">Siete dígitos, el último de los cuales es el dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1331">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1332">Checksum</span></span>

<span data-ttu-id="72dfe-1333">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1333">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1334">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1334">Definition</span></span>

<span data-ttu-id="72dfe-1335">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1335">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1336">La función Func_dea_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1336">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1337">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1337">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1338">Keywords</span></span>

<span data-ttu-id="72dfe-1339">Ninguno</span><span class="sxs-lookup"><span data-stu-id="72dfe-1339">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="72dfe-1340">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="72dfe-1340">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1341">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1341">Format</span></span>

<span data-ttu-id="72dfe-1342">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1342">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1343">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1343">Pattern</span></span>

<span data-ttu-id="72dfe-1344">Patrón muy complejo y robusto</span><span class="sxs-lookup"><span data-stu-id="72dfe-1344">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1345">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1345">Checksum</span></span>

<span data-ttu-id="72dfe-1346">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1346">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1347">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1347">Definition</span></span>

<span data-ttu-id="72dfe-1348">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1348">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1349">La función Func_eu_debit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1349">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1350">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1350">At least one of the following is true:</span></span>
    - <span data-ttu-id="72dfe-1351">Se encuentra una palabra clave de Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1351">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="72dfe-1352">Se encuentra una palabra clave de Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1352">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="72dfe-1353">Se encuentra una palabra clave de Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1353">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="72dfe-1354">Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1354">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="72dfe-1355">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1355">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="72dfe-1356">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1356">The checksum passes.</span></span>

```
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1357">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1357">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="72dfe-1358">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-1358">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="72dfe-1359">número de cuenta</span><span class="sxs-lookup"><span data-stu-id="72dfe-1359">account number</span></span> 
- <span data-ttu-id="72dfe-1360">card number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1360">card number</span></span> 
- <span data-ttu-id="72dfe-1361">card no.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1361">card no.</span></span> 
- <span data-ttu-id="72dfe-1362">security number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1362">security number</span></span> 
- <span data-ttu-id="72dfe-1363">CC</span><span class="sxs-lookup"><span data-stu-id="72dfe-1363">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="72dfe-1364">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="72dfe-1364">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="72dfe-1365">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1365">acct nbr</span></span> 
- <span data-ttu-id="72dfe-1366">acct num
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1366">acct num</span></span> 
- <span data-ttu-id="72dfe-1367">acct no
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1367">acct no</span></span> 
- <span data-ttu-id="72dfe-1368">american express
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1368">american express</span></span> 
- <span data-ttu-id="72dfe-1369">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1369">americanexpress</span></span> 
- <span data-ttu-id="72dfe-1370">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1370">americano espresso</span></span> 
- <span data-ttu-id="72dfe-1371">amex</span><span class="sxs-lookup"><span data-stu-id="72dfe-1371">amex</span></span> 
- <span data-ttu-id="72dfe-1372">atm card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1372">atm card</span></span> 
- <span data-ttu-id="72dfe-1373">atm cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1373">atm cards</span></span> 
- <span data-ttu-id="72dfe-1374">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1374">atm kaart</span></span> 
- <span data-ttu-id="72dfe-1375">atmcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1375">atmcard</span></span> 
- <span data-ttu-id="72dfe-1376">atmcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1376">atmcards</span></span> 
- <span data-ttu-id="72dfe-1377">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1377">atmkaart</span></span> 
- <span data-ttu-id="72dfe-1378">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1378">atmkaarten</span></span> 
- <span data-ttu-id="72dfe-1379">bancontact
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1379">bancontact</span></span> 
- <span data-ttu-id="72dfe-1380">bank card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1380">bank card</span></span> 
- <span data-ttu-id="72dfe-1381">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1381">bankkaart</span></span> 
- <span data-ttu-id="72dfe-1382">card holder
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1382">card holder</span></span> 
- <span data-ttu-id="72dfe-1383">card holders
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1383">card holders</span></span> 
- <span data-ttu-id="72dfe-1384">card num
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1384">card num</span></span> 
- <span data-ttu-id="72dfe-1385">card number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1385">card number</span></span> 
- <span data-ttu-id="72dfe-1386">card numbers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1386">card numbers</span></span> 
- <span data-ttu-id="72dfe-1387">card type
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1387">card type</span></span> 
- <span data-ttu-id="72dfe-1388">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1388">cardano numerico</span></span> 
- <span data-ttu-id="72dfe-1389">cardholder
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1389">cardholder</span></span> 
- <span data-ttu-id="72dfe-1390">cardholders
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1390">cardholders</span></span> 
- <span data-ttu-id="72dfe-1391">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1391">cardnumber</span></span> 
- <span data-ttu-id="72dfe-1392">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1392">cardnumbers</span></span> 
- <span data-ttu-id="72dfe-1393">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1393">carta bianca</span></span> 
- <span data-ttu-id="72dfe-1394">carta credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1394">carta credito</span></span> 
- <span data-ttu-id="72dfe-1395">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1395">carta di credito</span></span> 
- <span data-ttu-id="72dfe-1396">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1396">cartao de credito</span></span> 
- <span data-ttu-id="72dfe-1397">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1397">cartao de crédito</span></span> 
- <span data-ttu-id="72dfe-1398">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1398">cartao de debito</span></span> 
- <span data-ttu-id="72dfe-1399">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1399">cartao de débito</span></span> 
- <span data-ttu-id="72dfe-1400">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1400">carte bancaire</span></span> 
- <span data-ttu-id="72dfe-1401">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1401">carte blanche</span></span> 
- <span data-ttu-id="72dfe-1402">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1402">carte bleue</span></span> 
- <span data-ttu-id="72dfe-1403">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1403">carte de credit</span></span> 
- <span data-ttu-id="72dfe-1404">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1404">carte de crédit</span></span> 
- <span data-ttu-id="72dfe-1405">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1405">carte di credito</span></span> 
- <span data-ttu-id="72dfe-1406">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1406">carteblanche</span></span> 
- <span data-ttu-id="72dfe-1407">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1407">cartão de credito</span></span> 
- <span data-ttu-id="72dfe-1408">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1408">cartão de crédito</span></span> 
- <span data-ttu-id="72dfe-1409">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1409">cartão de debito</span></span> 
- <span data-ttu-id="72dfe-1410">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1410">cartão de débito</span></span> 
- <span data-ttu-id="72dfe-1411">cb
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1411">cb</span></span> 
- <span data-ttu-id="72dfe-1412">ccn
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1412">ccn</span></span> 
- <span data-ttu-id="72dfe-1413">check card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1413">check card</span></span> 
- <span data-ttu-id="72dfe-1414">check cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1414">check cards</span></span> 
- <span data-ttu-id="72dfe-1415">checkcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1415">checkcard</span></span>
- <span data-ttu-id="72dfe-1416">checkcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1416">checkcards</span></span> 
- <span data-ttu-id="72dfe-1417">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1417">chequekaart</span></span> 
- <span data-ttu-id="72dfe-1418">cirrus
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1418">cirrus</span></span> 
- <span data-ttu-id="72dfe-1419">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1419">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="72dfe-1420">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1420">controlekaart</span></span> 
- <span data-ttu-id="72dfe-1421">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1421">controlekaarten</span></span> 
- <span data-ttu-id="72dfe-1422">credit card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1422">credit card</span></span> 
- <span data-ttu-id="72dfe-1423">credit cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1423">credit cards</span></span> 
- <span data-ttu-id="72dfe-1424">creditcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1424">creditcard</span></span> 
- <span data-ttu-id="72dfe-1425">creditcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1425">creditcards</span></span> 
- <span data-ttu-id="72dfe-1426">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1426">debetkaart</span></span> 
- <span data-ttu-id="72dfe-1427">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1427">debetkaarten</span></span> 
- <span data-ttu-id="72dfe-1428">debit card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1428">debit card</span></span> 
- <span data-ttu-id="72dfe-1429">debit cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1429">debit cards</span></span> 
- <span data-ttu-id="72dfe-1430">debitcard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1430">debitcard</span></span> 
- <span data-ttu-id="72dfe-1431">debitcards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1431">debitcards</span></span> 
- <span data-ttu-id="72dfe-1432">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1432">debito automatico</span></span> 
- <span data-ttu-id="72dfe-1433">diners club
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1433">diners club</span></span> 
- <span data-ttu-id="72dfe-1434">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1434">dinersclub</span></span> 
- <span data-ttu-id="72dfe-1435">advierte</span><span class="sxs-lookup"><span data-stu-id="72dfe-1435">discover</span></span> 
- <span data-ttu-id="72dfe-1436">discover card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1436">discover card</span></span> 
- <span data-ttu-id="72dfe-1437">discover cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1437">discover cards</span></span> 
- <span data-ttu-id="72dfe-1438">discovercard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1438">discovercard</span></span> 
- <span data-ttu-id="72dfe-1439">discovercards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1439">discovercards</span></span> 
- <span data-ttu-id="72dfe-1440">débito automático</span><span class="sxs-lookup"><span data-stu-id="72dfe-1440">débito automático</span></span>
- <span data-ttu-id="72dfe-1441">
edc
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1441">edc</span></span> 
- <span data-ttu-id="72dfe-1442">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1442">eigentümername</span></span> 
- <span data-ttu-id="72dfe-1443">european debit card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1443">european debit card</span></span> 
- <span data-ttu-id="72dfe-1444">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1444">hoofdkaart</span></span> 
- <span data-ttu-id="72dfe-1445">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1445">hoofdkaarten</span></span> 
- <span data-ttu-id="72dfe-1446">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1446">in viaggio</span></span> 
- <span data-ttu-id="72dfe-1447">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1447">japanese card bureau</span></span> 
- <span data-ttu-id="72dfe-1448">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1448">japanse kaartdienst</span></span> 
- <span data-ttu-id="72dfe-1449">jcb
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1449">jcb</span></span> 
- <span data-ttu-id="72dfe-1450">kaart
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1450">kaart</span></span> 
- <span data-ttu-id="72dfe-1451">kaart num
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1451">kaart num</span></span> 
- <span data-ttu-id="72dfe-1452">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1452">kaartaantal</span></span> 
- <span data-ttu-id="72dfe-1453">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1453">kaartaantallen</span></span> 
- <span data-ttu-id="72dfe-1454">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1454">kaarthouder</span></span> 
- <span data-ttu-id="72dfe-1455">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1455">kaarthouders</span></span> 
- <span data-ttu-id="72dfe-1456">karte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1456">karte</span></span>  
- <span data-ttu-id="72dfe-1457">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1457">karteninhaber</span></span> 
- <span data-ttu-id="72dfe-1458">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="72dfe-1458">karteninhabers</span></span>
- <span data-ttu-id="72dfe-1459">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1459">kartennr</span></span> 
- <span data-ttu-id="72dfe-1460">kartennummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1460">kartennummer</span></span> 
- <span data-ttu-id="72dfe-1461">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1461">kreditkarte</span></span> 
- <span data-ttu-id="72dfe-1462">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1462">kreditkarten-nummer</span></span> 
- <span data-ttu-id="72dfe-1463">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1463">kreditkarteninhaber</span></span> 
- <span data-ttu-id="72dfe-1464">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1464">kreditkarteninstitut</span></span> 
- <span data-ttu-id="72dfe-1465">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1465">kreditkartennummer</span></span> 
- <span data-ttu-id="72dfe-1466">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1466">kreditkartentyp</span></span> 
- <span data-ttu-id="72dfe-1467">maestro
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1467">maestro</span></span> 
- <span data-ttu-id="72dfe-1468">master card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1468">master card</span></span> 
- <span data-ttu-id="72dfe-1469">master cards
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1469">master cards</span></span> 
- <span data-ttu-id="72dfe-1470">mastercard
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1470">mastercard</span></span> 
- <span data-ttu-id="72dfe-1471">mastercards</span><span class="sxs-lookup"><span data-stu-id="72dfe-1471">mastercards</span></span> 
- <span data-ttu-id="72dfe-1472">valuación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1472">mc</span></span> 
- <span data-ttu-id="72dfe-1473">mister cash
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1473">mister cash</span></span> 
- <span data-ttu-id="72dfe-1474">carta n</span><span class="sxs-lookup"><span data-stu-id="72dfe-1474">n carta</span></span> 
- <span data-ttu-id="72dfe-1475">cobro</span><span class="sxs-lookup"><span data-stu-id="72dfe-1475">carta</span></span> 
- <span data-ttu-id="72dfe-1476">sin tarjeta de</span><span class="sxs-lookup"><span data-stu-id="72dfe-1476">no de tarjeta</span></span> 
- <span data-ttu-id="72dfe-1477">no hacer carta</span><span class="sxs-lookup"><span data-stu-id="72dfe-1477">no do cartao</span></span> 
- <span data-ttu-id="72dfe-1478">no cartão</span><span class="sxs-lookup"><span data-stu-id="72dfe-1478">no do cartão</span></span> 
- <span data-ttu-id="72dfe-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="72dfe-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p118">no. do cartao</span></span> 
- <span data-ttu-id="72dfe-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p119">no. do cartão</span></span> 
- <span data-ttu-id="72dfe-1485">Carta de NR</span><span class="sxs-lookup"><span data-stu-id="72dfe-1485">nr carta</span></span> 
- <span data-ttu-id="72dfe-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p120">nr. carta</span></span> 
- <span data-ttu-id="72dfe-1488">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1488">numeri di scheda</span></span> 
- <span data-ttu-id="72dfe-1489">numero carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1489">numero carta</span></span> 
- <span data-ttu-id="72dfe-1490">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1490">numero de cartao</span></span> 
- <span data-ttu-id="72dfe-1491">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1491">numero de carte</span></span> 
- <span data-ttu-id="72dfe-1492">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1492">numero de cartão</span></span> 
- <span data-ttu-id="72dfe-1493">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1493">numero de tarjeta</span></span>
- <span data-ttu-id="72dfe-1494">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1494">numero della carta</span></span> 
- <span data-ttu-id="72dfe-1495">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1495">numero di carta</span></span> 
- <span data-ttu-id="72dfe-1496">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1496">numero di scheda</span></span> 
- <span data-ttu-id="72dfe-1497">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1497">numero do cartao</span></span> 
- <span data-ttu-id="72dfe-1498">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1498">numero do cartão</span></span> 
- <span data-ttu-id="72dfe-1499">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1499">numéro de carte</span></span> 
- <span data-ttu-id="72dfe-1500">nº carta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1500">nº carta</span></span> 
- <span data-ttu-id="72dfe-1501">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1501">nº de carte</span></span> 
- <span data-ttu-id="72dfe-1502">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1502">nº de la carte</span></span> 
- <span data-ttu-id="72dfe-1503">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1503">nº de tarjeta</span></span> 
- <span data-ttu-id="72dfe-1504">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1504">nº do cartao</span></span> 
- <span data-ttu-id="72dfe-1505">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="72dfe-1505">nº do cartão</span></span> 
- <span data-ttu-id="72dfe-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p121">nº. do cartão</span></span> 
- <span data-ttu-id="72dfe-1508">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1508">número de cartao</span></span> 
- <span data-ttu-id="72dfe-1509">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1509">número de cartão</span></span> 
- <span data-ttu-id="72dfe-1510">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1510">número de tarjeta</span></span> 
- <span data-ttu-id="72dfe-1511">número do cartao</span><span class="sxs-lookup"><span data-stu-id="72dfe-1511">número do cartao</span></span> 
- <span data-ttu-id="72dfe-1512">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1512">scheda dell'assegno</span></span> 
- <span data-ttu-id="72dfe-1513">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1513">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="72dfe-1514">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1514">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="72dfe-1515">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1515">scheda della banca</span></span> 
- <span data-ttu-id="72dfe-1516">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1516">scheda di controllo</span></span> 
- <span data-ttu-id="72dfe-1517">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1517">scheda di debito</span></span> 
- <span data-ttu-id="72dfe-1518">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1518">scheda matrice</span></span> 
- <span data-ttu-id="72dfe-1519">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1519">schede dell'atmosfera</span></span> 
- <span data-ttu-id="72dfe-1520">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1520">schede di controllo</span></span> 
- <span data-ttu-id="72dfe-1521">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1521">schede di debito</span></span> 
- <span data-ttu-id="72dfe-1522">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1522">schede matrici</span></span> 
- <span data-ttu-id="72dfe-1523">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1523">scoprono la scheda</span></span> 
- <span data-ttu-id="72dfe-1524">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1524">scoprono le schede</span></span> 
- <span data-ttu-id="72dfe-1525">solo
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1525">solo</span></span> 
- <span data-ttu-id="72dfe-1526">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1526">supporti di scheda</span></span> 
- <span data-ttu-id="72dfe-1527">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1527">supporto di scheda</span></span> 
- <span data-ttu-id="72dfe-1528">conmutador</span><span class="sxs-lookup"><span data-stu-id="72dfe-1528">switch</span></span> 
- <span data-ttu-id="72dfe-1529">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1529">tarjeta atm</span></span> 
- <span data-ttu-id="72dfe-1530">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1530">tarjeta credito</span></span> 
- <span data-ttu-id="72dfe-1531">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1531">tarjeta de atm</span></span> 
- <span data-ttu-id="72dfe-1532">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1532">tarjeta de credito</span></span> 
- <span data-ttu-id="72dfe-1533">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1533">tarjeta de debito</span></span> 
- <span data-ttu-id="72dfe-1534">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1534">tarjeta debito</span></span> 
- <span data-ttu-id="72dfe-1535">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1535">tarjeta no</span></span>
- <span data-ttu-id="72dfe-1536">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1536">tarjetahabiente</span></span> 
- <span data-ttu-id="72dfe-1537">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1537">tipo della scheda</span></span> 
- <span data-ttu-id="72dfe-1538">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="72dfe-1538">ufficio giapponese della</span></span> 
- <span data-ttu-id="72dfe-1539">scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1539">scheda</span></span> 
- <span data-ttu-id="72dfe-1540">v pay
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1540">v pay</span></span> 
- <span data-ttu-id="72dfe-1541">v-Pay</span><span class="sxs-lookup"><span data-stu-id="72dfe-1541">v-pay</span></span> 
- <span data-ttu-id="72dfe-1542">visa
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1542">visa</span></span> 
- <span data-ttu-id="72dfe-1543">visa plus
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1543">visa plus</span></span> 
- <span data-ttu-id="72dfe-1544">visa electron
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1544">visa electron</span></span> 
- <span data-ttu-id="72dfe-1545">visto
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1545">visto</span></span> 
- <span data-ttu-id="72dfe-1546">visum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1546">visum</span></span> 
- <span data-ttu-id="72dfe-1547">vpay
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1547">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="72dfe-1548">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="72dfe-1548">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="72dfe-1549">card identification number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1549">card identification number</span></span>
- <span data-ttu-id="72dfe-1550">card verification</span><span class="sxs-lookup"><span data-stu-id="72dfe-1550">card verification</span></span> 
- <span data-ttu-id="72dfe-1551">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1551">cardi la verifica</span></span> 
- <span data-ttu-id="72dfe-1552">cid
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1552">cid</span></span> 
- <span data-ttu-id="72dfe-1553">seg de bacalao</span><span class="sxs-lookup"><span data-stu-id="72dfe-1553">cod seg</span></span> 
- <span data-ttu-id="72dfe-1554">c.o.d. SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="72dfe-1554">cod seguranca</span></span> 
- <span data-ttu-id="72dfe-1555">c.o.d. segurança</span><span class="sxs-lookup"><span data-stu-id="72dfe-1555">cod segurança</span></span> 
- <span data-ttu-id="72dfe-1556">c.o.d. sicurezza</span><span class="sxs-lookup"><span data-stu-id="72dfe-1556">cod sicurezza</span></span> 
- <span data-ttu-id="72dfe-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p122">cod. seg</span></span> 
- <span data-ttu-id="72dfe-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p123">cod. seguranca</span></span> 
- <span data-ttu-id="72dfe-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p124">cod. segurança</span></span> 
- <span data-ttu-id="72dfe-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="72dfe-1565">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1565">codice di sicurezza</span></span> 
- <span data-ttu-id="72dfe-1566">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1566">codice di verifica</span></span> 
- <span data-ttu-id="72dfe-1567">codigo
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1567">codigo</span></span> 
- <span data-ttu-id="72dfe-1568">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1568">codigo de seguranca</span></span> 
- <span data-ttu-id="72dfe-1569">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1569">codigo de segurança</span></span> 
- <span data-ttu-id="72dfe-1570">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1570">crittogramma</span></span> 
- <span data-ttu-id="72dfe-1571">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1571">cryptogram</span></span> 
- <span data-ttu-id="72dfe-1572">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1572">cryptogramme</span></span> 
- <span data-ttu-id="72dfe-1573">CV2</span><span class="sxs-lookup"><span data-stu-id="72dfe-1573">cv2</span></span> 
- <span data-ttu-id="72dfe-1574">cvc
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1574">cvc</span></span> 
- <span data-ttu-id="72dfe-1575">CVC2</span><span class="sxs-lookup"><span data-stu-id="72dfe-1575">cvc2</span></span> 
- <span data-ttu-id="72dfe-1576">cvn
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1576">cvn</span></span> 
- <span data-ttu-id="72dfe-1577">cvv
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1577">cvv</span></span> 
- <span data-ttu-id="72dfe-1578">CVV2</span><span class="sxs-lookup"><span data-stu-id="72dfe-1578">cvv2</span></span> 
- <span data-ttu-id="72dfe-1579">Cód SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="72dfe-1579">cód seguranca</span></span> 
- <span data-ttu-id="72dfe-1580">Cód segurança</span><span class="sxs-lookup"><span data-stu-id="72dfe-1580">cód segurança</span></span> 
- <span data-ttu-id="72dfe-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p126">cód. seguranca</span></span> 
- <span data-ttu-id="72dfe-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p127">cód. segurança</span></span> 
- <span data-ttu-id="72dfe-1585">código
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1585">código</span></span> 
- <span data-ttu-id="72dfe-1586">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1586">código de seguranca</span></span> 
- <span data-ttu-id="72dfe-1587">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1587">código de segurança</span></span> 
- <span data-ttu-id="72dfe-1588">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1588">de kaart controle</span></span> 
- <span data-ttu-id="72dfe-1589">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1589">geeft nr uit</span></span> 
- <span data-ttu-id="72dfe-1590">issue no
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1590">issue no</span></span> 
- <span data-ttu-id="72dfe-1591">issue number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1591">issue number</span></span> 
- <span data-ttu-id="72dfe-1592">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1592">kaartidentificatienummer</span></span> 
- <span data-ttu-id="72dfe-1593">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1593">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="72dfe-1594">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1594">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="72dfe-1595">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1595">kwestieaantal</span></span> 
- <span data-ttu-id="72dfe-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="72dfe-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="72dfe-1600">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1600">numero de securite</span></span> 
- <span data-ttu-id="72dfe-1601">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1601">numero de verificacao</span></span> 
- <span data-ttu-id="72dfe-1602">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1602">numero dell'edizione</span></span> 
- <span data-ttu-id="72dfe-1603">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="72dfe-1603">numero di identificazione della</span></span> 
- <span data-ttu-id="72dfe-1604">scheda
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1604">scheda</span></span> 
- <span data-ttu-id="72dfe-1605">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1605">numero di sicurezza</span></span> 
- <span data-ttu-id="72dfe-1606">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1606">numero van veiligheid</span></span> 
- <span data-ttu-id="72dfe-1607">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1607">numéro de sécurité</span></span> 
- <span data-ttu-id="72dfe-1608">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1608">nº autorizzazione</span></span> 
- <span data-ttu-id="72dfe-1609">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1609">número de verificação</span></span> 
- <span data-ttu-id="72dfe-1610">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1610">perno il blocco</span></span> 
- <span data-ttu-id="72dfe-1611">pin block
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1611">pin block</span></span> 
- <span data-ttu-id="72dfe-1612">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1612">prufziffer</span></span> 
- <span data-ttu-id="72dfe-1613">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1613">prüfziffer</span></span> 
- <span data-ttu-id="72dfe-1614">security code
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1614">security code</span></span> 
- <span data-ttu-id="72dfe-1615">security no
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1615">security no</span></span> 
- <span data-ttu-id="72dfe-1616">security number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1616">security number</span></span> 
- <span data-ttu-id="72dfe-1617">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1617">sicherheits kode</span></span> 
- <span data-ttu-id="72dfe-1618">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1618">sicherheitscode</span></span> 
- <span data-ttu-id="72dfe-1619">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1619">sicherheitsnummer</span></span> 
- <span data-ttu-id="72dfe-1620">speldblok
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1620">speldblok</span></span> 
- <span data-ttu-id="72dfe-1621">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1621">veiligheid nr</span></span> 
- <span data-ttu-id="72dfe-1622">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1622">veiligheidsaantal</span></span> 
- <span data-ttu-id="72dfe-1623">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1623">veiligheidscode</span></span> 
- <span data-ttu-id="72dfe-1624">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1624">veiligheidsnummer</span></span> 
- <span data-ttu-id="72dfe-1625">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1625">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="72dfe-1626">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="72dfe-1626">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="72dfe-1627">ablauf
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1627">ablauf</span></span> 
- <span data-ttu-id="72dfe-1628">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1628">data de expiracao</span></span> 
- <span data-ttu-id="72dfe-1629">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1629">data de expiração</span></span> 
- <span data-ttu-id="72dfe-1630">data del exp
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1630">data del exp</span></span> 
- <span data-ttu-id="72dfe-1631">data di exp
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1631">data di exp</span></span> 
- <span data-ttu-id="72dfe-1632">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1632">data di scadenza</span></span> 
- <span data-ttu-id="72dfe-1633">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1633">data em que expira</span></span> 
- <span data-ttu-id="72dfe-1634">data scad
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1634">data scad</span></span> 
- <span data-ttu-id="72dfe-1635">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1635">data scadenza</span></span> 
- <span data-ttu-id="72dfe-1636">date de validité
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1636">date de validité</span></span> 
- <span data-ttu-id="72dfe-1637">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1637">datum afloop</span></span> 
- <span data-ttu-id="72dfe-1638">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1638">datum van exp</span></span> 
- <span data-ttu-id="72dfe-1639">de afloop
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1639">de afloop</span></span> 
- <span data-ttu-id="72dfe-1640">espira
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1640">espira</span></span> 
- <span data-ttu-id="72dfe-1641">espira
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1641">espira</span></span> 
- <span data-ttu-id="72dfe-1642">exp date
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1642">exp date</span></span> 
- <span data-ttu-id="72dfe-1643">exp datum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1643">exp datum</span></span> 
- <span data-ttu-id="72dfe-1644">expiración</span><span class="sxs-lookup"><span data-stu-id="72dfe-1644">expiration</span></span> 
- <span data-ttu-id="72dfe-1645">expirar
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1645">expire</span></span> 
- <span data-ttu-id="72dfe-1646">expires
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1646">expires</span></span> 
- <span data-ttu-id="72dfe-1647">expiry
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1647">expiry</span></span> 
- <span data-ttu-id="72dfe-1648">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1648">fecha de expiracion</span></span> 
- <span data-ttu-id="72dfe-1649">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1649">fecha de venc</span></span> 
- <span data-ttu-id="72dfe-1650">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1650">gultig bis</span></span> 
- <span data-ttu-id="72dfe-1651">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1651">gultigkeitsdatum</span></span> 
- <span data-ttu-id="72dfe-1652">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1652">gültig bis</span></span> 
- <span data-ttu-id="72dfe-1653">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1653">gültigkeitsdatum</span></span> 
- <span data-ttu-id="72dfe-1654">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1654">la scadenza</span></span> 
- <span data-ttu-id="72dfe-1655">scadenza
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1655">scadenza</span></span> 
- <span data-ttu-id="72dfe-1656">valable
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1656">valable</span></span> 
- <span data-ttu-id="72dfe-1657">validade
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1657">validade</span></span> 
- <span data-ttu-id="72dfe-1658">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1658">valido hasta</span></span> 
- <span data-ttu-id="72dfe-1659">valor
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1659">valor</span></span> 
- <span data-ttu-id="72dfe-1660">venc
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1660">venc</span></span> 
- <span data-ttu-id="72dfe-1661">vencimento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1661">vencimento</span></span> 
- <span data-ttu-id="72dfe-1662">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1662">vencimiento</span></span> 
- <span data-ttu-id="72dfe-1663">verloopt
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1663">verloopt</span></span> 
- <span data-ttu-id="72dfe-1664">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1664">vervaldag</span></span> 
- <span data-ttu-id="72dfe-1665">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1665">vervaldatum</span></span> 
- <span data-ttu-id="72dfe-1666">vto
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1666">vto</span></span> 
- <span data-ttu-id="72dfe-1667">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1667">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="72dfe-1668">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="72dfe-1668">EU Driver's License Number</span></span>

<span data-ttu-id="72dfe-1669">Para obtener más información, vea [tipo de información confidencial del número de licencia del conductor de la UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="72dfe-1669">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="72dfe-1670">Número de identificación nacional de la UE</span><span class="sxs-lookup"><span data-stu-id="72dfe-1670">EU National Identification Number</span></span>

<span data-ttu-id="72dfe-1671">Para obtener más información, consulte el [tipo de información confidencial de número de identificación nacional de la UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="72dfe-1671">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="72dfe-1672">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="72dfe-1672">EU Passport Number</span></span>

<span data-ttu-id="72dfe-1673">Para obtener más información, consulte [EU Number Sensitive Information Type](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="72dfe-1673">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="72dfe-1674">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="72dfe-1674">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="72dfe-1675">Para obtener más información, consulte el [número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="72dfe-1675">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="72dfe-1676">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="72dfe-1676">EU Tax Identification Number</span></span>

<span data-ttu-id="72dfe-1677">Para obtener más información, vea [tipo de información confidencial de número de identificación de impuestos de la UE](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="72dfe-1677">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="72dfe-1678">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="72dfe-1678">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1679">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1679">Format</span></span>

<span data-ttu-id="72dfe-1680">Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-1680">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1681">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1681">Pattern</span></span>

<span data-ttu-id="72dfe-1682">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1682">Pattern must include all of the following:</span></span>
- <span data-ttu-id="72dfe-1683">Seis dígitos en el formato DDMMAA que son una fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-1683">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="72dfe-1684">Marcador del siglo (ya sea '-', '+' o 'a')</span><span class="sxs-lookup"><span data-stu-id="72dfe-1684">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="72dfe-1685">Número de identificación personal de tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1685">Three-digit personal identification number</span></span> 
- <span data-ttu-id="72dfe-1686">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-1686">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1687">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1687">Checksum</span></span>

<span data-ttu-id="72dfe-1688">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1688">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1689">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1689">Definition</span></span>

<span data-ttu-id="72dfe-1690">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1690">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1691">La función Func_finnish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1691">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1692">Se encuentra una palabra clave de Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1692">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="72dfe-1693">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1693">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1694">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1694">Keywords</span></span>

- <span data-ttu-id="72dfe-1695">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="72dfe-1695">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="72dfe-1696">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="72dfe-1696">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="72dfe-1697">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="72dfe-1697">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="72dfe-1698">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="72dfe-1698">Personbeteckning</span></span>
- <span data-ttu-id="72dfe-1699">Personnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1699">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="72dfe-1700">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="72dfe-1700">Finland Passport Number</span></span>

<span data-ttu-id="72dfe-p130">Combinación de formato de nueve letras y dígitos de la combinación de los patrones de nueve letras y dígitos: dos letras (no distingue entre mayúsculas y minúsculas) siete dígitos de suma de comprobación no Definition una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón. Se encuentra una palabra clave de Keyword_finland_passport_number. Palabras clave <!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> 
 de Passport <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> </Entity></span><span class="sxs-lookup"><span data-stu-id="72dfe-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="72dfe-1705">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="72dfe-1705">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1706">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1706">Format</span></span>

<span data-ttu-id="72dfe-1707">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1707">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1708">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1708">Pattern</span></span>

<span data-ttu-id="72dfe-1709">12 dígitos con validación para descontar patrones similares como los números de teléfono franceses</span><span class="sxs-lookup"><span data-stu-id="72dfe-1709">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1710">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-1710">Checksum</span></span>

<span data-ttu-id="72dfe-1711">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-1711">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1712">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1712">Definition</span></span>

<span data-ttu-id="72dfe-1713">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1713">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1714">La función Func_french_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1714">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1715">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1715">At least one of the following is true:</span></span>
- <span data-ttu-id="72dfe-1716">Se encuentra una palabra clave de Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1716">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="72dfe-1717">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1717">The function Func_eu_date finds a date in the right date format.</span></span>

```
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1718">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1718">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="72dfe-1719">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="72dfe-1719">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="72dfe-1720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="72dfe-1720">drivers licence</span></span>
- <span data-ttu-id="72dfe-1721">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-1721">drivers license</span></span>
- <span data-ttu-id="72dfe-1722">driving licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1722">driving licence</span></span>
- <span data-ttu-id="72dfe-1723">licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-1723">driving license</span></span>
- <span data-ttu-id="72dfe-1724">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="72dfe-1724">permis de conduire</span></span>
- <span data-ttu-id="72dfe-1725">
licence number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1725">licence number</span></span>
- <span data-ttu-id="72dfe-1726">
license number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1726">license number</span></span>
- <span data-ttu-id="72dfe-1727">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="72dfe-1727">licence numbers</span></span>
- <span data-ttu-id="72dfe-1728">

license numbers</span><span class="sxs-lookup"><span data-stu-id="72dfe-1728">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="72dfe-1729">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="72dfe-1729">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1730">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1730">Format</span></span>

<span data-ttu-id="72dfe-1731">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1731">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1732">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1732">Pattern</span></span>

<span data-ttu-id="72dfe-1733">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1733">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1734">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1734">Checksum</span></span>

<span data-ttu-id="72dfe-1735">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-1735">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1736">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1736">Definition</span></span>

<span data-ttu-id="72dfe-1737">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1737">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1738">La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1738">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1739">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1739">Keywords</span></span>

<span data-ttu-id="72dfe-1740">Ninguno</span><span class="sxs-lookup"><span data-stu-id="72dfe-1740">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="72dfe-1741">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="72dfe-1741">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1742">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1742">Format</span></span>

<span data-ttu-id="72dfe-1743">Nueve dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="72dfe-1743">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1744">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1744">Pattern</span></span>

<span data-ttu-id="72dfe-1745">Nueve dígitos y letras:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1745">Nine digits and letters:</span></span>
- <span data-ttu-id="72dfe-1746">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1746">Two digits</span></span> 
- <span data-ttu-id="72dfe-1747">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-1747">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-1748">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1748">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1749">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-1749">Checksum</span></span>

<span data-ttu-id="72dfe-1750">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-1750">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1751">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1751">Definition</span></span>

<span data-ttu-id="72dfe-1752">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1752">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1753">La función Func_fr_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1753">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1754">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1754">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1755">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1755">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="72dfe-1756">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-1756">Keyword_passport</span></span>

- <span data-ttu-id="72dfe-1757">Passport Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1757">Passport Number</span></span>
- <span data-ttu-id="72dfe-1758">
Passport No</span><span class="sxs-lookup"><span data-stu-id="72dfe-1758">Passport No</span></span>
- <span data-ttu-id="72dfe-1759">Passport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1759">Passport #</span></span>
- <span data-ttu-id="72dfe-1760">Passport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1760">Passport#</span></span>
- <span data-ttu-id="72dfe-1761">PassportID</span><span class="sxs-lookup"><span data-stu-id="72dfe-1761">PassportID</span></span>
- <span data-ttu-id="72dfe-1762">Passportno
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1762">Passportno</span></span>
- <span data-ttu-id="72dfe-1763">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1763">passportnumber</span></span>
- <span data-ttu-id="72dfe-1764">パスポート</span><span class="sxs-lookup"><span data-stu-id="72dfe-1764">パスポート</span></span>
- <span data-ttu-id="72dfe-1765">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1765">パスポート番号</span></span>
- <span data-ttu-id="72dfe-1766">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1766">パスポートのNum</span></span>
- <span data-ttu-id="72dfe-1767">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1767">パスポート ＃</span></span> 
- <span data-ttu-id="72dfe-1768">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="72dfe-1768">Numéro de passeport</span></span>
- <span data-ttu-id="72dfe-1769">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="72dfe-1769">Passeport n °</span></span>
- <span data-ttu-id="72dfe-1770">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1770">Passeport Non</span></span>
- <span data-ttu-id="72dfe-1771">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1771">Passeport #</span></span>
- <span data-ttu-id="72dfe-1772">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1772">Passeport#</span></span>
- <span data-ttu-id="72dfe-1773">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="72dfe-1773">PasseportNon</span></span>
- <span data-ttu-id="72dfe-1774">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="72dfe-1774">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="72dfe-1775">Número de seguridad social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="72dfe-1775">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1776">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1776">Format</span></span>

<span data-ttu-id="72dfe-1777">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1777">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1778">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1778">Pattern</span></span>

<span data-ttu-id="72dfe-1779">Debe coincidir uno de los dos patrones:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1779">Must match one of two patterns:</span></span>
- <span data-ttu-id="72dfe-1780">13 dígitos seguidos de un espacio seguido de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1780">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="72dfe-1781">o</span><span class="sxs-lookup"><span data-stu-id="72dfe-1781">or</span></span>
- <span data-ttu-id="72dfe-1782">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1782">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1783">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1783">Checksum</span></span>

<span data-ttu-id="72dfe-1784">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1784">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1785">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1785">Definition</span></span>

<span data-ttu-id="72dfe-1786">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1786">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1787">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1787">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1788">Se encuentra una palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1788">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="72dfe-1789">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1789">The checksum passes.</span></span>

<span data-ttu-id="72dfe-1790">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1790">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1791">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1791">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1792">No se encuentra ninguna palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1792">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="72dfe-1793">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1793">The checksum passes.</span></span>

```
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1794">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1794">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="72dfe-1795">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="72dfe-1795">Keyword_fr_insee</span></span>

- <span data-ttu-id="72dfe-1796">insee</span><span class="sxs-lookup"><span data-stu-id="72dfe-1796">insee</span></span>
- <span data-ttu-id="72dfe-1797">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="72dfe-1797">securité sociale</span></span>
- <span data-ttu-id="72dfe-1798">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="72dfe-1798">securite sociale</span></span>
- <span data-ttu-id="72dfe-1799">
national id</span><span class="sxs-lookup"><span data-stu-id="72dfe-1799">national id</span></span>
- <span data-ttu-id="72dfe-1800">
national identification</span><span class="sxs-lookup"><span data-stu-id="72dfe-1800">national identification</span></span>
- <span data-ttu-id="72dfe-1801">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="72dfe-1801">numéro d'identité</span></span>
- <span data-ttu-id="72dfe-1802">sin d'identité</span><span class="sxs-lookup"><span data-stu-id="72dfe-1802">no d'identité</span></span>
- <span data-ttu-id="72dfe-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="72dfe-p131">no. d'identité</span></span>
- <span data-ttu-id="72dfe-1805">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="72dfe-1805">numero d'identite</span></span>
- <span data-ttu-id="72dfe-1806">sin d'identite</span><span class="sxs-lookup"><span data-stu-id="72dfe-1806">no d'identite</span></span>
- <span data-ttu-id="72dfe-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="72dfe-p132">no. d'identite</span></span>
- <span data-ttu-id="72dfe-1809">social security number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1809">social security number</span></span>
- <span data-ttu-id="72dfe-1810">
social security code</span><span class="sxs-lookup"><span data-stu-id="72dfe-1810">social security code</span></span>
- <span data-ttu-id="72dfe-1811">social insurance number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1811">social insurance number</span></span>
- <span data-ttu-id="72dfe-1812">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="72dfe-1812">le numéro d'identification nationale</span></span>
- <span data-ttu-id="72dfe-1813">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="72dfe-1813">d'identité nationale</span></span>
- <span data-ttu-id="72dfe-1814">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="72dfe-1814">numéro de sécurité sociale</span></span>
- <span data-ttu-id="72dfe-1815">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="72dfe-1815">le code de la sécurité sociale</span></span>
- <span data-ttu-id="72dfe-1816">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="72dfe-1816">numéro d'assurance sociale</span></span>
- <span data-ttu-id="72dfe-1817">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="72dfe-1817">numéro de sécu</span></span>
- <span data-ttu-id="72dfe-1818">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1818">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="72dfe-1819">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="72dfe-1819">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1820">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1820">Format</span></span>

<span data-ttu-id="72dfe-1821">Combinación de 11 dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="72dfe-1821">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1822">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1822">Pattern</span></span>

<span data-ttu-id="72dfe-1823">11 dígitos y letras (no distingue entre mayúsculas y minúsculas):</span><span class="sxs-lookup"><span data-stu-id="72dfe-1823">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="72dfe-1824">Un dígito o una letra </span><span class="sxs-lookup"><span data-stu-id="72dfe-1824">A digit or letter</span></span> 
- <span data-ttu-id="72dfe-1825">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1825">Two digits</span></span> 
- <span data-ttu-id="72dfe-1826">Seis dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="72dfe-1826">Six digits or letters</span></span> 
- <span data-ttu-id="72dfe-1827">Un dígito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1827">A digit</span></span> 
- <span data-ttu-id="72dfe-1828">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="72dfe-1828">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1829">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1829">Checksum</span></span>

<span data-ttu-id="72dfe-1830">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1830">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1831">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1831">Definition</span></span>

<span data-ttu-id="72dfe-1832">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1833">La función Func_german_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1833">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1834">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1834">At least one of the following is true:</span></span>
    - <span data-ttu-id="72dfe-1835">Se encuentra una palabra clave de Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1835">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="72dfe-1836">Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1836">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="72dfe-1837">Se encuentra una palabra clave de Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1837">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="72dfe-1838">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1838">The checksum passes.</span></span>

```
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1839">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1839">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="72dfe-1840">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1840">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="72dfe-1841">Führerschein</span><span class="sxs-lookup"><span data-stu-id="72dfe-1841">Führerschein</span></span>
- <span data-ttu-id="72dfe-1842">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="72dfe-1842">Fuhrerschein</span></span>
- <span data-ttu-id="72dfe-1843">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="72dfe-1843">Fuehrerschein</span></span>
- <span data-ttu-id="72dfe-1844">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1844">Führerscheinnummer</span></span>
- <span data-ttu-id="72dfe-1845">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1845">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="72dfe-1846">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1846">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="72dfe-1847">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1847">Führerschein-</span></span> 
- <span data-ttu-id="72dfe-1848">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1848">Fuhrerschein-</span></span> 
- <span data-ttu-id="72dfe-1849">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1849">Fuehrerschein-</span></span> 
- <span data-ttu-id="72dfe-1850">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="72dfe-1850">FührerscheinnummerNr</span></span>
- <span data-ttu-id="72dfe-1851">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="72dfe-1851">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="72dfe-1852">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="72dfe-1852">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="72dfe-1853">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1853">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="72dfe-1854">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1854">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="72dfe-1855">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1855">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="72dfe-1856">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1856">Führerschein- Nr</span></span>
- <span data-ttu-id="72dfe-1857">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1857">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="72dfe-1858">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1858">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="72dfe-1859">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1859">Führerschein- Klasse</span></span> 
- <span data-ttu-id="72dfe-1860">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1860">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="72dfe-1861">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1861">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="72dfe-1862">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="72dfe-1862">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="72dfe-1863">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="72dfe-1863">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="72dfe-1864">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="72dfe-1864">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="72dfe-1865">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1865">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="72dfe-1866">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1866">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="72dfe-1867">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1867">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="72dfe-1868">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1868">Führerschein- Nr</span></span> 
- <span data-ttu-id="72dfe-1869">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1869">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="72dfe-1870">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1870">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="72dfe-1871">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1871">Führerschein- Klasse</span></span> 
- <span data-ttu-id="72dfe-1872">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1872">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="72dfe-1873">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1873">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="72dfe-1874">DL</span><span class="sxs-lookup"><span data-stu-id="72dfe-1874">DL</span></span> 
- <span data-ttu-id="72dfe-1875">DLS</span><span class="sxs-lookup"><span data-stu-id="72dfe-1875">DLS</span></span>
- <span data-ttu-id="72dfe-1876">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1876">Driv Lic</span></span> 
- <span data-ttu-id="72dfe-1877">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1877">Driv Licen</span></span> 
- <span data-ttu-id="72dfe-1878">Driv License</span><span class="sxs-lookup"><span data-stu-id="72dfe-1878">Driv License</span></span>
- <span data-ttu-id="72dfe-1879">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1879">Driv Licenses</span></span> 
- <span data-ttu-id="72dfe-1880">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1880">Driv Licence</span></span> 
- <span data-ttu-id="72dfe-1881">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1881">Driv Licences</span></span> 
- <span data-ttu-id="72dfe-1882">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1882">Driv Lic</span></span> 
- <span data-ttu-id="72dfe-1883">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1883">Driver Licen</span></span> 
- <span data-ttu-id="72dfe-1884">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-1884">Driver License</span></span> 
- <span data-ttu-id="72dfe-1885">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-1885">Driver Licenses</span></span> 
- <span data-ttu-id="72dfe-1886">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1886">Driver Licence</span></span> 
- <span data-ttu-id="72dfe-1887">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1887">Driver Licences</span></span> 
- <span data-ttu-id="72dfe-1888">Lic de los drivers</span><span class="sxs-lookup"><span data-stu-id="72dfe-1888">Drivers Lic</span></span> 
- <span data-ttu-id="72dfe-1889">Controladores licen</span><span class="sxs-lookup"><span data-stu-id="72dfe-1889">Drivers Licen</span></span> 
- <span data-ttu-id="72dfe-1890">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-1890">Drivers License</span></span> 
- <span data-ttu-id="72dfe-1891">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-1891">Drivers Licenses</span></span> 
- <span data-ttu-id="72dfe-1892">Licencia de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-1892">Drivers Licence</span></span> 
- <span data-ttu-id="72dfe-1893">Licencias de conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-1893">Drivers Licences</span></span> 
- <span data-ttu-id="72dfe-1894">Lic del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-1894">Driver's Lic</span></span> 
- <span data-ttu-id="72dfe-1895">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1895">Driver's Licen</span></span> 
- <span data-ttu-id="72dfe-1896">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-1896">Driver's License</span></span> 
- <span data-ttu-id="72dfe-1897">Licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-1897">Driver's Licenses</span></span> 
- <span data-ttu-id="72dfe-1898">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1898">Driver's Licence</span></span> 
- <span data-ttu-id="72dfe-1899">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1899">Driver's Licences</span></span> 
- <span data-ttu-id="72dfe-1900">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1900">Driving Lic</span></span> 
- <span data-ttu-id="72dfe-1901">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1901">Driving Licen</span></span> 
- <span data-ttu-id="72dfe-1902">Driving License
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1902">Driving License</span></span> 
- <span data-ttu-id="72dfe-1903">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1903">Driving Licenses</span></span> 
- <span data-ttu-id="72dfe-1904">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="72dfe-1904">Driving Licence</span></span> 
- <span data-ttu-id="72dfe-1905">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="72dfe-1905">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="72dfe-1906">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="72dfe-1906">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="72dfe-1907">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1907">Nr-Führerschein</span></span> 
- <span data-ttu-id="72dfe-1908">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1908">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="72dfe-1909">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1909">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="72dfe-1910">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1910">No-Führerschein</span></span> 
- <span data-ttu-id="72dfe-1911">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1911">No-Fuhrerschein</span></span> 
- <span data-ttu-id="72dfe-1912">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1912">No-Fuehrerschein</span></span> 
- <span data-ttu-id="72dfe-1913">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1913">N-Führerschein</span></span> 
- <span data-ttu-id="72dfe-1914">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1914">N-Fuhrerschein</span></span> 
- <span data-ttu-id="72dfe-1915">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="72dfe-1915">N-Fuehrerschein</span></span>
- <span data-ttu-id="72dfe-1916">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1916">Nr-Führerschein</span></span> 
- <span data-ttu-id="72dfe-1917">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1917">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="72dfe-1918">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1918">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="72dfe-1919">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1919">No-Führerschein</span></span> 
- <span data-ttu-id="72dfe-1920">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1920">No-Fuhrerschein</span></span> 
- <span data-ttu-id="72dfe-1921">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1921">No-Fuehrerschein</span></span> 
- <span data-ttu-id="72dfe-1922">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1922">N-Führerschein</span></span> 
- <span data-ttu-id="72dfe-1923">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1923">N-Fuhrerschein</span></span> 
- <span data-ttu-id="72dfe-1924">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="72dfe-1924">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="72dfe-1925">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="72dfe-1925">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="72dfe-1926">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="72dfe-1926">ausstellungsdatum</span></span>
- <span data-ttu-id="72dfe-1927">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="72dfe-1927">ausstellungsort</span></span>
- <span data-ttu-id="72dfe-1928">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="72dfe-1928">ausstellende behöde</span></span>
- <span data-ttu-id="72dfe-1929">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="72dfe-1929">ausstellende behorde</span></span>
- <span data-ttu-id="72dfe-1930">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="72dfe-1930">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="72dfe-1931">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="72dfe-1931">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1932">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1932">Format</span></span>

<span data-ttu-id="72dfe-1933">10 dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="72dfe-1933">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1934">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1934">Pattern</span></span>

<span data-ttu-id="72dfe-1935">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1935">Pattern must include all of the following:</span></span>
- <span data-ttu-id="72dfe-1936">El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="72dfe-1936">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="72dfe-1937">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1937">Three digits</span></span> 
- <span data-ttu-id="72dfe-1938">Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="72dfe-1938">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="72dfe-1939">Un dígito</span><span class="sxs-lookup"><span data-stu-id="72dfe-1939">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1940">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1940">Checksum</span></span>

<span data-ttu-id="72dfe-1941">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-1941">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1942">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1942">Definition</span></span>

<span data-ttu-id="72dfe-1943">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1943">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1944">La función Func_german_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1944">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1945">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1945">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="72dfe-1946">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1946">The checksum passes.</span></span>

<span data-ttu-id="72dfe-1947">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1947">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1948">La función Func_german_passport_data encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1948">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1949">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1949">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="72dfe-1950">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1950">The checksum passes.</span></span>

```
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1951">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1951">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="72dfe-1952">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-1952">Keyword_german_passport</span></span>

- <span data-ttu-id="72dfe-1953">reisepass</span><span class="sxs-lookup"><span data-stu-id="72dfe-1953">reisepass</span></span>
- <span data-ttu-id="72dfe-1954">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="72dfe-1954">reisepasse</span></span>
- <span data-ttu-id="72dfe-1955">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1955">reisepassnummer</span></span>
- <span data-ttu-id="72dfe-1956">passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-1956">passport</span></span>
- <span data-ttu-id="72dfe-1957">

passports</span><span class="sxs-lookup"><span data-stu-id="72dfe-1957">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="72dfe-1958">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="72dfe-1958">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="72dfe-1959">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="72dfe-1959">geburtsdatum</span></span>
- <span data-ttu-id="72dfe-1960">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="72dfe-1960">ausstellungsdatum</span></span>
- <span data-ttu-id="72dfe-1961">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="72dfe-1961">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="72dfe-1962">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-1962">Keyword_german_passport_number</span></span>

<span data-ttu-id="72dfe-1963">No-Reisepass NR-Reisepass</span><span class="sxs-lookup"><span data-stu-id="72dfe-1963">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="72dfe-1964">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="72dfe-1964">Keyword_german_passport1</span></span>

<span data-ttu-id="72dfe-1965">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="72dfe-1965">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="72dfe-1966">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="72dfe-1966">Keyword_german_passport2</span></span>

<span data-ttu-id="72dfe-1967">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="72dfe-1967">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="72dfe-1968">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="72dfe-1968">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1969">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1969">Format</span></span>

<span data-ttu-id="72dfe-1970">Desde el 1 de noviembre de 2010: nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1970">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="72dfe-1971">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1971">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1972">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1972">Pattern</span></span>

<span data-ttu-id="72dfe-1973">Desde el 1 de noviembre de 2010:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1973">Since 1 November 2010:</span></span>
- <span data-ttu-id="72dfe-1974">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-1974">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-1975">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1975">Eight digits</span></span>

<span data-ttu-id="72dfe-1976">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1976">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="72dfe-1977">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-1977">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-1978">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-1978">Checksum</span></span>

<span data-ttu-id="72dfe-1979">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-1979">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-1980">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-1980">Definition</span></span>

<span data-ttu-id="72dfe-1981">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-1981">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-1982">La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1982">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-1983">Se encuentra una palabra clave de Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-1983">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-1984">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-1984">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="72dfe-1985">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-1985">Keyword_germany_id_card</span></span>

- <span data-ttu-id="72dfe-1986">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-1986">Identity Card</span></span>
- <span data-ttu-id="72dfe-1987">ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-1987">ID</span></span>
- <span data-ttu-id="72dfe-1988">Identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-1988">Identification</span></span>
- <span data-ttu-id="72dfe-1989">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="72dfe-1989">Personalausweis</span></span>
- <span data-ttu-id="72dfe-1990">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-1990">Identifizierungsnummer</span></span>
- <span data-ttu-id="72dfe-1991">Ausweis</span><span class="sxs-lookup"><span data-stu-id="72dfe-1991">Ausweis</span></span>
- <span data-ttu-id="72dfe-1992">Identifikation</span><span class="sxs-lookup"><span data-stu-id="72dfe-1992">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="72dfe-1993">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="72dfe-1993">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-1994">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-1994">Format</span></span>

<span data-ttu-id="72dfe-1995">Combinación de 7 u 8 letras y números más un guión</span><span class="sxs-lookup"><span data-stu-id="72dfe-1995">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-1996">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-1996">Pattern</span></span>

<span data-ttu-id="72dfe-1997">Siete letras y números (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="72dfe-1997">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="72dfe-1998">Una letra (cualquier letra del alfabeto griego) </span><span class="sxs-lookup"><span data-stu-id="72dfe-1998">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="72dfe-1999">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-1999">A dash</span></span> 
- <span data-ttu-id="72dfe-2000">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2000">Six digits</span></span>

<span data-ttu-id="72dfe-2001">Ocho letras y números (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="72dfe-2001">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="72dfe-2002">Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2002">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="72dfe-2003">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-2003">A dash</span></span> 
- <span data-ttu-id="72dfe-2004">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2004">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2005">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2005">Checksum</span></span>

<span data-ttu-id="72dfe-2006">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2006">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2007">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2007">Definition</span></span>

<span data-ttu-id="72dfe-2008">Una directiva DLP está 75 % segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2008">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2009">La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2009">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2010">Se encuentra una palabra clave de Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2010">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2011">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2011">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="72dfe-2012">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-2012">Keyword_greece_id_card</span></span>

- <span data-ttu-id="72dfe-2013">Tarjeta de identidad griega</span><span class="sxs-lookup"><span data-stu-id="72dfe-2013">Greek identity Card</span></span>
- <span data-ttu-id="72dfe-2014">Tautotita</span><span class="sxs-lookup"><span data-stu-id="72dfe-2014">Tautotita</span></span>
- <span data-ttu-id="72dfe-2015">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="72dfe-2015">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="72dfe-2016">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="72dfe-2016">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="72dfe-2017">Número de tarjeta de identidad de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2017">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2018">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2018">Format</span></span>

<span data-ttu-id="72dfe-2019">Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final</span><span class="sxs-lookup"><span data-stu-id="72dfe-2019">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2020">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2020">Pattern</span></span>

<span data-ttu-id="72dfe-2021">Combinación de 8 o 9 letras:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2021">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="72dfe-2022">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2022">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-2023">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2023">Six digits</span></span> 
- <span data-ttu-id="72dfe-2024">El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2024">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2025">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2025">Checksum</span></span>

<span data-ttu-id="72dfe-2026">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2026">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2027">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2027">Definition</span></span>

<span data-ttu-id="72dfe-2028">Una directiva DLP está 75 % segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2028">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2029">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2029">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2030">Se encuentra una palabra clave de Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2030">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="72dfe-2031">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2031">The checksum passes.</span></span>

<span data-ttu-id="72dfe-2032">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2032">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2033">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2033">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2034">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2034">The checksum passes.</span></span>

```
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2035">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2035">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="72dfe-2036">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-2036">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="72dfe-2037">tarjeta de identidad de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="72dfe-2037">hong kong identity card</span></span>
- <span data-ttu-id="72dfe-2038">HKIDC</span><span class="sxs-lookup"><span data-stu-id="72dfe-2038">HKIDC</span></span>
- <span data-ttu-id="72dfe-2039">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2039">id card</span></span>
- <span data-ttu-id="72dfe-2040">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-2040">identity card</span></span>
- <span data-ttu-id="72dfe-2041">tarjeta de identidad HK</span><span class="sxs-lookup"><span data-stu-id="72dfe-2041">hk identity card</span></span>
- <span data-ttu-id="72dfe-2042">ID de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="72dfe-2042">hong kong id</span></span>
- <span data-ttu-id="72dfe-2043">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2043">香港身份證</span></span>
- <span data-ttu-id="72dfe-2044">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2044">香港永久性居民身份證</span></span>
- <span data-ttu-id="72dfe-2045">身份證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2045">身份證</span></span>
- <span data-ttu-id="72dfe-2046">身份証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2046">身份証</span></span>
- <span data-ttu-id="72dfe-2047">身分證 </span><span class="sxs-lookup"><span data-stu-id="72dfe-2047">身分證</span></span>
- <span data-ttu-id="72dfe-2048">身分証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2048">身分証</span></span>
- <span data-ttu-id="72dfe-2049">香港身份証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2049">香港身份証</span></span>
- <span data-ttu-id="72dfe-2050">香港身分證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2050">香港身分證</span></span>
- <span data-ttu-id="72dfe-2051">香港身分証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2051">香港身分証</span></span>
- <span data-ttu-id="72dfe-2052">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2052">香港身份證</span></span>
- <span data-ttu-id="72dfe-2053">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2053">香港居民身份證</span></span>
- <span data-ttu-id="72dfe-2054">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2054">香港居民身份証</span></span>
- <span data-ttu-id="72dfe-2055">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2055">香港居民身分證</span></span>
- <span data-ttu-id="72dfe-2056">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2056">香港居民身分証</span></span>
- <span data-ttu-id="72dfe-2057">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2057">香港永久性居民身份証</span></span>
- <span data-ttu-id="72dfe-2058">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2058">香港永久性居民身分證</span></span>
- <span data-ttu-id="72dfe-2059">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2059">香港永久性居民身分証</span></span>
- <span data-ttu-id="72dfe-2060">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2060">香港永久性居民身份證</span></span>
- <span data-ttu-id="72dfe-2061">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2061">香港非永久性居民身份證</span></span>
- <span data-ttu-id="72dfe-2062">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2062">香港非永久性居民身份証</span></span>
- <span data-ttu-id="72dfe-2063">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2063">香港非永久性居民身分證</span></span>
- <span data-ttu-id="72dfe-2064">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2064">香港非永久性居民身分証</span></span>
- <span data-ttu-id="72dfe-2065">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2065">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="72dfe-2066">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2066">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="72dfe-2067">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2067">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="72dfe-2068">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2068">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="72dfe-2069">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2069">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="72dfe-2070">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2070">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="72dfe-2071">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="72dfe-2071">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="72dfe-2072">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2072">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="72dfe-2073">Número de cuenta permanente de India (PAN)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2073">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2074">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2074">Format</span></span>

<span data-ttu-id="72dfe-2075">10 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2075">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2076">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2076">Pattern</span></span>

<span data-ttu-id="72dfe-2077">10 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2077">10 letters or digits:</span></span>
- <span data-ttu-id="72dfe-2078">Cinco letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2078">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-2079">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2079">Four digits</span></span> 
- <span data-ttu-id="72dfe-2080">Una letra que es un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="72dfe-2080">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2081">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2081">Checksum</span></span>

<span data-ttu-id="72dfe-2082">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2083">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2083">Definition</span></span>

<span data-ttu-id="72dfe-2084">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2084">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2085">La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2085">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2086">Se encuentra una palabra clave de Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2086">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="72dfe-2087">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2087">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2088">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2088">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="72dfe-2089">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2089">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="72dfe-2090">Número de cuenta permanente
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2090">Permanent Account Number</span></span> 
- <span data-ttu-id="72dfe-2091">PAN
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2091">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="72dfe-2092">Número de identificación único (Aadhaar) de la India</span><span class="sxs-lookup"><span data-stu-id="72dfe-2092">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2093">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2093">Format</span></span>

<span data-ttu-id="72dfe-2094">12 dígitos que contienen espacios o guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="72dfe-2094">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2095">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2095">Pattern</span></span>

<span data-ttu-id="72dfe-2096">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2096">12 digits:</span></span>
- <span data-ttu-id="72dfe-2097">Cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2097">Four digits</span></span> 
- <span data-ttu-id="72dfe-2098">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="72dfe-2098">An optional space or dash</span></span> 
- <span data-ttu-id="72dfe-2099">Cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2099">Four digits</span></span> 
- <span data-ttu-id="72dfe-2100">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="72dfe-2100">An optional space or dash</span></span> 
- <span data-ttu-id="72dfe-2101">El dígito final que es el dígito de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-2101">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2102">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2102">Checksum</span></span>

<span data-ttu-id="72dfe-2103">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2103">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2104">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2104">Definition</span></span>

<span data-ttu-id="72dfe-p133">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón. Se encuentra una palabra clave de Keyword_india_aadhar. La suma de comprobación se supera. Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón. La suma de comprobación se supera. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="72dfe-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="72dfe-2111">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2111">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="72dfe-2112">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="72dfe-2112">Keyword_india_aadhar</span></span>
- <span data-ttu-id="72dfe-2113">Aadhar</span><span class="sxs-lookup"><span data-stu-id="72dfe-2113">Aadhar</span></span>
- <span data-ttu-id="72dfe-2114">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="72dfe-2114">Aadhaar</span></span>
- <span data-ttu-id="72dfe-2115">UID</span><span class="sxs-lookup"><span data-stu-id="72dfe-2115">UID</span></span>
- <span data-ttu-id="72dfe-2116">आधार</span><span class="sxs-lookup"><span data-stu-id="72dfe-2116">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="72dfe-2117">Número de tarjeta de identidad (KTP) de Indonesia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2117">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2118">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2118">Format</span></span>

<span data-ttu-id="72dfe-2119">16 dígitos que contienen puntos opcionales</span><span class="sxs-lookup"><span data-stu-id="72dfe-2119">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2120">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2120">Pattern</span></span>

<span data-ttu-id="72dfe-2121">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2121">16 digits:</span></span>
- <span data-ttu-id="72dfe-2122">Código de la provincia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2122">Two-digit province code</span></span> 
- <span data-ttu-id="72dfe-2123">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2123">A period (optional)</span></span> 
- <span data-ttu-id="72dfe-2124">Código de ciudad o regencia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2124">Two-digit regency or city code</span></span> 
- <span data-ttu-id="72dfe-2125">Código de subdistrito de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2125">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="72dfe-2126">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2126">A period (optional)</span></span> 
- <span data-ttu-id="72dfe-2127">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-2127">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="72dfe-2128">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2128">A period (optional)</span></span> 
- <span data-ttu-id="72dfe-2129">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2129">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2130">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2130">Checksum</span></span>

<span data-ttu-id="72dfe-2131">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2131">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2132">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2132">Definition</span></span>

<span data-ttu-id="72dfe-2133">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2133">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2134">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2134">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2135">Se encuentra una palabra clave de Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2135">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="72dfe-2136">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2137">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2137">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2138">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2138">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="72dfe-2139">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-2139">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="72dfe-2140">KTP</span><span class="sxs-lookup"><span data-stu-id="72dfe-2140">KTP</span></span>
- <span data-ttu-id="72dfe-2141">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2141">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="72dfe-2142">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2142">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="72dfe-2143">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2143">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2144">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2144">Format</span></span>

<span data-ttu-id="72dfe-2145">Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2145">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2146">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2146">Pattern</span></span>

<span data-ttu-id="72dfe-2147">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2147">Pattern must include all of the following:</span></span>

- <span data-ttu-id="72dfe-2148">Código de país de dos letras</span><span class="sxs-lookup"><span data-stu-id="72dfe-2148">Two-letter country code</span></span>
- <span data-ttu-id="72dfe-2149">Dos dígitos de control (seguidos de un espacio opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2149">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="72dfe-2150">1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2150">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="72dfe-2151">1-3 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2151">1-3 letters or digits</span></span>

<span data-ttu-id="72dfe-p134">El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:</span><span class="sxs-lookup"><span data-stu-id="72dfe-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="72dfe-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="72dfe-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2155">Checksum</span></span>

<span data-ttu-id="72dfe-2156">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2156">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2157">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2157">Definition</span></span>

<span data-ttu-id="72dfe-2158">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2158">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2159">La función Func_iban encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2159">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2160">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2160">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2161">Keywords</span></span>

<span data-ttu-id="72dfe-2162">Ninguno</span><span class="sxs-lookup"><span data-stu-id="72dfe-2162">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="72dfe-2163">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="72dfe-2163">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2164">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2164">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="72dfe-2165">IPv4:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2165">IPv4:</span></span>
<span data-ttu-id="72dfe-2166">Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="72dfe-2166">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="72dfe-2167">IPv6:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2167">IPv6:</span></span>
<span data-ttu-id="72dfe-2168"> Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2168">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2169">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2169">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2170">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2170">Checksum</span></span>

<span data-ttu-id="72dfe-2171">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2172">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2172">Definition</span></span>

<span data-ttu-id="72dfe-2173">Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2173">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2174">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2174">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2175">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2175">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="72dfe-2176">Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2176">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2177">La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2177">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2178">Se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2178">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="72dfe-2179">Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2179">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2180">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2180">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2181">No se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2181">No keyword from Keyword_ipaddress is found.</span></span>

```
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2182">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2182">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="72dfe-2183">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="72dfe-2183">Keyword_ipaddress</span></span>

- <span data-ttu-id="72dfe-2184">IP (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2184">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="72dfe-2185">dirección IP
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2185">ip address</span></span> 
- <span data-ttu-id="72dfe-2186">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="72dfe-2186">ip addresses</span></span>
- <span data-ttu-id="72dfe-2187">internet protocol</span><span class="sxs-lookup"><span data-stu-id="72dfe-2187">internet protocol</span></span>
- <span data-ttu-id="72dfe-2188">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2188">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="72dfe-2189">Clasificación Internacional de enfermedades (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2189">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2190">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2190">Format</span></span>

<span data-ttu-id="72dfe-2191">Diccionario</span><span class="sxs-lookup"><span data-stu-id="72dfe-2191">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2192">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2192">Pattern</span></span>

<span data-ttu-id="72dfe-2193">Palabraclave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2193">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2194">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2194">Checksum</span></span>

<span data-ttu-id="72dfe-2195">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2195">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2196">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2196">Definition</span></span>

<span data-ttu-id="72dfe-2197">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2197">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2198">Se encuentra una palabra clave de Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2198">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="72dfe-2199">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2199">Keywords</span></span>

<span data-ttu-id="72dfe-p135">Cualquier término del Diccionario de palabras clave de Dictionary_icd_10_cm, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="72dfe-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="72dfe-2202">Clasificación Internacional de enfermedades (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2202">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2203">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2203">Format</span></span>

<span data-ttu-id="72dfe-2204">Diccionario</span><span class="sxs-lookup"><span data-stu-id="72dfe-2204">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2205">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2205">Pattern</span></span>

<span data-ttu-id="72dfe-2206">Palabraclave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2206">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2207">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2207">Checksum</span></span>

<span data-ttu-id="72dfe-2208">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2208">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2209">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2209">Definition</span></span>

<span data-ttu-id="72dfe-2210">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2210">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2211">Se encuentra una palabra clave de Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2211">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2212">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2212">Keywords</span></span>

<span data-ttu-id="72dfe-p136">Cualquier término del Diccionario de palabras clave de Dictionary_icd_9_cm, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="72dfe-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="72dfe-2215">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="72dfe-2215">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2216">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2216">Format</span></span>

<span data-ttu-id="72dfe-2217">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="72dfe-2217">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="72dfe-2218">Siete dígitos seguidos por 1 o 2 letras </span><span class="sxs-lookup"><span data-stu-id="72dfe-2218">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="72dfe-2219">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="72dfe-2219">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="72dfe-2220">Siete dígitos seguidos por dos letras</span><span class="sxs-lookup"><span data-stu-id="72dfe-2220">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2221">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2221">Pattern</span></span>

<span data-ttu-id="72dfe-2222">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="72dfe-2222">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="72dfe-2223">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2223">Seven digits</span></span> 
- <span data-ttu-id="72dfe-2224">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2224">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="72dfe-2225">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="72dfe-2225">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="72dfe-2226">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2226">Seven digits</span></span> 
- <span data-ttu-id="72dfe-2227">Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético </span><span class="sxs-lookup"><span data-stu-id="72dfe-2227">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="72dfe-2228">La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2228">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2229">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2229">Checksum</span></span>

<span data-ttu-id="72dfe-2230">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2230">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2231">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2231">Definition</span></span>

<span data-ttu-id="72dfe-2232">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2232">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2233">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2233">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2234">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2234">One of the following is true:</span></span>
    - <span data-ttu-id="72dfe-2235">Se encuentra una palabra clave de Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2235">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="72dfe-2236">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2236">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="72dfe-2237">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2237">The checksum passes.</span></span>

<span data-ttu-id="72dfe-2238">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2238">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2239">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2239">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2240">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2240">The checksum passes.</span></span>

```
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2241">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2241">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="72dfe-2242">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="72dfe-2242">Keyword_ireland_pps</span></span>

- <span data-ttu-id="72dfe-2243">Número de servicio público personal 
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2243">Personal Public Service Number</span></span> 
- <span data-ttu-id="72dfe-2244">Número de PPS
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2244">PPS Number</span></span> 
- <span data-ttu-id="72dfe-2245">Núm. PPS
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2245">PPS Num</span></span> 
- <span data-ttu-id="72dfe-2246">N.º PPS
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2246">PPS No.</span></span> 
- <span data-ttu-id="72dfe-2247">N.ro PPS
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2247">PPS #</span></span> 
- <span data-ttu-id="72dfe-2248">PPS</span><span class="sxs-lookup"><span data-stu-id="72dfe-2248">PPS#</span></span> 
- <span data-ttu-id="72dfe-2249">NPPS
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2249">PPSN</span></span> 
- <span data-ttu-id="72dfe-2250">Tarjeta de servicios públicos
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2250">Public Services Card</span></span> 
- <span data-ttu-id="72dfe-2251">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2251">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="72dfe-p137">Uimh. PSP
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="72dfe-2254">PSP
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2254">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="72dfe-2255">Número de cuenta bancaria de Israel</span><span class="sxs-lookup"><span data-stu-id="72dfe-2255">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2256">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2256">Format</span></span>

<span data-ttu-id="72dfe-2257">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2257">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2258">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2258">Pattern</span></span>

<span data-ttu-id="72dfe-2259">Con formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2259">Formatted:</span></span>
- <span data-ttu-id="72dfe-2260">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2260">Two digits</span></span> 
- <span data-ttu-id="72dfe-2261">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-2261">A dash</span></span> 
- <span data-ttu-id="72dfe-2262">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2262">Three digits</span></span> 
- <span data-ttu-id="72dfe-2263">Guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-2263">A dash</span></span> 
- <span data-ttu-id="72dfe-2264">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2264">Eight digits</span></span>

<span data-ttu-id="72dfe-2265">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2265">Unformatted:</span></span>
- <span data-ttu-id="72dfe-2266">	13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2266">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2267">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2267">Checksum</span></span>

<span data-ttu-id="72dfe-2268">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2269">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2269">Definition</span></span>

<span data-ttu-id="72dfe-2270">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2271">La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2271">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2272">Se encuentra una palabra clave de Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2272">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2273">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2273">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="72dfe-2274">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2274">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="72dfe-2275">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2275">Bank Account Number</span></span> 
- <span data-ttu-id="72dfe-2276">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2276">Bank Account</span></span> 
- <span data-ttu-id="72dfe-2277">Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2277">Account Number</span></span> 
- <span data-ttu-id="72dfe-2278">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2278">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="72dfe-2279">Identificación nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="72dfe-2279">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2280">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2280">Format</span></span>

<span data-ttu-id="72dfe-2281">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2281">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2282">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2282">Pattern</span></span>

<span data-ttu-id="72dfe-2283">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2283">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2284">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2284">Checksum</span></span>

<span data-ttu-id="72dfe-2285">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2285">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2286">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2286">Definition</span></span>

<span data-ttu-id="72dfe-2287">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2288">La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2288">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2289">Se encuentra una palabra clave de Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2289">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="72dfe-2290">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2290">The checksum passes.</span></span>

```
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2291">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2291">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="72dfe-2292">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-2292">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="72dfe-2293">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2293">מספר זהות</span></span> 
- <span data-ttu-id="72dfe-2294">National ID Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2294">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="72dfe-2295">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2295">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2296">Format</span></span>

<span data-ttu-id="72dfe-2297">Una combinación de 10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2297">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2298">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2298">Pattern</span></span>

- <span data-ttu-id="72dfe-2299">Una combinación de 10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2299">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="72dfe-2300">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2300">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-2301">La letra "A" o "V" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2301">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-2302">Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado</span><span class="sxs-lookup"><span data-stu-id="72dfe-2302">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="72dfe-2303">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2303">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2304">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2304">Checksum</span></span>

<span data-ttu-id="72dfe-2305">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2305">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2306">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2306">Definition</span></span>

<span data-ttu-id="72dfe-2307">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2308">La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2308">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2309">Se encuentra una palabra clave de Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2309">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2310">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2310">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="72dfe-2311">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2311">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="72dfe-2312">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2312">numero di patente di guida</span></span> 
- <span data-ttu-id="72dfe-2313">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2313">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="72dfe-2314">Número de cuenta bancaria de Japón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2314">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2315">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2315">Format</span></span>

<span data-ttu-id="72dfe-2316">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2316">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2317">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2317">Pattern</span></span>

<span data-ttu-id="72dfe-2318">Número de cuenta bancaria:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2318">Bank account number:</span></span>
- <span data-ttu-id="72dfe-2319">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2319">Seven or eight digits</span></span>
- <span data-ttu-id="72dfe-2320">Código de sucursal del banco:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2320">Bank account branch code:</span></span>
- <span data-ttu-id="72dfe-2321">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2321">Four digits</span></span> 
- <span data-ttu-id="72dfe-2322">Un espacio o un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2322">A space or dash (optional)</span></span> 
- <span data-ttu-id="72dfe-2323">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2323">Three digits</span></span>

<span data-ttu-id="72dfe-2324">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2324">Checksum</span></span>

<span data-ttu-id="72dfe-2325">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2325">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2326">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2326">Definition</span></span>

<span data-ttu-id="72dfe-2327">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2327">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2328">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2328">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2329">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2329">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="72dfe-2330">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2330">One of the following is true:</span></span>
- <span data-ttu-id="72dfe-2331">La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2331">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2332">Se encuentra una palabra clave de Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2332">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="72dfe-2333">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2333">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2334">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2334">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2335">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2335">A keyword from Keyword_jp_bank_account is found.</span></span>

```
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2336">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2336">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="72dfe-2337">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="72dfe-2337">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="72dfe-2338">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2338">Checking Account Number</span></span> 
- <span data-ttu-id="72dfe-2339">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2339">Checking Account</span></span> 
- <span data-ttu-id="72dfe-2340">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2340">Checking Account #</span></span> 
- <span data-ttu-id="72dfe-2341">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2341">Checking Acct Number</span></span> 
- <span data-ttu-id="72dfe-2342">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2342">Checking Acct #</span></span> 
- <span data-ttu-id="72dfe-2343">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2343">Checking Acct No.</span></span> 
- <span data-ttu-id="72dfe-2344">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2344">Checking Account No.</span></span> 
- <span data-ttu-id="72dfe-2345">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2345">Bank Account Number</span></span> 
- <span data-ttu-id="72dfe-2346">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2346">Bank Account</span></span> 
- <span data-ttu-id="72dfe-2347">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2347">Bank Account #</span></span> 
- <span data-ttu-id="72dfe-2348">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2348">Bank Acct Number</span></span> 
- <span data-ttu-id="72dfe-2349">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2349">Bank Acct #</span></span> 
- <span data-ttu-id="72dfe-2350">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2350">Bank Acct No.</span></span> 
- <span data-ttu-id="72dfe-2351">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2351">Bank Account No.</span></span> 
- <span data-ttu-id="72dfe-2352">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2352">Savings Account Number</span></span> 
- <span data-ttu-id="72dfe-2353">Cuenta de ahorro</span><span class="sxs-lookup"><span data-stu-id="72dfe-2353">Savings Account</span></span> 
- <span data-ttu-id="72dfe-2354">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2354">Savings Account #</span></span> 
- <span data-ttu-id="72dfe-2355">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2355">Savings Acct Number</span></span> 
- <span data-ttu-id="72dfe-2356">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2356">Savings Acct #</span></span> 
- <span data-ttu-id="72dfe-2357">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2357">Savings Acct No.</span></span> 
- <span data-ttu-id="72dfe-2358">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2358">Savings Account No.</span></span> 
- <span data-ttu-id="72dfe-2359">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2359">Debit Account Number</span></span> 
- <span data-ttu-id="72dfe-2360">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2360">Debit Account</span></span> 
- <span data-ttu-id="72dfe-2361">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2361">Debit Account #</span></span> 
- <span data-ttu-id="72dfe-2362">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2362">Debit Acct Number</span></span> 
- <span data-ttu-id="72dfe-2363">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2363">Debit Acct #</span></span> 
- <span data-ttu-id="72dfe-2364">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2364">Debit Acct No.</span></span> 
- <span data-ttu-id="72dfe-2365">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2365">Debit Account No.</span></span> 
- <span data-ttu-id="72dfe-2366">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2366">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="72dfe-2367">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2367">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="72dfe-2368">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2368">＃勘定の確認</span></span> 
- <span data-ttu-id="72dfe-2369">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2369">勘定番号の確認</span></span> 
- <span data-ttu-id="72dfe-2370">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2370">口座番号の確認</span></span> 
- <span data-ttu-id="72dfe-2371">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="72dfe-2371">銀行口座番号</span></span> 
- <span data-ttu-id="72dfe-2372">銀行口座</span><span class="sxs-lookup"><span data-stu-id="72dfe-2372">銀行口座</span></span> 
- <span data-ttu-id="72dfe-2373">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2373">銀行口座＃</span></span> 
- <span data-ttu-id="72dfe-2374">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2374">銀行の勘定番号</span></span> 
- <span data-ttu-id="72dfe-2375">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2375">銀行のacct＃</span></span> 
- <span data-ttu-id="72dfe-2376">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2376">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="72dfe-2377">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="72dfe-2377">銀行口座番号</span></span>
- <span data-ttu-id="72dfe-2378">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2378">普通預金口座番号</span></span> 
- <span data-ttu-id="72dfe-2379">預金口座
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2379">預金口座</span></span> 
- <span data-ttu-id="72dfe-2380">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2380">貯蓄口座＃</span></span> 
- <span data-ttu-id="72dfe-2381">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2381">貯蓄勘定の数</span></span> 
- <span data-ttu-id="72dfe-2382">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2382">貯蓄勘定＃</span></span> 
- <span data-ttu-id="72dfe-2383">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2383">貯蓄勘定番号</span></span> 
- <span data-ttu-id="72dfe-2384">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2384">普通預金口座番号</span></span> 
- <span data-ttu-id="72dfe-2385">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2385">引き落とし口座番号</span></span> 
- <span data-ttu-id="72dfe-2386">口座番号</span><span class="sxs-lookup"><span data-stu-id="72dfe-2386">口座番号</span></span> 
- <span data-ttu-id="72dfe-2387">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2387">口座番号＃</span></span> 
- <span data-ttu-id="72dfe-2388">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2388">デビットのacct番号</span></span> 
- <span data-ttu-id="72dfe-2389">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2389">デビット勘定＃</span></span> 
- <span data-ttu-id="72dfe-2390">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2390">デビットACCTの番号</span></span> 
- <span data-ttu-id="72dfe-2391">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2391">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="72dfe-2392">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="72dfe-2392">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="72dfe-2393">Otemachi</span><span class="sxs-lookup"><span data-stu-id="72dfe-2393">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="72dfe-2394">Número de licencia de conductor de Japón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2394">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2395">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2395">Format</span></span>

<span data-ttu-id="72dfe-2396">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2396">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2397">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2397">Pattern</span></span>

<span data-ttu-id="72dfe-2398">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2398">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2399">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2399">Checksum</span></span>

<span data-ttu-id="72dfe-2400">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2400">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2401">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2401">Definition</span></span>

<span data-ttu-id="72dfe-2402">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2402">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2403">La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2403">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2404">Se encuentra una palabra clave de Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2404">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2405">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2405">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="72dfe-2406">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2406">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="72dfe-2407">dl#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2407">dl#</span></span> 
- <span data-ttu-id="72dfe-2408">LISTAS</span><span class="sxs-lookup"><span data-stu-id="72dfe-2408">DL＃</span></span> 
- <span data-ttu-id="72dfe-2409">dls#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2409">dls#</span></span> 
- <span data-ttu-id="72dfe-2410">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="72dfe-2410">DLS＃</span></span> 
- <span data-ttu-id="72dfe-2411">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-2411">driver license</span></span> 
- <span data-ttu-id="72dfe-2412">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-2412">driver licenses</span></span> 
- <span data-ttu-id="72dfe-2413">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-2413">drivers license</span></span> 
- <span data-ttu-id="72dfe-2414">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-2414">driver's license</span></span> 
- <span data-ttu-id="72dfe-2415">permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-2415">drivers licenses</span></span> 
- <span data-ttu-id="72dfe-2416">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-2416">driver's licenses</span></span> 
- <span data-ttu-id="72dfe-2417">driving licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2417">driving licence</span></span> 
- <span data-ttu-id="72dfe-2418">lic#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2418">lic#</span></span> 
- <span data-ttu-id="72dfe-2419">Lic</span><span class="sxs-lookup"><span data-stu-id="72dfe-2419">LIC＃</span></span> 
- <span data-ttu-id="72dfe-2420">lics#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2420">lics#</span></span> 
- <span data-ttu-id="72dfe-2421">identificador de estado</span><span class="sxs-lookup"><span data-stu-id="72dfe-2421">state id</span></span> 
- <span data-ttu-id="72dfe-2422">state identification
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2422">state identification</span></span> 
- <span data-ttu-id="72dfe-2423">state identification number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2423">state identification number</span></span> 
- <span data-ttu-id="72dfe-2424">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2424">低所得国＃</span></span> 
- <span data-ttu-id="72dfe-2425">免許証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2425">免許証</span></span> 
- <span data-ttu-id="72dfe-2426">状態ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-2426">状態ID</span></span>
- <span data-ttu-id="72dfe-2427">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2427">状態の識別</span></span> 
- <span data-ttu-id="72dfe-2428">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2428">状態の識別番号</span></span> 
- <span data-ttu-id="72dfe-2429">運転免許</span><span class="sxs-lookup"><span data-stu-id="72dfe-2429">運転免許</span></span> 
- <span data-ttu-id="72dfe-2430">運転免許証</span><span class="sxs-lookup"><span data-stu-id="72dfe-2430">運転免許証</span></span> 
- <span data-ttu-id="72dfe-2431">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="72dfe-2431">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="72dfe-2432">Número de pasaporte de Japón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2432">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2433">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2433">Format</span></span>

<span data-ttu-id="72dfe-2434">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2434">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2435">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2435">Pattern</span></span>

<span data-ttu-id="72dfe-2436">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2436">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2437">Checksum</span></span>

<span data-ttu-id="72dfe-2438">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2438">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2439">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2439">Definition</span></span>

<span data-ttu-id="72dfe-2440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2441">La función Func_jp_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2441">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2442">Se encuentra una palabra clave de Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2442">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2443">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="72dfe-2444">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-2444">Keyword_jp_passport</span></span>

- <span data-ttu-id="72dfe-2445">パスポート
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2445">パスポート</span></span> 
- <span data-ttu-id="72dfe-2446">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2446">パスポート番号</span></span> 
- <span data-ttu-id="72dfe-2447">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2447">パスポートのNum</span></span> 
- <span data-ttu-id="72dfe-2448">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2448">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="72dfe-2449">Número de registro de residente de Japón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2449">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2450">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2450">Format</span></span>

<span data-ttu-id="72dfe-2451">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2451">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2452">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2452">Pattern</span></span>

<span data-ttu-id="72dfe-2453">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2453">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2454">Checksum</span></span>

<span data-ttu-id="72dfe-2455">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2455">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2456">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2456">Definition</span></span>

<span data-ttu-id="72dfe-2457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2458">La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2458">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2459">Se encuentra una palabra clave de Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2459">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2460">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="72dfe-2461">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2461">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="72dfe-2462">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2462">Resident Registration Number</span></span>
- <span data-ttu-id="72dfe-2463">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2463">Resident Register Number</span></span> 
- <span data-ttu-id="72dfe-2464">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2464">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="72dfe-2465">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2465">Resident Registration No.</span></span> 
- <span data-ttu-id="72dfe-2466">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2466">Resident Register No.</span></span> 
- <span data-ttu-id="72dfe-2467">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2467">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="72dfe-2468">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2468">Basic Resident Register No.</span></span> 
- <span data-ttu-id="72dfe-2469">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2469">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="72dfe-2470">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2470">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="72dfe-2471">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2471">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="72dfe-2472">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2472">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="72dfe-2473">Número de Seguridad Social de Japón (SIN)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2473">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2474">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2474">Format</span></span>

<span data-ttu-id="72dfe-2475">De 7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2475">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2476">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2476">Pattern</span></span>

<span data-ttu-id="72dfe-2477">7-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2477">7-12 digits:</span></span>
- <span data-ttu-id="72dfe-2478">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2478">Four digits</span></span> 
- <span data-ttu-id="72dfe-2479">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2479">A hyphen (optional)</span></span> 
- <span data-ttu-id="72dfe-2480">Seis dígitos o</span><span class="sxs-lookup"><span data-stu-id="72dfe-2480">Six digits OR</span></span>
- <span data-ttu-id="72dfe-2481">De 7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2481">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2482">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2482">Checksum</span></span>

<span data-ttu-id="72dfe-2483">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2483">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2484">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2484">Definition</span></span>

<span data-ttu-id="72dfe-2485">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2485">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2486">La función Func_jp_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2486">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2487">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2487">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="72dfe-2488">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2488">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2489">La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2489">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2490">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2490">A keyword from Keyword_jp_sin is found.</span></span>

```
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2491">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2491">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="72dfe-2492">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="72dfe-2492">Keyword_jp_sin</span></span>

- <span data-ttu-id="72dfe-2493">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2493">Social Insurance No.</span></span> 
- <span data-ttu-id="72dfe-2494">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2494">Social Insurance Num</span></span> 
- <span data-ttu-id="72dfe-2495">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2495">Social Insurance Number</span></span> 
- <span data-ttu-id="72dfe-2496">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2496">社会保険のテンキー</span></span> 
- <span data-ttu-id="72dfe-2497">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2497">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="72dfe-2498">Número de tarjeta de residencia japonés</span><span class="sxs-lookup"><span data-stu-id="72dfe-2498">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2499">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2499">Format</span></span>

<span data-ttu-id="72dfe-2500">12 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2500">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2501">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2501">Pattern</span></span>

<span data-ttu-id="72dfe-2502">12 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2502">12 letters and digits:</span></span>
- <span data-ttu-id="72dfe-2503">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2503">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="72dfe-2504">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2504">Eight digits</span></span> 
- <span data-ttu-id="72dfe-2505">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2505">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2506">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2506">Checksum</span></span>

<span data-ttu-id="72dfe-2507">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2507">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2508">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2508">Definition</span></span>

<span data-ttu-id="72dfe-2509">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2509">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2510">La expresión regular Regex_jp_residence_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2510">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2511">Se encuentra una palabra clave de Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2511">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2512">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2512">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="72dfe-2513">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2513">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="72dfe-2514">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2514">Residence card number</span></span>
- <span data-ttu-id="72dfe-2515">Nº de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2515">Residence card no</span></span>
- <span data-ttu-id="72dfe-2516">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2516">Residence card #</span></span>
- <span data-ttu-id="72dfe-2517">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="72dfe-2517">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="72dfe-2518">Número de la tarjeta de identificación de Malasia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2518">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2519">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2519">Format</span></span>

<span data-ttu-id="72dfe-2520">12 dígitos que contienen guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="72dfe-2520">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2521">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2521">Pattern</span></span>

<span data-ttu-id="72dfe-2522">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2522">12 digits:</span></span>
- <span data-ttu-id="72dfe-2523">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-2523">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="72dfe-2524">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2524">A dash (optional)</span></span> 
- <span data-ttu-id="72dfe-2525">Código de dos letras del lugar de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-2525">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="72dfe-2526">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2526">A dash (optional)</span></span> 
- <span data-ttu-id="72dfe-2527">Tres dígitos aleatorios </span><span class="sxs-lookup"><span data-stu-id="72dfe-2527">Three random digits</span></span> 
- <span data-ttu-id="72dfe-2528">Código de género de un dígito</span><span class="sxs-lookup"><span data-stu-id="72dfe-2528">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2529">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2529">Checksum</span></span>

<span data-ttu-id="72dfe-2530">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2530">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2531">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2531">Definition</span></span>

<span data-ttu-id="72dfe-2532">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2532">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2533">La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2533">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2534">Se encuentra una palabra clave de Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2534">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2535">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2535">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="72dfe-2536">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2536">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="72dfe-2537">tarjeta de aplicación digital</span><span class="sxs-lookup"><span data-stu-id="72dfe-2537">digital application card</span></span>
- <span data-ttu-id="72dfe-2538">i/c</span><span class="sxs-lookup"><span data-stu-id="72dfe-2538">i/c</span></span>
- <span data-ttu-id="72dfe-2539">i/c no</span><span class="sxs-lookup"><span data-stu-id="72dfe-2539">i/c no</span></span>
- <span data-ttu-id="72dfe-2540">i</span><span class="sxs-lookup"><span data-stu-id="72dfe-2540">ic</span></span>
- <span data-ttu-id="72dfe-2541">no IC</span><span class="sxs-lookup"><span data-stu-id="72dfe-2541">ic no</span></span>
- <span data-ttu-id="72dfe-2542">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2542">id card</span></span>
- <span data-ttu-id="72dfe-2543">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2543">identification Card</span></span>
- <span data-ttu-id="72dfe-2544">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-2544">identity card</span></span>
- <span data-ttu-id="72dfe-2545">k/p</span><span class="sxs-lookup"><span data-stu-id="72dfe-2545">k/p</span></span>
- <span data-ttu-id="72dfe-2546">k/p no</span><span class="sxs-lookup"><span data-stu-id="72dfe-2546">k/p no</span></span>
- <span data-ttu-id="72dfe-2547">Kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="72dfe-2547">kad akuan diri</span></span>
- <span data-ttu-id="72dfe-2548">Kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="72dfe-2548">kad aplikasi digital</span></span>
- <span data-ttu-id="72dfe-2549">Kad pengenalan Malasia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2549">kad pengenalan malaysia</span></span>
- <span data-ttu-id="72dfe-2550">PK</span><span class="sxs-lookup"><span data-stu-id="72dfe-2550">kp</span></span>
- <span data-ttu-id="72dfe-2551">KP no</span><span class="sxs-lookup"><span data-stu-id="72dfe-2551">kp no</span></span>
- <span data-ttu-id="72dfe-2552">mykad</span><span class="sxs-lookup"><span data-stu-id="72dfe-2552">mykad</span></span>
- <span data-ttu-id="72dfe-2553">MYKAS</span><span class="sxs-lookup"><span data-stu-id="72dfe-2553">mykas</span></span>
- <span data-ttu-id="72dfe-2554">mykid</span><span class="sxs-lookup"><span data-stu-id="72dfe-2554">mykid</span></span>
- <span data-ttu-id="72dfe-2555">mypr</span><span class="sxs-lookup"><span data-stu-id="72dfe-2555">mypr</span></span>
- <span data-ttu-id="72dfe-2556">mytentera</span><span class="sxs-lookup"><span data-stu-id="72dfe-2556">mytentera</span></span>
- <span data-ttu-id="72dfe-2557">tarjeta de identidad de Malasia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2557">malaysia identity card</span></span>
- <span data-ttu-id="72dfe-2558">tarjeta de identidad malasio</span><span class="sxs-lookup"><span data-stu-id="72dfe-2558">malaysian identity card</span></span>
- <span data-ttu-id="72dfe-2559">NRIC</span><span class="sxs-lookup"><span data-stu-id="72dfe-2559">nric</span></span>
- <span data-ttu-id="72dfe-2560">tarjeta de identificación personal</span><span class="sxs-lookup"><span data-stu-id="72dfe-2560">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="72dfe-2561">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2561">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2562">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2562">Format</span></span>

<span data-ttu-id="72dfe-2563">8 o 9 dígitos que contienen espacios opcionales</span><span class="sxs-lookup"><span data-stu-id="72dfe-2563">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2564">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2564">Pattern</span></span>

<span data-ttu-id="72dfe-2565">8 o 9 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2565">8-9 digits:</span></span>
- <span data-ttu-id="72dfe-2566">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2566">Three digits</span></span> 
- <span data-ttu-id="72dfe-2567">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2567">A space (optional)</span></span> 
- <span data-ttu-id="72dfe-2568">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2568">Three digits</span></span> 
- <span data-ttu-id="72dfe-2569">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2569">A space (optional)</span></span> 
- <span data-ttu-id="72dfe-2570">2 o 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2570">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2571">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2571">Checksum</span></span>

<span data-ttu-id="72dfe-2572">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2573">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2573">Definition</span></span>

<span data-ttu-id="72dfe-2574">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2574">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2575">La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2575">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2576">Se encuentra una palabra clave de Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2576">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="72dfe-2577">La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2577">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="72dfe-2578">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2578">The checksum passes.</span></span>

```
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2579">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2579">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="72dfe-2580">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="72dfe-2580">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="72dfe-2581">Número de servicio de ciudadanía
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2581">Citizen service number</span></span> 
- <span data-ttu-id="72dfe-2582">BSN

</span><span class="sxs-lookup"><span data-stu-id="72dfe-2582">BSN</span></span> 
- <span data-ttu-id="72dfe-2583">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2583">Burgerservicenummer</span></span> 
- <span data-ttu-id="72dfe-2584">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2584">Sofinummer</span></span> 
- <span data-ttu-id="72dfe-2585">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2585">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="72dfe-2586">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2586">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="72dfe-2587">Número de Ministerio de salud de Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="72dfe-2587">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2588">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2588">Format</span></span>

<span data-ttu-id="72dfe-2589">Tres letras, un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2589">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2590">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2590">Pattern</span></span>

<span data-ttu-id="72dfe-2591">Tres letras (no distingue entre mayúsculas y minúsculas), un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2591">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2592">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2592">Checksum</span></span>

<span data-ttu-id="72dfe-2593">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2593">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2594">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2594">Definition</span></span>

<span data-ttu-id="72dfe-2595">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2596">La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2596">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2597">Se encuentra una palabra clave de Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2597">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="72dfe-2598">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2598">The checksum passes.</span></span>

```
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="72dfe-2599">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2599">Keywords</span></span>

<span data-ttu-id="72dfe-2600">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="72dfe-2600">Keyword_nz_terms</span></span>

- <span data-ttu-id="72dfe-2601">NHI
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2601">NHI</span></span> 
- <span data-ttu-id="72dfe-2602">Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="72dfe-2602">New Zealand</span></span> 
- <span data-ttu-id="72dfe-2603">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-2603">Health</span></span> 
- <span data-ttu-id="72dfe-2604">tratamiento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2604">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="72dfe-2605">Número de identificación de Noruega</span><span class="sxs-lookup"><span data-stu-id="72dfe-2605">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2606">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2606">Format</span></span>

<span data-ttu-id="72dfe-2607">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2607">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2608">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2608">Pattern</span></span>

<span data-ttu-id="72dfe-2609">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2609">11 digits:</span></span>
- <span data-ttu-id="72dfe-2610">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-2610">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="72dfe-2611">Número individual de tres dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2611">Three-digit individual number</span></span> 
- <span data-ttu-id="72dfe-2612">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="72dfe-2612">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2613">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2613">Checksum</span></span>

<span data-ttu-id="72dfe-2614">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2614">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2615">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2615">Definition</span></span>

<span data-ttu-id="72dfe-2616">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2616">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2617">La función Func_norway_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2617">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2618">Se encuentra una palabra clave de Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2618">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="72dfe-2619">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2619">The checksum passes.</span></span>
- <span data-ttu-id="72dfe-2620">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2621">La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2621">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2622">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2622">The checksum passes.</span></span>

```
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2623">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2623">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="72dfe-2624">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2624">Keyword_norway_id_number</span></span>

- <span data-ttu-id="72dfe-2625">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="72dfe-2625">Personal identification number</span></span>
- <span data-ttu-id="72dfe-2626">Número de id. noruego</span><span class="sxs-lookup"><span data-stu-id="72dfe-2626">Norwegian ID Number</span></span>
- <span data-ttu-id="72dfe-2627">Número de id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2627">ID Number</span></span>
- <span data-ttu-id="72dfe-2628">Identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2628">Identification</span></span>
- <span data-ttu-id="72dfe-2629">Personnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-2629">Personnummer</span></span>
- <span data-ttu-id="72dfe-2630">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="72dfe-2630">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="72dfe-2631">Número de id. universal unificado de Filipinas</span><span class="sxs-lookup"><span data-stu-id="72dfe-2631">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2632">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2632">Format</span></span>

<span data-ttu-id="72dfe-2633">12 dígitos separados por guiones</span><span class="sxs-lookup"><span data-stu-id="72dfe-2633">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2634">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2634">Pattern</span></span>

<span data-ttu-id="72dfe-2635">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2635">12 digits:</span></span>
- <span data-ttu-id="72dfe-2636">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2636">Four digits</span></span> 
- <span data-ttu-id="72dfe-2637">Un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-2637">A hyphen</span></span> 
- <span data-ttu-id="72dfe-2638">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2638">Seven digits</span></span> 
- <span data-ttu-id="72dfe-2639">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-2639">A hyphen</span></span> 
- <span data-ttu-id="72dfe-2640">Un dígito</span><span class="sxs-lookup"><span data-stu-id="72dfe-2640">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2641">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2641">Checksum</span></span>

<span data-ttu-id="72dfe-2642">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2642">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2643">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2643">Definition</span></span>

<span data-ttu-id="72dfe-2644">Una directiva DLP está 75 % segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2644">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2645">La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2645">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2646">Se encuentra una palabra clave de Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2646">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2647">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2647">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="72dfe-2648">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="72dfe-2648">Keyword_philippines_id</span></span>

- <span data-ttu-id="72dfe-2649">Id. universal unificado
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2649">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="72dfe-2650">UMID
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2650">UMID</span></span> 
- <span data-ttu-id="72dfe-2651">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-2651">Identity Card</span></span> 
- <span data-ttu-id="72dfe-2652">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-2652">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="72dfe-2653">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2653">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2654">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2654">Format</span></span>

<span data-ttu-id="72dfe-2655">Tres letras y seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2655">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2656">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2656">Pattern</span></span>

<span data-ttu-id="72dfe-2657">Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2657">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2658">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2658">Checksum</span></span>

<span data-ttu-id="72dfe-2659">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2659">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2660">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2660">Definition</span></span>

<span data-ttu-id="72dfe-p138">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_polish_national_id encuentra contenido que coincide con el patrón. Se encuentra una palabra clave de Keyword_polish_national_id_passport_number. La suma de comprobación se supera.</span><span class="sxs-lookup"><span data-stu-id="72dfe-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2664">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2664">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="72dfe-2665">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2665">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="72dfe-2666">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="72dfe-2666">Dowód osobisty</span></span>
- <span data-ttu-id="72dfe-2667">Numerar dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="72dfe-2667">Numer dowodu osobistego</span></span>
- <span data-ttu-id="72dfe-2668">Nazwa i número dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="72dfe-2668">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="72dfe-2669">Nazwa i NR dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="72dfe-2669">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="72dfe-2670">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2670">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="72dfe-2671">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2671">Dowód Tożsamości</span></span>
- <span data-ttu-id="72dfe-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-p139">dow. os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="72dfe-2674">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2674">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2675">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2675">Format</span></span>

<span data-ttu-id="72dfe-2676">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2676">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2677">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2677">Pattern</span></span>

<span data-ttu-id="72dfe-2678">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2678">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2679">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2679">Checksum</span></span>

<span data-ttu-id="72dfe-2680">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2680">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2681">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2681">Definition</span></span>

<span data-ttu-id="72dfe-2682">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2682">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2683">La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2683">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2684">Se encuentra una palabra clave de Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2684">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="72dfe-2685">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2685">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2686">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2686">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="72dfe-2687">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2687">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="72dfe-2688">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="72dfe-2688">Nr PESEL</span></span>
- <span data-ttu-id="72dfe-2689">PESEL</span><span class="sxs-lookup"><span data-stu-id="72dfe-2689">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="72dfe-2690">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2690">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2691">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2691">Format</span></span>

<span data-ttu-id="72dfe-2692">Dos letras y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2692">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2693">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2693">Pattern</span></span>

<span data-ttu-id="72dfe-2694">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2694">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2695">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2695">Checksum</span></span>

<span data-ttu-id="72dfe-2696">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2696">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2697">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2697">Definition</span></span>

<span data-ttu-id="72dfe-2698">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2698">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2699">La función Func_polish_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2699">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2700">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2700">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="72dfe-2701">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2701">The checksum passes.</span></span>

```
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2702">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2702">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="72dfe-2703">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2703">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="72dfe-2704">Números paszportu</span><span class="sxs-lookup"><span data-stu-id="72dfe-2704">Numer paszportu</span></span>
- <span data-ttu-id="72dfe-p140">Nr. Paszportu</span><span class="sxs-lookup"><span data-stu-id="72dfe-p140">Nr. Paszportu</span></span>
- <span data-ttu-id="72dfe-2707">Paszport</span><span class="sxs-lookup"><span data-stu-id="72dfe-2707">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="72dfe-2708">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="72dfe-2708">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2709">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2709">Format</span></span>

<span data-ttu-id="72dfe-2710">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2710">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2711">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2711">Pattern</span></span>

<span data-ttu-id="72dfe-2712">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2712">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2713">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2713">Checksum</span></span>

<span data-ttu-id="72dfe-2714">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2714">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2715">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2715">Definition</span></span>

<span data-ttu-id="72dfe-2716">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2716">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2717">La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2717">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2718">Se encuentra una palabra clave de Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2718">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2719">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2719">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="72dfe-2720">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="72dfe-2720">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="72dfe-2721">Tarjeta del ciudadano</span><span class="sxs-lookup"><span data-stu-id="72dfe-2721">Citizen Card</span></span>
- <span data-ttu-id="72dfe-2722">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="72dfe-2722">National ID Card</span></span>
- <span data-ttu-id="72dfe-2723">CC</span><span class="sxs-lookup"><span data-stu-id="72dfe-2723">CC</span></span>
- <span data-ttu-id="72dfe-2724">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="72dfe-2724">Cartão de Cidadão</span></span>
- <span data-ttu-id="72dfe-2725">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="72dfe-2725">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="72dfe-2726">Identificación nacional de Arabia Saudí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2726">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2727">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2727">Format</span></span>

<span data-ttu-id="72dfe-2728">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2728">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2729">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2729">Pattern</span></span>

<span data-ttu-id="72dfe-2730">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2730">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2731">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2731">Checksum</span></span>

<span data-ttu-id="72dfe-2732">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2732">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2733">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2733">Definition</span></span>

<span data-ttu-id="72dfe-2734">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2734">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2735">La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2735">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2736">Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2736">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2737">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2737">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="72dfe-2738">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="72dfe-2738">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="72dfe-2739">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2739">Identification Card</span></span> 
- <span data-ttu-id="72dfe-2740">I card number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2740">I card number</span></span> 
- <span data-ttu-id="72dfe-2741">número de Id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2741">ID number</span></span> 
- <span data-ttu-id="72dfe-2742">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2742">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="72dfe-2743">Número de tarjeta de identidad de registro nacional (NRIC) de Singapur</span><span class="sxs-lookup"><span data-stu-id="72dfe-2743">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2744">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2744">Format</span></span>

<span data-ttu-id="72dfe-2745">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2745">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2746">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2746">Pattern</span></span>

- <span data-ttu-id="72dfe-2747">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2747">Nine letters and digits:</span></span>
- <span data-ttu-id="72dfe-2748">La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-2748">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-2749">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2749">Seven digits</span></span> 
- <span data-ttu-id="72dfe-2750">Un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="72dfe-2750">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2751">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2751">Checksum</span></span>

<span data-ttu-id="72dfe-2752">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2752">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2753">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2753">Definition</span></span>

<span data-ttu-id="72dfe-2754">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2754">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2755">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2755">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2756">Se encuentra una palabra clave de Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2756">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="72dfe-2757">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2757">The checksum passes.</span></span>

<span data-ttu-id="72dfe-2758">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2758">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2759">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2759">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2760">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2760">The checksum passes.</span></span>

```
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2761">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2761">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="72dfe-2762">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="72dfe-2762">Keyword_singapore_nric</span></span>

- <span data-ttu-id="72dfe-2763">Tarjeta de identidad de registro nacional
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2763">National Registration Identity Card</span></span> 
- <span data-ttu-id="72dfe-2764">Número de tarjeta de identidad
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2764">Identity Card Number</span></span> 
- <span data-ttu-id="72dfe-2765">NRIC
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2765">NRIC</span></span> 
- <span data-ttu-id="72dfe-2766">IC
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2766">IC</span></span> 
- <span data-ttu-id="72dfe-2767">Número de identificación de extranjeros
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2767">Foreign Identification Number</span></span> 
- <span data-ttu-id="72dfe-2768">FIN
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2768">FIN</span></span> 
- <span data-ttu-id="72dfe-2769">身份证 </span><span class="sxs-lookup"><span data-stu-id="72dfe-2769">身份证</span></span> 
- <span data-ttu-id="72dfe-2770">身份證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2770">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="72dfe-2771">Número de identificación de Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="72dfe-2771">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2772">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2772">Format</span></span>

<span data-ttu-id="72dfe-2773">13 dígitos que pueden contener espacios</span><span class="sxs-lookup"><span data-stu-id="72dfe-2773">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2774">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2774">Pattern</span></span>

<span data-ttu-id="72dfe-2775">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2775">13 digits:</span></span>
- <span data-ttu-id="72dfe-2776">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-2776">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="72dfe-2777">Cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2777">Four digits</span></span> 
- <span data-ttu-id="72dfe-2778">Un indicador de ciudadanía de un solo dígito </span><span class="sxs-lookup"><span data-stu-id="72dfe-2778">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="72dfe-2779">El dígito "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="72dfe-2779">The digit "8" or "9"</span></span> 
- <span data-ttu-id="72dfe-2780">Un dígito que es un dígito de suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2780">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2781">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2781">Checksum</span></span>

<span data-ttu-id="72dfe-2782">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2782">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2783">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2783">Definition</span></span>

<span data-ttu-id="72dfe-2784">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2785">La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2785">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2786">Se encuentra una palabra clave de Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2786">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="72dfe-2787">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2787">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2788">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2788">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="72dfe-2789">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2789">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="72dfe-2790">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="72dfe-2790">Identity card</span></span>
- <span data-ttu-id="72dfe-2791">ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-2791">ID</span></span>
- <span data-ttu-id="72dfe-2792">Identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2792">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="72dfe-2793">Número de registro de residente de Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="72dfe-2793">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2794">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2794">Format</span></span>

<span data-ttu-id="72dfe-2795">13 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="72dfe-2795">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2796">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2796">Pattern</span></span>

<span data-ttu-id="72dfe-2797">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2797">13 digits:</span></span>
- <span data-ttu-id="72dfe-2798">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="72dfe-2798">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="72dfe-2799">Un guión </span><span class="sxs-lookup"><span data-stu-id="72dfe-2799">A hyphen</span></span> 
- <span data-ttu-id="72dfe-2800">Un dígito determinado por el siglo y el sexo </span><span class="sxs-lookup"><span data-stu-id="72dfe-2800">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="72dfe-2801">Código de región de nacimiento de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2801">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="72dfe-2802">Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos </span><span class="sxs-lookup"><span data-stu-id="72dfe-2802">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="72dfe-2803">Un dígito de control.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2803">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2804">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2804">Checksum</span></span>

<span data-ttu-id="72dfe-2805">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2805">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2806">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2806">Definition</span></span>

<span data-ttu-id="72dfe-2807">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2807">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2808">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2808">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2809">Se encuentra una palabra clave de Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2809">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="72dfe-2810">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2810">The checksum passes.</span></span>

<span data-ttu-id="72dfe-2811">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2811">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2812">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2812">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2813">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2813">The checksum passes.</span></span>

```
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2814">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2814">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="72dfe-2815">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2815">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="72dfe-2816">Tarjeta de id. nacional
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2816">National ID card</span></span> 
- <span data-ttu-id="72dfe-2817">Número de registro de ciudadano
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2817">Citizen's Registration Number</span></span> 
- <span data-ttu-id="72dfe-2818">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2818">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="72dfe-2819">RRN
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2819">RRN</span></span> 
- <span data-ttu-id="72dfe-2820">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="72dfe-2820">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="72dfe-2821">Número de seguridad social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2821">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2822">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2822">Format</span></span>

<span data-ttu-id="72dfe-2823">11 o 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2823">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2824">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2824">Pattern</span></span>

<span data-ttu-id="72dfe-2825">11-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2825">11-12 digits:</span></span>
- <span data-ttu-id="72dfe-2826">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2826">Two digits</span></span> 
- <span data-ttu-id="72dfe-2827">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2827">A forward slash (optional)</span></span> 
- <span data-ttu-id="72dfe-2828">7-8 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2828">7-8 digits</span></span> 
- <span data-ttu-id="72dfe-2829">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2829">A forward slash (optional)</span></span> 
- <span data-ttu-id="72dfe-2830">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2830">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2831">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2831">Checksum</span></span>

<span data-ttu-id="72dfe-2832">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2832">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2833">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2833">Definition</span></span>

<span data-ttu-id="72dfe-2834">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2834">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2835">La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2835">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2836">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2836">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2837">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2837">Keywords</span></span>

<span data-ttu-id="72dfe-2838">Ninguno</span><span class="sxs-lookup"><span data-stu-id="72dfe-2838">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="72dfe-2839">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2839">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2840">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2840">Format</span></span>

<span data-ttu-id="72dfe-2841">10 o 12 dígitos y un delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="72dfe-2841">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2842">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2842">Pattern</span></span>

<span data-ttu-id="72dfe-2843">10 o 12 dígitos y un delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2843">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="72dfe-2844">2-4 dígitos (opcionales)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2844">2-4 digits (optional)</span></span> 
- <span data-ttu-id="72dfe-2845">Seis dígitos en fecha de formato AAMMDD</span><span class="sxs-lookup"><span data-stu-id="72dfe-2845">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="72dfe-2846">Delimitador de "-" o "+" (opcional), más</span><span class="sxs-lookup"><span data-stu-id="72dfe-2846">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="72dfe-2847">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2847">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2848">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2848">Checksum</span></span>

<span data-ttu-id="72dfe-2849">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2849">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2850">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2850">Definition</span></span>

<span data-ttu-id="72dfe-2851">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2851">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2852">La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2852">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2853">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2853">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2854">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2854">Keywords</span></span>

<span data-ttu-id="72dfe-2855">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2855">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="72dfe-2856">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="72dfe-2856">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2857">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2857">Format</span></span>

<span data-ttu-id="72dfe-2858">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2858">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2859">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2859">Pattern</span></span>

<span data-ttu-id="72dfe-2860">Ocho dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2860">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2861">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2861">Checksum</span></span>

<span data-ttu-id="72dfe-2862">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2862">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2863">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2863">Definition</span></span>

<span data-ttu-id="72dfe-2864">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2864">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2865">La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2865">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2866">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2866">One of the following is true:</span></span>
    - <span data-ttu-id="72dfe-2867">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2867">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="72dfe-2868">Se encuentra una palabra clave de Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2868">A keyword from Keyword_sweden_passport is found.</span></span>

```
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2869">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2869">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="72dfe-2870">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-2870">Keyword_sweden_passport</span></span>

- <span data-ttu-id="72dfe-2871">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2871">visa requirements</span></span> 
- <span data-ttu-id="72dfe-2872">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2872">Alien Registration Card</span></span> 
- <span data-ttu-id="72dfe-2873">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2873">Schengen visas</span></span> 
- <span data-ttu-id="72dfe-2874">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2874">Schengen visa</span></span> 
- <span data-ttu-id="72dfe-2875">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2875">Visa Processing</span></span> 
- <span data-ttu-id="72dfe-2876">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2876">Visa Type</span></span> 
- <span data-ttu-id="72dfe-2877">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2877">Single Entry</span></span> 
- <span data-ttu-id="72dfe-2878">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2878">Multiple Entry</span></span> 
- <span data-ttu-id="72dfe-2879">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="72dfe-2879">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="72dfe-2880">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-2880">Keyword_passport</span></span>

- <span data-ttu-id="72dfe-2881">Passport Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-2881">Passport Number</span></span> 
- <span data-ttu-id="72dfe-2882">
Passport No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2882">Passport No</span></span> 
- <span data-ttu-id="72dfe-2883">Passport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2883">Passport #</span></span> 
- <span data-ttu-id="72dfe-2884">Passport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2884">Passport#</span></span> 
- <span data-ttu-id="72dfe-2885">PassportID</span><span class="sxs-lookup"><span data-stu-id="72dfe-2885">PassportID</span></span> 
- <span data-ttu-id="72dfe-2886">Passportno
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2886">Passportno</span></span> 
- <span data-ttu-id="72dfe-2887">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2887">passportnumber</span></span> 
- <span data-ttu-id="72dfe-2888">パスポート</span><span class="sxs-lookup"><span data-stu-id="72dfe-2888">パスポート</span></span> 
- <span data-ttu-id="72dfe-2889">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2889">パスポート番号</span></span> 
- <span data-ttu-id="72dfe-2890">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2890">パスポートのNum</span></span> 
- <span data-ttu-id="72dfe-2891">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2891">パスポート＃</span></span> 
- <span data-ttu-id="72dfe-2892">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="72dfe-2892">Numéro de passeport</span></span> 
- <span data-ttu-id="72dfe-2893">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="72dfe-2893">Passeport n °</span></span> 
- <span data-ttu-id="72dfe-2894">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2894">Passeport Non</span></span> 
- <span data-ttu-id="72dfe-2895">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2895">Passeport #</span></span> 
- <span data-ttu-id="72dfe-2896">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2896">Passeport#</span></span> 
- <span data-ttu-id="72dfe-2897">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="72dfe-2897">PasseportNon</span></span> 
- <span data-ttu-id="72dfe-2898">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2898">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="72dfe-2899">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="72dfe-2899">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2900">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2900">Format</span></span>

<span data-ttu-id="72dfe-2901">Cuatro letras seguidas de 5 a 31 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2901">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2902">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2902">Pattern</span></span>

<span data-ttu-id="72dfe-2903">Cuatro letras seguidas de 5-31 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2903">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="72dfe-2904">Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2904">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-2905">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="72dfe-2905">An optional space</span></span> 
- <span data-ttu-id="72dfe-2906">4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))</span><span class="sxs-lookup"><span data-stu-id="72dfe-2906">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="72dfe-2907">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="72dfe-2907">An optional space</span></span> 
- <span data-ttu-id="72dfe-2908">1-3 letras o dígitos (el resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2908">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2909">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2909">Checksum</span></span>

<span data-ttu-id="72dfe-2910">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2910">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2911">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2911">Definition</span></span>

<span data-ttu-id="72dfe-2912">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2913">La expresión regular Regex_swift encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2913">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2914">Se encuentra una palabra clave de Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2914">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2915">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2915">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="72dfe-2916">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="72dfe-2916">Keyword_swift</span></span>

- <span data-ttu-id="72dfe-2917">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2917">international organization for standardization 9362</span></span> 
- <span data-ttu-id="72dfe-2918">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2918">iso 9362</span></span> 
- <span data-ttu-id="72dfe-2919">iso9362</span><span class="sxs-lookup"><span data-stu-id="72dfe-2919">iso9362</span></span> 
- <span data-ttu-id="72dfe-2920">rápido\#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2920">swift\#</span></span> 
- <span data-ttu-id="72dfe-2921">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2921">swiftcode</span></span> 
- <span data-ttu-id="72dfe-2922">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2922">swiftnumber</span></span> 
- <span data-ttu-id="72dfe-2923">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2923">swiftroutingnumber</span></span> 
- <span data-ttu-id="72dfe-2924">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="72dfe-2924">swift code</span></span> 
- <span data-ttu-id="72dfe-2925">swift number #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2925">swift number #</span></span> 
- <span data-ttu-id="72dfe-2926">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2926">swift routing number</span></span> 
- <span data-ttu-id="72dfe-2927">bic number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2927">bic number</span></span> 
- <span data-ttu-id="72dfe-2928">bic code
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2928">bic code</span></span> 
- <span data-ttu-id="72dfe-2929">BIC\#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2929">bic \#</span></span> 
- <span data-ttu-id="72dfe-2930">BIC\#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2930">bic\#</span></span> 
- <span data-ttu-id="72dfe-2931">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2931">bank identifier code</span></span> 
- <span data-ttu-id="72dfe-2932">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="72dfe-2932">標準化9362</span></span> 
- <span data-ttu-id="72dfe-2933">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2933">迅速＃</span></span> 
- <span data-ttu-id="72dfe-2934">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2934">SWIFTコード</span></span> 
- <span data-ttu-id="72dfe-2935">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2935">SWIFT番号</span></span> 
- <span data-ttu-id="72dfe-2936">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2936">迅速なルーティング番号</span></span> 
- <span data-ttu-id="72dfe-2937">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2937">BIC番号</span></span> 
- <span data-ttu-id="72dfe-2938">BICコード
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2938">BICコード</span></span> 
- <span data-ttu-id="72dfe-2939">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2939">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="72dfe-2940">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2940">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="72dfe-2941">rápido\#</span><span class="sxs-lookup"><span data-stu-id="72dfe-2941">rapide \#</span></span> 
- <span data-ttu-id="72dfe-2942">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2942">code SWIFT</span></span> 
- <span data-ttu-id="72dfe-2943">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2943">le numéro de swift</span></span> 
- <span data-ttu-id="72dfe-2944">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2944">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="72dfe-2945">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2945">le numéro BIC</span></span> 
- <span data-ttu-id="72dfe-2946">\#BIC</span><span class="sxs-lookup"><span data-stu-id="72dfe-2946">\# BIC</span></span> 
- <span data-ttu-id="72dfe-2947">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2947">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="72dfe-2948">Identificación nacional de Taiwán</span><span class="sxs-lookup"><span data-stu-id="72dfe-2948">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2949">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2949">Format</span></span>

<span data-ttu-id="72dfe-2950">Una letra  seguida de nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2950">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2951">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2951">Pattern</span></span>

<span data-ttu-id="72dfe-2952">Una letra seguida de nueve dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2952">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="72dfe-2953">Una letra (en inglés, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-2953">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-2954">El dígito "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="72dfe-2954">The digit "1" or "2"</span></span> 
- <span data-ttu-id="72dfe-2955">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2955">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2956">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-2956">Checksum</span></span>

<span data-ttu-id="72dfe-2957">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-2957">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2958">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2958">Definition</span></span>

<span data-ttu-id="72dfe-2959">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2959">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2960">La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2960">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2961">Se encuentra una palabra clave de Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2961">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="72dfe-2962">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2962">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2963">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2963">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="72dfe-2964">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="72dfe-2964">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="72dfe-2965">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2965">身份證字號</span></span> 
- <span data-ttu-id="72dfe-2966">身份證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2966">身份證</span></span> 
- <span data-ttu-id="72dfe-2967">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2967">身份證號碼</span></span> 
- <span data-ttu-id="72dfe-2968">身份證號
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2968">身份證號</span></span> 
- <span data-ttu-id="72dfe-2969">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2969">身分證字號</span></span> 
- <span data-ttu-id="72dfe-2970">身分證 </span><span class="sxs-lookup"><span data-stu-id="72dfe-2970">身分證</span></span> 
- <span data-ttu-id="72dfe-2971">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2971">身分證號碼</span></span> 
- <span data-ttu-id="72dfe-2972">身份證號
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2972">身份證號</span></span> 
- <span data-ttu-id="72dfe-2973">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2973">身分證統一編號</span></span> 
- <span data-ttu-id="72dfe-2974">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2974">國民身分證統一編號</span></span> 
- <span data-ttu-id="72dfe-2975">簽名
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2975">簽名</span></span> 
- <span data-ttu-id="72dfe-2976">蓋章
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2976">蓋章</span></span> 
- <span data-ttu-id="72dfe-2977">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="72dfe-2977">簽名或蓋章</span></span> 
- <span data-ttu-id="72dfe-2978">簽章</span><span class="sxs-lookup"><span data-stu-id="72dfe-2978">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="72dfe-2979">Número de pasaporte de Taiwán</span><span class="sxs-lookup"><span data-stu-id="72dfe-2979">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-2980">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-2980">Format</span></span>

- <span data-ttu-id="72dfe-2981">Número de pasaporte biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2981">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="72dfe-2982">Número de pasaporte no biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2982">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-2983">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-2983">Pattern</span></span>
<span data-ttu-id="72dfe-2984">Número de pasaporte biométrico:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2984">Biometric passport number:</span></span>
- <span data-ttu-id="72dfe-2985">El dígito "3" </span><span class="sxs-lookup"><span data-stu-id="72dfe-2985">The digit "3"</span></span> 
- <span data-ttu-id="72dfe-2986">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2986">Eight digits</span></span>

<span data-ttu-id="72dfe-2987">Número de pasaporte no biométrico:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2987">Non-biometric passport number:</span></span>
- <span data-ttu-id="72dfe-2988">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-2988">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-2989">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-2989">Checksum</span></span>

<span data-ttu-id="72dfe-2990">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-2990">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-2991">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-2991">Definition</span></span>

<span data-ttu-id="72dfe-2992">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-2992">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-2993">La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2993">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-2994">Se encuentra una palabra clave de Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="72dfe-2994">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-2995">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-2995">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="72dfe-2996">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-2996">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="72dfe-2997">Número de pasaporte ROC
</span><span class="sxs-lookup"><span data-stu-id="72dfe-2997">ROC passport number</span></span> 
- <span data-ttu-id="72dfe-2998">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="72dfe-2998">Passport number</span></span> 
- <span data-ttu-id="72dfe-2999">N.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="72dfe-2999">Passport no</span></span> 
- <span data-ttu-id="72dfe-3000">N.ro pasaporte
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3000">Passport Num</span></span> 
- <span data-ttu-id="72dfe-3001">Passport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3001">Passport #</span></span> 
- <span data-ttu-id="72dfe-3002">护照
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3002">护照</span></span> 
- <span data-ttu-id="72dfe-3003">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3003">中華民國護照</span></span> 
- <span data-ttu-id="72dfe-3004">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="72dfe-3004">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="72dfe-3005">Número de certificado de residente (ARC/TARC) de Taiwán</span><span class="sxs-lookup"><span data-stu-id="72dfe-3005">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3006">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3006">Format</span></span>

<span data-ttu-id="72dfe-3007">10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3007">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3008">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3008">Pattern</span></span>

<span data-ttu-id="72dfe-3009">10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3009">10 letters and digits:</span></span>
- <span data-ttu-id="72dfe-3010">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="72dfe-3010">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="72dfe-3011">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3011">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3012">Checksum</span><span class="sxs-lookup"><span data-stu-id="72dfe-3012">Checksum</span></span>

<span data-ttu-id="72dfe-3013">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3013">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3014">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3014">Definition</span></span>

<span data-ttu-id="72dfe-3015">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3015">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3016">La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3016">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3017">Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3017">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3018">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3018">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="72dfe-3019">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="72dfe-3019">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="72dfe-3020">Certificado de residente
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3020">Resident Certificate</span></span> 
- <span data-ttu-id="72dfe-3021">Certificado residente</span><span class="sxs-lookup"><span data-stu-id="72dfe-3021">Resident Cert</span></span> 
- <span data-ttu-id="72dfe-3022">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3022">Resident Cert.</span></span> 
- <span data-ttu-id="72dfe-3023">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3023">Identification card</span></span> 
- <span data-ttu-id="72dfe-3024">Certificado de residente extranjero
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3024">Alien Resident Certificate</span></span> 
- <span data-ttu-id="72dfe-3025">ARCOS</span><span class="sxs-lookup"><span data-stu-id="72dfe-3025">ARC</span></span> 
- <span data-ttu-id="72dfe-3026">Certificado de residente en el área de Taiwán
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3026">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="72dfe-3027">TARC
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3027">TARC</span></span> 
- <span data-ttu-id="72dfe-3028">居留證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3028">居留證</span></span> 
- <span data-ttu-id="72dfe-3029">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3029">外僑居留證</span></span> 
- <span data-ttu-id="72dfe-3030">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3030">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="72dfe-3031">Código de identificación de población tailandesa</span><span class="sxs-lookup"><span data-stu-id="72dfe-3031">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3032">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3032">Format</span></span>

<span data-ttu-id="72dfe-3033">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3033">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3034">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3034">Pattern</span></span>

<span data-ttu-id="72dfe-3035">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3035">13 digits:</span></span>
- <span data-ttu-id="72dfe-3036">El primer dígito no es 0 ni 9</span><span class="sxs-lookup"><span data-stu-id="72dfe-3036">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="72dfe-3037">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3037">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3038">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3038">Checksum</span></span>

<span data-ttu-id="72dfe-3039">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3040">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3040">Definition</span></span>

<span data-ttu-id="72dfe-3041">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3042">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3042">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3043">Se encuentra una palabra clave de Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3043">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="72dfe-3044">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3044">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3045">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3045">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3046">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3046">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="72dfe-3047">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="72dfe-3047">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="72dfe-3048">Número de id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3048">ID Number</span></span>
- <span data-ttu-id="72dfe-3049">Número de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3049">Identification Number</span></span>
- <span data-ttu-id="72dfe-3050">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="72dfe-3050">บัตรประชาชน</span></span>
- <span data-ttu-id="72dfe-3051">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="72dfe-3051">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="72dfe-3052">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="72dfe-3052">บัตรประชาชน</span></span>
- <span data-ttu-id="72dfe-3053">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="72dfe-3053">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="72dfe-3054">Número de identificación nacional de Turco</span><span class="sxs-lookup"><span data-stu-id="72dfe-3054">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3055">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3055">Format</span></span>

<span data-ttu-id="72dfe-3056">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3056">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3057">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3057">Pattern</span></span>

<span data-ttu-id="72dfe-3058">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3058">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3059">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3059">Checksum</span></span>

<span data-ttu-id="72dfe-3060">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3061">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3061">Definition</span></span>

<span data-ttu-id="72dfe-3062">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3063">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3063">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3064">Se encuentra una palabra clave de Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3064">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="72dfe-3065">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3065">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3066">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3066">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3067">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3067">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="72dfe-3068">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="72dfe-3068">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="72dfe-3069">TC Kimlik no</span><span class="sxs-lookup"><span data-stu-id="72dfe-3069">TC Kimlik No</span></span>
- <span data-ttu-id="72dfe-3070">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="72dfe-3070">TC Kimlik numarası</span></span>
- <span data-ttu-id="72dfe-3071">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="72dfe-3071">Vatandaşlık numarası</span></span>
- <span data-ttu-id="72dfe-3072">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="72dfe-3072">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="72dfe-p141">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="72dfe-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3075">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3075">Format</span></span>

<span data-ttu-id="72dfe-3076">Combinación de 18 letras y dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="72dfe-3076">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3077">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3077">Pattern</span></span>

<span data-ttu-id="72dfe-3078">18 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3078">18 letters and digits:</span></span>
- <span data-ttu-id="72dfe-3079">Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="72dfe-3079">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="72dfe-3080">Un dígito</span><span class="sxs-lookup"><span data-stu-id="72dfe-3080">One digit</span></span> 
- <span data-ttu-id="72dfe-3081">Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-3081">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="72dfe-3082">Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="72dfe-3082">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="72dfe-3083">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3083">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3084">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3084">Checksum</span></span>

<span data-ttu-id="72dfe-3085">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-3085">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3086">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3086">Definition</span></span>

<span data-ttu-id="72dfe-3087">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3087">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3088">La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3088">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3089">Se encuentra una palabra clave de Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3089">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="72dfe-3090">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3090">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3091">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3091">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="72dfe-3092">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="72dfe-3092">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="72dfe-3093">DVLA
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3093">DVLA</span></span> 
- <span data-ttu-id="72dfe-3094">light vans
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3094">light vans</span></span> 
- <span data-ttu-id="72dfe-3095">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3095">quadbikes</span></span> 
- <span data-ttu-id="72dfe-3096">motor cars
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3096">motor cars</span></span> 
- <span data-ttu-id="72dfe-3097">125cc</span><span class="sxs-lookup"><span data-stu-id="72dfe-3097">125cc</span></span> 
- <span data-ttu-id="72dfe-3098">sidecar
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3098">sidecar</span></span> 
- <span data-ttu-id="72dfe-3099">tricycles
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3099">tricycles</span></span> 
- <span data-ttu-id="72dfe-3100">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3100">motorcycles</span></span> 
- <span data-ttu-id="72dfe-3101">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3101">photocard licence</span></span> 
- <span data-ttu-id="72dfe-3102">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3102">learner drivers</span></span> 
- <span data-ttu-id="72dfe-3103">licence holder
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3103">licence holder</span></span> 
- <span data-ttu-id="72dfe-3104">licence holders
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3104">licence holders</span></span> 
- <span data-ttu-id="72dfe-3105">driving licences
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3105">driving licences</span></span> 
- <span data-ttu-id="72dfe-3106">driving licence
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3106">driving licence</span></span> 
- <span data-ttu-id="72dfe-3107">dual control car
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3107">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="72dfe-p142">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="72dfe-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3110">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3110">Format</span></span>

<span data-ttu-id="72dfe-3111">Dos letras seguidas por entre 1 y 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3111">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3112">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3112">Pattern</span></span>

<span data-ttu-id="72dfe-3113">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números</span><span class="sxs-lookup"><span data-stu-id="72dfe-3113">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3114">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3114">Checksum</span></span>

<span data-ttu-id="72dfe-3115">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3115">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3116">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3116">Definition</span></span>

<span data-ttu-id="72dfe-3117">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3118">La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3118">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3119">Se encuentra una palabra clave de Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3119">A keyword from Keyword_uk_electoral is found.</span></span>

```
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3120">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3120">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="72dfe-3121">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="72dfe-3121">Keyword_uk_electoral</span></span>

- <span data-ttu-id="72dfe-3122">council nomination
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3122">council nomination</span></span> 
- <span data-ttu-id="72dfe-3123">nomination form
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3123">nomination form</span></span> 
- <span data-ttu-id="72dfe-3124">electoral register

</span><span class="sxs-lookup"><span data-stu-id="72dfe-3124">electoral register</span></span> 
- <span data-ttu-id="72dfe-3125">electoral roll</span><span class="sxs-lookup"><span data-stu-id="72dfe-3125">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="72dfe-p143">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="72dfe-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3128">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3128">Format</span></span>

<span data-ttu-id="72dfe-3129">De 10 a 17 dígitos separados por espacios</span><span class="sxs-lookup"><span data-stu-id="72dfe-3129">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3130">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3130">Pattern</span></span>

<span data-ttu-id="72dfe-3131">10-17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3131">10-17 digits:</span></span>
- <span data-ttu-id="72dfe-3132">3 o 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3132">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="72dfe-3133">Un espacio</span><span class="sxs-lookup"><span data-stu-id="72dfe-3133">A space</span></span> 
- <span data-ttu-id="72dfe-3134">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3134">Three digits</span></span> 
- <span data-ttu-id="72dfe-3135">Un espacio</span><span class="sxs-lookup"><span data-stu-id="72dfe-3135">A space</span></span> 
- <span data-ttu-id="72dfe-3136">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3136">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3137">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3137">Checksum</span></span>

<span data-ttu-id="72dfe-3138">Sí</span><span class="sxs-lookup"><span data-stu-id="72dfe-3138">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3139">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3139">Definition</span></span>

<span data-ttu-id="72dfe-3140">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3141">La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3141">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3142">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3142">One of the following is true:</span></span>
    - <span data-ttu-id="72dfe-3143">Se encuentra una palabra clave de Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3143">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="72dfe-3144">Se encuentra una palabra clave de Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3144">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="72dfe-3145">Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3145">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="72dfe-3146">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3146">The checksum passes.</span></span>

```
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3147">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3147">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="72dfe-3148">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="72dfe-3148">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="72dfe-3149">national health service
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3149">national health service</span></span> 
- <span data-ttu-id="72dfe-3150">nhs
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3150">nhs</span></span> 
- <span data-ttu-id="72dfe-3151">health services authority

</span><span class="sxs-lookup"><span data-stu-id="72dfe-3151">health services authority</span></span> 
- <span data-ttu-id="72dfe-3152">health authority</span><span class="sxs-lookup"><span data-stu-id="72dfe-3152">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="72dfe-3153">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="72dfe-3153">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="72dfe-3154">patient id
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3154">patient id</span></span> 
- <span data-ttu-id="72dfe-3155">patient identification
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3155">patient identification</span></span> 
- <span data-ttu-id="72dfe-3156">patient no

</span><span class="sxs-lookup"><span data-stu-id="72dfe-3156">patient no</span></span> 
- <span data-ttu-id="72dfe-3157">patient number</span><span class="sxs-lookup"><span data-stu-id="72dfe-3157">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="72dfe-3158">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="72dfe-3158">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="72dfe-3159">DG</span><span class="sxs-lookup"><span data-stu-id="72dfe-3159">GP</span></span> 
- <span data-ttu-id="72dfe-3160">DOB
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3160">DOB</span></span> 
- <span data-ttu-id="72dfe-3161">D. O. B</span><span class="sxs-lookup"><span data-stu-id="72dfe-3161">D.O.B</span></span> 
- <span data-ttu-id="72dfe-3162">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3162">Date of Birth</span></span> 
- <span data-ttu-id="72dfe-3163">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3163">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="72dfe-p144">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="72dfe-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3166">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3166">Format</span></span>

<span data-ttu-id="72dfe-3167">7 caracteres o 9 caracteres separados por espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="72dfe-3167">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3168">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3168">Pattern</span></span>

<span data-ttu-id="72dfe-3169">Dos patrones posibles:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3169">Two possible patterns:</span></span>

- <span data-ttu-id="72dfe-3170">Dos letras (los NINO válidos usan solo caracteres determinados en este prefijo, que valida este patrón; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-3170">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="72dfe-3171">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3171">Six digits</span></span>
- <span data-ttu-id="72dfe-3172">' A ', ' B ', ' C ' o ' T ' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="72dfe-3172">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="72dfe-3173">O BIEN</span><span class="sxs-lookup"><span data-stu-id="72dfe-3173">OR</span></span>

- <span data-ttu-id="72dfe-3174">Dos letras</span><span class="sxs-lookup"><span data-stu-id="72dfe-3174">Two letters</span></span>
- <span data-ttu-id="72dfe-3175">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-3175">A space or dash</span></span>
- <span data-ttu-id="72dfe-3176">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3176">Two digits</span></span>
- <span data-ttu-id="72dfe-3177">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-3177">A space or dash</span></span>
- <span data-ttu-id="72dfe-3178">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3178">Two digits</span></span>
- <span data-ttu-id="72dfe-3179">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-3179">A space or dash</span></span>
- <span data-ttu-id="72dfe-3180">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3180">Two digits</span></span>
- <span data-ttu-id="72dfe-3181">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-3181">A space or dash</span></span>
- <span data-ttu-id="72dfe-3182">' A ', ' B ', ' C ' o ' T '</span><span class="sxs-lookup"><span data-stu-id="72dfe-3182">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3183">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3183">Checksum</span></span>

<span data-ttu-id="72dfe-3184">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3185">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3185">Definition</span></span>

<span data-ttu-id="72dfe-3186">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3186">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3187">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3187">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3188">Se encuentra una palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3188">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="72dfe-3189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3190">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3190">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3191">No se encuentra ninguna palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3191">No keyword from Keyword_uk_nino is found.</span></span>

```
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3192">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="72dfe-3193">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="72dfe-3193">Keyword_uk_nino</span></span>

- <span data-ttu-id="72dfe-3194">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3194">national insurance number</span></span> 
- <span data-ttu-id="72dfe-3195">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3195">national insurance contributions</span></span> 
- <span data-ttu-id="72dfe-3196">protection act
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3196">protection act</span></span> 
- <span data-ttu-id="72dfe-3197">insurance
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3197">insurance</span></span> 
- <span data-ttu-id="72dfe-3198">social security number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3198">social security number</span></span> 
- <span data-ttu-id="72dfe-3199">insurance application
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3199">insurance application</span></span> 
- <span data-ttu-id="72dfe-3200">medical application
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3200">medical application</span></span> 
- <span data-ttu-id="72dfe-3201">social insurance
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3201">social insurance</span></span> 
- <span data-ttu-id="72dfe-3202">medical attention
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3202">medical attention</span></span> 
- <span data-ttu-id="72dfe-3203">seguridad social</span><span class="sxs-lookup"><span data-stu-id="72dfe-3203">social security</span></span> 
- <span data-ttu-id="72dfe-3204">great britain
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3204">great britain</span></span> 
- <span data-ttu-id="72dfe-3205">insurance
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3205">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="72dfe-p145">Número de pasaporte EE. UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="72dfe-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3208">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3208">Format</span></span>

<span data-ttu-id="72dfe-3209">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3209">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3210">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3210">Pattern</span></span>

<span data-ttu-id="72dfe-3211">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3211">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3212">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3212">Checksum</span></span>

<span data-ttu-id="72dfe-3213">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3213">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3214">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3214">Definition</span></span>

<span data-ttu-id="72dfe-3215">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3215">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3216">La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3216">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3217">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3217">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3218">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3218">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="72dfe-3219">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="72dfe-3219">Keyword_passport</span></span>

- <span data-ttu-id="72dfe-3220">Passport Number</span><span class="sxs-lookup"><span data-stu-id="72dfe-3220">Passport Number</span></span> 
- <span data-ttu-id="72dfe-3221">
Passport No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3221">Passport No</span></span> 
- <span data-ttu-id="72dfe-3222">Passport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3222">Passport #</span></span> 
- <span data-ttu-id="72dfe-3223">Passport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3223">Passport#</span></span> 
- <span data-ttu-id="72dfe-3224">PassportID</span><span class="sxs-lookup"><span data-stu-id="72dfe-3224">PassportID</span></span> 
- <span data-ttu-id="72dfe-3225">Passportno
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3225">Passportno</span></span> 
- <span data-ttu-id="72dfe-3226">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3226">passportnumber</span></span> 
- <span data-ttu-id="72dfe-3227">パスポート</span><span class="sxs-lookup"><span data-stu-id="72dfe-3227">パスポート</span></span> 
- <span data-ttu-id="72dfe-3228">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3228">パスポート番号</span></span> 
- <span data-ttu-id="72dfe-3229">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3229">パスポートのNum</span></span> 
- <span data-ttu-id="72dfe-3230">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3230">パスポート＃</span></span> 
- <span data-ttu-id="72dfe-3231">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="72dfe-3231">Numéro de passeport</span></span> 
- <span data-ttu-id="72dfe-3232">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="72dfe-3232">Passeport n °</span></span> 
- <span data-ttu-id="72dfe-3233">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3233">Passeport Non</span></span> 
- <span data-ttu-id="72dfe-3234">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3234">Passeport #</span></span> 
- <span data-ttu-id="72dfe-3235">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3235">Passeport#</span></span> 
- <span data-ttu-id="72dfe-3236">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="72dfe-3236">PasseportNon</span></span> 
- <span data-ttu-id="72dfe-3237">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3237">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="72dfe-3238">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3238">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3239">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3239">Format</span></span>

<span data-ttu-id="72dfe-3240">Entre 8 y 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3240">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3241">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3241">Pattern</span></span>

<span data-ttu-id="72dfe-3242">Entre 8 y 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3242">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3243">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3243">Checksum</span></span>

<span data-ttu-id="72dfe-3244">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3244">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3245">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3245">Definition</span></span>

<span data-ttu-id="72dfe-3246">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3247">La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3247">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3248">Se encuentra una palabra clave de Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3248">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3249">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3249">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="72dfe-3250">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="72dfe-3250">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="72dfe-3251">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3251">Checking Account Number</span></span> 
- <span data-ttu-id="72dfe-3252">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3252">Checking Account</span></span> 
- <span data-ttu-id="72dfe-3253">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3253">Checking Account #</span></span> 
- <span data-ttu-id="72dfe-3254">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3254">Checking Acct Number</span></span> 
- <span data-ttu-id="72dfe-3255">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3255">Checking Acct #</span></span> 
- <span data-ttu-id="72dfe-3256">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3256">Checking Acct No.</span></span> 
- <span data-ttu-id="72dfe-3257">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3257">Checking Account No.</span></span> 
- <span data-ttu-id="72dfe-3258">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3258">Bank Account Number</span></span> 
- <span data-ttu-id="72dfe-3259">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3259">Bank Account #</span></span> 
- <span data-ttu-id="72dfe-3260">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3260">Bank Acct Number</span></span> 
- <span data-ttu-id="72dfe-3261">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3261">Bank Acct #</span></span> 
- <span data-ttu-id="72dfe-3262">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3262">Bank Acct No.</span></span> 
- <span data-ttu-id="72dfe-3263">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3263">Bank Account No.</span></span> 
- <span data-ttu-id="72dfe-3264">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3264">Savings Account Number</span></span> 
- <span data-ttu-id="72dfe-3265">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3265">Savings Account.</span></span> 
- <span data-ttu-id="72dfe-3266">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3266">Savings Account #</span></span> 
- <span data-ttu-id="72dfe-3267">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3267">Savings Acct Number</span></span> 
- <span data-ttu-id="72dfe-3268">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3268">Savings Acct #</span></span> 
- <span data-ttu-id="72dfe-3269">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3269">Savings Acct No.</span></span> 
- <span data-ttu-id="72dfe-3270">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3270">Savings Account No.</span></span> 
- <span data-ttu-id="72dfe-3271">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3271">Debit Account Number</span></span> 
- <span data-ttu-id="72dfe-3272">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3272">Debit Account</span></span> 
- <span data-ttu-id="72dfe-3273">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3273">Debit Account #</span></span> 
- <span data-ttu-id="72dfe-3274">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3274">Debit Acct Number</span></span> 
- <span data-ttu-id="72dfe-3275">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3275">Debit Acct #</span></span> 
- <span data-ttu-id="72dfe-3276">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3276">Debit Acct No.</span></span> 
- <span data-ttu-id="72dfe-3277">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3277">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="72dfe-3278">Número de licencia de conductor de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3278">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3279">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3279">Format</span></span>

<span data-ttu-id="72dfe-3280">Depende del estado</span><span class="sxs-lookup"><span data-stu-id="72dfe-3280">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3281">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3281">Pattern</span></span>

<span data-ttu-id="72dfe-3282">Depende del estado, por ejemplo, Nueva York:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3282">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="72dfe-3283">Nueve dígitos como ddd ddd ddd coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3283">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="72dfe-3284">Nueve dígitos como ddddddddd no coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3284">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3285">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3285">Checksum</span></span>

<span data-ttu-id="72dfe-3286">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3287">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3287">Definition</span></span>

<span data-ttu-id="72dfe-3288">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3289">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3289">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3290">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3290">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="72dfe-3291">Se encuentra una palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3291">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="72dfe-3292">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3292">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3293">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3293">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3294">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3294">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="72dfe-3295">Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3295">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="72dfe-3296">No se encuentra ninguna palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3296">No keyword from Keyword_us_drivers_license is found.</span></span>

```
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3297">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3297">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="72dfe-3298">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="72dfe-3298">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="72dfe-3299">DL</span><span class="sxs-lookup"><span data-stu-id="72dfe-3299">DL</span></span> 
- <span data-ttu-id="72dfe-3300">DLS</span><span class="sxs-lookup"><span data-stu-id="72dfe-3300">DLS</span></span> 
- <span data-ttu-id="72dfe-3301">CDL</span><span class="sxs-lookup"><span data-stu-id="72dfe-3301">CDL</span></span> 
- <span data-ttu-id="72dfe-3302">CDLS</span><span class="sxs-lookup"><span data-stu-id="72dfe-3302">CDLS</span></span> 
- <span data-ttu-id="72dfe-3303">ID</span><span class="sxs-lookup"><span data-stu-id="72dfe-3303">ID</span></span> 
- <span data-ttu-id="72dfe-3304">Falta</span><span class="sxs-lookup"><span data-stu-id="72dfe-3304">IDs</span></span> 
- <span data-ttu-id="72dfe-3305">DL#</span><span class="sxs-lookup"><span data-stu-id="72dfe-3305">DL#</span></span> 
- <span data-ttu-id="72dfe-3306">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3306">DLS#</span></span> 
- <span data-ttu-id="72dfe-3307">CDL#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3307">CDL#</span></span> 
- <span data-ttu-id="72dfe-3308">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3308">CDLS#</span></span> 
- <span data-ttu-id="72dfe-3309">ID#</span><span class="sxs-lookup"><span data-stu-id="72dfe-3309">ID#</span></span>
- <span data-ttu-id="72dfe-3310">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3310">IDs#</span></span> 
- <span data-ttu-id="72dfe-3311">número de Id.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3311">ID number</span></span> 
- <span data-ttu-id="72dfe-3312">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3312">ID numbers</span></span> 
- <span data-ttu-id="72dfe-3313">LIC</span><span class="sxs-lookup"><span data-stu-id="72dfe-3313">LIC</span></span> 
- <span data-ttu-id="72dfe-3314">LIC#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3314">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="72dfe-3315">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="72dfe-3315">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="72dfe-3316">DriverLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-3316">DriverLic</span></span> 
- <span data-ttu-id="72dfe-3317">DriverLics</span><span class="sxs-lookup"><span data-stu-id="72dfe-3317">DriverLics</span></span> 
- <span data-ttu-id="72dfe-3318">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-3318">DriverLicense</span></span> 
- <span data-ttu-id="72dfe-3319">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-3319">DriverLicenses</span></span> 
- <span data-ttu-id="72dfe-3320">Lic del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-3320">Driver Lic</span></span> 
- <span data-ttu-id="72dfe-3321">Controlador conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-3321">Driver Lics</span></span> 
- <span data-ttu-id="72dfe-3322">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-3322">Driver License</span></span> 
- <span data-ttu-id="72dfe-3323">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-3323">Driver Licenses</span></span> 
- <span data-ttu-id="72dfe-3324">DriversLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-3324">DriversLic</span></span> 
- <span data-ttu-id="72dfe-3325">DriversLics</span><span class="sxs-lookup"><span data-stu-id="72dfe-3325">DriversLics</span></span> 
- <span data-ttu-id="72dfe-3326">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-3326">DriversLicense</span></span> 
- <span data-ttu-id="72dfe-3327">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-3327">DriversLicenses</span></span> 
- <span data-ttu-id="72dfe-3328">Lic de los drivers</span><span class="sxs-lookup"><span data-stu-id="72dfe-3328">Drivers Lic</span></span> 
- <span data-ttu-id="72dfe-3329">Controladores conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-3329">Drivers Lics</span></span> 
- <span data-ttu-id="72dfe-3330">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-3330">Drivers License</span></span> 
- <span data-ttu-id="72dfe-3331">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="72dfe-3331">Drivers Licenses</span></span> 
- <span data-ttu-id="72dfe-3332">N.º carné</span><span class="sxs-lookup"><span data-stu-id="72dfe-3332">Driver'Lic</span></span> 
- <span data-ttu-id="72dfe-3333">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="72dfe-3333">Driver'Lics</span></span> 
- <span data-ttu-id="72dfe-3334">Conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-3334">Driver'License</span></span> 
- <span data-ttu-id="72dfe-3335">Conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-3335">Driver'Licenses</span></span> 
- <span data-ttu-id="72dfe-3336">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-3336">Driver' Lic</span></span> 
- <span data-ttu-id="72dfe-3337">Controlador de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-3337">Driver' Lics</span></span> 
- <span data-ttu-id="72dfe-3338">Licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-3338">Driver' License</span></span> 
- <span data-ttu-id="72dfe-3339">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="72dfe-3339">Driver' Licenses</span></span>
- <span data-ttu-id="72dfe-3340">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="72dfe-3340">Driver'sLic</span></span> 
- <span data-ttu-id="72dfe-3341">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="72dfe-3341">Driver'sLics</span></span> 
- <span data-ttu-id="72dfe-3342">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="72dfe-3342">Driver'sLicense</span></span> 
- <span data-ttu-id="72dfe-3343">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="72dfe-3343">Driver'sLicenses</span></span> 
- <span data-ttu-id="72dfe-3344">Lic del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-3344">Driver's Lic</span></span> 
- <span data-ttu-id="72dfe-3345">Conducción del conductor</span><span class="sxs-lookup"><span data-stu-id="72dfe-3345">Driver's Lics</span></span> 
- <span data-ttu-id="72dfe-3346">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-3346">Driver's License</span></span> 
- <span data-ttu-id="72dfe-3347">Licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-3347">Driver's Licenses</span></span> 
- <span data-ttu-id="72dfe-3348">identification number
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3348">identification number</span></span> 
- <span data-ttu-id="72dfe-3349">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3349">identification numbers</span></span> 
- <span data-ttu-id="72dfe-3350">identification #
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3350">identification #</span></span> 
- <span data-ttu-id="72dfe-3351">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3351">id card</span></span> 
- <span data-ttu-id="72dfe-3352">tarjetas de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3352">id cards</span></span> 
- <span data-ttu-id="72dfe-3353">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3353">identification card</span></span> 
- <span data-ttu-id="72dfe-3354">tarjetas de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3354">identification cards</span></span> 
- <span data-ttu-id="72dfe-3355">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3355">DriverLic#</span></span> 
- <span data-ttu-id="72dfe-3356">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3356">DriverLics#</span></span> 
- <span data-ttu-id="72dfe-3357">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3357">DriverLicense#</span></span> 
- <span data-ttu-id="72dfe-3358">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3358">DriverLicenses#</span></span> 
- <span data-ttu-id="72dfe-3359">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="72dfe-3359">Driver Lic#</span></span> 
- <span data-ttu-id="72dfe-3360">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3360">Driver Lics#</span></span> 
- <span data-ttu-id="72dfe-3361">N.º de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-3361">Driver License#</span></span> 
- <span data-ttu-id="72dfe-3362">N.º de licencias de conducir</span><span class="sxs-lookup"><span data-stu-id="72dfe-3362">Driver Licenses#</span></span> 
- <span data-ttu-id="72dfe-3363">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3363">DriversLic#</span></span> 
- <span data-ttu-id="72dfe-3364">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3364">DriversLics#</span></span> 
- <span data-ttu-id="72dfe-3365">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3365">DriversLicense#</span></span> 
- <span data-ttu-id="72dfe-3366">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3366">DriversLicenses#</span></span> 
- <span data-ttu-id="72dfe-3367">N.º de Lic de los conductores</span><span class="sxs-lookup"><span data-stu-id="72dfe-3367">Drivers Lic#</span></span> 
- <span data-ttu-id="72dfe-3368">Controladores conducción #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3368">Drivers Lics#</span></span> 
- <span data-ttu-id="72dfe-3369">N.º de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="72dfe-3369">Drivers License#</span></span> 
- <span data-ttu-id="72dfe-3370">N.º de licencias de impulsores</span><span class="sxs-lookup"><span data-stu-id="72dfe-3370">Drivers Licenses#</span></span> 
- <span data-ttu-id="72dfe-3371">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3371">Driver'Lic#</span></span> 
- <span data-ttu-id="72dfe-3372">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3372">Driver'Lics#</span></span> 
- <span data-ttu-id="72dfe-3373">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3373">Driver'License#</span></span> 
- <span data-ttu-id="72dfe-3374">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3374">Driver'Licenses#</span></span> 
- <span data-ttu-id="72dfe-3375">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3375">Driver' Lic#</span></span> 
- <span data-ttu-id="72dfe-3376">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3376">Driver' Lics#</span></span> 
- <span data-ttu-id="72dfe-3377">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3377">Driver' License#</span></span> 
- <span data-ttu-id="72dfe-3378">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3378">Driver' Licenses#</span></span> 
- <span data-ttu-id="72dfe-3379">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3379">Driver'sLic#</span></span> 
- <span data-ttu-id="72dfe-3380">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3380">Driver'sLics#</span></span> 
- <span data-ttu-id="72dfe-3381">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3381">Driver'sLicense#</span></span> 
- <span data-ttu-id="72dfe-3382">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="72dfe-3382">Driver'sLicenses#</span></span> 
- <span data-ttu-id="72dfe-3383">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3383">Driver's Lic#</span></span> 
- <span data-ttu-id="72dfe-3384">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3384">Driver's Lics#</span></span> 
- <span data-ttu-id="72dfe-3385">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3385">Driver's License#</span></span> 
- <span data-ttu-id="72dfe-3386">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3386">Driver's Licenses#</span></span> 
- <span data-ttu-id="72dfe-3387">número de tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3387">id card#</span></span> 
- <span data-ttu-id="72dfe-3388">id cards#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3388">id cards#</span></span> 
- <span data-ttu-id="72dfe-3389">identification card#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3389">identification card#</span></span> 
- <span data-ttu-id="72dfe-3390">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3390">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="72dfe-3391">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="72dfe-3391">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="72dfe-3392">Abreviatura del estado (por ejemplo, "NY")
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3392">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="72dfe-3393">Nombre del estado (por ejemplo, "New York")
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3393">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="72dfe-3394">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3394">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3395">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3395">Format</span></span>

<span data-ttu-id="72dfe-3396">Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="72dfe-3396">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3397">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3397">Pattern</span></span>

<span data-ttu-id="72dfe-3398">Con formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3398">Formatted:</span></span>
- <span data-ttu-id="72dfe-3399">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="72dfe-3399">The digit "9"</span></span> 
- <span data-ttu-id="72dfe-3400">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3400">Two digits</span></span> 
- <span data-ttu-id="72dfe-3401">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-3401">A space or dash</span></span> 
- <span data-ttu-id="72dfe-3402">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="72dfe-3402">A "7" or "8"</span></span> 
- <span data-ttu-id="72dfe-3403">Un dígito</span><span class="sxs-lookup"><span data-stu-id="72dfe-3403">A digit</span></span> 
- <span data-ttu-id="72dfe-3404">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="72dfe-3404">A space, or dash</span></span> 
- <span data-ttu-id="72dfe-3405">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3405">Four digits</span></span>

<span data-ttu-id="72dfe-3406">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3406">Unformatted:</span></span>
- <span data-ttu-id="72dfe-3407">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="72dfe-3407">The digit "9"</span></span> 
- <span data-ttu-id="72dfe-3408">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3408">Two digits</span></span> 
- <span data-ttu-id="72dfe-3409">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="72dfe-3409">A "7" or "8"</span></span> 
- <span data-ttu-id="72dfe-3410">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="72dfe-3410">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3411">Checksum</span></span>

<span data-ttu-id="72dfe-3412">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3412">No</span></span>

### <a name="definition"></a><span data-ttu-id="72dfe-3413">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3413">Definition</span></span>

<span data-ttu-id="72dfe-3414">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3415">La función Func_formatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3415">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3416">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3416">At least one of the following is true:</span></span>
    - <span data-ttu-id="72dfe-3417">Se encuentra una palabra clave de Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3417">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="72dfe-3418">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3418">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="72dfe-3419">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3419">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="72dfe-3420">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3420">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="72dfe-3421">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3421">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3422">La función Func_unformatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3422">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3423">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3423">At least one of the following is true:</span></span>
    - <span data-ttu-id="72dfe-3424">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3424">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="72dfe-3425">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3425">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="72dfe-3426">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3426">The function Func_us_date finds a date in the right date format.</span></span>

```
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3427">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3427">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="72dfe-3428">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="72dfe-3428">Keyword_itin</span></span>

- <span data-ttu-id="72dfe-3429">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3429">taxpayer</span></span> 
- <span data-ttu-id="72dfe-3430">tax id
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3430">tax id</span></span> 
- <span data-ttu-id="72dfe-3431">tax identification
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3431">tax identification</span></span> 
- <span data-ttu-id="72dfe-3432">itin
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3432">itin</span></span> 
- <span data-ttu-id="72dfe-3433">SSN</span><span class="sxs-lookup"><span data-stu-id="72dfe-3433">ssn</span></span> 
- <span data-ttu-id="72dfe-3434">tin
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3434">tin</span></span> 
- <span data-ttu-id="72dfe-3435">seguridad social</span><span class="sxs-lookup"><span data-stu-id="72dfe-3435">social security</span></span> 
- <span data-ttu-id="72dfe-3436">tax payer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3436">tax payer</span></span> 
- <span data-ttu-id="72dfe-3437">itins
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3437">itins</span></span> 
- <span data-ttu-id="72dfe-3438">taxid

</span><span class="sxs-lookup"><span data-stu-id="72dfe-3438">taxid</span></span> 
- <span data-ttu-id="72dfe-3439">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3439">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="72dfe-3440">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="72dfe-3440">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="72dfe-3441">License</span><span class="sxs-lookup"><span data-stu-id="72dfe-3441">License</span></span> 
- <span data-ttu-id="72dfe-3442">DL</span><span class="sxs-lookup"><span data-stu-id="72dfe-3442">DL</span></span> 
- <span data-ttu-id="72dfe-3443">DOB
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3443">DOB</span></span> 
- <span data-ttu-id="72dfe-3444">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="72dfe-3444">Birthdate</span></span> 
- <span data-ttu-id="72dfe-3445">Cumpleaños </span><span class="sxs-lookup"><span data-stu-id="72dfe-3445">Birthday</span></span> 
- <span data-ttu-id="72dfe-3446">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3446">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="72dfe-3447">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3447">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="72dfe-3448">Formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3448">Format</span></span>

<span data-ttu-id="72dfe-3449">9 dígitos, que pueden ser un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="72dfe-3449">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="72dfe-3450">Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="72dfe-3450">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="72dfe-3451">Patrón</span><span class="sxs-lookup"><span data-stu-id="72dfe-3451">Pattern</span></span>

<span data-ttu-id="72dfe-3452">Cuatro funciones buscan SSN en cuatro patrones diferentes:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3452">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="72dfe-3453">Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="72dfe-3453">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="72dfe-3454">Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="72dfe-3454">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="72dfe-3455">Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="72dfe-3455">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="72dfe-3456">Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="72dfe-3456">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="72dfe-3457">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="72dfe-3457">Checksum</span></span>

<span data-ttu-id="72dfe-3458">No</span><span class="sxs-lookup"><span data-stu-id="72dfe-3458">No</span></span>


### <a name="definition"></a><span data-ttu-id="72dfe-3459">Definición</span><span class="sxs-lookup"><span data-stu-id="72dfe-3459">Definition</span></span>

<span data-ttu-id="72dfe-3460">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3461">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3461">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3462">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3462">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="72dfe-3463">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3464">La función Func_unformatted_ssn busca contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3464">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3465">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3465">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="72dfe-3466">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3467">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3467">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3468">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3468">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="72dfe-3469">La función Func_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3469">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="72dfe-3470">Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="72dfe-3470">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="72dfe-3471">La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3471">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="72dfe-3472">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3472">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="72dfe-3473">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="72dfe-3473">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

```
<!-- U.S. Social Security Number (SSN) -->
    <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="72dfe-3474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="72dfe-3474">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="72dfe-3475">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="72dfe-3475">Keyword_ssn</span></span>

- <span data-ttu-id="72dfe-3476">Social Security
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3476">Social Security</span></span> 
- <span data-ttu-id="72dfe-3477">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3477">Social Security#</span></span> 
- <span data-ttu-id="72dfe-3478">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3478">Soc Sec</span></span> 
- <span data-ttu-id="72dfe-3479">SSN</span><span class="sxs-lookup"><span data-stu-id="72dfe-3479">SSN</span></span> 
- <span data-ttu-id="72dfe-3480">SSNS
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3480">SSNS</span></span> 
- <span data-ttu-id="72dfe-3481">SSN#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3481">SSN#</span></span> 
- <span data-ttu-id="72dfe-3482">SS#
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3482">SS#</span></span> 
- <span data-ttu-id="72dfe-3483">SSID
</span><span class="sxs-lookup"><span data-stu-id="72dfe-3483">SSID</span></span> 
   

