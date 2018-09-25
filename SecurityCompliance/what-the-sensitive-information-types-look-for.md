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
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye los tipos de información confidencial 80 que están listos para su uso en las directivas de DLP. En este tema se enumera todos estos tipos de información confidencial y muestra lo que busca una directiva de DLP cuando detecta cada tipo.
ms.openlocfilehash: 5097227d8efa833f255631febde50b937add48ef
ms.sourcegitcommit: ede6230c2df398dc0a633e8f32ee0bfede0d5142
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25002693"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="39868-104">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="39868-104">What the sensitive information types look for</span></span>

<span data-ttu-id="39868-p102">Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se enumera todos estos tipos de información confidencial y muestra lo que busca una directiva de DLP cuando detecta cada tipo. Un tipo de información confidencial se define mediante un patrón que puede identificarse mediante una expresión regular o una función. Además, como las palabras clave y sumas de comprobación de prueba puede utilizarse para identificar un tipo de información confidencial. Proximidad y nivel de confianza también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="39868-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="39868-110">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="39868-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-111">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-111">Format</span></span>

<span data-ttu-id="39868-112">9 dígitos, que pueden tener un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="39868-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-113">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-113">Pattern</span></span>

<span data-ttu-id="39868-114">Con formato:</span><span class="sxs-lookup"><span data-stu-id="39868-114">Formatted:</span></span>
- <span data-ttu-id="39868-115">Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="39868-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="39868-116">Un guion</span><span class="sxs-lookup"><span data-stu-id="39868-116">A hyphen</span></span>
- <span data-ttu-id="39868-117">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-117">Four digits</span></span>
- <span data-ttu-id="39868-118">Un guion</span><span class="sxs-lookup"><span data-stu-id="39868-118">A hyphen</span></span>
- <span data-ttu-id="39868-119">Un dígito</span><span class="sxs-lookup"><span data-stu-id="39868-119">A digit</span></span>

<span data-ttu-id="39868-120">Sin formato: dígitos consecutivos 9 a partir de 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="39868-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="39868-121">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-121">Checksum</span></span>

<span data-ttu-id="39868-122">No</span><span class="sxs-lookup"><span data-stu-id="39868-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-123">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-123">Definition</span></span>

<span data-ttu-id="39868-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-125">La función Func_aba_routing encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-126">Se encuentra una palabra clave de Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="39868-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="39868-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="39868-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="39868-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="39868-129">aba</span><span class="sxs-lookup"><span data-stu-id="39868-129">aba</span></span>
- <span data-ttu-id="39868-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="39868-130">aba #</span></span>
- <span data-ttu-id="39868-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="39868-131">aba routing #</span></span>
- <span data-ttu-id="39868-132">número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="39868-132">aba routing number</span></span>
- <span data-ttu-id="39868-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="39868-133">aba#</span></span>
- <span data-ttu-id="39868-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="39868-134">abarouting#</span></span>
- <span data-ttu-id="39868-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="39868-135">aba number</span></span>
- <span data-ttu-id="39868-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="39868-136">abaroutingnumber</span></span>
- <span data-ttu-id="39868-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="39868-137">american bank association routing #</span></span>
- <span data-ttu-id="39868-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="39868-138">american bank association routing number</span></span>
- <span data-ttu-id="39868-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="39868-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="39868-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="39868-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="39868-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="39868-141">bank routing number</span></span>
- <span data-ttu-id="39868-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="39868-142">bankrouting#</span></span>
- <span data-ttu-id="39868-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="39868-143">bankroutingnumber</span></span>
- <span data-ttu-id="39868-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="39868-144">routing transit number</span></span>
- <span data-ttu-id="39868-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="39868-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="39868-146">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="39868-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-147">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-147">Format</span></span>

<span data-ttu-id="39868-148">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="39868-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-149">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-149">Pattern</span></span>

<span data-ttu-id="39868-150">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-150">Eight digits:</span></span>
- <span data-ttu-id="39868-151">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-151">Two digits</span></span>
- <span data-ttu-id="39868-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-152">A period</span></span>
- <span data-ttu-id="39868-153">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-153">Three digits</span></span>
- <span data-ttu-id="39868-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-154">A period</span></span>
- <span data-ttu-id="39868-155">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-156">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-156">Checksum</span></span>

<span data-ttu-id="39868-157">No</span><span class="sxs-lookup"><span data-stu-id="39868-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-158">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-158">Definition</span></span>

<span data-ttu-id="39868-159">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-160">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-161">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="39868-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="39868-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="39868-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="39868-164">Número de identidad nacional de Argentina
</span><span class="sxs-lookup"><span data-stu-id="39868-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="39868-165">Identidad</span><span class="sxs-lookup"><span data-stu-id="39868-165">Identity</span></span> 
- <span data-ttu-id="39868-166">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="39868-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="39868-167">DNI</span></span> 
- <span data-ttu-id="39868-168">Registro nacional de NIC de personas</span><span class="sxs-lookup"><span data-stu-id="39868-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="39868-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="39868-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="39868-170">Registro nacional de las personas
</span><span class="sxs-lookup"><span data-stu-id="39868-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="39868-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="39868-171">Identidad</span></span> 
- <span data-ttu-id="39868-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="39868-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="39868-173">Número de cuenta bancaria de Australia</span><span class="sxs-lookup"><span data-stu-id="39868-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-174">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-174">Format</span></span>

<span data-ttu-id="39868-175">De 6 a 10 dígitos con o sin número de sucursal bancaria de estado</span><span class="sxs-lookup"><span data-stu-id="39868-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-176">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-176">Pattern</span></span>

<span data-ttu-id="39868-p103">Número de cuenta es 10 de 6 dígitos. Número de sucursal de estado de banco de Australia:</span><span class="sxs-lookup"><span data-stu-id="39868-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="39868-179">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-179">Three digits</span></span> 
- <span data-ttu-id="39868-180">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-180">A hyphen</span></span> 
- <span data-ttu-id="39868-181">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-182">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-182">Checksum</span></span>

<span data-ttu-id="39868-183">No</span><span class="sxs-lookup"><span data-stu-id="39868-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-184">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-184">Definition</span></span>

<span data-ttu-id="39868-185">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-186">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="39868-187">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="39868-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="39868-188">La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="39868-189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-190">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="39868-191">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="39868-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="39868-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="39868-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="39868-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="39868-194">swift bank code</span></span>
- <span data-ttu-id="39868-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="39868-195">correspondent bank</span></span>
- <span data-ttu-id="39868-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="39868-196">base currency</span></span>
- <span data-ttu-id="39868-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="39868-197">usa account</span></span>
- <span data-ttu-id="39868-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="39868-198">holder address</span></span>
- <span data-ttu-id="39868-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="39868-199">bank address</span></span>
- <span data-ttu-id="39868-200">
information account</span><span class="sxs-lookup"><span data-stu-id="39868-200">information account</span></span>
- <span data-ttu-id="39868-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="39868-201">fund transfers</span></span>
- <span data-ttu-id="39868-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="39868-202">bank charges</span></span>
- <span data-ttu-id="39868-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="39868-203">bank details</span></span>
- <span data-ttu-id="39868-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="39868-204">banking information</span></span>
- <span data-ttu-id="39868-205">
full names</span><span class="sxs-lookup"><span data-stu-id="39868-205">full names</span></span>
- <span data-ttu-id="39868-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="39868-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="39868-207">Número de licencia de conducción de Australia</span><span class="sxs-lookup"><span data-stu-id="39868-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-208">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-208">Format</span></span>

<span data-ttu-id="39868-209">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-210">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-210">Pattern</span></span>

<span data-ttu-id="39868-211">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="39868-212">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="39868-213">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-213">Two digits</span></span> 
- <span data-ttu-id="39868-214">Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="39868-215">O bien</span><span class="sxs-lookup"><span data-stu-id="39868-215">OR</span></span>

- <span data-ttu-id="39868-216">1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="39868-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="39868-217">4-9 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-217">4-9 digits</span></span>

<span data-ttu-id="39868-218">O bien</span><span class="sxs-lookup"><span data-stu-id="39868-218">OR</span></span>

- <span data-ttu-id="39868-219">Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-220">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-220">Checksum</span></span>

<span data-ttu-id="39868-221">No</span><span class="sxs-lookup"><span data-stu-id="39868-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-222">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-222">Definition</span></span>

<span data-ttu-id="39868-223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-224">La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-225">Se encuentra una palabra clave de Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="39868-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="39868-226">No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="39868-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="39868-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="39868-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="39868-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="39868-229">international driving permits</span></span>
- <span data-ttu-id="39868-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="39868-230">australian automobile association</span></span>
- <span data-ttu-id="39868-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="39868-231">sydney nsw</span></span>
- <span data-ttu-id="39868-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="39868-232">international driving permit</span></span>
- <span data-ttu-id="39868-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="39868-233">DriverLicence</span></span>
- <span data-ttu-id="39868-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="39868-234">DriverLicences</span></span>
- <span data-ttu-id="39868-235">Lic de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-235">Driver Lic</span></span>
- <span data-ttu-id="39868-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="39868-236">Driver Licence</span></span>
- <span data-ttu-id="39868-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="39868-237">Driver Licences</span></span>
- <span data-ttu-id="39868-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="39868-238">DriversLic</span></span>
- <span data-ttu-id="39868-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="39868-239">DriversLicence</span></span>
- <span data-ttu-id="39868-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="39868-240">DriversLicences</span></span>
- <span data-ttu-id="39868-241">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-241">Drivers Lic</span></span>
- <span data-ttu-id="39868-242">LIC de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-242">Drivers Lics</span></span>
- <span data-ttu-id="39868-243">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-243">Drivers Licence</span></span>
- <span data-ttu-id="39868-244">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-244">Drivers Licences</span></span>
- <span data-ttu-id="39868-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="39868-245">Driver'Lic</span></span>
- <span data-ttu-id="39868-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="39868-246">Driver'Lics</span></span>
- <span data-ttu-id="39868-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="39868-247">Driver'Licence</span></span>
- <span data-ttu-id="39868-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="39868-248">Driver'Licences</span></span>
- <span data-ttu-id="39868-249">Controlador ' Lic</span><span class="sxs-lookup"><span data-stu-id="39868-249">Driver' Lic</span></span>
- <span data-ttu-id="39868-250">Controlador ' LIC</span><span class="sxs-lookup"><span data-stu-id="39868-250">Driver' Lics</span></span>
- <span data-ttu-id="39868-251">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="39868-251">Driver' Licence</span></span>
- <span data-ttu-id="39868-252">Controlador ' certificados</span><span class="sxs-lookup"><span data-stu-id="39868-252">Driver' Licences</span></span>
- <span data-ttu-id="39868-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="39868-253">Driver'sLic</span></span>
- <span data-ttu-id="39868-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="39868-254">Driver'sLics</span></span>
- <span data-ttu-id="39868-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="39868-255">Driver'sLicence</span></span>
- <span data-ttu-id="39868-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="39868-256">Driver'sLicences</span></span>
- <span data-ttu-id="39868-257">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-257">Driver's Lic</span></span>
- <span data-ttu-id="39868-258">LIC del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-258">Driver's Lics</span></span>
- <span data-ttu-id="39868-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="39868-259">Driver's Licence</span></span>
- <span data-ttu-id="39868-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="39868-260">Driver's Licences</span></span>
- <span data-ttu-id="39868-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="39868-261">DriverLic#</span></span>
- <span data-ttu-id="39868-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="39868-262">DriverLics#</span></span>
- <span data-ttu-id="39868-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="39868-263">DriverLicence#</span></span>
- <span data-ttu-id="39868-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="39868-264">DriverLicences#</span></span>
- <span data-ttu-id="39868-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="39868-265">Driver Lic#</span></span>
- <span data-ttu-id="39868-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-266">Driver Lics#</span></span>
- <span data-ttu-id="39868-267">Controlador certificado #</span><span class="sxs-lookup"><span data-stu-id="39868-267">Driver Licence#</span></span>
- <span data-ttu-id="39868-268">Controlador certificados #</span><span class="sxs-lookup"><span data-stu-id="39868-268">Driver Licences#</span></span>
- <span data-ttu-id="39868-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="39868-269">DriversLic#</span></span>
- <span data-ttu-id="39868-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="39868-270">DriversLics#</span></span>
- <span data-ttu-id="39868-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="39868-271">DriversLicence#</span></span>
- <span data-ttu-id="39868-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="39868-272">DriversLicences#</span></span>
- <span data-ttu-id="39868-273">Controladores Lic #</span><span class="sxs-lookup"><span data-stu-id="39868-273">Drivers Lic#</span></span>
- <span data-ttu-id="39868-274">Controladores LIC #</span><span class="sxs-lookup"><span data-stu-id="39868-274">Drivers Lics#</span></span>
- <span data-ttu-id="39868-275">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-275">Drivers Licence#</span></span>
- <span data-ttu-id="39868-276">Controladores certificados #</span><span class="sxs-lookup"><span data-stu-id="39868-276">Drivers Licences#</span></span>
- <span data-ttu-id="39868-277">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-277">Driver'Lic#</span></span>
- <span data-ttu-id="39868-278">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-278">Driver'Lics#</span></span>
- <span data-ttu-id="39868-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="39868-279">Driver'Licence#</span></span>
- <span data-ttu-id="39868-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="39868-280">Driver'Licences#</span></span>
- <span data-ttu-id="39868-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-281">Driver' Lic#</span></span>
- <span data-ttu-id="39868-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-282">Driver' Lics#</span></span>
- <span data-ttu-id="39868-283">Controlador ' certificado #</span><span class="sxs-lookup"><span data-stu-id="39868-283">Driver' Licence#</span></span>
- <span data-ttu-id="39868-284">Controlador ' certificados #</span><span class="sxs-lookup"><span data-stu-id="39868-284">Driver' Licences#</span></span>
- <span data-ttu-id="39868-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="39868-285">Driver'sLic#</span></span>
- <span data-ttu-id="39868-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="39868-286">Driver'sLics#</span></span>
- <span data-ttu-id="39868-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="39868-287">Driver'sLicence#</span></span>
- <span data-ttu-id="39868-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="39868-288">Driver'sLicences#</span></span>
- <span data-ttu-id="39868-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-289">Driver's Lic#</span></span>
- <span data-ttu-id="39868-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-290">Driver's Lics#</span></span>
- <span data-ttu-id="39868-291">Certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-291">Driver's Licence#</span></span>
- <span data-ttu-id="39868-292">El certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="39868-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="39868-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="39868-294">aaa</span><span class="sxs-lookup"><span data-stu-id="39868-294">aaa</span></span>
- <span data-ttu-id="39868-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="39868-295">DriverLicense</span></span>
- <span data-ttu-id="39868-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-296">DriverLicenses</span></span>
- <span data-ttu-id="39868-297">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-297">Driver License</span></span>
- <span data-ttu-id="39868-298">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-298">Driver Licenses</span></span>
- <span data-ttu-id="39868-299">PermisoDeConducción</span><span class="sxs-lookup"><span data-stu-id="39868-299">DriversLicense</span></span>
- <span data-ttu-id="39868-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-300">DriversLicenses</span></span>
- <span data-ttu-id="39868-301">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-301">Drivers License</span></span>
- <span data-ttu-id="39868-302">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-302">Drivers Licenses</span></span>
- <span data-ttu-id="39868-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="39868-303">Driver'License</span></span>
- <span data-ttu-id="39868-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="39868-304">Driver'Licenses</span></span>
- <span data-ttu-id="39868-305">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="39868-305">Driver' License</span></span>
- <span data-ttu-id="39868-306">Controlador ' licencias</span><span class="sxs-lookup"><span data-stu-id="39868-306">Driver' Licenses</span></span>
- <span data-ttu-id="39868-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="39868-307">Driver'sLicense</span></span>
- <span data-ttu-id="39868-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-308">Driver'sLicenses</span></span>
- <span data-ttu-id="39868-309">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="39868-309">Driver's License</span></span>
- <span data-ttu-id="39868-310">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-310">Driver's Licenses</span></span>
- <span data-ttu-id="39868-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="39868-311">DriverLicense#</span></span>
- <span data-ttu-id="39868-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-312">DriverLicenses#</span></span>
- <span data-ttu-id="39868-313">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="39868-313">Driver License#</span></span>
- <span data-ttu-id="39868-314">Controlador licencias #</span><span class="sxs-lookup"><span data-stu-id="39868-314">Driver Licenses#</span></span>
- <span data-ttu-id="39868-315">PermisoDeConducción #</span><span class="sxs-lookup"><span data-stu-id="39868-315">DriversLicense#</span></span>
- <span data-ttu-id="39868-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-316">DriversLicenses#</span></span>
- <span data-ttu-id="39868-317">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-317">Drivers License#</span></span>
- <span data-ttu-id="39868-318">Licencias de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-318">Drivers Licenses#</span></span>
- <span data-ttu-id="39868-319">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="39868-319">Driver'License#</span></span>
- <span data-ttu-id="39868-320">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-320">Driver'Licenses#</span></span>
- <span data-ttu-id="39868-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="39868-321">Driver' License#</span></span>
- <span data-ttu-id="39868-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-322">Driver' Licenses#</span></span>
- <span data-ttu-id="39868-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="39868-323">Driver'sLicense#</span></span>
- <span data-ttu-id="39868-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="39868-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="39868-325">Driver's License#</span></span>
- <span data-ttu-id="39868-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="39868-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="39868-327">Número de cuenta médica de Australia</span><span class="sxs-lookup"><span data-stu-id="39868-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-328">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-328">Format</span></span>

<span data-ttu-id="39868-329">Entre 10 y 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-330">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-330">Pattern</span></span>

<span data-ttu-id="39868-331">Entre 10 y 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-331">10-11 digits:</span></span>
- <span data-ttu-id="39868-332">el primer dígito está en el intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="39868-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="39868-333">El noveno dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="39868-334">El décimo dígito es el dígito de emisión</span><span class="sxs-lookup"><span data-stu-id="39868-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="39868-335">El undécimo dígito (opcional) es el número individual</span><span class="sxs-lookup"><span data-stu-id="39868-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-336">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-336">Checksum</span></span>

<span data-ttu-id="39868-337">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-338">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-338">Definition</span></span>

<span data-ttu-id="39868-339">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-340">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-341">Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="39868-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="39868-342">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-342">The checksum passes.</span></span>

<span data-ttu-id="39868-343">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-344">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-345">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-346">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="39868-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="39868-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="39868-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="39868-348">bank account details</span></span>
- <span data-ttu-id="39868-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="39868-349">medicare payments</span></span>
- <span data-ttu-id="39868-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="39868-350">mortgage account</span></span>
- <span data-ttu-id="39868-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="39868-351">bank payments</span></span>
- <span data-ttu-id="39868-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="39868-352">information branch</span></span>
- <span data-ttu-id="39868-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="39868-353">credit card loan</span></span>
- <span data-ttu-id="39868-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="39868-354">department of human services</span></span>
- <span data-ttu-id="39868-355">servicio local</span><span class="sxs-lookup"><span data-stu-id="39868-355">local service</span></span>
- <span data-ttu-id="39868-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="39868-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="39868-357">Número de pasaporte de Australia</span><span class="sxs-lookup"><span data-stu-id="39868-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-358">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-358">Format</span></span>

<span data-ttu-id="39868-359">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-360">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-360">Pattern</span></span>

<span data-ttu-id="39868-361">Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-362">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-362">Checksum</span></span>

<span data-ttu-id="39868-363">No</span><span class="sxs-lookup"><span data-stu-id="39868-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-364">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-364">Definition</span></span>

<span data-ttu-id="39868-365">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-366">La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-367">Se ha encontrado una palabra clave de Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="39868-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-368">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="39868-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="39868-369">Keyword_passport</span></span>

- <span data-ttu-id="39868-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="39868-370">Passport Number</span></span>
- <span data-ttu-id="39868-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="39868-371">Passport No</span></span>
- <span data-ttu-id="39868-372">Passport #
</span><span class="sxs-lookup"><span data-stu-id="39868-372">Passport #</span></span>
- <span data-ttu-id="39868-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="39868-373">Passport#</span></span>
- <span data-ttu-id="39868-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="39868-374">PassportID</span></span>
- <span data-ttu-id="39868-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="39868-375">Passportno</span></span>
- <span data-ttu-id="39868-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-376">passportnumber</span></span>
- <span data-ttu-id="39868-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="39868-377">パスポート</span></span>
- <span data-ttu-id="39868-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="39868-378">パスポート番号</span></span>
- <span data-ttu-id="39868-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="39868-379">パスポートのNum</span></span>
- <span data-ttu-id="39868-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="39868-380">パスポート ＃</span></span> 
- <span data-ttu-id="39868-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="39868-381">Numéro de passeport</span></span>
- <span data-ttu-id="39868-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="39868-382">Passeport n °</span></span>
- <span data-ttu-id="39868-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="39868-383">Passeport Non</span></span>
- <span data-ttu-id="39868-384">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="39868-384">Passeport #</span></span>
- <span data-ttu-id="39868-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="39868-385">Passeport#</span></span>
- <span data-ttu-id="39868-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="39868-386">PasseportNon</span></span>
- <span data-ttu-id="39868-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="39868-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="39868-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="39868-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="39868-389">passport</span><span class="sxs-lookup"><span data-stu-id="39868-389">passport</span></span>
- <span data-ttu-id="39868-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="39868-390">passport details</span></span>
- <span data-ttu-id="39868-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="39868-391">immigration and citizenship</span></span>
- <span data-ttu-id="39868-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="39868-392">commonwealth of australia</span></span>
- <span data-ttu-id="39868-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="39868-393">department of immigration</span></span>
- <span data-ttu-id="39868-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="39868-394">residential address</span></span>
- <span data-ttu-id="39868-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="39868-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="39868-396">visa
</span><span class="sxs-lookup"><span data-stu-id="39868-396">visa</span></span>
- <span data-ttu-id="39868-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="39868-397">national identity card</span></span>
- <span data-ttu-id="39868-398">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="39868-398">passport number</span></span>
- <span data-ttu-id="39868-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="39868-399">travel document</span></span>
- <span data-ttu-id="39868-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="39868-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="39868-401">Número de archivo de impuestos de Australia</span><span class="sxs-lookup"><span data-stu-id="39868-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-402">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-402">Format</span></span>

<span data-ttu-id="39868-403">Entre 8 y 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-404">Pattern</span></span>

<span data-ttu-id="39868-405">8-9 dígitos que normalmente se presentan con espacios como sigue:</span><span class="sxs-lookup"><span data-stu-id="39868-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="39868-406">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-406">Three digits</span></span> 
- <span data-ttu-id="39868-407">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="39868-407">An optional space</span></span> 
- <span data-ttu-id="39868-408">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-408">Three digits</span></span> 
- <span data-ttu-id="39868-409">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="39868-409">An optional space</span></span> 
- <span data-ttu-id="39868-410">2-3 dígitos donde el último dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-411">Checksum</span></span>

<span data-ttu-id="39868-412">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-413">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-413">Definition</span></span>

<span data-ttu-id="39868-414">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-415">La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-416">No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="39868-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="39868-417">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-418">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="39868-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="39868-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="39868-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="39868-420">australian business number</span></span>
- <span data-ttu-id="39868-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="39868-421">marginal tax rate</span></span>
- <span data-ttu-id="39868-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="39868-422">medicare levy</span></span>
- <span data-ttu-id="39868-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="39868-423">portfolio number</span></span>
- <span data-ttu-id="39868-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="39868-424">service veterans</span></span>
- <span data-ttu-id="39868-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="39868-425">withholding tax</span></span>
- <span data-ttu-id="39868-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="39868-426">individual tax return</span></span>
- <span data-ttu-id="39868-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="39868-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="39868-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="39868-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="39868-429">00000000</span><span class="sxs-lookup"><span data-stu-id="39868-429">00000000</span></span>
- <span data-ttu-id="39868-430">11111111</span><span class="sxs-lookup"><span data-stu-id="39868-430">11111111</span></span>
- <span data-ttu-id="39868-431">por 22222222</span><span class="sxs-lookup"><span data-stu-id="39868-431">22222222</span></span>
- <span data-ttu-id="39868-432">33333333</span><span class="sxs-lookup"><span data-stu-id="39868-432">33333333</span></span>
- <span data-ttu-id="39868-433">44444444</span><span class="sxs-lookup"><span data-stu-id="39868-433">44444444</span></span>
- <span data-ttu-id="39868-434">55555555</span><span class="sxs-lookup"><span data-stu-id="39868-434">55555555</span></span>
- <span data-ttu-id="39868-435">66666666</span><span class="sxs-lookup"><span data-stu-id="39868-435">66666666</span></span>
- <span data-ttu-id="39868-436">77777777</span><span class="sxs-lookup"><span data-stu-id="39868-436">77777777</span></span>
- <span data-ttu-id="39868-437">88888888</span><span class="sxs-lookup"><span data-stu-id="39868-437">88888888</span></span>
- <span data-ttu-id="39868-438">99999999</span><span class="sxs-lookup"><span data-stu-id="39868-438">99999999</span></span>
- <span data-ttu-id="39868-439">000000000</span><span class="sxs-lookup"><span data-stu-id="39868-439">000000000</span></span>
- <span data-ttu-id="39868-440">111111111</span><span class="sxs-lookup"><span data-stu-id="39868-440">111111111</span></span>
- <span data-ttu-id="39868-441">222222222</span><span class="sxs-lookup"><span data-stu-id="39868-441">222222222</span></span>
- <span data-ttu-id="39868-442">333333333</span><span class="sxs-lookup"><span data-stu-id="39868-442">333333333</span></span>
- <span data-ttu-id="39868-443">444444444</span><span class="sxs-lookup"><span data-stu-id="39868-443">444444444</span></span>
- <span data-ttu-id="39868-444">555555555</span><span class="sxs-lookup"><span data-stu-id="39868-444">555555555</span></span>
- <span data-ttu-id="39868-445">666666666</span><span class="sxs-lookup"><span data-stu-id="39868-445">666666666</span></span>
- <span data-ttu-id="39868-446">777777777</span><span class="sxs-lookup"><span data-stu-id="39868-446">777777777</span></span>
- <span data-ttu-id="39868-447">888888888</span><span class="sxs-lookup"><span data-stu-id="39868-447">888888888</span></span>
- <span data-ttu-id="39868-448">999999999</span><span class="sxs-lookup"><span data-stu-id="39868-448">999999999</span></span>
- <span data-ttu-id="39868-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="39868-449">0000000000</span></span>
- <span data-ttu-id="39868-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="39868-450">1111111111</span></span>
- <span data-ttu-id="39868-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="39868-451">2222222222</span></span>
- <span data-ttu-id="39868-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="39868-452">3333333333</span></span>
- <span data-ttu-id="39868-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="39868-453">4444444444</span></span>
- <span data-ttu-id="39868-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="39868-454">5555555555</span></span>
- <span data-ttu-id="39868-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="39868-455">6666666666</span></span>
- <span data-ttu-id="39868-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="39868-456">7777777777</span></span>
- <span data-ttu-id="39868-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="39868-457">8888888888</span></span>
- <span data-ttu-id="39868-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="39868-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="39868-459">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="39868-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-460">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-460">Format</span></span>

<span data-ttu-id="39868-461">11 dígitos más delimitadores</span><span class="sxs-lookup"><span data-stu-id="39868-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-462">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-462">Pattern</span></span>

<span data-ttu-id="39868-463">11 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="39868-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="39868-464">Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="39868-465">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-465">A hyphen</span></span> 
- <span data-ttu-id="39868-466">Tres dígitos secuenciales (impares para hombres, pares para mujeres) </span><span class="sxs-lookup"><span data-stu-id="39868-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="39868-467">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-467">A period</span></span> 
- <span data-ttu-id="39868-468">Dos dígitos que son un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-469">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-469">Checksum</span></span>

<span data-ttu-id="39868-470">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-471">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-471">Definition</span></span>

<span data-ttu-id="39868-472">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-473">La función Func_belgium_national_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-474">Se encuentra una palabra clave de Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="39868-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="39868-475">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-476">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="39868-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="39868-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="39868-478">Identidad</span><span class="sxs-lookup"><span data-stu-id="39868-478">Identity</span></span>
- <span data-ttu-id="39868-479">Registration</span><span class="sxs-lookup"><span data-stu-id="39868-479">Registration</span></span>
- <span data-ttu-id="39868-480">Identificación</span><span class="sxs-lookup"><span data-stu-id="39868-480">Identification</span></span> 
- <span data-ttu-id="39868-481">ID</span><span class="sxs-lookup"><span data-stu-id="39868-481">ID</span></span> 
- <span data-ttu-id="39868-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="39868-482">Identiteitskaart</span></span>
- <span data-ttu-id="39868-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="39868-483">Registratie nummer</span></span> 
- <span data-ttu-id="39868-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="39868-484">Identificatie nummer</span></span> 
- <span data-ttu-id="39868-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="39868-485">Identiteit</span></span>
- <span data-ttu-id="39868-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="39868-486">Registratie</span></span>
- <span data-ttu-id="39868-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="39868-487">Identificatie</span></span> 
- <span data-ttu-id="39868-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="39868-488">Carte d’identité</span></span> 
- <span data-ttu-id="39868-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="39868-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="39868-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="39868-490">numéro d'identification</span></span>
- <span data-ttu-id="39868-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="39868-491">identité</span></span> 
- <span data-ttu-id="39868-492">inscription
</span><span class="sxs-lookup"><span data-stu-id="39868-492">inscription</span></span> 
- <span data-ttu-id="39868-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="39868-493">Identifikation</span></span>
- <span data-ttu-id="39868-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="39868-494">Identifizierung</span></span>
- <span data-ttu-id="39868-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="39868-495">Identifikationsnummer</span></span>
- <span data-ttu-id="39868-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="39868-496">Personalausweis</span></span>
- <span data-ttu-id="39868-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="39868-497">Registrierung</span></span>
- <span data-ttu-id="39868-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="39868-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="39868-499">Número CPF de Brasil</span><span class="sxs-lookup"><span data-stu-id="39868-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-500">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-500">Format</span></span>

<span data-ttu-id="39868-501">11 dígitos incluido un dígito de control y que pueden tener o no formato</span><span class="sxs-lookup"><span data-stu-id="39868-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-502">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-502">Pattern</span></span>

<span data-ttu-id="39868-503">Con formato:</span><span class="sxs-lookup"><span data-stu-id="39868-503">Formatted:</span></span>
- <span data-ttu-id="39868-504">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-504">Three digits</span></span> 
- <span data-ttu-id="39868-505">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-505">A period</span></span> 
- <span data-ttu-id="39868-506">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-506">Three digits</span></span> 
- <span data-ttu-id="39868-507">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-507">A period</span></span> 
- <span data-ttu-id="39868-508">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-508">Three digits</span></span> 
- <span data-ttu-id="39868-509">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-509">A hyphen</span></span> 
- <span data-ttu-id="39868-510">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="39868-510">Two digits which are check digits</span></span>

<span data-ttu-id="39868-511">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="39868-511">Unformatted:</span></span>
- <span data-ttu-id="39868-512">11 dígitos, donde los dos últimos dígitos son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="39868-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-513">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-513">Checksum</span></span>

<span data-ttu-id="39868-514">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-515">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-515">Definition</span></span>

<span data-ttu-id="39868-516">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-517">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-518">Se encuentra una palabra clave de Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="39868-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="39868-519">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-519">The checksum passes.</span></span>

<span data-ttu-id="39868-520">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-521">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-522">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-523">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="39868-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="39868-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="39868-525">CPF</span><span class="sxs-lookup"><span data-stu-id="39868-525">CPF</span></span>
- <span data-ttu-id="39868-526">Identificación</span><span class="sxs-lookup"><span data-stu-id="39868-526">Identification</span></span>
- <span data-ttu-id="39868-527">Registro</span><span class="sxs-lookup"><span data-stu-id="39868-527">Registration</span></span>
- <span data-ttu-id="39868-528">Ingresos</span><span class="sxs-lookup"><span data-stu-id="39868-528">Revenue</span></span>
- <span data-ttu-id="39868-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="39868-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="39868-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="39868-530">Imposto</span></span> 
- <span data-ttu-id="39868-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="39868-531">Identificação</span></span> 
- <span data-ttu-id="39868-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="39868-532">Inscrição</span></span> 
- <span data-ttu-id="39868-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="39868-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="39868-534">Número de entidad jurídica de Brasil (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="39868-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="39868-535">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-535">Format</span></span>

<span data-ttu-id="39868-536">14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores</span><span class="sxs-lookup"><span data-stu-id="39868-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-537">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-537">Pattern</span></span>
<span data-ttu-id="39868-538">14 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="39868-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="39868-539">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-539">Two digits</span></span> 
- <span data-ttu-id="39868-540">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-540">A period</span></span> 
- <span data-ttu-id="39868-541">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-541">Three digits</span></span> 
- <span data-ttu-id="39868-542">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-542">A period</span></span> 
- <span data-ttu-id="39868-543">Tres dígitos (estos ocho primeros dígitos son el número de registro) </span><span class="sxs-lookup"><span data-stu-id="39868-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="39868-544">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="39868-544">A forward slash</span></span> 
- <span data-ttu-id="39868-545">Número de sucursal de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-545">Four-digit branch number</span></span> 
- <span data-ttu-id="39868-546">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-546">A hyphen</span></span> 
- <span data-ttu-id="39868-547">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="39868-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-548">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-548">Checksum</span></span>

<span data-ttu-id="39868-549">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-550">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-550">Definition</span></span>

<span data-ttu-id="39868-551">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-552">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-553">Se encuentra una palabra clave de Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="39868-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="39868-554">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-554">The checksum passes.</span></span>

<span data-ttu-id="39868-555">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-556">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-557">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-558">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="39868-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="39868-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="39868-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="39868-560">CNPJ</span></span> 
- <span data-ttu-id="39868-561">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="39868-561">CNPJ/MF</span></span> 
- <span data-ttu-id="39868-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="39868-562">CNPJ-MF</span></span> 
- <span data-ttu-id="39868-563">Registro nacional de entidades jurídicas
</span><span class="sxs-lookup"><span data-stu-id="39868-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="39868-564">Registro de contribuyentes
</span><span class="sxs-lookup"><span data-stu-id="39868-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="39868-565">Entidad jurídica
</span><span class="sxs-lookup"><span data-stu-id="39868-565">Legal entity</span></span> 
- <span data-ttu-id="39868-566">Entidades jurídicas
</span><span class="sxs-lookup"><span data-stu-id="39868-566">Legal entities</span></span> 
- <span data-ttu-id="39868-567">Estado de registro
</span><span class="sxs-lookup"><span data-stu-id="39868-567">Registration Status</span></span> 
- <span data-ttu-id="39868-568">Negocio
</span><span class="sxs-lookup"><span data-stu-id="39868-568">Business</span></span> 
- <span data-ttu-id="39868-569">Company</span><span class="sxs-lookup"><span data-stu-id="39868-569">Company</span></span>
- <span data-ttu-id="39868-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="39868-570">CNPJ</span></span> 
- <span data-ttu-id="39868-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="39868-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="39868-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="39868-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="39868-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="39868-573">CGC</span></span> 
- <span data-ttu-id="39868-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="39868-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="39868-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="39868-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="39868-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="39868-576">Situação cadastral</span></span> 
- <span data-ttu-id="39868-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="39868-577">Inscrição</span></span> 
- <span data-ttu-id="39868-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="39868-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="39868-579">Tarjeta de identificación nacional de Brasil (RG)</span><span class="sxs-lookup"><span data-stu-id="39868-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="39868-580">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-580">Format</span></span>

<span data-ttu-id="39868-581">Registro Geral (formato anterior): nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="39868-582">Registro de Identidade (RIC) (nuevo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-583">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-583">Pattern</span></span>

<span data-ttu-id="39868-584">Registro de Geral (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="39868-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="39868-585">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-585">Two digits</span></span> 
- <span data-ttu-id="39868-586">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-586">A period</span></span> 
- <span data-ttu-id="39868-587">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-587">Three digits</span></span> 
- <span data-ttu-id="39868-588">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-588">A period</span></span> 
- <span data-ttu-id="39868-589">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-589">Three digits</span></span> 
- <span data-ttu-id="39868-590">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-590">A hyphen</span></span> 
- <span data-ttu-id="39868-591">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-591">One digit which is a check digit</span></span>

<span data-ttu-id="39868-592">Registro de Identidade (RIC) (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="39868-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="39868-593">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-593">10 digits</span></span> 
- <span data-ttu-id="39868-594">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-594">A hyphen</span></span> 
- <span data-ttu-id="39868-595">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-596">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-596">Checksum</span></span>

<span data-ttu-id="39868-597">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-598">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-598">Definition</span></span>

<span data-ttu-id="39868-599">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-600">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-601">Se encuentra una palabra clave de Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="39868-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="39868-602">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-602">The checksum passes.</span></span>

<span data-ttu-id="39868-603">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-604">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-605">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-606">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="39868-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="39868-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="39868-608">Cédula de identidade tarjeta de identidad nacional identificador número de rregistro registro de Iidentidade registro geral RG (esta palabra clave distingue mayúsculas de minúsculas) RIC (esta palabra clave distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="39868-609">Número de cuenta bancaria de Canadá</span><span class="sxs-lookup"><span data-stu-id="39868-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-610">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-610">Format</span></span>

<span data-ttu-id="39868-611">Siete o doce dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-612">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-612">Pattern</span></span>

<span data-ttu-id="39868-613">El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.</span><span class="sxs-lookup"><span data-stu-id="39868-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="39868-614">Un número de tránsito de cuenta bancaria de Canadá es:</span><span class="sxs-lookup"><span data-stu-id="39868-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="39868-615">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-615">Five digits</span></span> 
- <span data-ttu-id="39868-616">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-616">A hyphen</span></span> 
- <span data-ttu-id="39868-617">Tres dígitos o</span><span class="sxs-lookup"><span data-stu-id="39868-617">Three digits OR</span></span>
- <span data-ttu-id="39868-618">Un cero "0" </span><span class="sxs-lookup"><span data-stu-id="39868-618">A zero "0"</span></span> 
- <span data-ttu-id="39868-619">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-620">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-620">Checksum</span></span>

<span data-ttu-id="39868-621">No</span><span class="sxs-lookup"><span data-stu-id="39868-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-622">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-622">Definition</span></span>

<span data-ttu-id="39868-623">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-624">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-625">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="39868-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="39868-626">La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="39868-627">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-628">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-629">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="39868-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-630">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="39868-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="39868-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="39868-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="39868-632">canada savings bonds</span></span>
- <span data-ttu-id="39868-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="39868-633">canada revenue agency</span></span>
- <span data-ttu-id="39868-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="39868-634">canadian financial institution</span></span>
- <span data-ttu-id="39868-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="39868-635">direct deposit form</span></span>
- <span data-ttu-id="39868-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="39868-636">canadian citizen</span></span>
- <span data-ttu-id="39868-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="39868-637">legal representative</span></span>
- <span data-ttu-id="39868-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="39868-638">notary public</span></span>
- <span data-ttu-id="39868-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="39868-639">commissioner for oaths</span></span>
- <span data-ttu-id="39868-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="39868-640">child care benefit</span></span>
- <span data-ttu-id="39868-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="39868-641">universal child care</span></span>
- <span data-ttu-id="39868-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="39868-642">canada child tax benefit</span></span>
- <span data-ttu-id="39868-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="39868-643">income tax benefit</span></span>
- <span data-ttu-id="39868-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="39868-644">harmonized sales tax</span></span>
- <span data-ttu-id="39868-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="39868-645">social insurance number</span></span>
- <span data-ttu-id="39868-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="39868-646">income tax refund</span></span>
- <span data-ttu-id="39868-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="39868-647">child tax benefit</span></span>
- <span data-ttu-id="39868-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="39868-648">territorial payments</span></span>
- <span data-ttu-id="39868-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="39868-649">institution number</span></span>
- <span data-ttu-id="39868-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="39868-650">deposit request</span></span>
- <span data-ttu-id="39868-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="39868-651">banking information</span></span>
- <span data-ttu-id="39868-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="39868-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="39868-653">Número de licencia de conductor de Canadá</span><span class="sxs-lookup"><span data-stu-id="39868-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-654">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-654">Format</span></span>

<span data-ttu-id="39868-655">Varía según la provincia</span><span class="sxs-lookup"><span data-stu-id="39868-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-656">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-656">Pattern</span></span>

<span data-ttu-id="39868-657">Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="39868-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-658">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-658">Checksum</span></span>

<span data-ttu-id="39868-659">No</span><span class="sxs-lookup"><span data-stu-id="39868-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-660">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-660">Definition</span></span>

<span data-ttu-id="39868-661">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-662">La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-663">Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="39868-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="39868-664">Se encuentra una palabra clave de Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="39868-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-665">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="39868-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="39868-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="39868-667">La abreviatura de la provincia, por ejemplo, AB</span><span class="sxs-lookup"><span data-stu-id="39868-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="39868-668">
El nombre de la provincia, por ejemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="39868-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="39868-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="39868-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="39868-670">DL</span><span class="sxs-lookup"><span data-stu-id="39868-670">DL</span></span>
- <span data-ttu-id="39868-671">DLS</span><span class="sxs-lookup"><span data-stu-id="39868-671">DLS</span></span>
- <span data-ttu-id="39868-672">CDL</span><span class="sxs-lookup"><span data-stu-id="39868-672">CDL</span></span>
- <span data-ttu-id="39868-673">CDLS</span><span class="sxs-lookup"><span data-stu-id="39868-673">CDLS</span></span>
- <span data-ttu-id="39868-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="39868-674">DriverLic</span></span>
- <span data-ttu-id="39868-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="39868-675">DriverLics</span></span>
- <span data-ttu-id="39868-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="39868-676">DriverLicense</span></span>
- <span data-ttu-id="39868-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-677">DriverLicenses</span></span>
- <span data-ttu-id="39868-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="39868-678">DriverLicence</span></span>
- <span data-ttu-id="39868-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="39868-679">DriverLicences</span></span>
- <span data-ttu-id="39868-680">Lic de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-680">Driver Lic</span></span>
- <span data-ttu-id="39868-681">LIC de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-681">Driver Lics</span></span>
- <span data-ttu-id="39868-682">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-682">Driver License</span></span>
- <span data-ttu-id="39868-683">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-683">Driver Licenses</span></span>
- <span data-ttu-id="39868-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="39868-684">Driver Licence</span></span>
- <span data-ttu-id="39868-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="39868-685">Driver Licences</span></span>
- <span data-ttu-id="39868-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="39868-686">DriversLic</span></span>
- <span data-ttu-id="39868-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="39868-687">DriversLics</span></span>
- <span data-ttu-id="39868-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="39868-688">DriversLicence</span></span>
- <span data-ttu-id="39868-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="39868-689">DriversLicences</span></span>
- <span data-ttu-id="39868-690">PermisoDeConducción</span><span class="sxs-lookup"><span data-stu-id="39868-690">DriversLicense</span></span>
- <span data-ttu-id="39868-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-691">DriversLicenses</span></span>
- <span data-ttu-id="39868-692">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-692">Drivers Lic</span></span>
- <span data-ttu-id="39868-693">LIC de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-693">Drivers Lics</span></span>
- <span data-ttu-id="39868-694">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-694">Drivers License</span></span>
- <span data-ttu-id="39868-695">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-695">Drivers Licenses</span></span>
- <span data-ttu-id="39868-696">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-696">Drivers Licence</span></span>
- <span data-ttu-id="39868-697">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-697">Drivers Licences</span></span>
- <span data-ttu-id="39868-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="39868-698">Driver'Lic</span></span>
- <span data-ttu-id="39868-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="39868-699">Driver'Lics</span></span>
- <span data-ttu-id="39868-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="39868-700">Driver'License</span></span>
- <span data-ttu-id="39868-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="39868-701">Driver'Licenses</span></span>
- <span data-ttu-id="39868-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="39868-702">Driver'Licence</span></span>
- <span data-ttu-id="39868-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="39868-703">Driver'Licences</span></span>
- <span data-ttu-id="39868-704">Controlador ' Lic</span><span class="sxs-lookup"><span data-stu-id="39868-704">Driver' Lic</span></span>
- <span data-ttu-id="39868-705">Controlador ' LIC</span><span class="sxs-lookup"><span data-stu-id="39868-705">Driver' Lics</span></span>
- <span data-ttu-id="39868-706">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="39868-706">Driver' License</span></span>
- <span data-ttu-id="39868-707">Controlador ' licencias</span><span class="sxs-lookup"><span data-stu-id="39868-707">Driver' Licenses</span></span>
- <span data-ttu-id="39868-708">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="39868-708">Driver' Licence</span></span>
- <span data-ttu-id="39868-709">Controlador ' certificados</span><span class="sxs-lookup"><span data-stu-id="39868-709">Driver' Licences</span></span>
- <span data-ttu-id="39868-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="39868-710">Driver'sLic</span></span>
- <span data-ttu-id="39868-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="39868-711">Driver'sLics</span></span>
- <span data-ttu-id="39868-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="39868-712">Driver'sLicense</span></span>
- <span data-ttu-id="39868-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-713">Driver'sLicenses</span></span>
- <span data-ttu-id="39868-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="39868-714">Driver'sLicence</span></span>
- <span data-ttu-id="39868-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="39868-715">Driver'sLicences</span></span>
- <span data-ttu-id="39868-716">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-716">Driver's Lic</span></span>
- <span data-ttu-id="39868-717">LIC del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-717">Driver's Lics</span></span>
- <span data-ttu-id="39868-718">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="39868-718">Driver's License</span></span>
- <span data-ttu-id="39868-719">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-719">Driver's Licenses</span></span>
- <span data-ttu-id="39868-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="39868-720">Driver's Licence</span></span>
- <span data-ttu-id="39868-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="39868-721">Driver's Licences</span></span>
- <span data-ttu-id="39868-722">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="39868-722">Permis de Conduire</span></span>
- <span data-ttu-id="39868-723">id</span><span class="sxs-lookup"><span data-stu-id="39868-723">id</span></span>
- <span data-ttu-id="39868-724">identificadores de</span><span class="sxs-lookup"><span data-stu-id="39868-724">ids</span></span>
- <span data-ttu-id="39868-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="39868-725">idcard number</span></span>
- <span data-ttu-id="39868-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="39868-726">idcard numbers</span></span>
- <span data-ttu-id="39868-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="39868-727">idcard #</span></span>
- <span data-ttu-id="39868-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="39868-728">idcard #s</span></span>
- <span data-ttu-id="39868-729">tarjeta de idcard</span><span class="sxs-lookup"><span data-stu-id="39868-729">idcard card</span></span>
- <span data-ttu-id="39868-730">tarjetas de idcard</span><span class="sxs-lookup"><span data-stu-id="39868-730">idcard cards</span></span>
- <span data-ttu-id="39868-731">idcard</span><span class="sxs-lookup"><span data-stu-id="39868-731">idcard</span></span>
- <span data-ttu-id="39868-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="39868-732">identification number</span></span>
- <span data-ttu-id="39868-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="39868-733">identification numbers</span></span>
- <span data-ttu-id="39868-734">identification #
</span><span class="sxs-lookup"><span data-stu-id="39868-734">identification #</span></span>
- <span data-ttu-id="39868-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="39868-735">identification #s</span></span>
- <span data-ttu-id="39868-736">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-736">identification card</span></span>
- <span data-ttu-id="39868-737">tarjetas de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-737">identification cards</span></span>
- <span data-ttu-id="39868-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="39868-738">identification</span></span> 
- <span data-ttu-id="39868-739">DL#</span><span class="sxs-lookup"><span data-stu-id="39868-739">DL#</span></span>
- <span data-ttu-id="39868-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="39868-740">DLS#</span></span> 
- <span data-ttu-id="39868-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="39868-741">CDL#</span></span> 
- <span data-ttu-id="39868-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="39868-742">CDLS#</span></span> 
- <span data-ttu-id="39868-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="39868-743">DriverLic#</span></span> 
- <span data-ttu-id="39868-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="39868-744">DriverLics#</span></span> 
- <span data-ttu-id="39868-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="39868-745">DriverLicense#</span></span> 
- <span data-ttu-id="39868-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-746">DriverLicenses#</span></span> 
- <span data-ttu-id="39868-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="39868-747">DriverLicence#</span></span> 
- <span data-ttu-id="39868-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="39868-748">DriverLicences#</span></span> 
- <span data-ttu-id="39868-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="39868-749">Driver Lic#</span></span>
- <span data-ttu-id="39868-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-750">Driver Lics#</span></span> 
- <span data-ttu-id="39868-751">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="39868-751">Driver License#</span></span> 
- <span data-ttu-id="39868-752">Controlador licencias #</span><span class="sxs-lookup"><span data-stu-id="39868-752">Driver Licenses#</span></span> 
- <span data-ttu-id="39868-753">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="39868-753">Driver License#</span></span> 
- <span data-ttu-id="39868-754">Controlador certificados #</span><span class="sxs-lookup"><span data-stu-id="39868-754">Driver Licences#</span></span> 
- <span data-ttu-id="39868-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="39868-755">DriversLic#</span></span> 
- <span data-ttu-id="39868-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="39868-756">DriversLics#</span></span> 
- <span data-ttu-id="39868-757">PermisoDeConducción #</span><span class="sxs-lookup"><span data-stu-id="39868-757">DriversLicense#</span></span> 
- <span data-ttu-id="39868-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-758">DriversLicenses#</span></span> 
- <span data-ttu-id="39868-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="39868-759">DriversLicence#</span></span> 
- <span data-ttu-id="39868-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="39868-760">DriversLicences#</span></span> 
- <span data-ttu-id="39868-761">Controladores Lic #</span><span class="sxs-lookup"><span data-stu-id="39868-761">Drivers Lic#</span></span> 
- <span data-ttu-id="39868-762">Controladores LIC #</span><span class="sxs-lookup"><span data-stu-id="39868-762">Drivers Lics#</span></span> 
- <span data-ttu-id="39868-763">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-763">Drivers License#</span></span> 
- <span data-ttu-id="39868-764">Licencias de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="39868-765">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-765">Drivers Licence#</span></span> 
- <span data-ttu-id="39868-766">Controladores certificados #</span><span class="sxs-lookup"><span data-stu-id="39868-766">Drivers Licences#</span></span> 
- <span data-ttu-id="39868-767">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-767">Driver'Lic#</span></span> 
- <span data-ttu-id="39868-768">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-768">Driver'Lics#</span></span> 
- <span data-ttu-id="39868-769">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="39868-769">Driver'License#</span></span> 
- <span data-ttu-id="39868-770">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="39868-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="39868-771">Driver'Licence#</span></span> 
- <span data-ttu-id="39868-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="39868-772">Driver'Licences#</span></span> 
- <span data-ttu-id="39868-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-773">Driver' Lic#</span></span> 
- <span data-ttu-id="39868-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-774">Driver' Lics#</span></span> 
- <span data-ttu-id="39868-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="39868-775">Driver' License#</span></span> 
- <span data-ttu-id="39868-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="39868-777">Controlador ' certificado #</span><span class="sxs-lookup"><span data-stu-id="39868-777">Driver' Licence#</span></span> 
- <span data-ttu-id="39868-778">Controlador ' certificados #</span><span class="sxs-lookup"><span data-stu-id="39868-778">Driver' Licences#</span></span> 
- <span data-ttu-id="39868-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="39868-779">Driver'sLic#</span></span> 
- <span data-ttu-id="39868-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="39868-780">Driver'sLics#</span></span> 
- <span data-ttu-id="39868-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="39868-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="39868-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="39868-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="39868-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="39868-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="39868-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="39868-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-785">Driver's Lic#</span></span> 
- <span data-ttu-id="39868-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-786">Driver's Lics#</span></span> 
- <span data-ttu-id="39868-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="39868-787">Driver's License#</span></span> 
- <span data-ttu-id="39868-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="39868-789">Certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-789">Driver's Licence#</span></span> 
- <span data-ttu-id="39868-790">El certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-790">Driver's Licences#</span></span> 
- <span data-ttu-id="39868-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="39868-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="39868-792">identificador de #</span><span class="sxs-lookup"><span data-stu-id="39868-792">id#</span></span> 
- <span data-ttu-id="39868-793">los identificadores de #</span><span class="sxs-lookup"><span data-stu-id="39868-793">ids#</span></span> 
- <span data-ttu-id="39868-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="39868-794">idcard card#</span></span> 
- <span data-ttu-id="39868-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="39868-795">idcard cards#</span></span> 
- <span data-ttu-id="39868-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="39868-796">idcard#</span></span> 
- <span data-ttu-id="39868-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="39868-797">identification card#</span></span> 
- <span data-ttu-id="39868-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="39868-798">identification cards#</span></span> 
- <span data-ttu-id="39868-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="39868-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="39868-800">Número de servicio de salud de Canadá</span><span class="sxs-lookup"><span data-stu-id="39868-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-801">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-801">Format</span></span>

<span data-ttu-id="39868-802">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-803">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-803">Pattern</span></span>

<span data-ttu-id="39868-804">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-805">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-805">Checksum</span></span>

<span data-ttu-id="39868-806">No</span><span class="sxs-lookup"><span data-stu-id="39868-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-807">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-807">Definition</span></span>

<span data-ttu-id="39868-808">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-809">La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-810">Se encuentra una palabra clave de Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="39868-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-811">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="39868-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="39868-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="39868-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="39868-813">personal health number</span></span>
- <span data-ttu-id="39868-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="39868-814">patient information</span></span>
- <span data-ttu-id="39868-815">Servicios de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="39868-815">health services</span></span>
- <span data-ttu-id="39868-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="39868-816">speciality services</span></span>
- <span data-ttu-id="39868-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="39868-817">automobile accident</span></span>
- <span data-ttu-id="39868-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="39868-818">patient hospital</span></span>
- <span data-ttu-id="39868-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="39868-819">psychiatrist</span></span>
- <span data-ttu-id="39868-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="39868-820">workers compensation</span></span>
- <span data-ttu-id="39868-821">
disability</span><span class="sxs-lookup"><span data-stu-id="39868-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="39868-822">Número de pasaporte de Canadá</span><span class="sxs-lookup"><span data-stu-id="39868-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-823">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-823">Format</span></span>

<span data-ttu-id="39868-824">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-825">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-825">Pattern</span></span>

<span data-ttu-id="39868-826">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-827">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-827">Checksum</span></span>

<span data-ttu-id="39868-828">No</span><span class="sxs-lookup"><span data-stu-id="39868-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-829">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-829">Definition</span></span>

<span data-ttu-id="39868-830">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-831">La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-832">Se ha encontrado una palabra clave de Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="39868-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-833">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="39868-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="39868-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="39868-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="39868-835">canadian citizenship</span></span>
- <span data-ttu-id="39868-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="39868-836">canadian passport</span></span>
- <span data-ttu-id="39868-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="39868-837">passport application</span></span>
- <span data-ttu-id="39868-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="39868-838">passport photos</span></span>
- <span data-ttu-id="39868-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="39868-839">certified translator</span></span>
- <span data-ttu-id="39868-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="39868-840">canadian citizens</span></span>
- <span data-ttu-id="39868-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="39868-841">processing times</span></span>
- <span data-ttu-id="39868-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="39868-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="39868-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="39868-843">Keyword_passport</span></span>

- <span data-ttu-id="39868-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="39868-844">Passport Number</span></span>
- <span data-ttu-id="39868-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="39868-845">Passport No</span></span>
- <span data-ttu-id="39868-846">Passport #
</span><span class="sxs-lookup"><span data-stu-id="39868-846">Passport #</span></span>
- <span data-ttu-id="39868-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="39868-847">Passport#</span></span>
- <span data-ttu-id="39868-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="39868-848">PassportID</span></span>
- <span data-ttu-id="39868-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="39868-849">Passportno</span></span>
- <span data-ttu-id="39868-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-850">passportnumber</span></span>
- <span data-ttu-id="39868-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="39868-851">パスポート</span></span>
- <span data-ttu-id="39868-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="39868-852">パスポート番号</span></span>
- <span data-ttu-id="39868-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="39868-853">パスポートのNum</span></span>
- <span data-ttu-id="39868-854">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="39868-854">パスポート＃</span></span>
- <span data-ttu-id="39868-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="39868-855">Numéro de passeport</span></span>
- <span data-ttu-id="39868-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="39868-856">Passeport n °</span></span>
- <span data-ttu-id="39868-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="39868-857">Passeport Non</span></span>
- <span data-ttu-id="39868-858">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="39868-858">Passeport #</span></span>
- <span data-ttu-id="39868-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="39868-859">Passeport#</span></span>
- <span data-ttu-id="39868-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="39868-860">PasseportNon</span></span>
- <span data-ttu-id="39868-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="39868-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="39868-862">Número de Identificación Personal de salud en Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="39868-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="39868-863">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-863">Format</span></span>

<span data-ttu-id="39868-864">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-865">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-865">Pattern</span></span>

<span data-ttu-id="39868-866">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-867">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-867">Checksum</span></span>

<span data-ttu-id="39868-868">No</span><span class="sxs-lookup"><span data-stu-id="39868-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-869">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-869">Definition</span></span>

<span data-ttu-id="39868-p104">Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la expresión regular Regex_canada_phin busca contenido que coincide con el patrón. Al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces se encuentran..</span><span class="sxs-lookup"><span data-stu-id="39868-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-872">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="39868-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="39868-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="39868-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="39868-874">social insurance number</span></span>
- <span data-ttu-id="39868-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="39868-875">health information act</span></span>
- <span data-ttu-id="39868-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="39868-876">income tax information</span></span>
- <span data-ttu-id="39868-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="39868-877">manitoba health</span></span>
- <span data-ttu-id="39868-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="39868-878">health registration</span></span>
- <span data-ttu-id="39868-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="39868-879">prescription purchases</span></span>
- <span data-ttu-id="39868-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="39868-880">benefit eligibility</span></span>
- <span data-ttu-id="39868-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="39868-881">personal health</span></span>
- <span data-ttu-id="39868-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="39868-882">power of attorney</span></span>
- <span data-ttu-id="39868-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="39868-883">registration number</span></span>
- <span data-ttu-id="39868-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="39868-884">personal health number</span></span>
- <span data-ttu-id="39868-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="39868-885">practitioner referral</span></span>
- <span data-ttu-id="39868-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="39868-886">wellness professional</span></span>
- <span data-ttu-id="39868-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="39868-887">patient referral</span></span>
- <span data-ttu-id="39868-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="39868-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="39868-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="39868-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="39868-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="39868-890">Nunavut</span></span>
- <span data-ttu-id="39868-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="39868-891">Quebec</span></span>
- <span data-ttu-id="39868-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="39868-892">Northwest Territories</span></span>
- <span data-ttu-id="39868-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="39868-893">Ontario</span></span>
- <span data-ttu-id="39868-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="39868-894">British Columbia</span></span>
- <span data-ttu-id="39868-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="39868-895">Alberta</span></span>
- <span data-ttu-id="39868-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="39868-896">Saskatchewan</span></span>
- <span data-ttu-id="39868-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="39868-897">Manitoba</span></span>
- <span data-ttu-id="39868-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="39868-898">Yukon</span></span>
- <span data-ttu-id="39868-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="39868-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="39868-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="39868-900">New Brunswick</span></span>
- <span data-ttu-id="39868-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="39868-901">Nova Scotia</span></span>
- <span data-ttu-id="39868-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="39868-902">Prince Edward Island</span></span>
- <span data-ttu-id="39868-903">Canadá</span><span class="sxs-lookup"><span data-stu-id="39868-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="39868-904">Número de seguridad social de Canadá</span><span class="sxs-lookup"><span data-stu-id="39868-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-905">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-905">Format</span></span>

<span data-ttu-id="39868-906">Nueve dígitos con guiones opcionales o espacios</span><span class="sxs-lookup"><span data-stu-id="39868-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-907">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-907">Pattern</span></span>

<span data-ttu-id="39868-908">Con formato:</span><span class="sxs-lookup"><span data-stu-id="39868-908">Formatted:</span></span>
- <span data-ttu-id="39868-909">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-909">Three digits</span></span> 
- <span data-ttu-id="39868-910">Un guión o un espacio </span><span class="sxs-lookup"><span data-stu-id="39868-910">A hyphen or space</span></span> 
- <span data-ttu-id="39868-911">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-911">Three digits</span></span> 
- <span data-ttu-id="39868-912">Un guión o un espacio </span><span class="sxs-lookup"><span data-stu-id="39868-912">A hyphen or space</span></span> 
- <span data-ttu-id="39868-913">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-913">Three digits</span></span>

<span data-ttu-id="39868-914">Sin formato: Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-915">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-915">Checksum</span></span>

<span data-ttu-id="39868-916">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-917">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-917">Definition</span></span>

<span data-ttu-id="39868-918">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-919">La función Func_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-920">Al menos dos de cualquier combinación de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39868-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="39868-921">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="39868-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="39868-922">Se encuentra una palabra clave de Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="39868-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="39868-923">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="39868-924">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-924">The checksum passes.</span></span>

<span data-ttu-id="39868-925">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-926">La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-927">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="39868-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="39868-928">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-929">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="39868-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="39868-930">Keyword_sin</span></span>

- <span data-ttu-id="39868-931">seno</span><span class="sxs-lookup"><span data-stu-id="39868-931">sin</span></span> 
- <span data-ttu-id="39868-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="39868-932">social insurance</span></span> 
- <span data-ttu-id="39868-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="39868-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="39868-934">sins
</span><span class="sxs-lookup"><span data-stu-id="39868-934">sins</span></span> 
- <span data-ttu-id="39868-935">ssn</span><span class="sxs-lookup"><span data-stu-id="39868-935">ssn</span></span> 
- <span data-ttu-id="39868-936">números de seguridad social</span><span class="sxs-lookup"><span data-stu-id="39868-936">ssns</span></span> 
- <span data-ttu-id="39868-937">seguridad social</span><span class="sxs-lookup"><span data-stu-id="39868-937">social security</span></span> 
- <span data-ttu-id="39868-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="39868-938">numero d'assurance social</span></span> 
- <span data-ttu-id="39868-939">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="39868-939">national identification number</span></span> 
- <span data-ttu-id="39868-940">
national id</span><span class="sxs-lookup"><span data-stu-id="39868-940">national id</span></span> 
- <span data-ttu-id="39868-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="39868-941">sin#</span></span> 
- <span data-ttu-id="39868-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="39868-942">soc ins</span></span> 
- <span data-ttu-id="39868-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="39868-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="39868-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="39868-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="39868-945">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="39868-945">driver's license</span></span> 
- <span data-ttu-id="39868-946">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-946">drivers license</span></span> 
- <span data-ttu-id="39868-947">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-947">driver's licence</span></span> 
- <span data-ttu-id="39868-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39868-948">drivers licence</span></span> 
- <span data-ttu-id="39868-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="39868-949">DOB</span></span> 
- <span data-ttu-id="39868-950">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="39868-950">Birthdate</span></span> 
- <span data-ttu-id="39868-951">Cumpleaños </span><span class="sxs-lookup"><span data-stu-id="39868-951">Birthday</span></span> 
- <span data-ttu-id="39868-952">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="39868-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="39868-953">Número de tarjeta de identidad de Chile</span><span class="sxs-lookup"><span data-stu-id="39868-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-954">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-954">Format</span></span>

<span data-ttu-id="39868-955">7-8 dígitos y delimitadores un dígito de control o una letra</span><span class="sxs-lookup"><span data-stu-id="39868-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-956">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-956">Pattern</span></span>

<span data-ttu-id="39868-957">7 u 8 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="39868-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="39868-958">1 o 2 dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-958">1-2 digits</span></span> 
- <span data-ttu-id="39868-959">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-959">A period</span></span> 
- <span data-ttu-id="39868-960">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-960">Three digits</span></span> 
- <span data-ttu-id="39868-961">Un punto </span><span class="sxs-lookup"><span data-stu-id="39868-961">A period</span></span> 
- <span data-ttu-id="39868-962">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-962">Three digits</span></span> 
- <span data-ttu-id="39868-963">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-963">A dash</span></span> 
- <span data-ttu-id="39868-964">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-965">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-965">Checksum</span></span>

<span data-ttu-id="39868-966">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-967">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-967">Definition</span></span>

<span data-ttu-id="39868-968">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-969">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-970">Se encuentra una palabra clave de Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="39868-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="39868-971">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-971">The checksum passes.</span></span>

<span data-ttu-id="39868-972">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-973">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-974">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-975">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="39868-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="39868-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="39868-977">Número de identificación nacional
</span><span class="sxs-lookup"><span data-stu-id="39868-977">National Identification Number</span></span> 
- <span data-ttu-id="39868-978">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="39868-978">Identity card</span></span> 
- <span data-ttu-id="39868-979">ID</span><span class="sxs-lookup"><span data-stu-id="39868-979">ID</span></span> 
- <span data-ttu-id="39868-980">Identificación</span><span class="sxs-lookup"><span data-stu-id="39868-980">Identification</span></span> 
- <span data-ttu-id="39868-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="39868-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="39868-982">EJECUTAR</span><span class="sxs-lookup"><span data-stu-id="39868-982">RUN</span></span> 
- <span data-ttu-id="39868-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="39868-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="39868-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="39868-984">RUT</span></span> 
- <span data-ttu-id="39868-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="39868-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="39868-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="39868-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="39868-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="39868-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="39868-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="39868-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="39868-989">	Número de tarjeta de identidad de residente de China (PRC)</span><span class="sxs-lookup"><span data-stu-id="39868-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-990">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-990">Format</span></span>

<span data-ttu-id="39868-991">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-992">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-992">Pattern</span></span>

<span data-ttu-id="39868-993">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-993">18 digits:</span></span>
- <span data-ttu-id="39868-994">Seis dígitos que son un código de dirección </span><span class="sxs-lookup"><span data-stu-id="39868-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="39868-995">Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="39868-996">Tres dígitos que son un código de pedido </span><span class="sxs-lookup"><span data-stu-id="39868-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="39868-997">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-998">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-998">Checksum</span></span>

<span data-ttu-id="39868-999">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1000">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1000">Definition</span></span>

<span data-ttu-id="39868-1001">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1002">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1003">Se encuentra una palabra clave de Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="39868-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="39868-1004">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1004">The checksum passes.</span></span>

<span data-ttu-id="39868-1005">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1006">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1007">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1008">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="39868-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="39868-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="39868-1010">Tarjeta de identidad de residente
</span><span class="sxs-lookup"><span data-stu-id="39868-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="39868-1011">República Popular China
</span><span class="sxs-lookup"><span data-stu-id="39868-1011">PRC</span></span> 
- <span data-ttu-id="39868-1012">Tarjeta de identificación nacional
</span><span class="sxs-lookup"><span data-stu-id="39868-1012">National Identification Card</span></span> 
- <span data-ttu-id="39868-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="39868-1013">身份证</span></span> 
- <span data-ttu-id="39868-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="39868-1014">居民 身份证</span></span> 
- <span data-ttu-id="39868-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="39868-1015">居民身份证</span></span> 
- <span data-ttu-id="39868-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="39868-1016">鉴定</span></span> 
- <span data-ttu-id="39868-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="39868-1017">身分證</span></span> 
- <span data-ttu-id="39868-1018">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="39868-1018">居民 身份證</span></span>
- <span data-ttu-id="39868-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="39868-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="39868-1020">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="39868-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1021">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1021">Format</span></span>

<span data-ttu-id="39868-1022">16 dígitos que se pueden dar formato o sin formato (dddddddddddddddd) y debe pasar la prueba Luhn.</span><span class="sxs-lookup"><span data-stu-id="39868-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1023">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1023">Pattern</span></span>

<span data-ttu-id="39868-1024">Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.</span><span class="sxs-lookup"><span data-stu-id="39868-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1025">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1025">Checksum</span></span>

<span data-ttu-id="39868-1026">Sí, la suma de comprobación de Luhn</span><span class="sxs-lookup"><span data-stu-id="39868-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1027">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1027">Definition</span></span>

<span data-ttu-id="39868-1028">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1029">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1030">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-1030">One of the following is true:</span></span>
    - <span data-ttu-id="39868-1031">Se encuentra una palabra clave de Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="39868-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="39868-1032">Se encuentra una palabra clave de Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="39868-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="39868-1033">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="39868-1034">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1034">The checksum passes.</span></span>

<span data-ttu-id="39868-1035">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1036">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1037">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1038">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="39868-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="39868-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="39868-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="39868-1040">card verification</span></span>
- <span data-ttu-id="39868-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="39868-1041">card identification number</span></span>
- <span data-ttu-id="39868-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="39868-1042">cvn</span></span>
- <span data-ttu-id="39868-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="39868-1043">cid</span></span>
- <span data-ttu-id="39868-1044">CVC2 obtenidos</span><span class="sxs-lookup"><span data-stu-id="39868-1044">cvc2</span></span>
- <span data-ttu-id="39868-1045">cvv2</span><span class="sxs-lookup"><span data-stu-id="39868-1045">cvv2</span></span>
- <span data-ttu-id="39868-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="39868-1046">pin block</span></span>
- <span data-ttu-id="39868-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="39868-1047">security code</span></span>
- <span data-ttu-id="39868-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="39868-1048">security number</span></span>
- <span data-ttu-id="39868-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="39868-1049">security no</span></span>
- <span data-ttu-id="39868-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="39868-1050">issue number</span></span>
- <span data-ttu-id="39868-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="39868-1051">issue no</span></span>
- <span data-ttu-id="39868-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="39868-1052">cryptogramme</span></span>
- <span data-ttu-id="39868-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="39868-1053">numéro de sécurité</span></span>
- <span data-ttu-id="39868-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="39868-1054">numero de securite</span></span>
- <span data-ttu-id="39868-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="39868-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="39868-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="39868-1057">prüfziffer</span></span>
- <span data-ttu-id="39868-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="39868-1058">prufziffer</span></span>
- <span data-ttu-id="39868-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="39868-1059">sicherheits Kode</span></span>
- <span data-ttu-id="39868-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="39868-1060">sicherheitscode</span></span>
- <span data-ttu-id="39868-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="39868-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="39868-1062">verfalldatum</span></span>
- <span data-ttu-id="39868-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="39868-1063">codice di verifica</span></span>
- <span data-ttu-id="39868-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="39868-p105">cod. sicurezza</span></span>
- <span data-ttu-id="39868-1066">COD sicurezza</span><span class="sxs-lookup"><span data-stu-id="39868-1066">cod sicurezza</span></span>
- <span data-ttu-id="39868-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="39868-1067">n autorizzazione</span></span>
- <span data-ttu-id="39868-1068">código
</span><span class="sxs-lookup"><span data-stu-id="39868-1068">código</span></span>
- <span data-ttu-id="39868-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="39868-1069">codigo</span></span>
- <span data-ttu-id="39868-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="39868-p106">cod. seg</span></span>
- <span data-ttu-id="39868-1072">COD seg</span><span class="sxs-lookup"><span data-stu-id="39868-1072">cod seg</span></span>
- <span data-ttu-id="39868-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="39868-1073">código de segurança</span></span>
- <span data-ttu-id="39868-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="39868-1074">codigo de seguranca</span></span>
- <span data-ttu-id="39868-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="39868-1075">codigo de segurança</span></span>
- <span data-ttu-id="39868-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="39868-1076">código de seguranca</span></span>
- <span data-ttu-id="39868-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="39868-p107">cód. segurança</span></span>
- <span data-ttu-id="39868-p108">Cod. seguranca cod. segurança</span><span class="sxs-lookup"><span data-stu-id="39868-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="39868-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="39868-p109">cód. seguranca</span></span>
- <span data-ttu-id="39868-1084">campo Cód. segurança</span><span class="sxs-lookup"><span data-stu-id="39868-1084">cód segurança</span></span>
- <span data-ttu-id="39868-1085">bacalao seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="39868-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="39868-1086">campo Cód. seguranca</span><span class="sxs-lookup"><span data-stu-id="39868-1086">cód seguranca</span></span>
- <span data-ttu-id="39868-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="39868-1087">número de verificação</span></span>
- <span data-ttu-id="39868-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="39868-1088">numero de verificacao</span></span>
- <span data-ttu-id="39868-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="39868-1089">ablauf</span></span>
- <span data-ttu-id="39868-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="39868-1090">gültig bis</span></span>
- <span data-ttu-id="39868-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="39868-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="39868-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="39868-1092">gultig bis</span></span>
- <span data-ttu-id="39868-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="39868-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="39868-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="39868-1094">scadenza</span></span>
- <span data-ttu-id="39868-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="39868-1095">data scad</span></span>
- <span data-ttu-id="39868-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="39868-1096">fecha de expiracion</span></span>
- <span data-ttu-id="39868-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="39868-1097">fecha de venc</span></span>
- <span data-ttu-id="39868-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="39868-1098">vencimiento</span></span>
- <span data-ttu-id="39868-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="39868-1099">válido hasta</span></span>
- <span data-ttu-id="39868-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="39868-1100">valido hasta</span></span>
- <span data-ttu-id="39868-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="39868-1101">vto</span></span>
- <span data-ttu-id="39868-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="39868-1102">data de expiração</span></span>
- <span data-ttu-id="39868-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="39868-1103">data de expiracao</span></span>
- <span data-ttu-id="39868-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="39868-1104">data em que expira</span></span>
- <span data-ttu-id="39868-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="39868-1105">validade</span></span>
- <span data-ttu-id="39868-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="39868-1106">valor</span></span>
- <span data-ttu-id="39868-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="39868-1107">vencimento</span></span>
- <span data-ttu-id="39868-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="39868-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="39868-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="39868-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="39868-1110">amex</span><span class="sxs-lookup"><span data-stu-id="39868-1110">amex</span></span>
- <span data-ttu-id="39868-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="39868-1111">american express</span></span>
- <span data-ttu-id="39868-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="39868-1112">americanexpress</span></span>
- <span data-ttu-id="39868-1113">Visa</span><span class="sxs-lookup"><span data-stu-id="39868-1113">Visa</span></span>
- <span data-ttu-id="39868-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="39868-1114">mastercard</span></span>
- <span data-ttu-id="39868-1115">master card
</span><span class="sxs-lookup"><span data-stu-id="39868-1115">master card</span></span>
- <span data-ttu-id="39868-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="39868-1116">mc</span></span> 
- <span data-ttu-id="39868-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="39868-1117">mastercards</span></span>
- <span data-ttu-id="39868-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="39868-1118">master cards</span></span>
- <span data-ttu-id="39868-1119">Club del comensal</span><span class="sxs-lookup"><span data-stu-id="39868-1119">diner's Club</span></span>
- <span data-ttu-id="39868-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="39868-1120">diners club</span></span>
- <span data-ttu-id="39868-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="39868-1121">dinersclub</span></span>
- <span data-ttu-id="39868-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="39868-1122">discover card</span></span>
- <span data-ttu-id="39868-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="39868-1123">discovercard</span></span>
- <span data-ttu-id="39868-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1124">discover cards</span></span>
- <span data-ttu-id="39868-1125">JCB</span><span class="sxs-lookup"><span data-stu-id="39868-1125">JCB</span></span>
- <span data-ttu-id="39868-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="39868-1126">japanese card bureau</span></span>
- <span data-ttu-id="39868-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="39868-1127">carte blanche</span></span>
- <span data-ttu-id="39868-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="39868-1128">carteblanche</span></span>
- <span data-ttu-id="39868-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="39868-1129">credit card</span></span>
- <span data-ttu-id="39868-1130">CC #</span><span class="sxs-lookup"><span data-stu-id="39868-1130">cc#</span></span>
- <span data-ttu-id="39868-1131">cc #:</span><span class="sxs-lookup"><span data-stu-id="39868-1131">cc#:</span></span>
- <span data-ttu-id="39868-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="39868-1132">expiration date</span></span>
- <span data-ttu-id="39868-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="39868-1133">exp date</span></span>
- <span data-ttu-id="39868-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="39868-1134">expiry date</span></span>
- <span data-ttu-id="39868-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="39868-1135">date d’expiration</span></span>
- <span data-ttu-id="39868-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="39868-1136">date d'exp</span></span>
- <span data-ttu-id="39868-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="39868-1137">date expiration</span></span>
- <span data-ttu-id="39868-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="39868-1138">bank card</span></span>
- <span data-ttu-id="39868-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="39868-1139">bankcard</span></span>
- <span data-ttu-id="39868-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="39868-1140">card number</span></span>
- <span data-ttu-id="39868-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="39868-1141">card num</span></span>
- <span data-ttu-id="39868-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-1142">cardnumber</span></span>
- <span data-ttu-id="39868-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="39868-1143">cardnumbers</span></span>
- <span data-ttu-id="39868-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="39868-1144">card numbers</span></span>
- <span data-ttu-id="39868-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1145">creditcard</span></span>
- <span data-ttu-id="39868-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1146">credit cards</span></span>
- <span data-ttu-id="39868-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1147">creditcards</span></span>
- <span data-ttu-id="39868-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="39868-1148">ccn</span></span>
- <span data-ttu-id="39868-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="39868-1149">card holder</span></span>
- <span data-ttu-id="39868-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="39868-1150">cardholder</span></span>
- <span data-ttu-id="39868-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="39868-1151">card holders</span></span>
- <span data-ttu-id="39868-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="39868-1152">cardholders</span></span>
- <span data-ttu-id="39868-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="39868-1153">check card</span></span>
- <span data-ttu-id="39868-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1154">checkcard</span></span>
- <span data-ttu-id="39868-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1155">check cards</span></span>
- <span data-ttu-id="39868-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1156">checkcards</span></span>
- <span data-ttu-id="39868-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="39868-1157">debit card</span></span>
- <span data-ttu-id="39868-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1158">debitcard</span></span>
- <span data-ttu-id="39868-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1159">debit cards</span></span>
- <span data-ttu-id="39868-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1160">debitcards</span></span>
- <span data-ttu-id="39868-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="39868-1161">atm card</span></span>
- <span data-ttu-id="39868-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1162">atmcard</span></span>
- <span data-ttu-id="39868-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1163">atm cards</span></span>
- <span data-ttu-id="39868-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1164">atmcards</span></span>
- <span data-ttu-id="39868-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="39868-1165">enroute</span></span>
- <span data-ttu-id="39868-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="39868-1166">en route</span></span>
- <span data-ttu-id="39868-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="39868-1167">card type</span></span>
- <span data-ttu-id="39868-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="39868-1168">carte bancaire</span></span>
- <span data-ttu-id="39868-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="39868-1169">carte de crédit</span></span>
- <span data-ttu-id="39868-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="39868-1170">carte de credit</span></span>
- <span data-ttu-id="39868-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1171">numéro de carte</span></span>
- <span data-ttu-id="39868-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1172">numero de carte</span></span>
- <span data-ttu-id="39868-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1173">nº de la carte</span></span>
- <span data-ttu-id="39868-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1174">nº de carte</span></span>
- <span data-ttu-id="39868-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="39868-1175">kreditkarte</span></span>
- <span data-ttu-id="39868-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="39868-1176">karte</span></span>
- <span data-ttu-id="39868-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="39868-1177">karteninhaber</span></span>
- <span data-ttu-id="39868-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="39868-1178">karteninhabers</span></span>
- <span data-ttu-id="39868-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="39868-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="39868-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="39868-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="39868-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="39868-1181">kreditkartentyp</span></span>
- <span data-ttu-id="39868-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="39868-1182">eigentümername</span></span>
- <span data-ttu-id="39868-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="39868-1183">kartennr</span></span> 
- <span data-ttu-id="39868-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="39868-1184">kartennummer</span></span>
- <span data-ttu-id="39868-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="39868-1185">kreditkartennummer</span></span>
- <span data-ttu-id="39868-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="39868-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="39868-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1187">carta di credito</span></span>
- <span data-ttu-id="39868-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1188">carta credito</span></span>
- <span data-ttu-id="39868-1189">carta</span><span class="sxs-lookup"><span data-stu-id="39868-1189">carta</span></span>
- <span data-ttu-id="39868-1190">carta n</span><span class="sxs-lookup"><span data-stu-id="39868-1190">n carta</span></span>
- <span data-ttu-id="39868-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="39868-p110">nr. carta</span></span>
- <span data-ttu-id="39868-1193">carta n</span><span class="sxs-lookup"><span data-stu-id="39868-1193">nr carta</span></span>
- <span data-ttu-id="39868-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="39868-1194">numero carta</span></span>
- <span data-ttu-id="39868-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="39868-1195">numero della carta</span></span>
- <span data-ttu-id="39868-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="39868-1196">numero di carta</span></span>
- <span data-ttu-id="39868-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1197">tarjeta credito</span></span>
- <span data-ttu-id="39868-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1198">tarjeta de credito</span></span>
- <span data-ttu-id="39868-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="39868-1199">tarjeta crédito</span></span>
- <span data-ttu-id="39868-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="39868-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="39868-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="39868-1201">tarjeta de atm</span></span>
- <span data-ttu-id="39868-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="39868-1202">tarjeta atm</span></span>
- <span data-ttu-id="39868-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1203">tarjeta debito</span></span>
- <span data-ttu-id="39868-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1204">tarjeta de debito</span></span>
- <span data-ttu-id="39868-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="39868-1205">tarjeta débito</span></span>
- <span data-ttu-id="39868-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="39868-1206">tarjeta de débito</span></span>
- <span data-ttu-id="39868-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-1207">nº de tarjeta</span></span>
- <span data-ttu-id="39868-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-p111">no. de tarjeta</span></span>
- <span data-ttu-id="39868-1210">No hay tarjeta de</span><span class="sxs-lookup"><span data-stu-id="39868-1210">no de tarjeta</span></span>
- <span data-ttu-id="39868-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-1211">numero de tarjeta</span></span>
- <span data-ttu-id="39868-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-1212">número de tarjeta</span></span>
- <span data-ttu-id="39868-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="39868-1213">tarjeta no</span></span>
- <span data-ttu-id="39868-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="39868-1214">tarjetahabiente</span></span>
- <span data-ttu-id="39868-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="39868-1215">cartão de crédito</span></span>
- <span data-ttu-id="39868-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1216">cartão de credito</span></span>
- <span data-ttu-id="39868-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="39868-1217">cartao de crédito</span></span>
- <span data-ttu-id="39868-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1218">cartao de credito</span></span>
- <span data-ttu-id="39868-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="39868-1219">cartão de débito</span></span>
- <span data-ttu-id="39868-1220">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="39868-1220">cartao de débito</span></span>
- <span data-ttu-id="39868-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1221">cartão de debito</span></span>
- <span data-ttu-id="39868-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1222">cartao de debito</span></span>
- <span data-ttu-id="39868-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="39868-1223">débito automático</span></span>
- <span data-ttu-id="39868-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="39868-1224">debito automatico</span></span>
- <span data-ttu-id="39868-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="39868-1225">número do cartão</span></span>
- <span data-ttu-id="39868-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-1226">numero do cartão</span></span> 
- <span data-ttu-id="39868-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="39868-1227">número do cartao</span></span>
- <span data-ttu-id="39868-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="39868-1228">numero do cartao</span></span>
- <span data-ttu-id="39868-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-1229">número de cartão</span></span>
- <span data-ttu-id="39868-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-1230">numero de cartão</span></span>
- <span data-ttu-id="39868-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-1231">número de cartao</span></span>
- <span data-ttu-id="39868-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-1232">numero de cartao</span></span>
- <span data-ttu-id="39868-1233">Nº cartão</span><span class="sxs-lookup"><span data-stu-id="39868-1233">nº do cartão</span></span>
- <span data-ttu-id="39868-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-1234">nº do cartao</span></span>
- <span data-ttu-id="39868-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-p112">nº. do cartão</span></span>
- <span data-ttu-id="39868-1237">No hay cartão</span><span class="sxs-lookup"><span data-stu-id="39868-1237">no do cartão</span></span>
- <span data-ttu-id="39868-1238">No hay cartao</span><span class="sxs-lookup"><span data-stu-id="39868-1238">no do cartao</span></span>
- <span data-ttu-id="39868-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-p113">no. do cartão</span></span>
- <span data-ttu-id="39868-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="39868-1243">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="39868-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1244">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1244">Format</span></span>

<span data-ttu-id="39868-1245">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1246">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1246">Pattern</span></span>

<span data-ttu-id="39868-1247">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1248">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1248">Checksum</span></span>

<span data-ttu-id="39868-1249">No</span><span class="sxs-lookup"><span data-stu-id="39868-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1250">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1250">Definition</span></span>

<span data-ttu-id="39868-1251">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1252">La función Func_croatia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1253">Se encuentra una palabra clave de Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="39868-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-1254">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="39868-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="39868-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="39868-1256">Tarjeta de identidad croata</span><span class="sxs-lookup"><span data-stu-id="39868-1256">Croatian identity card</span></span>
- <span data-ttu-id="39868-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="39868-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="39868-1258">	Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="39868-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1259">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1259">Format</span></span>

<span data-ttu-id="39868-1260">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1261">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1261">Pattern</span></span>

<span data-ttu-id="39868-1262">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-1262">10 digits:</span></span>
- <span data-ttu-id="39868-1263">Seis dígitos en forma DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="39868-1264">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1265">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1265">Checksum</span></span>

<span data-ttu-id="39868-1266">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1267">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1267">Definition</span></span>

<span data-ttu-id="39868-1268">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1269">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1270">Se encuentra una palabra clave de Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="39868-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="39868-1271">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1271">The checksum passes.</span></span>

<span data-ttu-id="39868-1272">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1273">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1274">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1275">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="39868-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="39868-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="39868-1277">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="39868-1277">Personal Identification Number</span></span>
- <span data-ttu-id="39868-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="39868-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="39868-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="39868-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="39868-1280">	número de tarjeta de identidad nacional checa</span><span class="sxs-lookup"><span data-stu-id="39868-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1281">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1281">Format</span></span>

<span data-ttu-id="39868-1282">10 dígitos que contienen una barra diagonal</span><span class="sxs-lookup"><span data-stu-id="39868-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1283">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1283">Pattern</span></span>

<span data-ttu-id="39868-1284">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-1284">10 digits:</span></span>
- <span data-ttu-id="39868-1285">Seis dígitos que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="39868-1286">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="39868-1286">A forward slash</span></span> 
- <span data-ttu-id="39868-1287">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1288">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1288">Checksum</span></span>

<span data-ttu-id="39868-1289">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1290">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1290">Definition</span></span>

<span data-ttu-id="39868-p115">Una directiva de DLP es 85% seguro de que ha detectado este tipo de información confidencial if, dentro de una proximidad de 300 caracteres: la función Func_czech_id_card busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_czech_id_card. Pasa la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="39868-1294">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1294">Keywords</span></span>

- <span data-ttu-id="39868-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="39868-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="39868-1296">tarjeta de identidad nacional checa</span><span class="sxs-lookup"><span data-stu-id="39868-1296">Czech national identity card</span></span>
- <span data-ttu-id="39868-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="39868-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="39868-1298">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="39868-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1299">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1299">Format</span></span>

<span data-ttu-id="39868-1300">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="39868-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1301">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1301">Pattern</span></span>

<span data-ttu-id="39868-1302">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-1302">10 digits:</span></span>
- <span data-ttu-id="39868-1303">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="39868-1304">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-1304">A hyphen</span></span> 
- <span data-ttu-id="39868-1305">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1306">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1306">Checksum</span></span>

<span data-ttu-id="39868-1307">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1308">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1308">Definition</span></span>

<span data-ttu-id="39868-p116">Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la expresión regular Regex_denmark_id busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_denmark_id. Pasa la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-1312">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="39868-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="39868-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="39868-1314">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="39868-1314">Personal Identification Number</span></span>
- <span data-ttu-id="39868-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="39868-1315">CPR</span></span>
- <span data-ttu-id="39868-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="39868-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="39868-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="39868-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="39868-1318">Número de la Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="39868-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1319">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1319">Format</span></span>

<span data-ttu-id="39868-1320">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1321">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1321">Pattern</span></span>

<span data-ttu-id="39868-1322">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39868-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="39868-1323">Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito</span><span class="sxs-lookup"><span data-stu-id="39868-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="39868-1324">Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito.</span><span class="sxs-lookup"><span data-stu-id="39868-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="39868-1325">Siete dígitos, el último de los cuales es el dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1326">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1326">Checksum</span></span>

<span data-ttu-id="39868-1327">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1328">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1328">Definition</span></span>

<span data-ttu-id="39868-1329">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1330">La función Func_dea_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1331">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-1332">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1332">Keywords</span></span>

<span data-ttu-id="39868-1333">Ninguno</span><span class="sxs-lookup"><span data-stu-id="39868-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="39868-1334">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="39868-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1335">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1335">Format</span></span>

<span data-ttu-id="39868-1336">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1337">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1337">Pattern</span></span>

<span data-ttu-id="39868-1338">Patrón muy complejo y robusto</span><span class="sxs-lookup"><span data-stu-id="39868-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1339">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1339">Checksum</span></span>

<span data-ttu-id="39868-1340">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1341">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1341">Definition</span></span>

<span data-ttu-id="39868-1342">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1343">La función Func_eu_debit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1344">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="39868-1345">Se encuentra una palabra clave de Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="39868-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="39868-1346">Se encuentra una palabra clave de Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="39868-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="39868-1347">Se encuentra una palabra clave de Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="39868-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="39868-1348">Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="39868-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="39868-1349">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="39868-1350">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1351">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="39868-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="39868-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="39868-1353">número de cuenta</span><span class="sxs-lookup"><span data-stu-id="39868-1353">account number</span></span> 
- <span data-ttu-id="39868-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="39868-1354">card number</span></span> 
- <span data-ttu-id="39868-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="39868-1355">card no.</span></span> 
- <span data-ttu-id="39868-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="39868-1356">security number</span></span> 
- <span data-ttu-id="39868-1357">CC #</span><span class="sxs-lookup"><span data-stu-id="39868-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="39868-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="39868-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="39868-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="39868-1359">acct nbr</span></span> 
- <span data-ttu-id="39868-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="39868-1360">acct num</span></span> 
- <span data-ttu-id="39868-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="39868-1361">acct no</span></span> 
- <span data-ttu-id="39868-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="39868-1362">american express</span></span> 
- <span data-ttu-id="39868-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="39868-1363">americanexpress</span></span> 
- <span data-ttu-id="39868-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="39868-1364">americano espresso</span></span> 
- <span data-ttu-id="39868-1365">amex</span><span class="sxs-lookup"><span data-stu-id="39868-1365">amex</span></span> 
- <span data-ttu-id="39868-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="39868-1366">atm card</span></span> 
- <span data-ttu-id="39868-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1367">atm cards</span></span> 
- <span data-ttu-id="39868-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1368">atm kaart</span></span> 
- <span data-ttu-id="39868-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1369">atmcard</span></span> 
- <span data-ttu-id="39868-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1370">atmcards</span></span> 
- <span data-ttu-id="39868-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1371">atmkaart</span></span> 
- <span data-ttu-id="39868-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="39868-1372">atmkaarten</span></span> 
- <span data-ttu-id="39868-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="39868-1373">bancontact</span></span> 
- <span data-ttu-id="39868-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="39868-1374">bank card</span></span> 
- <span data-ttu-id="39868-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1375">bankkaart</span></span> 
- <span data-ttu-id="39868-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="39868-1376">card holder</span></span> 
- <span data-ttu-id="39868-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="39868-1377">card holders</span></span> 
- <span data-ttu-id="39868-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="39868-1378">card num</span></span> 
- <span data-ttu-id="39868-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="39868-1379">card number</span></span> 
- <span data-ttu-id="39868-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="39868-1380">card numbers</span></span> 
- <span data-ttu-id="39868-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="39868-1381">card type</span></span> 
- <span data-ttu-id="39868-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="39868-1382">cardano numerico</span></span> 
- <span data-ttu-id="39868-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="39868-1383">cardholder</span></span> 
- <span data-ttu-id="39868-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="39868-1384">cardholders</span></span> 
- <span data-ttu-id="39868-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-1385">cardnumber</span></span> 
- <span data-ttu-id="39868-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="39868-1386">cardnumbers</span></span> 
- <span data-ttu-id="39868-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="39868-1387">carta bianca</span></span> 
- <span data-ttu-id="39868-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1388">carta credito</span></span> 
- <span data-ttu-id="39868-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1389">carta di credito</span></span> 
- <span data-ttu-id="39868-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1390">cartao de credito</span></span> 
- <span data-ttu-id="39868-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="39868-1391">cartao de crédito</span></span> 
- <span data-ttu-id="39868-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1392">cartao de debito</span></span> 
- <span data-ttu-id="39868-1393">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="39868-1393">cartao de débito</span></span> 
- <span data-ttu-id="39868-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="39868-1394">carte bancaire</span></span> 
- <span data-ttu-id="39868-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="39868-1395">carte blanche</span></span> 
- <span data-ttu-id="39868-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="39868-1396">carte bleue</span></span> 
- <span data-ttu-id="39868-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="39868-1397">carte de credit</span></span> 
- <span data-ttu-id="39868-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="39868-1398">carte de crédit</span></span> 
- <span data-ttu-id="39868-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1399">carte di credito</span></span> 
- <span data-ttu-id="39868-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="39868-1400">carteblanche</span></span> 
- <span data-ttu-id="39868-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1401">cartão de credito</span></span> 
- <span data-ttu-id="39868-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="39868-1402">cartão de crédito</span></span> 
- <span data-ttu-id="39868-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1403">cartão de debito</span></span> 
- <span data-ttu-id="39868-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="39868-1404">cartão de débito</span></span> 
- <span data-ttu-id="39868-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="39868-1405">cb</span></span> 
- <span data-ttu-id="39868-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="39868-1406">ccn</span></span> 
- <span data-ttu-id="39868-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="39868-1407">check card</span></span> 
- <span data-ttu-id="39868-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1408">check cards</span></span> 
- <span data-ttu-id="39868-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1409">checkcard</span></span>
- <span data-ttu-id="39868-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1410">checkcards</span></span> 
- <span data-ttu-id="39868-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1411">chequekaart</span></span> 
- <span data-ttu-id="39868-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="39868-1412">cirrus</span></span> 
- <span data-ttu-id="39868-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="39868-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="39868-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1414">controlekaart</span></span> 
- <span data-ttu-id="39868-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="39868-1415">controlekaarten</span></span> 
- <span data-ttu-id="39868-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="39868-1416">credit card</span></span> 
- <span data-ttu-id="39868-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1417">credit cards</span></span> 
- <span data-ttu-id="39868-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1418">creditcard</span></span> 
- <span data-ttu-id="39868-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1419">creditcards</span></span> 
- <span data-ttu-id="39868-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1420">debetkaart</span></span> 
- <span data-ttu-id="39868-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="39868-1421">debetkaarten</span></span> 
- <span data-ttu-id="39868-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="39868-1422">debit card</span></span> 
- <span data-ttu-id="39868-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1423">debit cards</span></span> 
- <span data-ttu-id="39868-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="39868-1424">debitcard</span></span> 
- <span data-ttu-id="39868-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="39868-1425">debitcards</span></span> 
- <span data-ttu-id="39868-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="39868-1426">debito automatico</span></span> 
- <span data-ttu-id="39868-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="39868-1427">diners club</span></span> 
- <span data-ttu-id="39868-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="39868-1428">dinersclub</span></span> 
- <span data-ttu-id="39868-1429">descubrir</span><span class="sxs-lookup"><span data-stu-id="39868-1429">discover</span></span> 
- <span data-ttu-id="39868-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="39868-1430">discover card</span></span> 
- <span data-ttu-id="39868-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1431">discover cards</span></span> 
- <span data-ttu-id="39868-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="39868-1432">discovercard</span></span> 
- <span data-ttu-id="39868-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="39868-1433">discovercards</span></span> 
- <span data-ttu-id="39868-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="39868-1434">débito automático</span></span>
- <span data-ttu-id="39868-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="39868-1435">edc</span></span> 
- <span data-ttu-id="39868-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="39868-1436">eigentümername</span></span> 
- <span data-ttu-id="39868-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="39868-1437">european debit card</span></span> 
- <span data-ttu-id="39868-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1438">hoofdkaart</span></span> 
- <span data-ttu-id="39868-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="39868-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="39868-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="39868-1440">in viaggio</span></span> 
- <span data-ttu-id="39868-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="39868-1441">japanese card bureau</span></span> 
- <span data-ttu-id="39868-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="39868-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="39868-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="39868-1443">jcb</span></span> 
- <span data-ttu-id="39868-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="39868-1444">kaart</span></span> 
- <span data-ttu-id="39868-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="39868-1445">kaart num</span></span> 
- <span data-ttu-id="39868-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="39868-1446">kaartaantal</span></span> 
- <span data-ttu-id="39868-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="39868-1447">kaartaantallen</span></span> 
- <span data-ttu-id="39868-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="39868-1448">kaarthouder</span></span> 
- <span data-ttu-id="39868-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="39868-1449">kaarthouders</span></span> 
- <span data-ttu-id="39868-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="39868-1450">karte</span></span>  
- <span data-ttu-id="39868-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="39868-1451">karteninhaber</span></span> 
- <span data-ttu-id="39868-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="39868-1452">karteninhabers</span></span>
- <span data-ttu-id="39868-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="39868-1453">kartennr</span></span> 
- <span data-ttu-id="39868-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="39868-1454">kartennummer</span></span> 
- <span data-ttu-id="39868-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="39868-1455">kreditkarte</span></span> 
- <span data-ttu-id="39868-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="39868-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="39868-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="39868-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="39868-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="39868-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="39868-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="39868-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="39868-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="39868-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="39868-1461">maestro</span></span> 
- <span data-ttu-id="39868-1462">master card
</span><span class="sxs-lookup"><span data-stu-id="39868-1462">master card</span></span> 
- <span data-ttu-id="39868-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="39868-1463">master cards</span></span> 
- <span data-ttu-id="39868-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="39868-1464">mastercard</span></span> 
- <span data-ttu-id="39868-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="39868-1465">mastercards</span></span> 
- <span data-ttu-id="39868-1466">MC</span><span class="sxs-lookup"><span data-stu-id="39868-1466">mc</span></span> 
- <span data-ttu-id="39868-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="39868-1467">mister cash</span></span> 
- <span data-ttu-id="39868-1468">carta n</span><span class="sxs-lookup"><span data-stu-id="39868-1468">n carta</span></span> 
- <span data-ttu-id="39868-1469">carta</span><span class="sxs-lookup"><span data-stu-id="39868-1469">carta</span></span> 
- <span data-ttu-id="39868-1470">No hay tarjeta de</span><span class="sxs-lookup"><span data-stu-id="39868-1470">no de tarjeta</span></span> 
- <span data-ttu-id="39868-1471">No hay cartao</span><span class="sxs-lookup"><span data-stu-id="39868-1471">no do cartao</span></span> 
- <span data-ttu-id="39868-1472">No hay cartão</span><span class="sxs-lookup"><span data-stu-id="39868-1472">no do cartão</span></span> 
- <span data-ttu-id="39868-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="39868-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-p118">no. do cartao</span></span> 
- <span data-ttu-id="39868-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-p119">no. do cartão</span></span> 
- <span data-ttu-id="39868-1479">carta n</span><span class="sxs-lookup"><span data-stu-id="39868-1479">nr carta</span></span> 
- <span data-ttu-id="39868-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="39868-p120">nr. carta</span></span> 
- <span data-ttu-id="39868-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1482">numeri di scheda</span></span> 
- <span data-ttu-id="39868-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="39868-1483">numero carta</span></span> 
- <span data-ttu-id="39868-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-1484">numero de cartao</span></span> 
- <span data-ttu-id="39868-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1485">numero de carte</span></span> 
- <span data-ttu-id="39868-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-1486">numero de cartão</span></span> 
- <span data-ttu-id="39868-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-1487">numero de tarjeta</span></span>
- <span data-ttu-id="39868-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="39868-1488">numero della carta</span></span> 
- <span data-ttu-id="39868-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="39868-1489">numero di carta</span></span> 
- <span data-ttu-id="39868-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1490">numero di scheda</span></span> 
- <span data-ttu-id="39868-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-1491">numero do cartao</span></span> 
- <span data-ttu-id="39868-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-1492">numero do cartão</span></span> 
- <span data-ttu-id="39868-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1493">numéro de carte</span></span> 
- <span data-ttu-id="39868-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="39868-1494">nº carta</span></span> 
- <span data-ttu-id="39868-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1495">nº de carte</span></span> 
- <span data-ttu-id="39868-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="39868-1496">nº de la carte</span></span> 
- <span data-ttu-id="39868-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="39868-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-1498">nº do cartao</span></span> 
- <span data-ttu-id="39868-1499">Nº cartão</span><span class="sxs-lookup"><span data-stu-id="39868-1499">nº do cartão</span></span> 
- <span data-ttu-id="39868-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-p121">nº. do cartão</span></span> 
- <span data-ttu-id="39868-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="39868-1502">número de cartao</span></span> 
- <span data-ttu-id="39868-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="39868-1503">número de cartão</span></span> 
- <span data-ttu-id="39868-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="39868-1504">número de tarjeta</span></span> 
- <span data-ttu-id="39868-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="39868-1505">número do cartao</span></span> 
- <span data-ttu-id="39868-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="39868-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="39868-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="39868-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="39868-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="39868-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="39868-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="39868-1509">scheda della banca</span></span> 
- <span data-ttu-id="39868-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="39868-1510">scheda di controllo</span></span> 
- <span data-ttu-id="39868-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1511">scheda di debito</span></span> 
- <span data-ttu-id="39868-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="39868-1512">scheda matrice</span></span> 
- <span data-ttu-id="39868-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="39868-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="39868-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="39868-1514">schede di controllo</span></span> 
- <span data-ttu-id="39868-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1515">schede di debito</span></span> 
- <span data-ttu-id="39868-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="39868-1516">schede matrici</span></span> 
- <span data-ttu-id="39868-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="39868-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="39868-1518">scoprono le schede</span></span> 
- <span data-ttu-id="39868-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="39868-1519">solo</span></span> 
- <span data-ttu-id="39868-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1520">supporti di scheda</span></span> 
- <span data-ttu-id="39868-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1521">supporto di scheda</span></span> 
- <span data-ttu-id="39868-1522">conmutador</span><span class="sxs-lookup"><span data-stu-id="39868-1522">switch</span></span> 
- <span data-ttu-id="39868-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="39868-1523">tarjeta atm</span></span> 
- <span data-ttu-id="39868-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1524">tarjeta credito</span></span> 
- <span data-ttu-id="39868-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="39868-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="39868-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="39868-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="39868-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="39868-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="39868-1528">tarjeta debito</span></span> 
- <span data-ttu-id="39868-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="39868-1529">tarjeta no</span></span>
- <span data-ttu-id="39868-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="39868-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="39868-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1531">tipo della scheda</span></span> 
- <span data-ttu-id="39868-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="39868-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="39868-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1533">scheda</span></span> 
- <span data-ttu-id="39868-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="39868-1534">v pay</span></span> 
- <span data-ttu-id="39868-1535">v-pago</span><span class="sxs-lookup"><span data-stu-id="39868-1535">v-pay</span></span> 
- <span data-ttu-id="39868-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="39868-1536">visa</span></span> 
- <span data-ttu-id="39868-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="39868-1537">visa plus</span></span> 
- <span data-ttu-id="39868-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="39868-1538">visa electron</span></span> 
- <span data-ttu-id="39868-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="39868-1539">visto</span></span> 
- <span data-ttu-id="39868-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="39868-1540">visum</span></span> 
- <span data-ttu-id="39868-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="39868-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="39868-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="39868-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="39868-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="39868-1543">card identification number</span></span>
- <span data-ttu-id="39868-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="39868-1544">card verification</span></span> 
- <span data-ttu-id="39868-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="39868-1545">cardi la verifica</span></span> 
- <span data-ttu-id="39868-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="39868-1546">cid</span></span> 
- <span data-ttu-id="39868-1547">COD seg</span><span class="sxs-lookup"><span data-stu-id="39868-1547">cod seg</span></span> 
- <span data-ttu-id="39868-1548">COD seguranca</span><span class="sxs-lookup"><span data-stu-id="39868-1548">cod seguranca</span></span> 
- <span data-ttu-id="39868-1549">COD segurança</span><span class="sxs-lookup"><span data-stu-id="39868-1549">cod segurança</span></span> 
- <span data-ttu-id="39868-1550">COD sicurezza</span><span class="sxs-lookup"><span data-stu-id="39868-1550">cod sicurezza</span></span> 
- <span data-ttu-id="39868-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="39868-p122">cod. seg</span></span> 
- <span data-ttu-id="39868-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="39868-p123">cod. seguranca</span></span> 
- <span data-ttu-id="39868-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="39868-p124">cod. segurança</span></span> 
- <span data-ttu-id="39868-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="39868-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="39868-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="39868-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="39868-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="39868-1560">codice di verifica</span></span> 
- <span data-ttu-id="39868-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="39868-1561">codigo</span></span> 
- <span data-ttu-id="39868-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="39868-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="39868-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="39868-1563">codigo de segurança</span></span> 
- <span data-ttu-id="39868-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="39868-1564">crittogramma</span></span> 
- <span data-ttu-id="39868-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="39868-1565">cryptogram</span></span> 
- <span data-ttu-id="39868-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="39868-1566">cryptogramme</span></span> 
- <span data-ttu-id="39868-1567">CV2</span><span class="sxs-lookup"><span data-stu-id="39868-1567">cv2</span></span> 
- <span data-ttu-id="39868-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="39868-1568">cvc</span></span> 
- <span data-ttu-id="39868-1569">CVC2 obtenidos</span><span class="sxs-lookup"><span data-stu-id="39868-1569">cvc2</span></span> 
- <span data-ttu-id="39868-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="39868-1570">cvn</span></span> 
- <span data-ttu-id="39868-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="39868-1571">cvv</span></span> 
- <span data-ttu-id="39868-1572">cvv2</span><span class="sxs-lookup"><span data-stu-id="39868-1572">cvv2</span></span> 
- <span data-ttu-id="39868-1573">campo Cód. seguranca</span><span class="sxs-lookup"><span data-stu-id="39868-1573">cód seguranca</span></span> 
- <span data-ttu-id="39868-1574">campo Cód. segurança</span><span class="sxs-lookup"><span data-stu-id="39868-1574">cód segurança</span></span> 
- <span data-ttu-id="39868-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="39868-p126">cód. seguranca</span></span> 
- <span data-ttu-id="39868-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="39868-p127">cód. segurança</span></span> 
- <span data-ttu-id="39868-1579">código
</span><span class="sxs-lookup"><span data-stu-id="39868-1579">código</span></span> 
- <span data-ttu-id="39868-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="39868-1580">código de seguranca</span></span> 
- <span data-ttu-id="39868-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="39868-1581">código de segurança</span></span> 
- <span data-ttu-id="39868-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="39868-1582">de kaart controle</span></span> 
- <span data-ttu-id="39868-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="39868-1583">geeft nr uit</span></span> 
- <span data-ttu-id="39868-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="39868-1584">issue no</span></span> 
- <span data-ttu-id="39868-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="39868-1585">issue number</span></span> 
- <span data-ttu-id="39868-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="39868-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="39868-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="39868-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="39868-1589">kwestieaantal</span></span> 
- <span data-ttu-id="39868-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="39868-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="39868-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="39868-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="39868-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="39868-1594">numero de securite</span></span> 
- <span data-ttu-id="39868-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="39868-1595">numero de verificacao</span></span> 
- <span data-ttu-id="39868-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="39868-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="39868-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="39868-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="39868-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="39868-1598">scheda</span></span> 
- <span data-ttu-id="39868-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="39868-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="39868-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="39868-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="39868-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="39868-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="39868-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="39868-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="39868-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="39868-1603">número de verificação</span></span> 
- <span data-ttu-id="39868-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="39868-1604">perno il blocco</span></span> 
- <span data-ttu-id="39868-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="39868-1605">pin block</span></span> 
- <span data-ttu-id="39868-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="39868-1606">prufziffer</span></span> 
- <span data-ttu-id="39868-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="39868-1607">prüfziffer</span></span> 
- <span data-ttu-id="39868-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="39868-1608">security code</span></span> 
- <span data-ttu-id="39868-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="39868-1609">security no</span></span> 
- <span data-ttu-id="39868-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="39868-1610">security number</span></span> 
- <span data-ttu-id="39868-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="39868-1611">sicherheits kode</span></span> 
- <span data-ttu-id="39868-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="39868-1612">sicherheitscode</span></span> 
- <span data-ttu-id="39868-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="39868-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="39868-1614">speldblok</span></span> 
- <span data-ttu-id="39868-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1615">veiligheid nr</span></span> 
- <span data-ttu-id="39868-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="39868-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="39868-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="39868-1617">veiligheidscode</span></span> 
- <span data-ttu-id="39868-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="39868-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="39868-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="39868-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="39868-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="39868-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="39868-1621">ablauf</span></span> 
- <span data-ttu-id="39868-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="39868-1622">data de expiracao</span></span> 
- <span data-ttu-id="39868-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="39868-1623">data de expiração</span></span> 
- <span data-ttu-id="39868-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="39868-1624">data del exp</span></span> 
- <span data-ttu-id="39868-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="39868-1625">data di exp</span></span> 
- <span data-ttu-id="39868-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="39868-1626">data di scadenza</span></span> 
- <span data-ttu-id="39868-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="39868-1627">data em que expira</span></span> 
- <span data-ttu-id="39868-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="39868-1628">data scad</span></span> 
- <span data-ttu-id="39868-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="39868-1629">data scadenza</span></span> 
- <span data-ttu-id="39868-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="39868-1630">date de validité</span></span> 
- <span data-ttu-id="39868-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="39868-1631">datum afloop</span></span> 
- <span data-ttu-id="39868-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="39868-1632">datum van exp</span></span> 
- <span data-ttu-id="39868-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="39868-1633">de afloop</span></span> 
- <span data-ttu-id="39868-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="39868-1634">espira</span></span> 
- <span data-ttu-id="39868-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="39868-1635">espira</span></span> 
- <span data-ttu-id="39868-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="39868-1636">exp date</span></span> 
- <span data-ttu-id="39868-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="39868-1637">exp datum</span></span> 
- <span data-ttu-id="39868-1638">expiración</span><span class="sxs-lookup"><span data-stu-id="39868-1638">expiration</span></span> 
- <span data-ttu-id="39868-1639">expirar
</span><span class="sxs-lookup"><span data-stu-id="39868-1639">expire</span></span> 
- <span data-ttu-id="39868-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="39868-1640">expires</span></span> 
- <span data-ttu-id="39868-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="39868-1641">expiry</span></span> 
- <span data-ttu-id="39868-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="39868-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="39868-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="39868-1643">fecha de venc</span></span> 
- <span data-ttu-id="39868-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="39868-1644">gultig bis</span></span> 
- <span data-ttu-id="39868-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="39868-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="39868-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="39868-1646">gültig bis</span></span> 
- <span data-ttu-id="39868-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="39868-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="39868-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="39868-1648">la scadenza</span></span> 
- <span data-ttu-id="39868-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="39868-1649">scadenza</span></span> 
- <span data-ttu-id="39868-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="39868-1650">valable</span></span> 
- <span data-ttu-id="39868-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="39868-1651">validade</span></span> 
- <span data-ttu-id="39868-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="39868-1652">valido hasta</span></span> 
- <span data-ttu-id="39868-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="39868-1653">valor</span></span> 
- <span data-ttu-id="39868-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="39868-1654">venc</span></span> 
- <span data-ttu-id="39868-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="39868-1655">vencimento</span></span> 
- <span data-ttu-id="39868-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="39868-1656">vencimiento</span></span> 
- <span data-ttu-id="39868-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="39868-1657">verloopt</span></span> 
- <span data-ttu-id="39868-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="39868-1658">vervaldag</span></span> 
- <span data-ttu-id="39868-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="39868-1659">vervaldatum</span></span> 
- <span data-ttu-id="39868-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="39868-1660">vto</span></span> 
- <span data-ttu-id="39868-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="39868-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="39868-1662">Número de licencia del controlador de la UE</span><span class="sxs-lookup"><span data-stu-id="39868-1662">EU Driver's License Number</span></span>

<span data-ttu-id="39868-1663">Para obtener más información, vea el [tipo de información confidencial del número de licencia del controlador de la UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="39868-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="39868-1664">Número de identificación de la UE nacional</span><span class="sxs-lookup"><span data-stu-id="39868-1664">EU National Identification Number</span></span>

<span data-ttu-id="39868-1665">Para obtener más información, vea el [tipo de información confidencial del número de identificación nacional de la UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="39868-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="39868-1666">Número de cuenta de Passport de la UE</span><span class="sxs-lookup"><span data-stu-id="39868-1666">EU Passport Number</span></span>

<span data-ttu-id="39868-1667">Para obtener más información, vea el [tipo de información confidencial del número de cuenta de Passport de la UE](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="39868-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="39868-1668">Identificador de número de seguridad Social de la UE o equivalente</span><span class="sxs-lookup"><span data-stu-id="39868-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="39868-1669">Para obtener más información, vea el [número de seguridad Social de la UE o tipo de información confidencial de identificador equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="39868-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="39868-1670">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="39868-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="39868-1671">Para obtener más información, vea el [tipo de información confidencial del número de identificación de impuestos de la UE](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="39868-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="39868-1672">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="39868-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="39868-1673">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1673">Format</span></span>

<span data-ttu-id="39868-1674">Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1675">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1675">Pattern</span></span>

<span data-ttu-id="39868-1676">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39868-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="39868-1677">Seis dígitos en el formato DDMMAA que son una fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="39868-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="39868-1678">Marcador del siglo (ya sea '-', '+' o 'a')</span><span class="sxs-lookup"><span data-stu-id="39868-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="39868-1679">Número de identificación personal de tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="39868-1680">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1681">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1681">Checksum</span></span>

<span data-ttu-id="39868-1682">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1683">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1683">Definition</span></span>

<span data-ttu-id="39868-1684">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1685">La función Func_finnish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1686">Se encuentra una palabra clave de Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="39868-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="39868-1687">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-1688">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1688">Keywords</span></span>

- <span data-ttu-id="39868-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="39868-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="39868-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="39868-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="39868-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="39868-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="39868-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="39868-1692">Personbeteckning</span></span>
- <span data-ttu-id="39868-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="39868-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="39868-1694">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="39868-1694">Finland Passport Number</span></span>

<span data-ttu-id="39868-p130">Formato de combinación de nueve letras y dígitos combinación de patrón de nueve letras y dígitos: directiva de dos letras (no entre mayúsculas y minúsculas) siete dígitos DLP de una definición de suma de comprobación No está seguro de que ha detectado este tipo de información confidencial si al 75%, comprendido en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_finland_passport_number. <!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity> Erta pasiva de Passport de Keyword_finland_passport_number palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="39868-1699">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="39868-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1700">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1700">Format</span></span>

<span data-ttu-id="39868-1701">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1702">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1702">Pattern</span></span>

<span data-ttu-id="39868-1703">12 dígitos con validación para descontar patrones similares como los números de teléfono franceses</span><span class="sxs-lookup"><span data-stu-id="39868-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1704">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1704">Checksum</span></span>

<span data-ttu-id="39868-1705">No</span><span class="sxs-lookup"><span data-stu-id="39868-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1706">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1706">Definition</span></span>

<span data-ttu-id="39868-1707">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1708">La función Func_french_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1709">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="39868-1710">Se encuentra una palabra clave de Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="39868-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="39868-1711">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1712">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="39868-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="39868-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="39868-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39868-1714">drivers licence</span></span>
- <span data-ttu-id="39868-1715">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-1715">drivers license</span></span>
- <span data-ttu-id="39868-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="39868-1716">driving licence</span></span>
- <span data-ttu-id="39868-1717">licencia fuerzas</span><span class="sxs-lookup"><span data-stu-id="39868-1717">driving license</span></span>
- <span data-ttu-id="39868-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="39868-1718">permis de conduire</span></span>
- <span data-ttu-id="39868-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="39868-1719">licence number</span></span>
- <span data-ttu-id="39868-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="39868-1720">license number</span></span>
- <span data-ttu-id="39868-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="39868-1721">licence numbers</span></span>
- <span data-ttu-id="39868-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="39868-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="39868-1723">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="39868-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="39868-1724">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1724">Format</span></span>

<span data-ttu-id="39868-1725">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1726">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1726">Pattern</span></span>

<span data-ttu-id="39868-1727">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1728">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1728">Checksum</span></span>

<span data-ttu-id="39868-1729">No</span><span class="sxs-lookup"><span data-stu-id="39868-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1730">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1730">Definition</span></span>

<span data-ttu-id="39868-1731">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1732">La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-1733">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1733">Keywords</span></span>

<span data-ttu-id="39868-1734">Ninguno</span><span class="sxs-lookup"><span data-stu-id="39868-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="39868-1735">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="39868-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1736">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1736">Format</span></span>

<span data-ttu-id="39868-1737">Nueve dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="39868-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1738">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1738">Pattern</span></span>

<span data-ttu-id="39868-1739">Nueve dígitos y letras:</span><span class="sxs-lookup"><span data-stu-id="39868-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="39868-1740">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1740">Two digits</span></span> 
- <span data-ttu-id="39868-1741">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="39868-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="39868-1742">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1743">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1743">Checksum</span></span>

<span data-ttu-id="39868-1744">No</span><span class="sxs-lookup"><span data-stu-id="39868-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1745">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1745">Definition</span></span>

<span data-ttu-id="39868-1746">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1747">La función Func_fr_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1748">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="39868-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-1749">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="39868-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="39868-1750">Keyword_passport</span></span>

- <span data-ttu-id="39868-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="39868-1751">Passport Number</span></span>
- <span data-ttu-id="39868-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="39868-1752">Passport No</span></span>
- <span data-ttu-id="39868-1753">Passport #
</span><span class="sxs-lookup"><span data-stu-id="39868-1753">Passport #</span></span>
- <span data-ttu-id="39868-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="39868-1754">Passport#</span></span>
- <span data-ttu-id="39868-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="39868-1755">PassportID</span></span>
- <span data-ttu-id="39868-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="39868-1756">Passportno</span></span>
- <span data-ttu-id="39868-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-1757">passportnumber</span></span>
- <span data-ttu-id="39868-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="39868-1758">パスポート</span></span>
- <span data-ttu-id="39868-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="39868-1759">パスポート番号</span></span>
- <span data-ttu-id="39868-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="39868-1760">パスポートのNum</span></span>
- <span data-ttu-id="39868-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="39868-1761">パスポート ＃</span></span> 
- <span data-ttu-id="39868-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="39868-1762">Numéro de passeport</span></span>
- <span data-ttu-id="39868-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="39868-1763">Passeport n °</span></span>
- <span data-ttu-id="39868-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="39868-1764">Passeport Non</span></span>
- <span data-ttu-id="39868-1765">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="39868-1765">Passeport #</span></span>
- <span data-ttu-id="39868-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="39868-1766">Passeport#</span></span>
- <span data-ttu-id="39868-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="39868-1767">PasseportNon</span></span>
- <span data-ttu-id="39868-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="39868-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="39868-1769">Número de seguridad social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="39868-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="39868-1770">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1770">Format</span></span>

<span data-ttu-id="39868-1771">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1772">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1772">Pattern</span></span>

<span data-ttu-id="39868-1773">Debe coincidir uno de los dos patrones:</span><span class="sxs-lookup"><span data-stu-id="39868-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="39868-1774">13 dígitos seguidos de un espacio seguido de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1774">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="39868-1775">o</span><span class="sxs-lookup"><span data-stu-id="39868-1775">or</span></span>
- <span data-ttu-id="39868-1776">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1777">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1777">Checksum</span></span>

<span data-ttu-id="39868-1778">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1779">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1779">Definition</span></span>

<span data-ttu-id="39868-1780">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1781">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1782">Se encuentra una palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="39868-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="39868-1783">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1783">The checksum passes.</span></span>

<span data-ttu-id="39868-1784">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1785">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1786">No se encuentra ninguna palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="39868-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="39868-1787">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1788">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="39868-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="39868-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="39868-1790">insee</span><span class="sxs-lookup"><span data-stu-id="39868-1790">insee</span></span>
- <span data-ttu-id="39868-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="39868-1791">securité sociale</span></span>
- <span data-ttu-id="39868-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="39868-1792">securite sociale</span></span>
- <span data-ttu-id="39868-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="39868-1793">national id</span></span>
- <span data-ttu-id="39868-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="39868-1794">national identification</span></span>
- <span data-ttu-id="39868-1795">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="39868-1795">numéro d'identité</span></span>
- <span data-ttu-id="39868-1796">sin FEC ' identité</span><span class="sxs-lookup"><span data-stu-id="39868-1796">no d'identité</span></span>
- <span data-ttu-id="39868-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="39868-p131">no. d'identité</span></span>
- <span data-ttu-id="39868-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="39868-1799">numero d'identite</span></span>
- <span data-ttu-id="39868-1800">No hay d'identite</span><span class="sxs-lookup"><span data-stu-id="39868-1800">no d'identite</span></span>
- <span data-ttu-id="39868-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="39868-p132">no. d'identite</span></span>
- <span data-ttu-id="39868-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="39868-1803">social security number</span></span>
- <span data-ttu-id="39868-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="39868-1804">social security code</span></span>
- <span data-ttu-id="39868-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="39868-1805">social insurance number</span></span>
- <span data-ttu-id="39868-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="39868-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="39868-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="39868-1807">d'identité nationale</span></span>
- <span data-ttu-id="39868-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="39868-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="39868-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="39868-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="39868-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="39868-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="39868-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="39868-1811">numéro de sécu</span></span>
- <span data-ttu-id="39868-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="39868-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="39868-1813">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="39868-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1814">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1814">Format</span></span>

<span data-ttu-id="39868-1815">Combinación de 11 dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="39868-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1816">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1816">Pattern</span></span>

<span data-ttu-id="39868-1817">11 dígitos y letras (no distingue entre mayúsculas y minúsculas):</span><span class="sxs-lookup"><span data-stu-id="39868-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="39868-1818">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="39868-1818">A digit or letter</span></span> 
- <span data-ttu-id="39868-1819">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1819">Two digits</span></span> 
- <span data-ttu-id="39868-1820">Seis dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="39868-1820">Six digits or letters</span></span> 
- <span data-ttu-id="39868-1821">Un dígito</span><span class="sxs-lookup"><span data-stu-id="39868-1821">A digit</span></span> 
- <span data-ttu-id="39868-1822">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="39868-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1823">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1823">Checksum</span></span>

<span data-ttu-id="39868-1824">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1825">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1825">Definition</span></span>

<span data-ttu-id="39868-1826">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1827">La función Func_german_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1828">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="39868-1829">Se encuentra una palabra clave de Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="39868-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="39868-1830">Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="39868-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="39868-1831">Se encuentra una palabra clave de Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="39868-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="39868-1832">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1833">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="39868-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="39868-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="39868-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="39868-1835">Führerschein</span></span>
- <span data-ttu-id="39868-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="39868-1836">Fuhrerschein</span></span>
- <span data-ttu-id="39868-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="39868-1837">Fuehrerschein</span></span>
- <span data-ttu-id="39868-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="39868-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="39868-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="39868-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="39868-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="39868-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="39868-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="39868-1841">Führerschein-</span></span> 
- <span data-ttu-id="39868-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="39868-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="39868-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="39868-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="39868-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="39868-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="39868-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="39868-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="39868-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="39868-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="39868-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="39868-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="39868-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="39868-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="39868-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="39868-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="39868-1850">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="39868-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="39868-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="39868-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="39868-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="39868-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="39868-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="39868-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="39868-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="39868-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="39868-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="39868-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="39868-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="39868-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="39868-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="39868-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="39868-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="39868-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="39868-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="39868-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="39868-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="39868-1862">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="39868-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="39868-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="39868-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="39868-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="39868-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="39868-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="39868-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="39868-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="39868-1868">DL</span><span class="sxs-lookup"><span data-stu-id="39868-1868">DL</span></span> 
- <span data-ttu-id="39868-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="39868-1869">DLS</span></span>
- <span data-ttu-id="39868-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="39868-1870">Driv Lic</span></span> 
- <span data-ttu-id="39868-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="39868-1871">Driv Licen</span></span> 
- <span data-ttu-id="39868-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="39868-1872">Driv License</span></span>
- <span data-ttu-id="39868-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="39868-1873">Driv Licenses</span></span> 
- <span data-ttu-id="39868-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="39868-1874">Driv Licence</span></span> 
- <span data-ttu-id="39868-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="39868-1875">Driv Licences</span></span> 
- <span data-ttu-id="39868-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="39868-1876">Driv Lic</span></span> 
- <span data-ttu-id="39868-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="39868-1877">Driver Licen</span></span> 
- <span data-ttu-id="39868-1878">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-1878">Driver License</span></span> 
- <span data-ttu-id="39868-1879">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-1879">Driver Licenses</span></span> 
- <span data-ttu-id="39868-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="39868-1880">Driver Licence</span></span> 
- <span data-ttu-id="39868-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="39868-1881">Driver Licences</span></span> 
- <span data-ttu-id="39868-1882">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-1882">Drivers Lic</span></span> 
- <span data-ttu-id="39868-1883">Controladores Licen</span><span class="sxs-lookup"><span data-stu-id="39868-1883">Drivers Licen</span></span> 
- <span data-ttu-id="39868-1884">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-1884">Drivers License</span></span> 
- <span data-ttu-id="39868-1885">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="39868-1886">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-1886">Drivers Licence</span></span> 
- <span data-ttu-id="39868-1887">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-1887">Drivers Licences</span></span> 
- <span data-ttu-id="39868-1888">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-1888">Driver's Lic</span></span> 
- <span data-ttu-id="39868-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="39868-1889">Driver's Licen</span></span> 
- <span data-ttu-id="39868-1890">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="39868-1890">Driver's License</span></span> 
- <span data-ttu-id="39868-1891">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="39868-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="39868-1892">Driver's Licence</span></span> 
- <span data-ttu-id="39868-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="39868-1893">Driver's Licences</span></span> 
- <span data-ttu-id="39868-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="39868-1894">Driving Lic</span></span> 
- <span data-ttu-id="39868-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="39868-1895">Driving Licen</span></span> 
- <span data-ttu-id="39868-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="39868-1896">Driving License</span></span> 
- <span data-ttu-id="39868-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="39868-1897">Driving Licenses</span></span> 
- <span data-ttu-id="39868-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="39868-1898">Driving Licence</span></span> 
- <span data-ttu-id="39868-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="39868-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="39868-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="39868-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="39868-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="39868-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="39868-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="39868-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1904">No-Führerschein</span></span> 
- <span data-ttu-id="39868-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="39868-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="39868-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1907">N-Führerschein</span></span> 
- <span data-ttu-id="39868-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="39868-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="39868-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="39868-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="39868-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="39868-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="39868-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1913">No-Führerschein</span></span> 
- <span data-ttu-id="39868-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="39868-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="39868-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1916">N-Führerschein</span></span> 
- <span data-ttu-id="39868-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="39868-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="39868-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="39868-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="39868-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="39868-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="39868-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="39868-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="39868-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="39868-1921">ausstellungsort</span></span>
- <span data-ttu-id="39868-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="39868-1922">ausstellende behöde</span></span>
- <span data-ttu-id="39868-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="39868-1923">ausstellende behorde</span></span>
- <span data-ttu-id="39868-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="39868-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="39868-1925">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="39868-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1926">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1926">Format</span></span>

<span data-ttu-id="39868-1927">10 dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="39868-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1928">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1928">Pattern</span></span>

<span data-ttu-id="39868-1929">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39868-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="39868-1930">El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="39868-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="39868-1931">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1931">Three digits</span></span> 
- <span data-ttu-id="39868-1932">Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="39868-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="39868-1933">Un dígito</span><span class="sxs-lookup"><span data-stu-id="39868-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1934">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1934">Checksum</span></span>

<span data-ttu-id="39868-1935">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1936">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1936">Definition</span></span>

<span data-ttu-id="39868-1937">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1938">La función Func_german_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1939">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="39868-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="39868-1940">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1940">The checksum passes.</span></span>

<span data-ttu-id="39868-1941">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1942">La función Func_german_passport_data encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1943">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="39868-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="39868-1944">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-1945">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="39868-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="39868-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="39868-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="39868-1947">reisepass</span></span>
- <span data-ttu-id="39868-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="39868-1948">reisepasse</span></span>
- <span data-ttu-id="39868-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="39868-1949">reisepassnummer</span></span>
- <span data-ttu-id="39868-1950">passport</span><span class="sxs-lookup"><span data-stu-id="39868-1950">passport</span></span>
- <span data-ttu-id="39868-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="39868-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="39868-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="39868-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="39868-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="39868-1953">geburtsdatum</span></span>
- <span data-ttu-id="39868-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="39868-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="39868-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="39868-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="39868-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="39868-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="39868-1957">No-Reisepass n-Reisepass</span><span class="sxs-lookup"><span data-stu-id="39868-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="39868-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="39868-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="39868-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="39868-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="39868-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="39868-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="39868-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="39868-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="39868-1962">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="39868-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-1963">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1963">Format</span></span>

<span data-ttu-id="39868-1964">Desde el 1 de noviembre de 2010: nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="39868-1965">Desde el 1 de abril de 1987 hasta 31 dígitos de 2010:10 de octubre</span><span class="sxs-lookup"><span data-stu-id="39868-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1966">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1966">Pattern</span></span>

<span data-ttu-id="39868-1967">Desde el 1 de noviembre de 2010:</span><span class="sxs-lookup"><span data-stu-id="39868-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="39868-1968">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="39868-1969">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1969">Eight digits</span></span>

<span data-ttu-id="39868-1970">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:</span><span class="sxs-lookup"><span data-stu-id="39868-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="39868-1971">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1972">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1972">Checksum</span></span>

<span data-ttu-id="39868-1973">No</span><span class="sxs-lookup"><span data-stu-id="39868-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-1974">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-1974">Definition</span></span>

<span data-ttu-id="39868-1975">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-1976">La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-1977">Se encuentra una palabra clave de Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="39868-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-1978">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="39868-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="39868-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="39868-1980">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="39868-1980">Identity Card</span></span>
- <span data-ttu-id="39868-1981">ID</span><span class="sxs-lookup"><span data-stu-id="39868-1981">ID</span></span>
- <span data-ttu-id="39868-1982">Identificación</span><span class="sxs-lookup"><span data-stu-id="39868-1982">Identification</span></span>
- <span data-ttu-id="39868-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="39868-1983">Personalausweis</span></span>
- <span data-ttu-id="39868-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="39868-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="39868-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="39868-1985">Ausweis</span></span>
- <span data-ttu-id="39868-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="39868-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="39868-1987">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="39868-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="39868-1988">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-1988">Format</span></span>

<span data-ttu-id="39868-1989">Combinación de 7 u 8 letras y números más un guión</span><span class="sxs-lookup"><span data-stu-id="39868-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-1990">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-1990">Pattern</span></span>

<span data-ttu-id="39868-1991">Siete letras y números (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="39868-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="39868-1992">Una letra (cualquier letra del alfabeto griego) </span><span class="sxs-lookup"><span data-stu-id="39868-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="39868-1993">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-1993">A dash</span></span> 
- <span data-ttu-id="39868-1994">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1994">Six digits</span></span>

<span data-ttu-id="39868-1995">Ocho letras y números (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="39868-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="39868-1996">Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="39868-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="39868-1997">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-1997">A dash</span></span> 
- <span data-ttu-id="39868-1998">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-1999">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-1999">Checksum</span></span>

<span data-ttu-id="39868-2000">No</span><span class="sxs-lookup"><span data-stu-id="39868-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2001">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2001">Definition</span></span>

<span data-ttu-id="39868-2002">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2003">La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2004">Se encuentra una palabra clave de Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="39868-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2005">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="39868-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="39868-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="39868-2007">Tarjeta de identidad griega</span><span class="sxs-lookup"><span data-stu-id="39868-2007">Greek identity Card</span></span>
- <span data-ttu-id="39868-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="39868-2008">Tautotita</span></span>
- <span data-ttu-id="39868-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="39868-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="39868-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="39868-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="39868-2011">Número de tarjeta de identidad de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="39868-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2012">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2012">Format</span></span>

<span data-ttu-id="39868-2013">Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final</span><span class="sxs-lookup"><span data-stu-id="39868-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2014">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2014">Pattern</span></span>

<span data-ttu-id="39868-2015">Combinación de 8 o 9 letras:</span><span class="sxs-lookup"><span data-stu-id="39868-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="39868-2016">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="39868-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="39868-2017">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2017">Six digits</span></span> 
- <span data-ttu-id="39868-2018">El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="39868-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2019">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2019">Checksum</span></span>

<span data-ttu-id="39868-2020">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2021">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2021">Definition</span></span>

<span data-ttu-id="39868-2022">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2023">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2024">Se encuentra una palabra clave de Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="39868-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="39868-2025">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2025">The checksum passes.</span></span>

<span data-ttu-id="39868-2026">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2027">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2028">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2029">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="39868-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="39868-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="39868-2031">Tarjeta de identidad de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="39868-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="39868-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="39868-2032">HKID</span></span>
- <span data-ttu-id="39868-2033">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-2033">ID card</span></span>
- <span data-ttu-id="39868-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="39868-2034">香港身份證</span></span> 
- <span data-ttu-id="39868-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="39868-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="39868-2036">Número de cuenta permanente de India (PAN)</span><span class="sxs-lookup"><span data-stu-id="39868-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="39868-2037">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2037">Format</span></span>

<span data-ttu-id="39868-2038">10 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2039">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2039">Pattern</span></span>

<span data-ttu-id="39868-2040">10 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2040">10 letters or digits:</span></span>
- <span data-ttu-id="39868-2041">Cinco letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="39868-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="39868-2042">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2042">Four digits</span></span> 
- <span data-ttu-id="39868-2043">Una letra que es un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="39868-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2044">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2044">Checksum</span></span>

<span data-ttu-id="39868-2045">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2046">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2046">Definition</span></span>

<span data-ttu-id="39868-2047">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2048">La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2049">Se encuentra una palabra clave de Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="39868-2050">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2051">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="39868-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="39868-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="39868-2053">Número de cuenta permanente
</span><span class="sxs-lookup"><span data-stu-id="39868-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="39868-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="39868-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="39868-2055">Número de identificación único (Aadhaar) de la India</span><span class="sxs-lookup"><span data-stu-id="39868-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2056">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2056">Format</span></span>

<span data-ttu-id="39868-2057">12 dígitos que contienen espacios o guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="39868-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2058">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2058">Pattern</span></span>

<span data-ttu-id="39868-2059">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2059">12 digits:</span></span>
- <span data-ttu-id="39868-2060">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2060">Four digits</span></span> 
- <span data-ttu-id="39868-2061">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="39868-2061">An optional space or dash</span></span> 
- <span data-ttu-id="39868-2062">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2062">Four digits</span></span> 
- <span data-ttu-id="39868-2063">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="39868-2063">An optional space or dash</span></span> 
- <span data-ttu-id="39868-2064">El dígito final que es el dígito de control</span><span class="sxs-lookup"><span data-stu-id="39868-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2065">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2065">Checksum</span></span>

<span data-ttu-id="39868-2066">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2067">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2067">Definition</span></span>

<span data-ttu-id="39868-p133">Una directiva de DLP es 85% seguro de que ha detectado este tipo de información confidencial if, dentro de una proximidad de 300 caracteres: la función Func_india_aadhaar busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_india_aadhar. Pasa la suma de comprobación. Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la función Func_india_aadhaar busca contenido que coincide con el patrón. Pasa la suma de comprobación. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="39868-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="39868-2074">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="39868-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="39868-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="39868-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="39868-2076">Aadhar</span></span>
- <span data-ttu-id="39868-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="39868-2077">Aadhaar</span></span>
- <span data-ttu-id="39868-2078">UID</span><span class="sxs-lookup"><span data-stu-id="39868-2078">UID</span></span>
- <span data-ttu-id="39868-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="39868-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="39868-2080">Número de tarjeta de identidad (KTP) de Indonesia</span><span class="sxs-lookup"><span data-stu-id="39868-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2081">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2081">Format</span></span>

<span data-ttu-id="39868-2082">16 dígitos que contienen puntos opcionales</span><span class="sxs-lookup"><span data-stu-id="39868-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2083">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2083">Pattern</span></span>

<span data-ttu-id="39868-2084">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2084">16 digits:</span></span>
- <span data-ttu-id="39868-2085">Código de la provincia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2085">Two-digit province code</span></span> 
- <span data-ttu-id="39868-2086">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2086">A period (optional)</span></span> 
- <span data-ttu-id="39868-2087">Código de ciudad o regencia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="39868-2088">Código de subdistrito de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="39868-2089">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2089">A period (optional)</span></span> 
- <span data-ttu-id="39868-2090">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="39868-2091">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2091">A period (optional)</span></span> 
- <span data-ttu-id="39868-2092">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2093">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2093">Checksum</span></span>

<span data-ttu-id="39868-2094">No</span><span class="sxs-lookup"><span data-stu-id="39868-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2095">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2095">Definition</span></span>

<span data-ttu-id="39868-2096">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2097">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2098">Se encuentra una palabra clave de Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="39868-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="39868-2099">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2100">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2101">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="39868-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="39868-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="39868-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="39868-2103">KTP</span></span>
- <span data-ttu-id="39868-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="39868-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="39868-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="39868-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="39868-2106">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="39868-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="39868-2107">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2107">Format</span></span>

<span data-ttu-id="39868-2108">Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)
</span><span class="sxs-lookup"><span data-stu-id="39868-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2109">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2109">Pattern</span></span>

<span data-ttu-id="39868-2110">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39868-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="39868-2111">Código de país de dos letras</span><span class="sxs-lookup"><span data-stu-id="39868-2111">Two-letter country code</span></span>
- <span data-ttu-id="39868-2112">Dos dígitos de control (seguidos de un espacio opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="39868-2113">1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)</span><span class="sxs-lookup"><span data-stu-id="39868-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="39868-2114">1-3 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2114">1-3 letters or digits</span></span>

<span data-ttu-id="39868-p134">El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:</span><span class="sxs-lookup"><span data-stu-id="39868-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="39868-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="39868-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2118">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2118">Checksum</span></span>

<span data-ttu-id="39868-2119">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2120">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2120">Definition</span></span>

<span data-ttu-id="39868-2121">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2122">La función Func_iban encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2123">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2124">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2124">Keywords</span></span>

<span data-ttu-id="39868-2125">Ninguno</span><span class="sxs-lookup"><span data-stu-id="39868-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="39868-2126">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="39868-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="39868-2127">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="39868-2128">IPv4:</span><span class="sxs-lookup"><span data-stu-id="39868-2128">IPv4:</span></span>
<span data-ttu-id="39868-2129">Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="39868-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="39868-2130">IPv6:</span><span class="sxs-lookup"><span data-stu-id="39868-2130">IPv6:</span></span>
<span data-ttu-id="39868-2131"> Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)</span><span class="sxs-lookup"><span data-stu-id="39868-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2132">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2133">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2133">Checksum</span></span>

<span data-ttu-id="39868-2134">No</span><span class="sxs-lookup"><span data-stu-id="39868-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2135">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2135">Definition</span></span>

<span data-ttu-id="39868-2136">Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2137">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2138">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="39868-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="39868-2139">Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2140">La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2141">Se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="39868-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="39868-2142">Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2143">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2144">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="39868-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2145">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="39868-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="39868-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="39868-2147">IP (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="39868-2148">dirección IP
</span><span class="sxs-lookup"><span data-stu-id="39868-2148">ip address</span></span> 
- <span data-ttu-id="39868-2149">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="39868-2149">ip addresses</span></span>
- <span data-ttu-id="39868-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="39868-2150">internet protocol</span></span>
- <span data-ttu-id="39868-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="39868-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="39868-2152">Clasificación internacional de enfermedades (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="39868-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="39868-2153">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2153">Format</span></span>

<span data-ttu-id="39868-2154">Diccionario</span><span class="sxs-lookup"><span data-stu-id="39868-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2155">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2155">Pattern</span></span>

<span data-ttu-id="39868-2156">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="39868-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2157">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2157">Checksum</span></span>

<span data-ttu-id="39868-2158">No</span><span class="sxs-lookup"><span data-stu-id="39868-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2159">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2159">Definition</span></span>

<span data-ttu-id="39868-2160">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2161">Se ha encontrado una palabra clave de Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="39868-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="39868-2162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2162">Keywords</span></span>

<span data-ttu-id="39868-p135">Cualquiera de los términos del diccionario de palabra clave Dictionary_icd_10_cm, que se basa en la [clasificación internacional de enfermedades, revisión décima, modificación ensayos (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo sólo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="39868-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="39868-2165">Clasificación internacional de enfermedades (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="39868-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="39868-2166">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2166">Format</span></span>

<span data-ttu-id="39868-2167">Diccionario</span><span class="sxs-lookup"><span data-stu-id="39868-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2168">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2168">Pattern</span></span>

<span data-ttu-id="39868-2169">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="39868-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2170">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2170">Checksum</span></span>

<span data-ttu-id="39868-2171">No</span><span class="sxs-lookup"><span data-stu-id="39868-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2172">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2172">Definition</span></span>

<span data-ttu-id="39868-2173">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2174">Se ha encontrado una palabra clave de Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="39868-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2175">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2175">Keywords</span></span>

<span data-ttu-id="39868-p136">Cualquiera de los términos del diccionario de palabra clave Dictionary_icd_9_cm, que se basa en la [clasificación internacional de enfermedades, revisión del noveno, modificación ensayos (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo sólo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="39868-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="39868-2178">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="39868-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2179">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2179">Format</span></span>

<span data-ttu-id="39868-2180">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="39868-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="39868-2181">Siete dígitos seguidos por 1 o 2 letras </span><span class="sxs-lookup"><span data-stu-id="39868-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="39868-2182">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="39868-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="39868-2183">Siete dígitos seguidos por dos letras</span><span class="sxs-lookup"><span data-stu-id="39868-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2184">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2184">Pattern</span></span>

<span data-ttu-id="39868-2185">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="39868-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="39868-2186">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2186">Seven digits</span></span> 
- <span data-ttu-id="39868-2187">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="39868-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="39868-2188">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="39868-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="39868-2189">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2189">Seven digits</span></span> 
- <span data-ttu-id="39868-2190">Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético </span><span class="sxs-lookup"><span data-stu-id="39868-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="39868-2191">La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2192">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2192">Checksum</span></span>

<span data-ttu-id="39868-2193">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2194">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2194">Definition</span></span>

<span data-ttu-id="39868-2195">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2196">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2197">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-2197">One of the following is true:</span></span>
    - <span data-ttu-id="39868-2198">Se encuentra una palabra clave de Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="39868-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="39868-2199">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="39868-2200">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2200">The checksum passes.</span></span>

<span data-ttu-id="39868-2201">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2202">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2203">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2204">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="39868-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="39868-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="39868-2206">Número de servicio público personal 
</span><span class="sxs-lookup"><span data-stu-id="39868-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="39868-2207">Número de PPS
</span><span class="sxs-lookup"><span data-stu-id="39868-2207">PPS Number</span></span> 
- <span data-ttu-id="39868-2208">Núm. PPS
</span><span class="sxs-lookup"><span data-stu-id="39868-2208">PPS Num</span></span> 
- <span data-ttu-id="39868-2209">N.º PPS
</span><span class="sxs-lookup"><span data-stu-id="39868-2209">PPS No.</span></span> 
- <span data-ttu-id="39868-2210">N.ro PPS
</span><span class="sxs-lookup"><span data-stu-id="39868-2210">PPS #</span></span> 
- <span data-ttu-id="39868-2211">PPS #</span><span class="sxs-lookup"><span data-stu-id="39868-2211">PPS#</span></span> 
- <span data-ttu-id="39868-2212">NPPS
</span><span class="sxs-lookup"><span data-stu-id="39868-2212">PPSN</span></span> 
- <span data-ttu-id="39868-2213">Tarjeta de servicios públicos
</span><span class="sxs-lookup"><span data-stu-id="39868-2213">Public Services Card</span></span> 
- <span data-ttu-id="39868-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="39868-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="39868-p137">Uimh. PSP
</span><span class="sxs-lookup"><span data-stu-id="39868-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="39868-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="39868-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="39868-2218">Número de cuenta bancaria de Israel</span><span class="sxs-lookup"><span data-stu-id="39868-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2219">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2219">Format</span></span>

<span data-ttu-id="39868-2220">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2221">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2221">Pattern</span></span>

<span data-ttu-id="39868-2222">Con formato:</span><span class="sxs-lookup"><span data-stu-id="39868-2222">Formatted:</span></span>
- <span data-ttu-id="39868-2223">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2223">Two digits</span></span> 
- <span data-ttu-id="39868-2224">Guion</span><span class="sxs-lookup"><span data-stu-id="39868-2224">A dash</span></span> 
- <span data-ttu-id="39868-2225">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2225">Three digits</span></span> 
- <span data-ttu-id="39868-2226">Guion</span><span class="sxs-lookup"><span data-stu-id="39868-2226">A dash</span></span> 
- <span data-ttu-id="39868-2227">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2227">Eight digits</span></span>

<span data-ttu-id="39868-2228">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="39868-2228">Unformatted:</span></span>
- <span data-ttu-id="39868-2229">	13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2230">Checksum</span></span>

<span data-ttu-id="39868-2231">No</span><span class="sxs-lookup"><span data-stu-id="39868-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2232">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2232">Definition</span></span>

<span data-ttu-id="39868-2233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2234">La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2235">Se encuentra una palabra clave de Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="39868-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="39868-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="39868-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2238">Bank Account Number</span></span> 
- <span data-ttu-id="39868-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="39868-2239">Bank Account</span></span> 
- <span data-ttu-id="39868-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2240">Account Number</span></span> 
- <span data-ttu-id="39868-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="39868-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="39868-2242">Identificación nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="39868-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="39868-2243">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2243">Format</span></span>

<span data-ttu-id="39868-2244">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2245">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2245">Pattern</span></span>

<span data-ttu-id="39868-2246">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2247">Checksum</span></span>

<span data-ttu-id="39868-2248">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2249">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2249">Definition</span></span>

<span data-ttu-id="39868-2250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2251">La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2252">Se encuentra una palabra clave de Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="39868-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="39868-2253">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2254">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="39868-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="39868-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="39868-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="39868-2256">מספר זהות</span></span> 
- <span data-ttu-id="39868-2257">National ID Number</span><span class="sxs-lookup"><span data-stu-id="39868-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="39868-2258">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="39868-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2259">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2259">Format</span></span>

<span data-ttu-id="39868-2260">Una combinación de 10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2261">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2261">Pattern</span></span>

- <span data-ttu-id="39868-2262">Una combinación de 10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="39868-2263">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="39868-2264">La letra "A" o "V" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="39868-2265">Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado</span><span class="sxs-lookup"><span data-stu-id="39868-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="39868-2266">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2267">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2267">Checksum</span></span>

<span data-ttu-id="39868-2268">No</span><span class="sxs-lookup"><span data-stu-id="39868-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2269">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2269">Definition</span></span>

<span data-ttu-id="39868-2270">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2271">La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2272">Se encuentra una palabra clave de Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2273">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="39868-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="39868-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="39868-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="39868-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="39868-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="39868-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="39868-2277">Número de cuenta bancaria de Japón</span><span class="sxs-lookup"><span data-stu-id="39868-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2278">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2278">Format</span></span>

<span data-ttu-id="39868-2279">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2280">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2280">Pattern</span></span>

<span data-ttu-id="39868-2281">Número de cuenta bancaria:</span><span class="sxs-lookup"><span data-stu-id="39868-2281">Bank account number:</span></span>
- <span data-ttu-id="39868-2282">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2282">Seven or eight digits</span></span>
- <span data-ttu-id="39868-2283">Código de sucursal del banco:</span><span class="sxs-lookup"><span data-stu-id="39868-2283">Bank account branch code:</span></span>
- <span data-ttu-id="39868-2284">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2284">Four digits</span></span> 
- <span data-ttu-id="39868-2285">Un espacio o un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="39868-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="39868-2286">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2286">Three digits</span></span>

<span data-ttu-id="39868-2287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2287">Checksum</span></span>

<span data-ttu-id="39868-2288">No</span><span class="sxs-lookup"><span data-stu-id="39868-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2289">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2289">Definition</span></span>

<span data-ttu-id="39868-2290">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2291">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2292">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="39868-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="39868-2293">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-2293">One of the following is true:</span></span>
- <span data-ttu-id="39868-2294">La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2295">Se encuentra una palabra clave de Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="39868-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="39868-2296">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2297">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2298">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="39868-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2299">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="39868-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="39868-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="39868-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2301">Checking Account Number</span></span> 
- <span data-ttu-id="39868-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="39868-2302">Checking Account</span></span> 
- <span data-ttu-id="39868-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-2303">Checking Account #</span></span> 
- <span data-ttu-id="39868-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="39868-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-2305">Checking Acct #</span></span> 
- <span data-ttu-id="39868-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="39868-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2307">Checking Account No.</span></span> 
- <span data-ttu-id="39868-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2308">Bank Account Number</span></span> 
- <span data-ttu-id="39868-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="39868-2309">Bank Account</span></span> 
- <span data-ttu-id="39868-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-2310">Bank Account #</span></span> 
- <span data-ttu-id="39868-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="39868-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-2312">Bank Acct #</span></span> 
- <span data-ttu-id="39868-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="39868-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2314">Bank Account No.</span></span> 
- <span data-ttu-id="39868-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2315">Savings Account Number</span></span> 
- <span data-ttu-id="39868-2316">Cuenta de ahorro</span><span class="sxs-lookup"><span data-stu-id="39868-2316">Savings Account</span></span> 
- <span data-ttu-id="39868-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-2317">Savings Account #</span></span> 
- <span data-ttu-id="39868-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="39868-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-2319">Savings Acct #</span></span> 
- <span data-ttu-id="39868-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="39868-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2321">Savings Account No.</span></span> 
- <span data-ttu-id="39868-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2322">Debit Account Number</span></span> 
- <span data-ttu-id="39868-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="39868-2323">Debit Account</span></span> 
- <span data-ttu-id="39868-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-2324">Debit Account #</span></span> 
- <span data-ttu-id="39868-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="39868-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-2326">Debit Acct #</span></span> 
- <span data-ttu-id="39868-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="39868-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2328">Debit Account No.</span></span> 
- <span data-ttu-id="39868-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="39868-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="39868-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="39868-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="39868-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="39868-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="39868-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="39868-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="39868-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="39868-2333">口座番号の確認</span></span> 
- <span data-ttu-id="39868-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="39868-2334">銀行口座番号</span></span> 
- <span data-ttu-id="39868-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="39868-2335">銀行口座</span></span> 
- <span data-ttu-id="39868-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2336">銀行口座＃</span></span> 
- <span data-ttu-id="39868-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="39868-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="39868-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="39868-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="39868-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="39868-2340">銀行口座番号</span></span>
- <span data-ttu-id="39868-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="39868-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="39868-2342">預金口座</span></span> 
- <span data-ttu-id="39868-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="39868-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="39868-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="39868-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="39868-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="39868-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="39868-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="39868-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="39868-2349">口座番号</span></span> 
- <span data-ttu-id="39868-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2350">口座番号＃</span></span> 
- <span data-ttu-id="39868-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="39868-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="39868-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="39868-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="39868-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="39868-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="39868-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="39868-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="39868-2357">Número de licencia de conductor de Japón</span><span class="sxs-lookup"><span data-stu-id="39868-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2358">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2358">Format</span></span>

<span data-ttu-id="39868-2359">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2360">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2360">Pattern</span></span>

<span data-ttu-id="39868-2361">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2362">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2362">Checksum</span></span>

<span data-ttu-id="39868-2363">No</span><span class="sxs-lookup"><span data-stu-id="39868-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2364">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2364">Definition</span></span>

<span data-ttu-id="39868-2365">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2366">La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2367">Se encuentra una palabra clave de Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2368">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="39868-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="39868-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="39868-2370">dl#</span><span class="sxs-lookup"><span data-stu-id="39868-2370">dl#</span></span> 
- <span data-ttu-id="39868-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="39868-2371">DL＃</span></span> 
- <span data-ttu-id="39868-2372">dls#</span><span class="sxs-lookup"><span data-stu-id="39868-2372">dls#</span></span> 
- <span data-ttu-id="39868-2373">LISTAS DE DISTRIBUCIÓN #</span><span class="sxs-lookup"><span data-stu-id="39868-2373">DLS＃</span></span> 
- <span data-ttu-id="39868-2374">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="39868-2374">driver license</span></span> 
- <span data-ttu-id="39868-2375">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="39868-2375">driver licenses</span></span> 
- <span data-ttu-id="39868-2376">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-2376">drivers license</span></span> 
- <span data-ttu-id="39868-2377">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="39868-2377">driver's license</span></span> 
- <span data-ttu-id="39868-2378">permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-2378">drivers licenses</span></span> 
- <span data-ttu-id="39868-2379">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="39868-2379">driver's licenses</span></span> 
- <span data-ttu-id="39868-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="39868-2380">driving licence</span></span> 
- <span data-ttu-id="39868-2381">lic#</span><span class="sxs-lookup"><span data-stu-id="39868-2381">lic#</span></span> 
- <span data-ttu-id="39868-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="39868-2382">LIC＃</span></span> 
- <span data-ttu-id="39868-2383">lics#</span><span class="sxs-lookup"><span data-stu-id="39868-2383">lics#</span></span> 
- <span data-ttu-id="39868-2384">identificador de estado</span><span class="sxs-lookup"><span data-stu-id="39868-2384">state id</span></span> 
- <span data-ttu-id="39868-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="39868-2385">state identification</span></span> 
- <span data-ttu-id="39868-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="39868-2386">state identification number</span></span> 
- <span data-ttu-id="39868-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2387">低所得国＃</span></span> 
- <span data-ttu-id="39868-2388">免許証</span><span class="sxs-lookup"><span data-stu-id="39868-2388">免許証</span></span> 
- <span data-ttu-id="39868-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="39868-2389">状態ID</span></span>
- <span data-ttu-id="39868-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="39868-2390">状態の識別</span></span> 
- <span data-ttu-id="39868-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2391">状態の識別番号</span></span> 
- <span data-ttu-id="39868-2392">運転免許</span><span class="sxs-lookup"><span data-stu-id="39868-2392">運転免許</span></span> 
- <span data-ttu-id="39868-2393">運転免許証</span><span class="sxs-lookup"><span data-stu-id="39868-2393">運転免許証</span></span> 
- <span data-ttu-id="39868-2394">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="39868-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="39868-2395">Número de pasaporte de Japón</span><span class="sxs-lookup"><span data-stu-id="39868-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2396">Format</span></span>

<span data-ttu-id="39868-2397">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2398">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2398">Pattern</span></span>

<span data-ttu-id="39868-2399">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2400">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2400">Checksum</span></span>

<span data-ttu-id="39868-2401">No</span><span class="sxs-lookup"><span data-stu-id="39868-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2402">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2402">Definition</span></span>

<span data-ttu-id="39868-2403">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2404">La función Func_jp_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2405">Se encuentra una palabra clave de Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="39868-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2406">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="39868-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="39868-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="39868-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="39868-2408">パスポート</span></span> 
- <span data-ttu-id="39868-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2409">パスポート番号</span></span> 
- <span data-ttu-id="39868-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="39868-2410">パスポートのNum</span></span> 
- <span data-ttu-id="39868-2411">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="39868-2412">Número de registro de residente de Japón</span><span class="sxs-lookup"><span data-stu-id="39868-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2413">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2413">Format</span></span>

<span data-ttu-id="39868-2414">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2415">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2415">Pattern</span></span>

<span data-ttu-id="39868-2416">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2417">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2417">Checksum</span></span>

<span data-ttu-id="39868-2418">No</span><span class="sxs-lookup"><span data-stu-id="39868-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2419">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2419">Definition</span></span>

<span data-ttu-id="39868-2420">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2421">La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2422">Se encuentra una palabra clave de Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2423">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="39868-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="39868-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="39868-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="39868-2425">Resident Registration Number</span></span>
- <span data-ttu-id="39868-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2426">Resident Register Number</span></span> 
- <span data-ttu-id="39868-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="39868-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="39868-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2429">Resident Register No.</span></span> 
- <span data-ttu-id="39868-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="39868-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="39868-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="39868-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="39868-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="39868-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="39868-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="39868-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="39868-2436">Número de Seguridad Social de Japón (SIN)</span><span class="sxs-lookup"><span data-stu-id="39868-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="39868-2437">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2437">Format</span></span>

<span data-ttu-id="39868-2438">De 7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2439">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2439">Pattern</span></span>

<span data-ttu-id="39868-2440">7-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2440">7-12 digits:</span></span>
- <span data-ttu-id="39868-2441">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2441">Four digits</span></span> 
- <span data-ttu-id="39868-2442">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="39868-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="39868-2443">Seis dígitos o</span><span class="sxs-lookup"><span data-stu-id="39868-2443">Six digits OR</span></span>
- <span data-ttu-id="39868-2444">De 7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2445">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2445">Checksum</span></span>

<span data-ttu-id="39868-2446">No</span><span class="sxs-lookup"><span data-stu-id="39868-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2447">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2447">Definition</span></span>

<span data-ttu-id="39868-2448">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2449">La función Func_jp_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2450">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="39868-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="39868-2451">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2452">La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2453">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="39868-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2454">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="39868-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="39868-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="39868-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="39868-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="39868-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="39868-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="39868-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="39868-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="39868-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="39868-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="39868-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="39868-2461">Número de la tarjeta de identificación de Malasia</span><span class="sxs-lookup"><span data-stu-id="39868-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2462">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2462">Format</span></span>

<span data-ttu-id="39868-2463">12 dígitos que contienen guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="39868-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2464">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2464">Pattern</span></span>

<span data-ttu-id="39868-2465">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2465">12 digits:</span></span>
- <span data-ttu-id="39868-2466">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="39868-2467">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2467">A dash (optional)</span></span> 
- <span data-ttu-id="39868-2468">Código de dos letras del lugar de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="39868-2469">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2469">A dash (optional)</span></span> 
- <span data-ttu-id="39868-2470">Tres dígitos aleatorios </span><span class="sxs-lookup"><span data-stu-id="39868-2470">Three random digits</span></span> 
- <span data-ttu-id="39868-2471">Código de género de un dígito</span><span class="sxs-lookup"><span data-stu-id="39868-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2472">Checksum</span></span>

<span data-ttu-id="39868-2473">No</span><span class="sxs-lookup"><span data-stu-id="39868-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2474">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2474">Definition</span></span>

<span data-ttu-id="39868-2475">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2476">La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2477">Se encuentra una palabra clave de Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="39868-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="39868-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="39868-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="39868-2480">MyKad</span></span> 
- <span data-ttu-id="39868-2481">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="39868-2481">Identity Card</span></span> 
- <span data-ttu-id="39868-2482">Tarjeta de Id.</span><span class="sxs-lookup"><span data-stu-id="39868-2482">ID Card</span></span> 
- <span data-ttu-id="39868-2483">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-2483">Identification Card</span></span> 
- <span data-ttu-id="39868-2484">Tarjeta de solicitud digital
</span><span class="sxs-lookup"><span data-stu-id="39868-2484">Digital Application Card</span></span> 
- <span data-ttu-id="39868-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="39868-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="39868-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="39868-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="39868-2487">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="39868-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2488">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2488">Format</span></span>

<span data-ttu-id="39868-2489">8 o 9 dígitos que contienen espacios opcionales</span><span class="sxs-lookup"><span data-stu-id="39868-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2490">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2490">Pattern</span></span>

<span data-ttu-id="39868-2491">8 o 9 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2491">8-9 digits:</span></span>
- <span data-ttu-id="39868-2492">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2492">Three digits</span></span> 
- <span data-ttu-id="39868-2493">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2493">A space (optional)</span></span> 
- <span data-ttu-id="39868-2494">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2494">Three digits</span></span> 
- <span data-ttu-id="39868-2495">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="39868-2495">A space (optional)</span></span> 
- <span data-ttu-id="39868-2496">2 o 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2497">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2497">Checksum</span></span>

<span data-ttu-id="39868-2498">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2499">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2499">Definition</span></span>

<span data-ttu-id="39868-2500">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2501">La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2502">Se encuentra una palabra clave de Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="39868-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="39868-2503">La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="39868-2504">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2505">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="39868-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="39868-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="39868-2507">Número de servicio de ciudadanía
</span><span class="sxs-lookup"><span data-stu-id="39868-2507">Citizen service number</span></span> 
- <span data-ttu-id="39868-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="39868-2508">BSN</span></span> 
- <span data-ttu-id="39868-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="39868-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="39868-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="39868-2510">Sofinummer</span></span> 
- <span data-ttu-id="39868-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="39868-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="39868-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="39868-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="39868-2513">Número de Ministerio de salud de Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="39868-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2514">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2514">Format</span></span>

<span data-ttu-id="39868-2515">Tres letras, un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2516">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2516">Pattern</span></span>

<span data-ttu-id="39868-2517">Tres letras (no distinguir mayúsculas de minúsculas) un cuatro dígitos (opcional) espacio</span><span class="sxs-lookup"><span data-stu-id="39868-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2518">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2518">Checksum</span></span>

<span data-ttu-id="39868-2519">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2520">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2520">Definition</span></span>

<span data-ttu-id="39868-2521">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2522">La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2523">Se encuentra una palabra clave de Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="39868-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="39868-2524">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2524">The checksum passes.</span></span>

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

<span data-ttu-id="39868-2525">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2525">Keywords</span></span>

<span data-ttu-id="39868-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="39868-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="39868-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="39868-2527">NHI</span></span> 
- <span data-ttu-id="39868-2528">Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="39868-2528">New Zealand</span></span> 
- <span data-ttu-id="39868-2529">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="39868-2529">Health</span></span> 
- <span data-ttu-id="39868-2530">tratamiento
</span><span class="sxs-lookup"><span data-stu-id="39868-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="39868-2531">Número de identificación de Noruega</span><span class="sxs-lookup"><span data-stu-id="39868-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2532">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2532">Format</span></span>

<span data-ttu-id="39868-2533">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2534">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2534">Pattern</span></span>

<span data-ttu-id="39868-2535">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2535">11 digits:</span></span>
- <span data-ttu-id="39868-2536">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="39868-2537">Número individual de tres dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="39868-2538">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="39868-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2539">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2539">Checksum</span></span>

<span data-ttu-id="39868-2540">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2541">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2541">Definition</span></span>

<span data-ttu-id="39868-2542">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2543">La función Func_norway_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2544">Se encuentra una palabra clave de Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="39868-2545">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2545">The checksum passes.</span></span>
- <span data-ttu-id="39868-2546">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2547">La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2548">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2549">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="39868-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="39868-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="39868-2551">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="39868-2551">Personal identification number</span></span>
- <span data-ttu-id="39868-2552">Número de id. noruego</span><span class="sxs-lookup"><span data-stu-id="39868-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="39868-2553">Número de id.</span><span class="sxs-lookup"><span data-stu-id="39868-2553">ID Number</span></span>
- <span data-ttu-id="39868-2554">Identificación</span><span class="sxs-lookup"><span data-stu-id="39868-2554">Identification</span></span>
- <span data-ttu-id="39868-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="39868-2555">Personnummer</span></span>
- <span data-ttu-id="39868-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="39868-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="39868-2557">Número de id. universal unificado de Filipinas</span><span class="sxs-lookup"><span data-stu-id="39868-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2558">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2558">Format</span></span>

<span data-ttu-id="39868-2559">12 dígitos separados por guiones</span><span class="sxs-lookup"><span data-stu-id="39868-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2560">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2560">Pattern</span></span>

<span data-ttu-id="39868-2561">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2561">12 digits:</span></span>
- <span data-ttu-id="39868-2562">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2562">Four digits</span></span> 
- <span data-ttu-id="39868-2563">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-2563">A hyphen</span></span> 
- <span data-ttu-id="39868-2564">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2564">Seven digits</span></span> 
- <span data-ttu-id="39868-2565">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-2565">A hyphen</span></span> 
- <span data-ttu-id="39868-2566">Un dígito</span><span class="sxs-lookup"><span data-stu-id="39868-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2567">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2567">Checksum</span></span>

<span data-ttu-id="39868-2568">No</span><span class="sxs-lookup"><span data-stu-id="39868-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2569">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2569">Definition</span></span>

<span data-ttu-id="39868-2570">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2571">La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2572">Se encuentra una palabra clave de Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="39868-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2573">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="39868-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="39868-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="39868-2575">Id. universal unificado
</span><span class="sxs-lookup"><span data-stu-id="39868-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="39868-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="39868-2576">UMID</span></span> 
- <span data-ttu-id="39868-2577">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="39868-2577">Identity Card</span></span> 
- <span data-ttu-id="39868-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="39868-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="39868-2579">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="39868-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="39868-2580">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2580">Format</span></span>

<span data-ttu-id="39868-2581">Tres letras y seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2582">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2582">Pattern</span></span>

<span data-ttu-id="39868-2583">Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2584">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2584">Checksum</span></span>

<span data-ttu-id="39868-2585">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2586">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2586">Definition</span></span>

<span data-ttu-id="39868-p138">Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la función Func_polish_national_id busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_polish_national_id_passport_number. Pasa la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2590">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="39868-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="39868-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="39868-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="39868-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="39868-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="39868-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="39868-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="39868-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="39868-2596">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="39868-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="39868-2597">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2597">Format</span></span>

<span data-ttu-id="39868-2598">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2599">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2599">Pattern</span></span>

<span data-ttu-id="39868-2600">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2601">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2601">Checksum</span></span>

<span data-ttu-id="39868-2602">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2603">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2603">Definition</span></span>

<span data-ttu-id="39868-2604">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2605">La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2606">Se encuentra una palabra clave de Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="39868-2607">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2608">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="39868-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="39868-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="39868-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="39868-2610">Nr PESEL</span></span>
- <span data-ttu-id="39868-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="39868-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="39868-2612">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="39868-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="39868-2613">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2613">Format</span></span>

<span data-ttu-id="39868-2614">Dos letras y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2615">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2615">Pattern</span></span>

<span data-ttu-id="39868-2616">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2617">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2617">Checksum</span></span>

<span data-ttu-id="39868-2618">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2619">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2619">Definition</span></span>

<span data-ttu-id="39868-2620">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2621">La función Func_polish_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2622">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="39868-2623">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2624">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="39868-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="39868-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="39868-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="39868-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="39868-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="39868-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="39868-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="39868-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="39868-2630">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="39868-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2631">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2631">Format</span></span>

<span data-ttu-id="39868-2632">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2633">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2633">Pattern</span></span>

<span data-ttu-id="39868-2634">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2635">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2635">Checksum</span></span>

<span data-ttu-id="39868-2636">No</span><span class="sxs-lookup"><span data-stu-id="39868-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2637">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2637">Definition</span></span>

<span data-ttu-id="39868-2638">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2639">La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2640">Se encuentra una palabra clave de Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="39868-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2641">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="39868-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="39868-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="39868-2643">Tarjeta del ciudadano</span><span class="sxs-lookup"><span data-stu-id="39868-2643">Citizen Card</span></span>
- <span data-ttu-id="39868-2644">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="39868-2644">National ID Card</span></span>
- <span data-ttu-id="39868-2645">CC</span><span class="sxs-lookup"><span data-stu-id="39868-2645">CC</span></span>
- <span data-ttu-id="39868-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="39868-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="39868-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="39868-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="39868-2648">Identificación nacional de Arabia Saudí</span><span class="sxs-lookup"><span data-stu-id="39868-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="39868-2649">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2649">Format</span></span>

<span data-ttu-id="39868-2650">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2651">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2651">Pattern</span></span>

<span data-ttu-id="39868-2652">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2653">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2653">Checksum</span></span>

<span data-ttu-id="39868-2654">No</span><span class="sxs-lookup"><span data-stu-id="39868-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2655">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2655">Definition</span></span>

<span data-ttu-id="39868-2656">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2657">La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2658">Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="39868-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2659">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="39868-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="39868-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="39868-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="39868-2661">Identification Card</span></span> 
- <span data-ttu-id="39868-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="39868-2662">I card number</span></span> 
- <span data-ttu-id="39868-2663">número de Id.</span><span class="sxs-lookup"><span data-stu-id="39868-2663">ID number</span></span> 
- <span data-ttu-id="39868-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="39868-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="39868-2665">Número de tarjeta de identidad de registro nacional (NRIC) de Singapur</span><span class="sxs-lookup"><span data-stu-id="39868-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2666">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2666">Format</span></span>

<span data-ttu-id="39868-2667">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2668">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2668">Pattern</span></span>

- <span data-ttu-id="39868-2669">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="39868-2670">La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="39868-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="39868-2671">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2671">Seven digits</span></span> 
- <span data-ttu-id="39868-2672">Un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="39868-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2673">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2673">Checksum</span></span>

<span data-ttu-id="39868-2674">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2675">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2675">Definition</span></span>

<span data-ttu-id="39868-2676">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2677">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2678">Se encuentra una palabra clave de Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="39868-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="39868-2679">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2679">The checksum passes.</span></span>

<span data-ttu-id="39868-2680">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2681">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2682">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2683">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="39868-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="39868-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="39868-2685">Tarjeta de identidad de registro nacional
</span><span class="sxs-lookup"><span data-stu-id="39868-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="39868-2686">Número de tarjeta de identidad
</span><span class="sxs-lookup"><span data-stu-id="39868-2686">Identity Card Number</span></span> 
- <span data-ttu-id="39868-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="39868-2687">NRIC</span></span> 
- <span data-ttu-id="39868-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="39868-2688">IC</span></span> 
- <span data-ttu-id="39868-2689">Número de identificación de extranjeros
</span><span class="sxs-lookup"><span data-stu-id="39868-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="39868-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="39868-2690">FIN</span></span> 
- <span data-ttu-id="39868-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="39868-2691">身份证</span></span> 
- <span data-ttu-id="39868-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="39868-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="39868-2693">Número de identificación de Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="39868-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2694">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2694">Format</span></span>

<span data-ttu-id="39868-2695">13 dígitos que pueden contener espacios</span><span class="sxs-lookup"><span data-stu-id="39868-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2696">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2696">Pattern</span></span>

<span data-ttu-id="39868-2697">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2697">13 digits:</span></span>
- <span data-ttu-id="39868-2698">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="39868-2699">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2699">Four digits</span></span> 
- <span data-ttu-id="39868-2700">Un indicador de ciudadanía de un solo dígito </span><span class="sxs-lookup"><span data-stu-id="39868-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="39868-2701">El dígito "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="39868-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="39868-2702">Un dígito que es un dígito de suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2703">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2703">Checksum</span></span>

<span data-ttu-id="39868-2704">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2705">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2705">Definition</span></span>

<span data-ttu-id="39868-2706">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2707">La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2708">Se encuentra una palabra clave de Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="39868-2709">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2710">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="39868-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="39868-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="39868-2712">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="39868-2712">Identity card</span></span>
- <span data-ttu-id="39868-2713">ID</span><span class="sxs-lookup"><span data-stu-id="39868-2713">ID</span></span>
- <span data-ttu-id="39868-2714">Identificación</span><span class="sxs-lookup"><span data-stu-id="39868-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="39868-2715">Número de registro de residente de Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="39868-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2716">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2716">Format</span></span>

<span data-ttu-id="39868-2717">13 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="39868-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2718">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2718">Pattern</span></span>

<span data-ttu-id="39868-2719">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2719">13 digits:</span></span>
- <span data-ttu-id="39868-2720">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="39868-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="39868-2721">Un guión </span><span class="sxs-lookup"><span data-stu-id="39868-2721">A hyphen</span></span> 
- <span data-ttu-id="39868-2722">Un dígito determinado por el siglo y el sexo </span><span class="sxs-lookup"><span data-stu-id="39868-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="39868-2723">Código de región de nacimiento de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="39868-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="39868-2724">Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos </span><span class="sxs-lookup"><span data-stu-id="39868-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="39868-2725">Un dígito de control.</span><span class="sxs-lookup"><span data-stu-id="39868-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2726">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2726">Checksum</span></span>

<span data-ttu-id="39868-2727">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2728">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2728">Definition</span></span>

<span data-ttu-id="39868-2729">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2730">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2731">Se encuentra una palabra clave de Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="39868-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="39868-2732">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2732">The checksum passes.</span></span>

<span data-ttu-id="39868-2733">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2734">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2735">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2736">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="39868-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="39868-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="39868-2738">Tarjeta de id. nacional
</span><span class="sxs-lookup"><span data-stu-id="39868-2738">National ID card</span></span> 
- <span data-ttu-id="39868-2739">Número de registro de ciudadano
</span><span class="sxs-lookup"><span data-stu-id="39868-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="39868-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="39868-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="39868-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="39868-2741">RRN</span></span> 
- <span data-ttu-id="39868-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="39868-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="39868-2743">Número de seguridad social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="39868-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="39868-2744">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2744">Format</span></span>

<span data-ttu-id="39868-2745">11 o 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2746">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2746">Pattern</span></span>

<span data-ttu-id="39868-2747">12 de 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2747">11-12 digits:</span></span>
- <span data-ttu-id="39868-2748">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2748">Two digits</span></span> 
- <span data-ttu-id="39868-2749">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="39868-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="39868-2750">7-8 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2750">7-8 digits</span></span> 
- <span data-ttu-id="39868-2751">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="39868-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="39868-2752">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2753">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2753">Checksum</span></span>

<span data-ttu-id="39868-2754">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2755">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2755">Definition</span></span>

<span data-ttu-id="39868-2756">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2757">La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2758">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2759">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2759">Keywords</span></span>

<span data-ttu-id="39868-2760">Ninguno</span><span class="sxs-lookup"><span data-stu-id="39868-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="39868-2761">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="39868-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="39868-2762">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2762">Format</span></span>

<span data-ttu-id="39868-2763">10 o 12 dígitos y un delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="39868-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2764">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2764">Pattern</span></span>

<span data-ttu-id="39868-2765">10 o 12 dígitos y un delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="39868-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="39868-2766">2-4 dígitos (opcionales)</span><span class="sxs-lookup"><span data-stu-id="39868-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="39868-2767">Seis dígitos en fecha de formato AAMMDD</span><span class="sxs-lookup"><span data-stu-id="39868-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="39868-2768">Delimitador de "-" o "+" (opcional), más</span><span class="sxs-lookup"><span data-stu-id="39868-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="39868-2769">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2770">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2770">Checksum</span></span>

<span data-ttu-id="39868-2771">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2772">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2772">Definition</span></span>

<span data-ttu-id="39868-2773">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2774">La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2775">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2776">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2776">Keywords</span></span>

<span data-ttu-id="39868-2777">No</span><span class="sxs-lookup"><span data-stu-id="39868-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="39868-2778">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="39868-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2779">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2779">Format</span></span>

<span data-ttu-id="39868-2780">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2781">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2781">Pattern</span></span>

<span data-ttu-id="39868-2782">Ocho dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2783">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2783">Checksum</span></span>

<span data-ttu-id="39868-2784">No</span><span class="sxs-lookup"><span data-stu-id="39868-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2785">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2785">Definition</span></span>

<span data-ttu-id="39868-2786">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2787">La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2788">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-2788">One of the following is true:</span></span>
    - <span data-ttu-id="39868-2789">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="39868-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="39868-2790">Se encuentra una palabra clave de Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="39868-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-2791">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="39868-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="39868-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="39868-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="39868-2793">visa requirements</span></span> 
- <span data-ttu-id="39868-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="39868-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="39868-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="39868-2795">Schengen visas</span></span> 
- <span data-ttu-id="39868-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="39868-2796">Schengen visa</span></span> 
- <span data-ttu-id="39868-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="39868-2797">Visa Processing</span></span> 
- <span data-ttu-id="39868-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="39868-2798">Visa Type</span></span> 
- <span data-ttu-id="39868-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="39868-2799">Single Entry</span></span> 
- <span data-ttu-id="39868-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="39868-2800">Multiple Entry</span></span> 
- <span data-ttu-id="39868-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="39868-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="39868-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="39868-2802">Keyword_passport</span></span>

- <span data-ttu-id="39868-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="39868-2803">Passport Number</span></span> 
- <span data-ttu-id="39868-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="39868-2804">Passport No</span></span> 
- <span data-ttu-id="39868-2805">Passport #
</span><span class="sxs-lookup"><span data-stu-id="39868-2805">Passport #</span></span> 
- <span data-ttu-id="39868-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="39868-2806">Passport#</span></span> 
- <span data-ttu-id="39868-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="39868-2807">PassportID</span></span> 
- <span data-ttu-id="39868-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="39868-2808">Passportno</span></span> 
- <span data-ttu-id="39868-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-2809">passportnumber</span></span> 
- <span data-ttu-id="39868-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="39868-2810">パスポート</span></span> 
- <span data-ttu-id="39868-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2811">パスポート番号</span></span> 
- <span data-ttu-id="39868-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="39868-2812">パスポートのNum</span></span> 
- <span data-ttu-id="39868-2813">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2813">パスポート＃</span></span> 
- <span data-ttu-id="39868-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="39868-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="39868-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="39868-2815">Passeport n °</span></span> 
- <span data-ttu-id="39868-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="39868-2816">Passeport Non</span></span> 
- <span data-ttu-id="39868-2817">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="39868-2817">Passeport #</span></span> 
- <span data-ttu-id="39868-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="39868-2818">Passeport#</span></span> 
- <span data-ttu-id="39868-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="39868-2819">PasseportNon</span></span> 
- <span data-ttu-id="39868-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="39868-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="39868-2821">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="39868-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="39868-2822">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2822">Format</span></span>

<span data-ttu-id="39868-2823">Cuatro letras seguidas de 5 a 31 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2824">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2824">Pattern</span></span>

<span data-ttu-id="39868-2825">Cuatro letras seguidas de 5-31 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="39868-2826">Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="39868-2827">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="39868-2827">An optional space</span></span> 
- <span data-ttu-id="39868-2828">4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))</span><span class="sxs-lookup"><span data-stu-id="39868-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="39868-2829">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="39868-2829">An optional space</span></span> 
- <span data-ttu-id="39868-2830">1-3 letras o dígitos (el resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="39868-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2831">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2831">Checksum</span></span>

<span data-ttu-id="39868-2832">No</span><span class="sxs-lookup"><span data-stu-id="39868-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2833">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2833">Definition</span></span>

<span data-ttu-id="39868-2834">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2835">La expresión regular Regex_swift encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2836">Se encuentra una palabra clave de Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="39868-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2837">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="39868-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="39868-2838">Keyword_swift</span></span>

- <span data-ttu-id="39868-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="39868-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="39868-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="39868-2840">iso 9362</span></span> 
- <span data-ttu-id="39868-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="39868-2841">iso9362</span></span> 
- <span data-ttu-id="39868-2842">SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="39868-2842">swift\#</span></span> 
- <span data-ttu-id="39868-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="39868-2843">swiftcode</span></span> 
- <span data-ttu-id="39868-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-2844">swiftnumber</span></span> 
- <span data-ttu-id="39868-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="39868-2846">código SWIFT</span><span class="sxs-lookup"><span data-stu-id="39868-2846">swift code</span></span> 
- <span data-ttu-id="39868-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="39868-2847">swift number #</span></span> 
- <span data-ttu-id="39868-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="39868-2848">swift routing number</span></span> 
- <span data-ttu-id="39868-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="39868-2849">bic number</span></span> 
- <span data-ttu-id="39868-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="39868-2850">bic code</span></span> 
- <span data-ttu-id="39868-2851">BIC\#</span><span class="sxs-lookup"><span data-stu-id="39868-2851">bic \#</span></span> 
- <span data-ttu-id="39868-2852">BIC\#</span><span class="sxs-lookup"><span data-stu-id="39868-2852">bic\#</span></span> 
- <span data-ttu-id="39868-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="39868-2853">bank identifier code</span></span> 
- <span data-ttu-id="39868-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="39868-2854">標準化9362</span></span> 
- <span data-ttu-id="39868-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="39868-2855">迅速＃</span></span> 
- <span data-ttu-id="39868-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="39868-2856">SWIFTコード</span></span> 
- <span data-ttu-id="39868-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2857">SWIFT番号</span></span> 
- <span data-ttu-id="39868-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="39868-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="39868-2859">BIC番号</span></span> 
- <span data-ttu-id="39868-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="39868-2860">BICコード</span></span> 
- <span data-ttu-id="39868-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="39868-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="39868-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="39868-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="39868-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="39868-2863">rapide \#</span></span> 
- <span data-ttu-id="39868-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="39868-2864">code SWIFT</span></span> 
- <span data-ttu-id="39868-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="39868-2865">le numéro de swift</span></span> 
- <span data-ttu-id="39868-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="39868-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="39868-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="39868-2867">le numéro BIC</span></span> 
- <span data-ttu-id="39868-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="39868-2868">\# BIC</span></span> 
- <span data-ttu-id="39868-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="39868-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="39868-2870">Identificación nacional de Taiwán</span><span class="sxs-lookup"><span data-stu-id="39868-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="39868-2871">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2871">Format</span></span>

<span data-ttu-id="39868-2872">Una letra  seguida de nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2873">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2873">Pattern</span></span>

<span data-ttu-id="39868-2874">Una letra seguida de nueve dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="39868-2875">Una letra (en inglés, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="39868-2876">El dígito "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="39868-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="39868-2877">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2878">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2878">Checksum</span></span>

<span data-ttu-id="39868-2879">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2880">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2880">Definition</span></span>

<span data-ttu-id="39868-2881">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2882">La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2883">Se encuentra una palabra clave de Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="39868-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="39868-2884">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2885">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="39868-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="39868-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="39868-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="39868-2887">身份證字號</span></span> 
- <span data-ttu-id="39868-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="39868-2888">身份證</span></span> 
- <span data-ttu-id="39868-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="39868-2889">身份證號碼</span></span> 
- <span data-ttu-id="39868-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="39868-2890">身份證號</span></span> 
- <span data-ttu-id="39868-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="39868-2891">身分證字號</span></span> 
- <span data-ttu-id="39868-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="39868-2892">身分證</span></span> 
- <span data-ttu-id="39868-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="39868-2893">身分證號碼</span></span> 
- <span data-ttu-id="39868-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="39868-2894">身份證號</span></span> 
- <span data-ttu-id="39868-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="39868-2895">身分證統一編號</span></span> 
- <span data-ttu-id="39868-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="39868-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="39868-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="39868-2897">簽名</span></span> 
- <span data-ttu-id="39868-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="39868-2898">蓋章</span></span> 
- <span data-ttu-id="39868-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="39868-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="39868-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="39868-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="39868-2901">Número de pasaporte de Taiwán</span><span class="sxs-lookup"><span data-stu-id="39868-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2902">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2902">Format</span></span>

- <span data-ttu-id="39868-2903">Número de pasaporte biométrica: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="39868-2904">Número de cuenta de passport no biométrica: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2905">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2905">Pattern</span></span>
<span data-ttu-id="39868-2906">Número de cuenta de passport biométrica:</span><span class="sxs-lookup"><span data-stu-id="39868-2906">Biometric passport number:</span></span>
- <span data-ttu-id="39868-2907">El dígito "3" </span><span class="sxs-lookup"><span data-stu-id="39868-2907">The digit "3"</span></span> 
- <span data-ttu-id="39868-2908">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2908">Eight digits</span></span>

<span data-ttu-id="39868-2909">Número de cuenta de passport no biométrica:</span><span class="sxs-lookup"><span data-stu-id="39868-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="39868-2910">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2911">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2911">Checksum</span></span>

<span data-ttu-id="39868-2912">No</span><span class="sxs-lookup"><span data-stu-id="39868-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2913">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2913">Definition</span></span>

<span data-ttu-id="39868-2914">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2915">La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2916">Se encuentra una palabra clave de Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="39868-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2917">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="39868-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="39868-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="39868-2919">Número de pasaporte ROC
</span><span class="sxs-lookup"><span data-stu-id="39868-2919">ROC passport number</span></span> 
- <span data-ttu-id="39868-2920">Número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="39868-2920">Passport number</span></span> 
- <span data-ttu-id="39868-2921">Cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="39868-2921">Passport no</span></span> 
- <span data-ttu-id="39868-2922">N.ro pasaporte
</span><span class="sxs-lookup"><span data-stu-id="39868-2922">Passport Num</span></span> 
- <span data-ttu-id="39868-2923">Passport #
</span><span class="sxs-lookup"><span data-stu-id="39868-2923">Passport #</span></span> 
- <span data-ttu-id="39868-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="39868-2924">护照</span></span> 
- <span data-ttu-id="39868-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="39868-2925">中華民國護照</span></span> 
- <span data-ttu-id="39868-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="39868-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="39868-2927">Número de certificado de residente (ARC/TARC) de Taiwán</span><span class="sxs-lookup"><span data-stu-id="39868-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2928">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2928">Format</span></span>

<span data-ttu-id="39868-2929">10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2930">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2930">Pattern</span></span>

<span data-ttu-id="39868-2931">10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2931">10 letters and digits:</span></span>
- <span data-ttu-id="39868-2932">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="39868-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="39868-2933">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2934">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2934">Checksum</span></span>

<span data-ttu-id="39868-2935">No</span><span class="sxs-lookup"><span data-stu-id="39868-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2936">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2936">Definition</span></span>

<span data-ttu-id="39868-2937">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2938">La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2939">Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="39868-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2940">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="39868-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="39868-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="39868-2942">Certificado de residente
</span><span class="sxs-lookup"><span data-stu-id="39868-2942">Resident Certificate</span></span> 
- <span data-ttu-id="39868-2943">Cert residente</span><span class="sxs-lookup"><span data-stu-id="39868-2943">Resident Cert</span></span> 
- <span data-ttu-id="39868-2944">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="39868-2944">Resident Cert.</span></span> 
- <span data-ttu-id="39868-2945">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-2945">Identification card</span></span> 
- <span data-ttu-id="39868-2946">Certificado de residente extranjero
</span><span class="sxs-lookup"><span data-stu-id="39868-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="39868-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="39868-2947">ARC</span></span> 
- <span data-ttu-id="39868-2948">Certificado de residente en el área de Taiwán
</span><span class="sxs-lookup"><span data-stu-id="39868-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="39868-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="39868-2949">TARC</span></span> 
- <span data-ttu-id="39868-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="39868-2950">居留證</span></span> 
- <span data-ttu-id="39868-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="39868-2951">外僑居留證</span></span> 
- <span data-ttu-id="39868-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="39868-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="39868-p141">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="39868-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2955">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2955">Format</span></span>

<span data-ttu-id="39868-2956">Combinación de 18 letras y dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="39868-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2957">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2957">Pattern</span></span>

<span data-ttu-id="39868-2958">18 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-2958">18 letters and digits:</span></span>
- <span data-ttu-id="39868-2959">Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="39868-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="39868-2960">Un dígito</span><span class="sxs-lookup"><span data-stu-id="39868-2960">One digit</span></span> 
- <span data-ttu-id="39868-2961">Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="39868-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="39868-2962">Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="39868-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="39868-2963">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2964">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2964">Checksum</span></span>

<span data-ttu-id="39868-2965">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2966">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2966">Definition</span></span>

<span data-ttu-id="39868-2967">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2968">La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2969">Se encuentra una palabra clave de Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="39868-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="39868-2970">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-2971">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="39868-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="39868-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="39868-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="39868-2973">DVLA</span></span> 
- <span data-ttu-id="39868-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="39868-2974">light vans</span></span> 
- <span data-ttu-id="39868-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="39868-2975">quadbikes</span></span> 
- <span data-ttu-id="39868-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="39868-2976">motor cars</span></span> 
- <span data-ttu-id="39868-2977">125CC</span><span class="sxs-lookup"><span data-stu-id="39868-2977">125cc</span></span> 
- <span data-ttu-id="39868-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="39868-2978">sidecar</span></span> 
- <span data-ttu-id="39868-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="39868-2979">tricycles</span></span> 
- <span data-ttu-id="39868-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="39868-2980">motorcycles</span></span> 
- <span data-ttu-id="39868-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="39868-2981">photocard licence</span></span> 
- <span data-ttu-id="39868-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="39868-2982">learner drivers</span></span> 
- <span data-ttu-id="39868-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="39868-2983">licence holder</span></span> 
- <span data-ttu-id="39868-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="39868-2984">licence holders</span></span> 
- <span data-ttu-id="39868-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="39868-2985">driving licences</span></span> 
- <span data-ttu-id="39868-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="39868-2986">driving licence</span></span> 
- <span data-ttu-id="39868-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="39868-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="39868-p142">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="39868-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-2990">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-2990">Format</span></span>

<span data-ttu-id="39868-2991">Dos letras seguidas por entre 1 y 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-2992">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-2992">Pattern</span></span>

<span data-ttu-id="39868-2993">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números</span><span class="sxs-lookup"><span data-stu-id="39868-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-2994">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-2994">Checksum</span></span>

<span data-ttu-id="39868-2995">No</span><span class="sxs-lookup"><span data-stu-id="39868-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-2996">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-2996">Definition</span></span>

<span data-ttu-id="39868-2997">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-2998">La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-2999">Se encuentra una palabra clave de Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="39868-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-3000">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="39868-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="39868-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="39868-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="39868-3002">council nomination</span></span> 
- <span data-ttu-id="39868-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="39868-3003">nomination form</span></span> 
- <span data-ttu-id="39868-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="39868-3004">electoral register</span></span> 
- <span data-ttu-id="39868-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="39868-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="39868-p143">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="39868-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-3008">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-3008">Format</span></span>

<span data-ttu-id="39868-3009">De 10 a 17 dígitos separados por espacios</span><span class="sxs-lookup"><span data-stu-id="39868-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-3010">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-3010">Pattern</span></span>

<span data-ttu-id="39868-3011">10-17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="39868-3011">10-17 digits:</span></span>
- <span data-ttu-id="39868-3012">3 o 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="39868-3013">Un espacio</span><span class="sxs-lookup"><span data-stu-id="39868-3013">A space</span></span> 
- <span data-ttu-id="39868-3014">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3014">Three digits</span></span> 
- <span data-ttu-id="39868-3015">Un espacio</span><span class="sxs-lookup"><span data-stu-id="39868-3015">A space</span></span> 
- <span data-ttu-id="39868-3016">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-3017">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-3017">Checksum</span></span>

<span data-ttu-id="39868-3018">Sí</span><span class="sxs-lookup"><span data-stu-id="39868-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="39868-3019">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-3019">Definition</span></span>

<span data-ttu-id="39868-3020">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3021">La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3022">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-3022">One of the following is true:</span></span>
    - <span data-ttu-id="39868-3023">Se encuentra una palabra clave de Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="39868-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="39868-3024">Se encuentra una palabra clave de Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="39868-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="39868-3025">Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="39868-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="39868-3026">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="39868-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-3027">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="39868-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="39868-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="39868-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="39868-3029">national health service</span></span> 
- <span data-ttu-id="39868-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="39868-3030">nhs</span></span> 
- <span data-ttu-id="39868-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="39868-3031">health services authority</span></span> 
- <span data-ttu-id="39868-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="39868-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="39868-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="39868-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="39868-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="39868-3034">patient id</span></span> 
- <span data-ttu-id="39868-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="39868-3035">patient identification</span></span> 
- <span data-ttu-id="39868-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="39868-3036">patient no</span></span> 
- <span data-ttu-id="39868-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="39868-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="39868-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="39868-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="39868-3039">DG</span><span class="sxs-lookup"><span data-stu-id="39868-3039">GP</span></span> 
- <span data-ttu-id="39868-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="39868-3040">DOB</span></span> 
- <span data-ttu-id="39868-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="39868-3041">D.O.B</span></span> 
- <span data-ttu-id="39868-3042">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="39868-3042">Date of Birth</span></span> 
- <span data-ttu-id="39868-3043">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="39868-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="39868-p144">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="39868-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="39868-3046">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-3046">Format</span></span>

<span data-ttu-id="39868-3047">los 7 caracteres o 9 separadas por espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="39868-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-3048">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-3048">Pattern</span></span>

<span data-ttu-id="39868-3049">Dos modelos posibles:</span><span class="sxs-lookup"><span data-stu-id="39868-3049">Two possible patterns:</span></span>

- <span data-ttu-id="39868-3050">Dos letras (NINOs válidos utilizar sólo determinados caracteres en este prefijo, que valida este patrón; no mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="39868-3051">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3051">Six digits</span></span>
- <span data-ttu-id="39868-3052">Puede ser 'A', 'B', 'C', o tenía ' (como el prefijo, sólo ciertos caracteres se permiten en el sufijo; no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="39868-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="39868-3053">OR</span><span class="sxs-lookup"><span data-stu-id="39868-3053">OR</span></span>

- <span data-ttu-id="39868-3054">Dos letras</span><span class="sxs-lookup"><span data-stu-id="39868-3054">Two letters</span></span>
- <span data-ttu-id="39868-3055">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="39868-3055">A space or dash</span></span>
- <span data-ttu-id="39868-3056">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3056">Two digits</span></span>
- <span data-ttu-id="39868-3057">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="39868-3057">A space or dash</span></span>
- <span data-ttu-id="39868-3058">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3058">Two digits</span></span>
- <span data-ttu-id="39868-3059">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="39868-3059">A space or dash</span></span>
- <span data-ttu-id="39868-3060">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3060">Two digits</span></span>
- <span data-ttu-id="39868-3061">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="39868-3061">A space or dash</span></span>
- <span data-ttu-id="39868-3062">Puede ser 'A', 'B', 'C', o tenía '</span><span class="sxs-lookup"><span data-stu-id="39868-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-3063">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-3063">Checksum</span></span>

<span data-ttu-id="39868-3064">No</span><span class="sxs-lookup"><span data-stu-id="39868-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-3065">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-3065">Definition</span></span>

<span data-ttu-id="39868-3066">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3067">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3068">Se encuentra una palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="39868-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="39868-3069">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3070">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3071">No se encuentra ninguna palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="39868-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-3072">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="39868-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="39868-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="39868-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="39868-3074">national insurance number</span></span> 
- <span data-ttu-id="39868-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="39868-3075">national insurance contributions</span></span> 
- <span data-ttu-id="39868-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="39868-3076">protection act</span></span> 
- <span data-ttu-id="39868-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="39868-3077">insurance</span></span> 
- <span data-ttu-id="39868-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="39868-3078">social security number</span></span> 
- <span data-ttu-id="39868-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="39868-3079">insurance application</span></span> 
- <span data-ttu-id="39868-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="39868-3080">medical application</span></span> 
- <span data-ttu-id="39868-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="39868-3081">social insurance</span></span> 
- <span data-ttu-id="39868-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="39868-3082">medical attention</span></span> 
- <span data-ttu-id="39868-3083">seguridad social</span><span class="sxs-lookup"><span data-stu-id="39868-3083">social security</span></span> 
- <span data-ttu-id="39868-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="39868-3084">great britain</span></span> 
- <span data-ttu-id="39868-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="39868-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="39868-p145">Número de pasaporte EE. UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="39868-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-3088">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-3088">Format</span></span>

<span data-ttu-id="39868-3089">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-3090">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-3090">Pattern</span></span>

<span data-ttu-id="39868-3091">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-3092">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-3092">Checksum</span></span>

<span data-ttu-id="39868-3093">No</span><span class="sxs-lookup"><span data-stu-id="39868-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-3094">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-3094">Definition</span></span>

<span data-ttu-id="39868-3095">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3096">La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3097">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="39868-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-3098">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="39868-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="39868-3099">Keyword_passport</span></span>

- <span data-ttu-id="39868-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="39868-3100">Passport Number</span></span> 
- <span data-ttu-id="39868-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="39868-3101">Passport No</span></span> 
- <span data-ttu-id="39868-3102">Passport #
</span><span class="sxs-lookup"><span data-stu-id="39868-3102">Passport #</span></span> 
- <span data-ttu-id="39868-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="39868-3103">Passport#</span></span> 
- <span data-ttu-id="39868-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="39868-3104">PassportID</span></span> 
- <span data-ttu-id="39868-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="39868-3105">Passportno</span></span> 
- <span data-ttu-id="39868-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="39868-3106">passportnumber</span></span> 
- <span data-ttu-id="39868-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="39868-3107">パスポート</span></span> 
- <span data-ttu-id="39868-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="39868-3108">パスポート番号</span></span> 
- <span data-ttu-id="39868-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="39868-3109">パスポートのNum</span></span> 
- <span data-ttu-id="39868-3110">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="39868-3110">パスポート＃</span></span> 
- <span data-ttu-id="39868-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="39868-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="39868-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="39868-3112">Passeport n °</span></span> 
- <span data-ttu-id="39868-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="39868-3113">Passeport Non</span></span> 
- <span data-ttu-id="39868-3114">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="39868-3114">Passeport #</span></span> 
- <span data-ttu-id="39868-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="39868-3115">Passeport#</span></span> 
- <span data-ttu-id="39868-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="39868-3116">PasseportNon</span></span> 
- <span data-ttu-id="39868-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="39868-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="39868-3118">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="39868-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-3119">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-3119">Format</span></span>

<span data-ttu-id="39868-3120">Entre 8 y 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-3121">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-3121">Pattern</span></span>

<span data-ttu-id="39868-3122">Entre 8 y 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="39868-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-3123">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-3123">Checksum</span></span>

<span data-ttu-id="39868-3124">No</span><span class="sxs-lookup"><span data-stu-id="39868-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-3125">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-3125">Definition</span></span>

<span data-ttu-id="39868-3126">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3127">La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3128">Se encuentra una palabra clave de Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="39868-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39868-3129">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="39868-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="39868-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="39868-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3131">Checking Account Number</span></span> 
- <span data-ttu-id="39868-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="39868-3132">Checking Account</span></span> 
- <span data-ttu-id="39868-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-3133">Checking Account #</span></span> 
- <span data-ttu-id="39868-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="39868-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-3135">Checking Acct #</span></span> 
- <span data-ttu-id="39868-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="39868-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3137">Checking Account No.</span></span> 
- <span data-ttu-id="39868-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3138">Bank Account Number</span></span> 
- <span data-ttu-id="39868-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-3139">Bank Account #</span></span> 
- <span data-ttu-id="39868-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="39868-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-3141">Bank Acct #</span></span> 
- <span data-ttu-id="39868-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="39868-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3143">Bank Account No.</span></span> 
- <span data-ttu-id="39868-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3144">Savings Account Number</span></span> 
- <span data-ttu-id="39868-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="39868-3145">Savings Account.</span></span> 
- <span data-ttu-id="39868-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-3146">Savings Account #</span></span> 
- <span data-ttu-id="39868-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="39868-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-3148">Savings Acct #</span></span> 
- <span data-ttu-id="39868-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="39868-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3150">Savings Account No.</span></span> 
- <span data-ttu-id="39868-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3151">Debit Account Number</span></span> 
- <span data-ttu-id="39868-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="39868-3152">Debit Account</span></span> 
- <span data-ttu-id="39868-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="39868-3153">Debit Account #</span></span> 
- <span data-ttu-id="39868-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="39868-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="39868-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="39868-3155">Debit Acct #</span></span> 
- <span data-ttu-id="39868-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="39868-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="39868-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="39868-3158">Número de licencia de conductor de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="39868-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="39868-3159">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-3159">Format</span></span>

<span data-ttu-id="39868-3160">Depende del estado</span><span class="sxs-lookup"><span data-stu-id="39868-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-3161">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-3161">Pattern</span></span>

<span data-ttu-id="39868-3162">Depende del estado, por ejemplo, Nueva York:</span><span class="sxs-lookup"><span data-stu-id="39868-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="39868-3163">Nueve dígitos como ddd ddd ddd coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="39868-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="39868-3164">Nueve dígitos como ddddddddd no coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="39868-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-3165">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-3165">Checksum</span></span>

<span data-ttu-id="39868-3166">No</span><span class="sxs-lookup"><span data-stu-id="39868-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-3167">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-3167">Definition</span></span>

<span data-ttu-id="39868-3168">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3169">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3170">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="39868-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="39868-3171">Se encuentra una palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="39868-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="39868-3172">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3173">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3174">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="39868-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="39868-3175">Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="39868-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="39868-3176">No se encuentra ninguna palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="39868-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-3177">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="39868-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="39868-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="39868-3179">DL</span><span class="sxs-lookup"><span data-stu-id="39868-3179">DL</span></span> 
- <span data-ttu-id="39868-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="39868-3180">DLS</span></span> 
- <span data-ttu-id="39868-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="39868-3181">CDL</span></span> 
- <span data-ttu-id="39868-3182">CDLS</span><span class="sxs-lookup"><span data-stu-id="39868-3182">CDLS</span></span> 
- <span data-ttu-id="39868-3183">ID</span><span class="sxs-lookup"><span data-stu-id="39868-3183">ID</span></span> 
- <span data-ttu-id="39868-3184">Identificadores de</span><span class="sxs-lookup"><span data-stu-id="39868-3184">IDs</span></span> 
- <span data-ttu-id="39868-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="39868-3185">DL#</span></span> 
- <span data-ttu-id="39868-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="39868-3186">DLS#</span></span> 
- <span data-ttu-id="39868-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="39868-3187">CDL#</span></span> 
- <span data-ttu-id="39868-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="39868-3188">CDLS#</span></span> 
- <span data-ttu-id="39868-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="39868-3189">ID#</span></span>
- <span data-ttu-id="39868-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="39868-3190">IDs#</span></span> 
- <span data-ttu-id="39868-3191">número de Id.</span><span class="sxs-lookup"><span data-stu-id="39868-3191">ID number</span></span> 
- <span data-ttu-id="39868-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="39868-3192">ID numbers</span></span> 
- <span data-ttu-id="39868-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="39868-3193">LIC</span></span> 
- <span data-ttu-id="39868-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="39868-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="39868-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="39868-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="39868-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="39868-3196">DriverLic</span></span> 
- <span data-ttu-id="39868-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="39868-3197">DriverLics</span></span> 
- <span data-ttu-id="39868-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="39868-3198">DriverLicense</span></span> 
- <span data-ttu-id="39868-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-3199">DriverLicenses</span></span> 
- <span data-ttu-id="39868-3200">Lic de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-3200">Driver Lic</span></span> 
- <span data-ttu-id="39868-3201">LIC de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-3201">Driver Lics</span></span> 
- <span data-ttu-id="39868-3202">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-3202">Driver License</span></span> 
- <span data-ttu-id="39868-3203">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="39868-3203">Driver Licenses</span></span> 
- <span data-ttu-id="39868-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="39868-3204">DriversLic</span></span> 
- <span data-ttu-id="39868-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="39868-3205">DriversLics</span></span> 
- <span data-ttu-id="39868-3206">PermisoDeConducción</span><span class="sxs-lookup"><span data-stu-id="39868-3206">DriversLicense</span></span> 
- <span data-ttu-id="39868-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-3207">DriversLicenses</span></span> 
- <span data-ttu-id="39868-3208">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-3208">Drivers Lic</span></span> 
- <span data-ttu-id="39868-3209">LIC de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-3209">Drivers Lics</span></span> 
- <span data-ttu-id="39868-3210">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-3210">Drivers License</span></span> 
- <span data-ttu-id="39868-3211">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="39868-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="39868-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="39868-3212">Driver'Lic</span></span> 
- <span data-ttu-id="39868-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="39868-3213">Driver'Lics</span></span> 
- <span data-ttu-id="39868-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="39868-3214">Driver'License</span></span> 
- <span data-ttu-id="39868-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="39868-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="39868-3216">Controlador ' Lic</span><span class="sxs-lookup"><span data-stu-id="39868-3216">Driver' Lic</span></span> 
- <span data-ttu-id="39868-3217">Controlador ' LIC</span><span class="sxs-lookup"><span data-stu-id="39868-3217">Driver' Lics</span></span> 
- <span data-ttu-id="39868-3218">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="39868-3218">Driver' License</span></span> 
- <span data-ttu-id="39868-3219">Controlador ' licencias</span><span class="sxs-lookup"><span data-stu-id="39868-3219">Driver' Licenses</span></span>
- <span data-ttu-id="39868-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="39868-3220">Driver'sLic</span></span> 
- <span data-ttu-id="39868-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="39868-3221">Driver'sLics</span></span> 
- <span data-ttu-id="39868-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="39868-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="39868-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="39868-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="39868-3224">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-3224">Driver's Lic</span></span> 
- <span data-ttu-id="39868-3225">LIC del controlador</span><span class="sxs-lookup"><span data-stu-id="39868-3225">Driver's Lics</span></span> 
- <span data-ttu-id="39868-3226">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="39868-3226">Driver's License</span></span> 
- <span data-ttu-id="39868-3227">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="39868-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="39868-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="39868-3228">identification number</span></span> 
- <span data-ttu-id="39868-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="39868-3229">identification numbers</span></span> 
- <span data-ttu-id="39868-3230">identification #
</span><span class="sxs-lookup"><span data-stu-id="39868-3230">identification #</span></span> 
- <span data-ttu-id="39868-3231">tarjeta de Id.</span><span class="sxs-lookup"><span data-stu-id="39868-3231">id card</span></span> 
- <span data-ttu-id="39868-3232">identificador de tarjetas</span><span class="sxs-lookup"><span data-stu-id="39868-3232">id cards</span></span> 
- <span data-ttu-id="39868-3233">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-3233">identification card</span></span> 
- <span data-ttu-id="39868-3234">tarjetas de identificación</span><span class="sxs-lookup"><span data-stu-id="39868-3234">identification cards</span></span> 
- <span data-ttu-id="39868-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="39868-3235">DriverLic#</span></span> 
- <span data-ttu-id="39868-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="39868-3236">DriverLics#</span></span> 
- <span data-ttu-id="39868-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="39868-3237">DriverLicense#</span></span> 
- <span data-ttu-id="39868-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="39868-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="39868-3239">Driver Lic#</span></span> 
- <span data-ttu-id="39868-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-3240">Driver Lics#</span></span> 
- <span data-ttu-id="39868-3241">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="39868-3241">Driver License#</span></span> 
- <span data-ttu-id="39868-3242">Controlador licencias #</span><span class="sxs-lookup"><span data-stu-id="39868-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="39868-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="39868-3243">DriversLic#</span></span> 
- <span data-ttu-id="39868-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="39868-3244">DriversLics#</span></span> 
- <span data-ttu-id="39868-3245">PermisoDeConducción #</span><span class="sxs-lookup"><span data-stu-id="39868-3245">DriversLicense#</span></span> 
- <span data-ttu-id="39868-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="39868-3247">Controladores Lic #</span><span class="sxs-lookup"><span data-stu-id="39868-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="39868-3248">Controladores LIC #</span><span class="sxs-lookup"><span data-stu-id="39868-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="39868-3249">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-3249">Drivers License#</span></span> 
- <span data-ttu-id="39868-3250">Licencias de controladores #</span><span class="sxs-lookup"><span data-stu-id="39868-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="39868-3251">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="39868-3252">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="39868-3253">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="39868-3253">Driver'License#</span></span> 
- <span data-ttu-id="39868-3254">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="39868-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="39868-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="39868-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="39868-3257">Driver' License#</span></span> 
- <span data-ttu-id="39868-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="39868-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="39868-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="39868-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="39868-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="39868-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="39868-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="39868-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="39868-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="39868-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="39868-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="39868-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="39868-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="39868-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="39868-3265">Driver's License#</span></span> 
- <span data-ttu-id="39868-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="39868-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="39868-3267">tarjeta de identificación #</span><span class="sxs-lookup"><span data-stu-id="39868-3267">id card#</span></span> 
- <span data-ttu-id="39868-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="39868-3268">id cards#</span></span> 
- <span data-ttu-id="39868-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="39868-3269">identification card#</span></span> 
- <span data-ttu-id="39868-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="39868-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="39868-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="39868-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="39868-3272">Abreviatura del estado (por ejemplo, "NY")
</span><span class="sxs-lookup"><span data-stu-id="39868-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="39868-3273">Nombre del estado (por ejemplo, "New York")
</span><span class="sxs-lookup"><span data-stu-id="39868-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="39868-3274">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="39868-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="39868-3275">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-3275">Format</span></span>

<span data-ttu-id="39868-3276">Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="39868-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-3277">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-3277">Pattern</span></span>

<span data-ttu-id="39868-3278">Con formato:</span><span class="sxs-lookup"><span data-stu-id="39868-3278">Formatted:</span></span>
- <span data-ttu-id="39868-3279">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="39868-3279">The digit "9"</span></span> 
- <span data-ttu-id="39868-3280">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3280">Two digits</span></span> 
- <span data-ttu-id="39868-3281">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="39868-3281">A space or dash</span></span> 
- <span data-ttu-id="39868-3282">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="39868-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="39868-3283">Un dígito</span><span class="sxs-lookup"><span data-stu-id="39868-3283">A digit</span></span> 
- <span data-ttu-id="39868-3284">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="39868-3284">A space, or dash</span></span> 
- <span data-ttu-id="39868-3285">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3285">Four digits</span></span>

<span data-ttu-id="39868-3286">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="39868-3286">Unformatted:</span></span>
- <span data-ttu-id="39868-3287">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="39868-3287">The digit "9"</span></span> 
- <span data-ttu-id="39868-3288">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3288">Two digits</span></span> 
- <span data-ttu-id="39868-3289">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="39868-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="39868-3290">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="39868-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-3291">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-3291">Checksum</span></span>

<span data-ttu-id="39868-3292">No</span><span class="sxs-lookup"><span data-stu-id="39868-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="39868-3293">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-3293">Definition</span></span>

<span data-ttu-id="39868-3294">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3295">La función Func_formatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3296">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="39868-3297">Se encuentra una palabra clave de Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="39868-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="39868-3298">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="39868-3299">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="39868-3300">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="39868-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="39868-3301">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3302">La función Func_unformatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3303">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="39868-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="39868-3304">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="39868-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="39868-3305">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="39868-3306">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="39868-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-3307">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="39868-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="39868-3308">Keyword_itin</span></span>

- <span data-ttu-id="39868-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="39868-3309">taxpayer</span></span> 
- <span data-ttu-id="39868-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="39868-3310">tax id</span></span> 
- <span data-ttu-id="39868-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="39868-3311">tax identification</span></span> 
- <span data-ttu-id="39868-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="39868-3312">itin</span></span> 
- <span data-ttu-id="39868-3313">ssn</span><span class="sxs-lookup"><span data-stu-id="39868-3313">ssn</span></span> 
- <span data-ttu-id="39868-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="39868-3314">tin</span></span> 
- <span data-ttu-id="39868-3315">seguridad social</span><span class="sxs-lookup"><span data-stu-id="39868-3315">social security</span></span> 
- <span data-ttu-id="39868-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="39868-3316">tax payer</span></span> 
- <span data-ttu-id="39868-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="39868-3317">itins</span></span> 
- <span data-ttu-id="39868-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="39868-3318">taxid</span></span> 
- <span data-ttu-id="39868-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="39868-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="39868-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="39868-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="39868-3321">License</span><span class="sxs-lookup"><span data-stu-id="39868-3321">License</span></span> 
- <span data-ttu-id="39868-3322">DL</span><span class="sxs-lookup"><span data-stu-id="39868-3322">DL</span></span> 
- <span data-ttu-id="39868-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="39868-3323">DOB</span></span> 
- <span data-ttu-id="39868-3324">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="39868-3324">Birthdate</span></span> 
- <span data-ttu-id="39868-3325">Cumpleaños </span><span class="sxs-lookup"><span data-stu-id="39868-3325">Birthday</span></span> 
- <span data-ttu-id="39868-3326">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="39868-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="39868-3327">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="39868-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="39868-3328">Formato</span><span class="sxs-lookup"><span data-stu-id="39868-3328">Format</span></span>

<span data-ttu-id="39868-3329">9 dígitos, que pueden ser un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="39868-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="39868-3330">Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="39868-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="39868-3331">Patrón</span><span class="sxs-lookup"><span data-stu-id="39868-3331">Pattern</span></span>

<span data-ttu-id="39868-3332">Cuatro funciones buscan SSN en cuatro patrones diferentes:</span><span class="sxs-lookup"><span data-stu-id="39868-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="39868-3333">Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="39868-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="39868-3334">Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="39868-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="39868-3335">Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="39868-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="39868-3336">Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="39868-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="39868-3337">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="39868-3337">Checksum</span></span>

<span data-ttu-id="39868-3338">No</span><span class="sxs-lookup"><span data-stu-id="39868-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="39868-3339">Definición</span><span class="sxs-lookup"><span data-stu-id="39868-3339">Definition</span></span>

<span data-ttu-id="39868-3340">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3341">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3342">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="39868-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="39868-3343">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3344">La función Func_unformatted_ssn busca contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3345">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="39868-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="39868-3346">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3347">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3348">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="39868-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="39868-3349">La función Func_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="39868-3350">Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="39868-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="39868-3351">La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="39868-3352">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="39868-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="39868-3353">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="39868-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="39868-3354">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="39868-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="39868-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="39868-3355">Keyword_ssn</span></span>

- <span data-ttu-id="39868-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="39868-3356">Social Security</span></span> 
- <span data-ttu-id="39868-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="39868-3357">Social Security#</span></span> 
- <span data-ttu-id="39868-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="39868-3358">Soc Sec</span></span> 
- <span data-ttu-id="39868-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="39868-3359">SSN</span></span> 
- <span data-ttu-id="39868-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="39868-3360">SSNS</span></span> 
- <span data-ttu-id="39868-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="39868-3361">SSN#</span></span> 
- <span data-ttu-id="39868-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="39868-3362">SS#</span></span> 
- <span data-ttu-id="39868-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="39868-3363">SSID</span></span> 
   

