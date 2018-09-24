---
title: Qué buscan los tipos de información confidencial
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye los tipos de información confidencial 80 que están listos para su uso en las directivas de DLP. En este tema se enumera todos estos tipos de información confidencial y muestra lo que busca una directiva de DLP cuando detecta cada tipo.
ms.openlocfilehash: 2e59b322730ca7fa828a685ed3a80c48ebdbbfd8
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972362"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="1b076-104">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="1b076-104">What the sensitive information types look for</span></span>

<span data-ttu-id="1b076-p102">Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se enumera todos estos tipos de información confidencial y muestra lo que busca una directiva de DLP cuando detecta cada tipo. Un tipo de información confidencial se define mediante un patrón que puede identificarse mediante una expresión regular o una función. Además, como las palabras clave y sumas de comprobación de prueba puede utilizarse para identificar un tipo de información confidencial. Proximidad y nivel de confianza también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="1b076-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="1b076-110">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="1b076-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-111">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-111">Format</span></span>

<span data-ttu-id="1b076-112">9 dígitos, que pueden tener un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="1b076-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-113">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-113">Pattern</span></span>

<span data-ttu-id="1b076-114">Con formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-114">Formatted:</span></span>
- <span data-ttu-id="1b076-115">Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="1b076-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="1b076-116">Un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-116">A hyphen</span></span>
- <span data-ttu-id="1b076-117">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-117">Four digits</span></span>
- <span data-ttu-id="1b076-118">Un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-118">A hyphen</span></span>
- <span data-ttu-id="1b076-119">Un dígito</span><span class="sxs-lookup"><span data-stu-id="1b076-119">A digit</span></span>

<span data-ttu-id="1b076-120">Sin formato: dígitos consecutivos 9 a partir de 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="1b076-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="1b076-121">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-121">Checksum</span></span>

<span data-ttu-id="1b076-122">No</span><span class="sxs-lookup"><span data-stu-id="1b076-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-123">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-123">Definition</span></span>

<span data-ttu-id="1b076-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-125">La función Func_aba_routing encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-126">Se encuentra una palabra clave de Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="1b076-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="1b076-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="1b076-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="1b076-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="1b076-129">aba</span><span class="sxs-lookup"><span data-stu-id="1b076-129">aba</span></span>
- <span data-ttu-id="1b076-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="1b076-130">aba #</span></span>
- <span data-ttu-id="1b076-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="1b076-131">aba routing #</span></span>
- <span data-ttu-id="1b076-132">número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="1b076-132">aba routing number</span></span>
- <span data-ttu-id="1b076-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="1b076-133">aba#</span></span>
- <span data-ttu-id="1b076-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="1b076-134">abarouting#</span></span>
- <span data-ttu-id="1b076-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="1b076-135">aba number</span></span>
- <span data-ttu-id="1b076-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="1b076-136">abaroutingnumber</span></span>
- <span data-ttu-id="1b076-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="1b076-137">american bank association routing #</span></span>
- <span data-ttu-id="1b076-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="1b076-138">american bank association routing number</span></span>
- <span data-ttu-id="1b076-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="1b076-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="1b076-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="1b076-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="1b076-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="1b076-141">bank routing number</span></span>
- <span data-ttu-id="1b076-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="1b076-142">bankrouting#</span></span>
- <span data-ttu-id="1b076-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="1b076-143">bankroutingnumber</span></span>
- <span data-ttu-id="1b076-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="1b076-144">routing transit number</span></span>
- <span data-ttu-id="1b076-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="1b076-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="1b076-146">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="1b076-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-147">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-147">Format</span></span>

<span data-ttu-id="1b076-148">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="1b076-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-149">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-149">Pattern</span></span>

<span data-ttu-id="1b076-150">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-150">Eight digits:</span></span>
- <span data-ttu-id="1b076-151">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-151">Two digits</span></span>
- <span data-ttu-id="1b076-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-152">A period</span></span>
- <span data-ttu-id="1b076-153">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-153">Three digits</span></span>
- <span data-ttu-id="1b076-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-154">A period</span></span>
- <span data-ttu-id="1b076-155">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-156">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-156">Checksum</span></span>

<span data-ttu-id="1b076-157">No</span><span class="sxs-lookup"><span data-stu-id="1b076-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-158">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-158">Definition</span></span>

<span data-ttu-id="1b076-159">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-160">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-161">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="1b076-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="1b076-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="1b076-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="1b076-164">Número de identidad nacional de Argentina
</span><span class="sxs-lookup"><span data-stu-id="1b076-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="1b076-165">Identidad</span><span class="sxs-lookup"><span data-stu-id="1b076-165">Identity</span></span> 
- <span data-ttu-id="1b076-166">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="1b076-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="1b076-167">DNI</span></span> 
- <span data-ttu-id="1b076-168">Registro nacional de NIC de personas</span><span class="sxs-lookup"><span data-stu-id="1b076-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="1b076-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="1b076-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="1b076-170">Registro nacional de las personas
</span><span class="sxs-lookup"><span data-stu-id="1b076-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="1b076-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="1b076-171">Identidad</span></span> 
- <span data-ttu-id="1b076-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="1b076-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="1b076-173">Número de cuenta bancaria de Australia</span><span class="sxs-lookup"><span data-stu-id="1b076-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-174">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-174">Format</span></span>

<span data-ttu-id="1b076-175">De 6 a 10 dígitos con o sin número de sucursal bancaria de estado</span><span class="sxs-lookup"><span data-stu-id="1b076-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-176">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-176">Pattern</span></span>

<span data-ttu-id="1b076-p103">Número de cuenta es 10 de 6 dígitos. Número de sucursal de estado de banco de Australia:</span><span class="sxs-lookup"><span data-stu-id="1b076-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="1b076-179">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-179">Three digits</span></span> 
- <span data-ttu-id="1b076-180">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-180">A hyphen</span></span> 
- <span data-ttu-id="1b076-181">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-182">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-182">Checksum</span></span>

<span data-ttu-id="1b076-183">No</span><span class="sxs-lookup"><span data-stu-id="1b076-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-184">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-184">Definition</span></span>

<span data-ttu-id="1b076-185">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-186">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="1b076-187">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="1b076-188">La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="1b076-189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-190">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="1b076-191">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="1b076-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="1b076-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="1b076-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="1b076-194">swift bank code</span></span>
- <span data-ttu-id="1b076-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="1b076-195">correspondent bank</span></span>
- <span data-ttu-id="1b076-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="1b076-196">base currency</span></span>
- <span data-ttu-id="1b076-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="1b076-197">usa account</span></span>
- <span data-ttu-id="1b076-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="1b076-198">holder address</span></span>
- <span data-ttu-id="1b076-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="1b076-199">bank address</span></span>
- <span data-ttu-id="1b076-200">
information account</span><span class="sxs-lookup"><span data-stu-id="1b076-200">information account</span></span>
- <span data-ttu-id="1b076-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="1b076-201">fund transfers</span></span>
- <span data-ttu-id="1b076-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="1b076-202">bank charges</span></span>
- <span data-ttu-id="1b076-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="1b076-203">bank details</span></span>
- <span data-ttu-id="1b076-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="1b076-204">banking information</span></span>
- <span data-ttu-id="1b076-205">
full names</span><span class="sxs-lookup"><span data-stu-id="1b076-205">full names</span></span>
- <span data-ttu-id="1b076-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="1b076-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="1b076-207">Número de licencia de conducción de Australia</span><span class="sxs-lookup"><span data-stu-id="1b076-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-208">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-208">Format</span></span>

<span data-ttu-id="1b076-209">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-210">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-210">Pattern</span></span>

<span data-ttu-id="1b076-211">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="1b076-212">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-213">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-213">Two digits</span></span> 
- <span data-ttu-id="1b076-214">Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="1b076-215">O bien</span><span class="sxs-lookup"><span data-stu-id="1b076-215">OR</span></span>

- <span data-ttu-id="1b076-216">1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="1b076-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-217">4-9 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-217">4-9 digits</span></span>

<span data-ttu-id="1b076-218">O bien</span><span class="sxs-lookup"><span data-stu-id="1b076-218">OR</span></span>

- <span data-ttu-id="1b076-219">Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-220">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-220">Checksum</span></span>

<span data-ttu-id="1b076-221">No</span><span class="sxs-lookup"><span data-stu-id="1b076-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-222">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-222">Definition</span></span>

<span data-ttu-id="1b076-223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-224">La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-225">Se encuentra una palabra clave de Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="1b076-226">No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="1b076-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="1b076-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="1b076-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="1b076-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="1b076-229">international driving permits</span></span>
- <span data-ttu-id="1b076-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="1b076-230">australian automobile association</span></span>
- <span data-ttu-id="1b076-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="1b076-231">sydney nsw</span></span>
- <span data-ttu-id="1b076-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="1b076-232">international driving permit</span></span>
- <span data-ttu-id="1b076-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="1b076-233">DriverLicence</span></span>
- <span data-ttu-id="1b076-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="1b076-234">DriverLicences</span></span>
- <span data-ttu-id="1b076-235">Lic de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-235">Driver Lic</span></span>
- <span data-ttu-id="1b076-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-236">Driver Licence</span></span>
- <span data-ttu-id="1b076-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-237">Driver Licences</span></span>
- <span data-ttu-id="1b076-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="1b076-238">DriversLic</span></span>
- <span data-ttu-id="1b076-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="1b076-239">DriversLicence</span></span>
- <span data-ttu-id="1b076-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="1b076-240">DriversLicences</span></span>
- <span data-ttu-id="1b076-241">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-241">Drivers Lic</span></span>
- <span data-ttu-id="1b076-242">LIC de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-242">Drivers Lics</span></span>
- <span data-ttu-id="1b076-243">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-243">Drivers Licence</span></span>
- <span data-ttu-id="1b076-244">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-244">Drivers Licences</span></span>
- <span data-ttu-id="1b076-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="1b076-245">Driver'Lic</span></span>
- <span data-ttu-id="1b076-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="1b076-246">Driver'Lics</span></span>
- <span data-ttu-id="1b076-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="1b076-247">Driver'Licence</span></span>
- <span data-ttu-id="1b076-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="1b076-248">Driver'Licences</span></span>
- <span data-ttu-id="1b076-249">Controlador ' Lic</span><span class="sxs-lookup"><span data-stu-id="1b076-249">Driver' Lic</span></span>
- <span data-ttu-id="1b076-250">Controlador ' LIC</span><span class="sxs-lookup"><span data-stu-id="1b076-250">Driver' Lics</span></span>
- <span data-ttu-id="1b076-251">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="1b076-251">Driver' Licence</span></span>
- <span data-ttu-id="1b076-252">Controlador ' certificados</span><span class="sxs-lookup"><span data-stu-id="1b076-252">Driver' Licences</span></span>
- <span data-ttu-id="1b076-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="1b076-253">Driver'sLic</span></span>
- <span data-ttu-id="1b076-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="1b076-254">Driver'sLics</span></span>
- <span data-ttu-id="1b076-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="1b076-255">Driver'sLicence</span></span>
- <span data-ttu-id="1b076-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="1b076-256">Driver'sLicences</span></span>
- <span data-ttu-id="1b076-257">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-257">Driver's Lic</span></span>
- <span data-ttu-id="1b076-258">LIC del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-258">Driver's Lics</span></span>
- <span data-ttu-id="1b076-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-259">Driver's Licence</span></span>
- <span data-ttu-id="1b076-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-260">Driver's Licences</span></span>
- <span data-ttu-id="1b076-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-261">DriverLic#</span></span>
- <span data-ttu-id="1b076-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-262">DriverLics#</span></span>
- <span data-ttu-id="1b076-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="1b076-263">DriverLicence#</span></span>
- <span data-ttu-id="1b076-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="1b076-264">DriverLicences#</span></span>
- <span data-ttu-id="1b076-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="1b076-265">Driver Lic#</span></span>
- <span data-ttu-id="1b076-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-266">Driver Lics#</span></span>
- <span data-ttu-id="1b076-267">Controlador certificado #</span><span class="sxs-lookup"><span data-stu-id="1b076-267">Driver Licence#</span></span>
- <span data-ttu-id="1b076-268">Controlador certificados #</span><span class="sxs-lookup"><span data-stu-id="1b076-268">Driver Licences#</span></span>
- <span data-ttu-id="1b076-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-269">DriversLic#</span></span>
- <span data-ttu-id="1b076-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-270">DriversLics#</span></span>
- <span data-ttu-id="1b076-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="1b076-271">DriversLicence#</span></span>
- <span data-ttu-id="1b076-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="1b076-272">DriversLicences#</span></span>
- <span data-ttu-id="1b076-273">Controladores Lic #</span><span class="sxs-lookup"><span data-stu-id="1b076-273">Drivers Lic#</span></span>
- <span data-ttu-id="1b076-274">Controladores LIC #</span><span class="sxs-lookup"><span data-stu-id="1b076-274">Drivers Lics#</span></span>
- <span data-ttu-id="1b076-275">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-275">Drivers Licence#</span></span>
- <span data-ttu-id="1b076-276">Controladores certificados #</span><span class="sxs-lookup"><span data-stu-id="1b076-276">Drivers Licences#</span></span>
- <span data-ttu-id="1b076-277">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-277">Driver'Lic#</span></span>
- <span data-ttu-id="1b076-278">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-278">Driver'Lics#</span></span>
- <span data-ttu-id="1b076-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="1b076-279">Driver'Licence#</span></span>
- <span data-ttu-id="1b076-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="1b076-280">Driver'Licences#</span></span>
- <span data-ttu-id="1b076-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-281">Driver' Lic#</span></span>
- <span data-ttu-id="1b076-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-282">Driver' Lics#</span></span>
- <span data-ttu-id="1b076-283">Controlador ' certificado #</span><span class="sxs-lookup"><span data-stu-id="1b076-283">Driver' Licence#</span></span>
- <span data-ttu-id="1b076-284">Controlador ' certificados #</span><span class="sxs-lookup"><span data-stu-id="1b076-284">Driver' Licences#</span></span>
- <span data-ttu-id="1b076-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-285">Driver'sLic#</span></span>
- <span data-ttu-id="1b076-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-286">Driver'sLics#</span></span>
- <span data-ttu-id="1b076-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="1b076-287">Driver'sLicence#</span></span>
- <span data-ttu-id="1b076-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="1b076-288">Driver'sLicences#</span></span>
- <span data-ttu-id="1b076-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-289">Driver's Lic#</span></span>
- <span data-ttu-id="1b076-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-290">Driver's Lics#</span></span>
- <span data-ttu-id="1b076-291">Certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-291">Driver's Licence#</span></span>
- <span data-ttu-id="1b076-292">El certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="1b076-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="1b076-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="1b076-294">aaa</span><span class="sxs-lookup"><span data-stu-id="1b076-294">aaa</span></span>
- <span data-ttu-id="1b076-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="1b076-295">DriverLicense</span></span>
- <span data-ttu-id="1b076-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-296">DriverLicenses</span></span>
- <span data-ttu-id="1b076-297">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-297">Driver License</span></span>
- <span data-ttu-id="1b076-298">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-298">Driver Licenses</span></span>
- <span data-ttu-id="1b076-299">PermisoDeConducción</span><span class="sxs-lookup"><span data-stu-id="1b076-299">DriversLicense</span></span>
- <span data-ttu-id="1b076-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-300">DriversLicenses</span></span>
- <span data-ttu-id="1b076-301">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-301">Drivers License</span></span>
- <span data-ttu-id="1b076-302">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-302">Drivers Licenses</span></span>
- <span data-ttu-id="1b076-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="1b076-303">Driver'License</span></span>
- <span data-ttu-id="1b076-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="1b076-304">Driver'Licenses</span></span>
- <span data-ttu-id="1b076-305">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="1b076-305">Driver' License</span></span>
- <span data-ttu-id="1b076-306">Controlador ' licencias</span><span class="sxs-lookup"><span data-stu-id="1b076-306">Driver' Licenses</span></span>
- <span data-ttu-id="1b076-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="1b076-307">Driver'sLicense</span></span>
- <span data-ttu-id="1b076-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-308">Driver'sLicenses</span></span>
- <span data-ttu-id="1b076-309">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="1b076-309">Driver's License</span></span>
- <span data-ttu-id="1b076-310">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-310">Driver's Licenses</span></span>
- <span data-ttu-id="1b076-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="1b076-311">DriverLicense#</span></span>
- <span data-ttu-id="1b076-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-312">DriverLicenses#</span></span>
- <span data-ttu-id="1b076-313">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="1b076-313">Driver License#</span></span>
- <span data-ttu-id="1b076-314">Controlador licencias #</span><span class="sxs-lookup"><span data-stu-id="1b076-314">Driver Licenses#</span></span>
- <span data-ttu-id="1b076-315">PermisoDeConducción #</span><span class="sxs-lookup"><span data-stu-id="1b076-315">DriversLicense#</span></span>
- <span data-ttu-id="1b076-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-316">DriversLicenses#</span></span>
- <span data-ttu-id="1b076-317">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-317">Drivers License#</span></span>
- <span data-ttu-id="1b076-318">Licencias de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-318">Drivers Licenses#</span></span>
- <span data-ttu-id="1b076-319">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-319">Driver'License#</span></span>
- <span data-ttu-id="1b076-320">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-320">Driver'Licenses#</span></span>
- <span data-ttu-id="1b076-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-321">Driver' License#</span></span>
- <span data-ttu-id="1b076-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-322">Driver' Licenses#</span></span>
- <span data-ttu-id="1b076-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="1b076-323">Driver'sLicense#</span></span>
- <span data-ttu-id="1b076-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="1b076-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-325">Driver's License#</span></span>
- <span data-ttu-id="1b076-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="1b076-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="1b076-327">Número de cuenta médica de Australia</span><span class="sxs-lookup"><span data-stu-id="1b076-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-328">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-328">Format</span></span>

<span data-ttu-id="1b076-329">Entre 10 y 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-330">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-330">Pattern</span></span>

<span data-ttu-id="1b076-331">Entre 10 y 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-331">10-11 digits:</span></span>
- <span data-ttu-id="1b076-332">el primer dígito está en el intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="1b076-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="1b076-333">El noveno dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="1b076-334">El décimo dígito es el dígito de emisión</span><span class="sxs-lookup"><span data-stu-id="1b076-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="1b076-335">El undécimo dígito (opcional) es el número individual</span><span class="sxs-lookup"><span data-stu-id="1b076-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-336">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-336">Checksum</span></span>

<span data-ttu-id="1b076-337">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-338">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-338">Definition</span></span>

<span data-ttu-id="1b076-339">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-340">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-341">Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="1b076-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="1b076-342">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-342">The checksum passes.</span></span>

<span data-ttu-id="1b076-343">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-344">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-345">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-346">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="1b076-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="1b076-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="1b076-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="1b076-348">bank account details</span></span>
- <span data-ttu-id="1b076-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="1b076-349">medicare payments</span></span>
- <span data-ttu-id="1b076-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="1b076-350">mortgage account</span></span>
- <span data-ttu-id="1b076-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="1b076-351">bank payments</span></span>
- <span data-ttu-id="1b076-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="1b076-352">information branch</span></span>
- <span data-ttu-id="1b076-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="1b076-353">credit card loan</span></span>
- <span data-ttu-id="1b076-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="1b076-354">department of human services</span></span>
- <span data-ttu-id="1b076-355">servicio local</span><span class="sxs-lookup"><span data-stu-id="1b076-355">local service</span></span>
- <span data-ttu-id="1b076-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="1b076-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="1b076-357">Número de pasaporte de Australia</span><span class="sxs-lookup"><span data-stu-id="1b076-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-358">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-358">Format</span></span>

<span data-ttu-id="1b076-359">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-360">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-360">Pattern</span></span>

<span data-ttu-id="1b076-361">Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-362">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-362">Checksum</span></span>

<span data-ttu-id="1b076-363">No</span><span class="sxs-lookup"><span data-stu-id="1b076-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-364">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-364">Definition</span></span>

<span data-ttu-id="1b076-365">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-366">La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-367">Se ha encontrado una palabra clave de Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-368">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="1b076-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-369">Keyword_passport</span></span>

- <span data-ttu-id="1b076-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="1b076-370">Passport Number</span></span>
- <span data-ttu-id="1b076-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="1b076-371">Passport No</span></span>
- <span data-ttu-id="1b076-372">Passport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-372">Passport #</span></span>
- <span data-ttu-id="1b076-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-373">Passport#</span></span>
- <span data-ttu-id="1b076-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="1b076-374">PassportID</span></span>
- <span data-ttu-id="1b076-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="1b076-375">Passportno</span></span>
- <span data-ttu-id="1b076-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-376">passportnumber</span></span>
- <span data-ttu-id="1b076-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="1b076-377">パスポート</span></span>
- <span data-ttu-id="1b076-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-378">パスポート番号</span></span>
- <span data-ttu-id="1b076-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="1b076-379">パスポートのNum</span></span>
- <span data-ttu-id="1b076-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-380">パスポート ＃</span></span> 
- <span data-ttu-id="1b076-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="1b076-381">Numéro de passeport</span></span>
- <span data-ttu-id="1b076-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="1b076-382">Passeport n °</span></span>
- <span data-ttu-id="1b076-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="1b076-383">Passeport Non</span></span>
- <span data-ttu-id="1b076-384">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-384">Passeport #</span></span>
- <span data-ttu-id="1b076-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-385">Passeport#</span></span>
- <span data-ttu-id="1b076-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="1b076-386">PasseportNon</span></span>
- <span data-ttu-id="1b076-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="1b076-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="1b076-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="1b076-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="1b076-389">passport</span><span class="sxs-lookup"><span data-stu-id="1b076-389">passport</span></span>
- <span data-ttu-id="1b076-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="1b076-390">passport details</span></span>
- <span data-ttu-id="1b076-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="1b076-391">immigration and citizenship</span></span>
- <span data-ttu-id="1b076-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="1b076-392">commonwealth of australia</span></span>
- <span data-ttu-id="1b076-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="1b076-393">department of immigration</span></span>
- <span data-ttu-id="1b076-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="1b076-394">residential address</span></span>
- <span data-ttu-id="1b076-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="1b076-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="1b076-396">visa
</span><span class="sxs-lookup"><span data-stu-id="1b076-396">visa</span></span>
- <span data-ttu-id="1b076-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="1b076-397">national identity card</span></span>
- <span data-ttu-id="1b076-398">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="1b076-398">passport number</span></span>
- <span data-ttu-id="1b076-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="1b076-399">travel document</span></span>
- <span data-ttu-id="1b076-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="1b076-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="1b076-401">Número de archivo de impuestos de Australia</span><span class="sxs-lookup"><span data-stu-id="1b076-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-402">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-402">Format</span></span>

<span data-ttu-id="1b076-403">Entre 8 y 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-404">Pattern</span></span>

<span data-ttu-id="1b076-405">8-9 dígitos que normalmente se presentan con espacios como sigue:</span><span class="sxs-lookup"><span data-stu-id="1b076-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="1b076-406">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-406">Three digits</span></span> 
- <span data-ttu-id="1b076-407">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="1b076-407">An optional space</span></span> 
- <span data-ttu-id="1b076-408">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-408">Three digits</span></span> 
- <span data-ttu-id="1b076-409">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="1b076-409">An optional space</span></span> 
- <span data-ttu-id="1b076-410">2-3 dígitos donde el último dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-411">Checksum</span></span>

<span data-ttu-id="1b076-412">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-413">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-413">Definition</span></span>

<span data-ttu-id="1b076-414">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-415">La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-416">No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="1b076-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="1b076-417">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-418">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="1b076-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="1b076-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="1b076-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="1b076-420">australian business number</span></span>
- <span data-ttu-id="1b076-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="1b076-421">marginal tax rate</span></span>
- <span data-ttu-id="1b076-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="1b076-422">medicare levy</span></span>
- <span data-ttu-id="1b076-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="1b076-423">portfolio number</span></span>
- <span data-ttu-id="1b076-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="1b076-424">service veterans</span></span>
- <span data-ttu-id="1b076-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="1b076-425">withholding tax</span></span>
- <span data-ttu-id="1b076-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="1b076-426">individual tax return</span></span>
- <span data-ttu-id="1b076-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="1b076-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="1b076-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="1b076-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="1b076-429">00000000</span><span class="sxs-lookup"><span data-stu-id="1b076-429">00000000</span></span>
- <span data-ttu-id="1b076-430">11111111</span><span class="sxs-lookup"><span data-stu-id="1b076-430">11111111</span></span>
- <span data-ttu-id="1b076-431">por 22222222</span><span class="sxs-lookup"><span data-stu-id="1b076-431">22222222</span></span>
- <span data-ttu-id="1b076-432">33333333</span><span class="sxs-lookup"><span data-stu-id="1b076-432">33333333</span></span>
- <span data-ttu-id="1b076-433">44444444</span><span class="sxs-lookup"><span data-stu-id="1b076-433">44444444</span></span>
- <span data-ttu-id="1b076-434">55555555</span><span class="sxs-lookup"><span data-stu-id="1b076-434">55555555</span></span>
- <span data-ttu-id="1b076-435">66666666</span><span class="sxs-lookup"><span data-stu-id="1b076-435">66666666</span></span>
- <span data-ttu-id="1b076-436">77777777</span><span class="sxs-lookup"><span data-stu-id="1b076-436">77777777</span></span>
- <span data-ttu-id="1b076-437">88888888</span><span class="sxs-lookup"><span data-stu-id="1b076-437">88888888</span></span>
- <span data-ttu-id="1b076-438">99999999</span><span class="sxs-lookup"><span data-stu-id="1b076-438">99999999</span></span>
- <span data-ttu-id="1b076-439">000000000</span><span class="sxs-lookup"><span data-stu-id="1b076-439">000000000</span></span>
- <span data-ttu-id="1b076-440">111111111</span><span class="sxs-lookup"><span data-stu-id="1b076-440">111111111</span></span>
- <span data-ttu-id="1b076-441">222222222</span><span class="sxs-lookup"><span data-stu-id="1b076-441">222222222</span></span>
- <span data-ttu-id="1b076-442">333333333</span><span class="sxs-lookup"><span data-stu-id="1b076-442">333333333</span></span>
- <span data-ttu-id="1b076-443">444444444</span><span class="sxs-lookup"><span data-stu-id="1b076-443">444444444</span></span>
- <span data-ttu-id="1b076-444">555555555</span><span class="sxs-lookup"><span data-stu-id="1b076-444">555555555</span></span>
- <span data-ttu-id="1b076-445">666666666</span><span class="sxs-lookup"><span data-stu-id="1b076-445">666666666</span></span>
- <span data-ttu-id="1b076-446">777777777</span><span class="sxs-lookup"><span data-stu-id="1b076-446">777777777</span></span>
- <span data-ttu-id="1b076-447">888888888</span><span class="sxs-lookup"><span data-stu-id="1b076-447">888888888</span></span>
- <span data-ttu-id="1b076-448">999999999</span><span class="sxs-lookup"><span data-stu-id="1b076-448">999999999</span></span>
- <span data-ttu-id="1b076-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="1b076-449">0000000000</span></span>
- <span data-ttu-id="1b076-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="1b076-450">1111111111</span></span>
- <span data-ttu-id="1b076-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="1b076-451">2222222222</span></span>
- <span data-ttu-id="1b076-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="1b076-452">3333333333</span></span>
- <span data-ttu-id="1b076-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="1b076-453">4444444444</span></span>
- <span data-ttu-id="1b076-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="1b076-454">5555555555</span></span>
- <span data-ttu-id="1b076-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="1b076-455">6666666666</span></span>
- <span data-ttu-id="1b076-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="1b076-456">7777777777</span></span>
- <span data-ttu-id="1b076-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="1b076-457">8888888888</span></span>
- <span data-ttu-id="1b076-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="1b076-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="1b076-459">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="1b076-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-460">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-460">Format</span></span>

<span data-ttu-id="1b076-461">11 dígitos más delimitadores</span><span class="sxs-lookup"><span data-stu-id="1b076-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-462">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-462">Pattern</span></span>

<span data-ttu-id="1b076-463">11 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="1b076-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="1b076-464">Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="1b076-465">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-465">A hyphen</span></span> 
- <span data-ttu-id="1b076-466">Tres dígitos secuenciales (impares para hombres, pares para mujeres) </span><span class="sxs-lookup"><span data-stu-id="1b076-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="1b076-467">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-467">A period</span></span> 
- <span data-ttu-id="1b076-468">Dos dígitos que son un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-469">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-469">Checksum</span></span>

<span data-ttu-id="1b076-470">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-471">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-471">Definition</span></span>

<span data-ttu-id="1b076-472">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-473">La función Func_belgium_national_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-474">Se encuentra una palabra clave de Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="1b076-475">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-476">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="1b076-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="1b076-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="1b076-478">Identidad</span><span class="sxs-lookup"><span data-stu-id="1b076-478">Identity</span></span>
- <span data-ttu-id="1b076-479">Registration</span><span class="sxs-lookup"><span data-stu-id="1b076-479">Registration</span></span>
- <span data-ttu-id="1b076-480">Identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-480">Identification</span></span> 
- <span data-ttu-id="1b076-481">ID</span><span class="sxs-lookup"><span data-stu-id="1b076-481">ID</span></span> 
- <span data-ttu-id="1b076-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="1b076-482">Identiteitskaart</span></span>
- <span data-ttu-id="1b076-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="1b076-483">Registratie nummer</span></span> 
- <span data-ttu-id="1b076-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-484">Identificatie nummer</span></span> 
- <span data-ttu-id="1b076-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="1b076-485">Identiteit</span></span>
- <span data-ttu-id="1b076-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="1b076-486">Registratie</span></span>
- <span data-ttu-id="1b076-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="1b076-487">Identificatie</span></span> 
- <span data-ttu-id="1b076-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="1b076-488">Carte d’identité</span></span> 
- <span data-ttu-id="1b076-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="1b076-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="1b076-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="1b076-490">numéro d'identification</span></span>
- <span data-ttu-id="1b076-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="1b076-491">identité</span></span> 
- <span data-ttu-id="1b076-492">inscription
</span><span class="sxs-lookup"><span data-stu-id="1b076-492">inscription</span></span> 
- <span data-ttu-id="1b076-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="1b076-493">Identifikation</span></span>
- <span data-ttu-id="1b076-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="1b076-494">Identifizierung</span></span>
- <span data-ttu-id="1b076-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-495">Identifikationsnummer</span></span>
- <span data-ttu-id="1b076-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="1b076-496">Personalausweis</span></span>
- <span data-ttu-id="1b076-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="1b076-497">Registrierung</span></span>
- <span data-ttu-id="1b076-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="1b076-499">Número CPF de Brasil</span><span class="sxs-lookup"><span data-stu-id="1b076-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-500">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-500">Format</span></span>

<span data-ttu-id="1b076-501">11 dígitos incluido un dígito de control y que pueden tener o no formato</span><span class="sxs-lookup"><span data-stu-id="1b076-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-502">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-502">Pattern</span></span>

<span data-ttu-id="1b076-503">Con formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-503">Formatted:</span></span>
- <span data-ttu-id="1b076-504">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-504">Three digits</span></span> 
- <span data-ttu-id="1b076-505">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-505">A period</span></span> 
- <span data-ttu-id="1b076-506">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-506">Three digits</span></span> 
- <span data-ttu-id="1b076-507">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-507">A period</span></span> 
- <span data-ttu-id="1b076-508">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-508">Three digits</span></span> 
- <span data-ttu-id="1b076-509">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-509">A hyphen</span></span> 
- <span data-ttu-id="1b076-510">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="1b076-510">Two digits which are check digits</span></span>

<span data-ttu-id="1b076-511">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-511">Unformatted:</span></span>
- <span data-ttu-id="1b076-512">11 dígitos, donde los dos últimos dígitos son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="1b076-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-513">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-513">Checksum</span></span>

<span data-ttu-id="1b076-514">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-515">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-515">Definition</span></span>

<span data-ttu-id="1b076-516">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-517">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-518">Se encuentra una palabra clave de Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="1b076-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="1b076-519">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-519">The checksum passes.</span></span>

<span data-ttu-id="1b076-520">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-521">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-522">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-523">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="1b076-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="1b076-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="1b076-525">CPF</span><span class="sxs-lookup"><span data-stu-id="1b076-525">CPF</span></span>
- <span data-ttu-id="1b076-526">Identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-526">Identification</span></span>
- <span data-ttu-id="1b076-527">Registro</span><span class="sxs-lookup"><span data-stu-id="1b076-527">Registration</span></span>
- <span data-ttu-id="1b076-528">Ingresos</span><span class="sxs-lookup"><span data-stu-id="1b076-528">Revenue</span></span>
- <span data-ttu-id="1b076-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="1b076-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="1b076-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="1b076-530">Imposto</span></span> 
- <span data-ttu-id="1b076-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="1b076-531">Identificação</span></span> 
- <span data-ttu-id="1b076-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="1b076-532">Inscrição</span></span> 
- <span data-ttu-id="1b076-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="1b076-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="1b076-534">Número de entidad jurídica de Brasil (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="1b076-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-535">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-535">Format</span></span>

<span data-ttu-id="1b076-536">14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores</span><span class="sxs-lookup"><span data-stu-id="1b076-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-537">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-537">Pattern</span></span>
<span data-ttu-id="1b076-538">14 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="1b076-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="1b076-539">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-539">Two digits</span></span> 
- <span data-ttu-id="1b076-540">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-540">A period</span></span> 
- <span data-ttu-id="1b076-541">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-541">Three digits</span></span> 
- <span data-ttu-id="1b076-542">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-542">A period</span></span> 
- <span data-ttu-id="1b076-543">Tres dígitos (estos ocho primeros dígitos son el número de registro) </span><span class="sxs-lookup"><span data-stu-id="1b076-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="1b076-544">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="1b076-544">A forward slash</span></span> 
- <span data-ttu-id="1b076-545">Número de sucursal de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-545">Four-digit branch number</span></span> 
- <span data-ttu-id="1b076-546">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-546">A hyphen</span></span> 
- <span data-ttu-id="1b076-547">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="1b076-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-548">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-548">Checksum</span></span>

<span data-ttu-id="1b076-549">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-550">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-550">Definition</span></span>

<span data-ttu-id="1b076-551">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-552">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-553">Se encuentra una palabra clave de Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="1b076-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="1b076-554">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-554">The checksum passes.</span></span>

<span data-ttu-id="1b076-555">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-556">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-557">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-558">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="1b076-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="1b076-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="1b076-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="1b076-560">CNPJ</span></span> 
- <span data-ttu-id="1b076-561">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="1b076-561">CNPJ/MF</span></span> 
- <span data-ttu-id="1b076-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="1b076-562">CNPJ-MF</span></span> 
- <span data-ttu-id="1b076-563">Registro nacional de entidades jurídicas
</span><span class="sxs-lookup"><span data-stu-id="1b076-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="1b076-564">Registro de contribuyentes
</span><span class="sxs-lookup"><span data-stu-id="1b076-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="1b076-565">Entidad jurídica
</span><span class="sxs-lookup"><span data-stu-id="1b076-565">Legal entity</span></span> 
- <span data-ttu-id="1b076-566">Entidades jurídicas
</span><span class="sxs-lookup"><span data-stu-id="1b076-566">Legal entities</span></span> 
- <span data-ttu-id="1b076-567">Estado de registro
</span><span class="sxs-lookup"><span data-stu-id="1b076-567">Registration Status</span></span> 
- <span data-ttu-id="1b076-568">Negocio
</span><span class="sxs-lookup"><span data-stu-id="1b076-568">Business</span></span> 
- <span data-ttu-id="1b076-569">Company</span><span class="sxs-lookup"><span data-stu-id="1b076-569">Company</span></span>
- <span data-ttu-id="1b076-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="1b076-570">CNPJ</span></span> 
- <span data-ttu-id="1b076-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="1b076-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="1b076-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="1b076-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="1b076-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="1b076-573">CGC</span></span> 
- <span data-ttu-id="1b076-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="1b076-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="1b076-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="1b076-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="1b076-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="1b076-576">Situação cadastral</span></span> 
- <span data-ttu-id="1b076-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="1b076-577">Inscrição</span></span> 
- <span data-ttu-id="1b076-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="1b076-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="1b076-579">Tarjeta de identificación nacional de Brasil (RG)</span><span class="sxs-lookup"><span data-stu-id="1b076-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-580">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-580">Format</span></span>

<span data-ttu-id="1b076-581">Registro Geral (formato anterior): nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="1b076-582">Registro de Identidade (RIC) (nuevo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-583">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-583">Pattern</span></span>

<span data-ttu-id="1b076-584">Registro de Geral (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="1b076-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="1b076-585">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-585">Two digits</span></span> 
- <span data-ttu-id="1b076-586">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-586">A period</span></span> 
- <span data-ttu-id="1b076-587">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-587">Three digits</span></span> 
- <span data-ttu-id="1b076-588">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-588">A period</span></span> 
- <span data-ttu-id="1b076-589">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-589">Three digits</span></span> 
- <span data-ttu-id="1b076-590">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-590">A hyphen</span></span> 
- <span data-ttu-id="1b076-591">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-591">One digit which is a check digit</span></span>

<span data-ttu-id="1b076-592">Registro de Identidade (RIC) (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="1b076-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="1b076-593">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-593">10 digits</span></span> 
- <span data-ttu-id="1b076-594">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-594">A hyphen</span></span> 
- <span data-ttu-id="1b076-595">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-596">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-596">Checksum</span></span>

<span data-ttu-id="1b076-597">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-598">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-598">Definition</span></span>

<span data-ttu-id="1b076-599">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-600">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-601">Se encuentra una palabra clave de Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="1b076-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="1b076-602">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-602">The checksum passes.</span></span>

<span data-ttu-id="1b076-603">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-604">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-605">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-606">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="1b076-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="1b076-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="1b076-608">Cédula de identidade tarjeta de identidad nacional identificador número de rregistro registro de Iidentidade registro geral RG (esta palabra clave distingue mayúsculas de minúsculas) RIC (esta palabra clave distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="1b076-609">Número de cuenta bancaria de Canadá</span><span class="sxs-lookup"><span data-stu-id="1b076-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-610">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-610">Format</span></span>

<span data-ttu-id="1b076-611">Siete o doce dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-612">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-612">Pattern</span></span>

<span data-ttu-id="1b076-613">El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.</span><span class="sxs-lookup"><span data-stu-id="1b076-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="1b076-614">Un número de tránsito de cuenta bancaria de Canadá es:</span><span class="sxs-lookup"><span data-stu-id="1b076-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="1b076-615">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-615">Five digits</span></span> 
- <span data-ttu-id="1b076-616">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-616">A hyphen</span></span> 
- <span data-ttu-id="1b076-617">Tres dígitos o</span><span class="sxs-lookup"><span data-stu-id="1b076-617">Three digits OR</span></span>
- <span data-ttu-id="1b076-618">Un cero "0" </span><span class="sxs-lookup"><span data-stu-id="1b076-618">A zero "0"</span></span> 
- <span data-ttu-id="1b076-619">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-620">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-620">Checksum</span></span>

<span data-ttu-id="1b076-621">No</span><span class="sxs-lookup"><span data-stu-id="1b076-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-622">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-622">Definition</span></span>

<span data-ttu-id="1b076-623">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-624">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-625">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="1b076-626">La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="1b076-627">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-628">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-629">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-630">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="1b076-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="1b076-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="1b076-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="1b076-632">canada savings bonds</span></span>
- <span data-ttu-id="1b076-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="1b076-633">canada revenue agency</span></span>
- <span data-ttu-id="1b076-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="1b076-634">canadian financial institution</span></span>
- <span data-ttu-id="1b076-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="1b076-635">direct deposit form</span></span>
- <span data-ttu-id="1b076-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="1b076-636">canadian citizen</span></span>
- <span data-ttu-id="1b076-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="1b076-637">legal representative</span></span>
- <span data-ttu-id="1b076-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="1b076-638">notary public</span></span>
- <span data-ttu-id="1b076-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="1b076-639">commissioner for oaths</span></span>
- <span data-ttu-id="1b076-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="1b076-640">child care benefit</span></span>
- <span data-ttu-id="1b076-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="1b076-641">universal child care</span></span>
- <span data-ttu-id="1b076-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="1b076-642">canada child tax benefit</span></span>
- <span data-ttu-id="1b076-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="1b076-643">income tax benefit</span></span>
- <span data-ttu-id="1b076-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="1b076-644">harmonized sales tax</span></span>
- <span data-ttu-id="1b076-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="1b076-645">social insurance number</span></span>
- <span data-ttu-id="1b076-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="1b076-646">income tax refund</span></span>
- <span data-ttu-id="1b076-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="1b076-647">child tax benefit</span></span>
- <span data-ttu-id="1b076-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="1b076-648">territorial payments</span></span>
- <span data-ttu-id="1b076-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="1b076-649">institution number</span></span>
- <span data-ttu-id="1b076-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="1b076-650">deposit request</span></span>
- <span data-ttu-id="1b076-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="1b076-651">banking information</span></span>
- <span data-ttu-id="1b076-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="1b076-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="1b076-653">Número de licencia de conductor de Canadá</span><span class="sxs-lookup"><span data-stu-id="1b076-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-654">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-654">Format</span></span>

<span data-ttu-id="1b076-655">Varía según la provincia</span><span class="sxs-lookup"><span data-stu-id="1b076-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-656">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-656">Pattern</span></span>

<span data-ttu-id="1b076-657">Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="1b076-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-658">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-658">Checksum</span></span>

<span data-ttu-id="1b076-659">No</span><span class="sxs-lookup"><span data-stu-id="1b076-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-660">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-660">Definition</span></span>

<span data-ttu-id="1b076-661">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-662">La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-663">Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="1b076-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="1b076-664">Se encuentra una palabra clave de Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="1b076-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-665">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="1b076-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="1b076-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="1b076-667">La abreviatura de la provincia, por ejemplo, AB</span><span class="sxs-lookup"><span data-stu-id="1b076-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="1b076-668">
El nombre de la provincia, por ejemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="1b076-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="1b076-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="1b076-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="1b076-670">DL</span><span class="sxs-lookup"><span data-stu-id="1b076-670">DL</span></span>
- <span data-ttu-id="1b076-671">DLS</span><span class="sxs-lookup"><span data-stu-id="1b076-671">DLS</span></span>
- <span data-ttu-id="1b076-672">CDL</span><span class="sxs-lookup"><span data-stu-id="1b076-672">CDL</span></span>
- <span data-ttu-id="1b076-673">CDLS</span><span class="sxs-lookup"><span data-stu-id="1b076-673">CDLS</span></span>
- <span data-ttu-id="1b076-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="1b076-674">DriverLic</span></span>
- <span data-ttu-id="1b076-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="1b076-675">DriverLics</span></span>
- <span data-ttu-id="1b076-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="1b076-676">DriverLicense</span></span>
- <span data-ttu-id="1b076-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-677">DriverLicenses</span></span>
- <span data-ttu-id="1b076-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="1b076-678">DriverLicence</span></span>
- <span data-ttu-id="1b076-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="1b076-679">DriverLicences</span></span>
- <span data-ttu-id="1b076-680">Lic de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-680">Driver Lic</span></span>
- <span data-ttu-id="1b076-681">LIC de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-681">Driver Lics</span></span>
- <span data-ttu-id="1b076-682">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-682">Driver License</span></span>
- <span data-ttu-id="1b076-683">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-683">Driver Licenses</span></span>
- <span data-ttu-id="1b076-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-684">Driver Licence</span></span>
- <span data-ttu-id="1b076-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-685">Driver Licences</span></span>
- <span data-ttu-id="1b076-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="1b076-686">DriversLic</span></span>
- <span data-ttu-id="1b076-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="1b076-687">DriversLics</span></span>
- <span data-ttu-id="1b076-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="1b076-688">DriversLicence</span></span>
- <span data-ttu-id="1b076-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="1b076-689">DriversLicences</span></span>
- <span data-ttu-id="1b076-690">PermisoDeConducción</span><span class="sxs-lookup"><span data-stu-id="1b076-690">DriversLicense</span></span>
- <span data-ttu-id="1b076-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-691">DriversLicenses</span></span>
- <span data-ttu-id="1b076-692">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-692">Drivers Lic</span></span>
- <span data-ttu-id="1b076-693">LIC de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-693">Drivers Lics</span></span>
- <span data-ttu-id="1b076-694">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-694">Drivers License</span></span>
- <span data-ttu-id="1b076-695">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-695">Drivers Licenses</span></span>
- <span data-ttu-id="1b076-696">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-696">Drivers Licence</span></span>
- <span data-ttu-id="1b076-697">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-697">Drivers Licences</span></span>
- <span data-ttu-id="1b076-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="1b076-698">Driver'Lic</span></span>
- <span data-ttu-id="1b076-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="1b076-699">Driver'Lics</span></span>
- <span data-ttu-id="1b076-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="1b076-700">Driver'License</span></span>
- <span data-ttu-id="1b076-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="1b076-701">Driver'Licenses</span></span>
- <span data-ttu-id="1b076-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="1b076-702">Driver'Licence</span></span>
- <span data-ttu-id="1b076-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="1b076-703">Driver'Licences</span></span>
- <span data-ttu-id="1b076-704">Controlador ' Lic</span><span class="sxs-lookup"><span data-stu-id="1b076-704">Driver' Lic</span></span>
- <span data-ttu-id="1b076-705">Controlador ' LIC</span><span class="sxs-lookup"><span data-stu-id="1b076-705">Driver' Lics</span></span>
- <span data-ttu-id="1b076-706">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="1b076-706">Driver' License</span></span>
- <span data-ttu-id="1b076-707">Controlador ' licencias</span><span class="sxs-lookup"><span data-stu-id="1b076-707">Driver' Licenses</span></span>
- <span data-ttu-id="1b076-708">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="1b076-708">Driver' Licence</span></span>
- <span data-ttu-id="1b076-709">Controlador ' certificados</span><span class="sxs-lookup"><span data-stu-id="1b076-709">Driver' Licences</span></span>
- <span data-ttu-id="1b076-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="1b076-710">Driver'sLic</span></span>
- <span data-ttu-id="1b076-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="1b076-711">Driver'sLics</span></span>
- <span data-ttu-id="1b076-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="1b076-712">Driver'sLicense</span></span>
- <span data-ttu-id="1b076-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-713">Driver'sLicenses</span></span>
- <span data-ttu-id="1b076-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="1b076-714">Driver'sLicence</span></span>
- <span data-ttu-id="1b076-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="1b076-715">Driver'sLicences</span></span>
- <span data-ttu-id="1b076-716">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-716">Driver's Lic</span></span>
- <span data-ttu-id="1b076-717">LIC del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-717">Driver's Lics</span></span>
- <span data-ttu-id="1b076-718">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="1b076-718">Driver's License</span></span>
- <span data-ttu-id="1b076-719">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-719">Driver's Licenses</span></span>
- <span data-ttu-id="1b076-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-720">Driver's Licence</span></span>
- <span data-ttu-id="1b076-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-721">Driver's Licences</span></span>
- <span data-ttu-id="1b076-722">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="1b076-722">Permis de Conduire</span></span>
- <span data-ttu-id="1b076-723">id</span><span class="sxs-lookup"><span data-stu-id="1b076-723">id</span></span>
- <span data-ttu-id="1b076-724">identificadores de</span><span class="sxs-lookup"><span data-stu-id="1b076-724">ids</span></span>
- <span data-ttu-id="1b076-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="1b076-725">idcard number</span></span>
- <span data-ttu-id="1b076-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="1b076-726">idcard numbers</span></span>
- <span data-ttu-id="1b076-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="1b076-727">idcard #</span></span>
- <span data-ttu-id="1b076-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="1b076-728">idcard #s</span></span>
- <span data-ttu-id="1b076-729">tarjeta de idcard</span><span class="sxs-lookup"><span data-stu-id="1b076-729">idcard card</span></span>
- <span data-ttu-id="1b076-730">tarjetas de idcard</span><span class="sxs-lookup"><span data-stu-id="1b076-730">idcard cards</span></span>
- <span data-ttu-id="1b076-731">idcard</span><span class="sxs-lookup"><span data-stu-id="1b076-731">idcard</span></span>
- <span data-ttu-id="1b076-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="1b076-732">identification number</span></span>
- <span data-ttu-id="1b076-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="1b076-733">identification numbers</span></span>
- <span data-ttu-id="1b076-734">identification #
</span><span class="sxs-lookup"><span data-stu-id="1b076-734">identification #</span></span>
- <span data-ttu-id="1b076-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="1b076-735">identification #s</span></span>
- <span data-ttu-id="1b076-736">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-736">identification card</span></span>
- <span data-ttu-id="1b076-737">tarjetas de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-737">identification cards</span></span>
- <span data-ttu-id="1b076-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="1b076-738">identification</span></span> 
- <span data-ttu-id="1b076-739">DL#</span><span class="sxs-lookup"><span data-stu-id="1b076-739">DL#</span></span>
- <span data-ttu-id="1b076-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="1b076-740">DLS#</span></span> 
- <span data-ttu-id="1b076-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="1b076-741">CDL#</span></span> 
- <span data-ttu-id="1b076-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="1b076-742">CDLS#</span></span> 
- <span data-ttu-id="1b076-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-743">DriverLic#</span></span> 
- <span data-ttu-id="1b076-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-744">DriverLics#</span></span> 
- <span data-ttu-id="1b076-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="1b076-745">DriverLicense#</span></span> 
- <span data-ttu-id="1b076-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-746">DriverLicenses#</span></span> 
- <span data-ttu-id="1b076-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="1b076-747">DriverLicence#</span></span> 
- <span data-ttu-id="1b076-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="1b076-748">DriverLicences#</span></span> 
- <span data-ttu-id="1b076-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="1b076-749">Driver Lic#</span></span>
- <span data-ttu-id="1b076-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-750">Driver Lics#</span></span> 
- <span data-ttu-id="1b076-751">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="1b076-751">Driver License#</span></span> 
- <span data-ttu-id="1b076-752">Controlador licencias #</span><span class="sxs-lookup"><span data-stu-id="1b076-752">Driver Licenses#</span></span> 
- <span data-ttu-id="1b076-753">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="1b076-753">Driver License#</span></span> 
- <span data-ttu-id="1b076-754">Controlador certificados #</span><span class="sxs-lookup"><span data-stu-id="1b076-754">Driver Licences#</span></span> 
- <span data-ttu-id="1b076-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-755">DriversLic#</span></span> 
- <span data-ttu-id="1b076-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-756">DriversLics#</span></span> 
- <span data-ttu-id="1b076-757">PermisoDeConducción #</span><span class="sxs-lookup"><span data-stu-id="1b076-757">DriversLicense#</span></span> 
- <span data-ttu-id="1b076-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-758">DriversLicenses#</span></span> 
- <span data-ttu-id="1b076-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="1b076-759">DriversLicence#</span></span> 
- <span data-ttu-id="1b076-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="1b076-760">DriversLicences#</span></span> 
- <span data-ttu-id="1b076-761">Controladores Lic #</span><span class="sxs-lookup"><span data-stu-id="1b076-761">Drivers Lic#</span></span> 
- <span data-ttu-id="1b076-762">Controladores LIC #</span><span class="sxs-lookup"><span data-stu-id="1b076-762">Drivers Lics#</span></span> 
- <span data-ttu-id="1b076-763">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-763">Drivers License#</span></span> 
- <span data-ttu-id="1b076-764">Licencias de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="1b076-765">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-765">Drivers Licence#</span></span> 
- <span data-ttu-id="1b076-766">Controladores certificados #</span><span class="sxs-lookup"><span data-stu-id="1b076-766">Drivers Licences#</span></span> 
- <span data-ttu-id="1b076-767">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-767">Driver'Lic#</span></span> 
- <span data-ttu-id="1b076-768">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-768">Driver'Lics#</span></span> 
- <span data-ttu-id="1b076-769">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-769">Driver'License#</span></span> 
- <span data-ttu-id="1b076-770">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="1b076-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="1b076-771">Driver'Licence#</span></span> 
- <span data-ttu-id="1b076-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="1b076-772">Driver'Licences#</span></span> 
- <span data-ttu-id="1b076-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-773">Driver' Lic#</span></span> 
- <span data-ttu-id="1b076-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-774">Driver' Lics#</span></span> 
- <span data-ttu-id="1b076-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-775">Driver' License#</span></span> 
- <span data-ttu-id="1b076-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="1b076-777">Controlador ' certificado #</span><span class="sxs-lookup"><span data-stu-id="1b076-777">Driver' Licence#</span></span> 
- <span data-ttu-id="1b076-778">Controlador ' certificados #</span><span class="sxs-lookup"><span data-stu-id="1b076-778">Driver' Licences#</span></span> 
- <span data-ttu-id="1b076-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-779">Driver'sLic#</span></span> 
- <span data-ttu-id="1b076-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-780">Driver'sLics#</span></span> 
- <span data-ttu-id="1b076-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="1b076-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="1b076-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="1b076-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="1b076-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="1b076-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="1b076-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="1b076-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-785">Driver's Lic#</span></span> 
- <span data-ttu-id="1b076-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-786">Driver's Lics#</span></span> 
- <span data-ttu-id="1b076-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-787">Driver's License#</span></span> 
- <span data-ttu-id="1b076-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="1b076-789">Certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-789">Driver's Licence#</span></span> 
- <span data-ttu-id="1b076-790">El certificado # del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-790">Driver's Licences#</span></span> 
- <span data-ttu-id="1b076-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="1b076-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="1b076-792">identificador de #</span><span class="sxs-lookup"><span data-stu-id="1b076-792">id#</span></span> 
- <span data-ttu-id="1b076-793">los identificadores de #</span><span class="sxs-lookup"><span data-stu-id="1b076-793">ids#</span></span> 
- <span data-ttu-id="1b076-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="1b076-794">idcard card#</span></span> 
- <span data-ttu-id="1b076-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="1b076-795">idcard cards#</span></span> 
- <span data-ttu-id="1b076-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="1b076-796">idcard#</span></span> 
- <span data-ttu-id="1b076-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="1b076-797">identification card#</span></span> 
- <span data-ttu-id="1b076-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="1b076-798">identification cards#</span></span> 
- <span data-ttu-id="1b076-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="1b076-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="1b076-800">Número de servicio de salud de Canadá</span><span class="sxs-lookup"><span data-stu-id="1b076-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-801">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-801">Format</span></span>

<span data-ttu-id="1b076-802">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-803">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-803">Pattern</span></span>

<span data-ttu-id="1b076-804">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-805">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-805">Checksum</span></span>

<span data-ttu-id="1b076-806">No</span><span class="sxs-lookup"><span data-stu-id="1b076-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-807">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-807">Definition</span></span>

<span data-ttu-id="1b076-808">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-809">La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-810">Se encuentra una palabra clave de Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-811">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="1b076-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="1b076-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="1b076-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="1b076-813">personal health number</span></span>
- <span data-ttu-id="1b076-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="1b076-814">patient information</span></span>
- <span data-ttu-id="1b076-815">Servicios de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="1b076-815">health services</span></span>
- <span data-ttu-id="1b076-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="1b076-816">speciality services</span></span>
- <span data-ttu-id="1b076-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="1b076-817">automobile accident</span></span>
- <span data-ttu-id="1b076-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="1b076-818">patient hospital</span></span>
- <span data-ttu-id="1b076-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="1b076-819">psychiatrist</span></span>
- <span data-ttu-id="1b076-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="1b076-820">workers compensation</span></span>
- <span data-ttu-id="1b076-821">
disability</span><span class="sxs-lookup"><span data-stu-id="1b076-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="1b076-822">Número de pasaporte de Canadá</span><span class="sxs-lookup"><span data-stu-id="1b076-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-823">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-823">Format</span></span>

<span data-ttu-id="1b076-824">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-825">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-825">Pattern</span></span>

<span data-ttu-id="1b076-826">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-827">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-827">Checksum</span></span>

<span data-ttu-id="1b076-828">No</span><span class="sxs-lookup"><span data-stu-id="1b076-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-829">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-829">Definition</span></span>

<span data-ttu-id="1b076-830">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-831">La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-832">Se ha encontrado una palabra clave de Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="1b076-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-833">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="1b076-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="1b076-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="1b076-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="1b076-835">canadian citizenship</span></span>
- <span data-ttu-id="1b076-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="1b076-836">canadian passport</span></span>
- <span data-ttu-id="1b076-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="1b076-837">passport application</span></span>
- <span data-ttu-id="1b076-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="1b076-838">passport photos</span></span>
- <span data-ttu-id="1b076-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="1b076-839">certified translator</span></span>
- <span data-ttu-id="1b076-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="1b076-840">canadian citizens</span></span>
- <span data-ttu-id="1b076-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="1b076-841">processing times</span></span>
- <span data-ttu-id="1b076-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="1b076-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="1b076-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-843">Keyword_passport</span></span>

- <span data-ttu-id="1b076-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="1b076-844">Passport Number</span></span>
- <span data-ttu-id="1b076-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="1b076-845">Passport No</span></span>
- <span data-ttu-id="1b076-846">Passport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-846">Passport #</span></span>
- <span data-ttu-id="1b076-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-847">Passport#</span></span>
- <span data-ttu-id="1b076-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="1b076-848">PassportID</span></span>
- <span data-ttu-id="1b076-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="1b076-849">Passportno</span></span>
- <span data-ttu-id="1b076-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-850">passportnumber</span></span>
- <span data-ttu-id="1b076-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="1b076-851">パスポート</span></span>
- <span data-ttu-id="1b076-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-852">パスポート番号</span></span>
- <span data-ttu-id="1b076-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="1b076-853">パスポートのNum</span></span>
- <span data-ttu-id="1b076-854">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-854">パスポート＃</span></span>
- <span data-ttu-id="1b076-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="1b076-855">Numéro de passeport</span></span>
- <span data-ttu-id="1b076-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="1b076-856">Passeport n °</span></span>
- <span data-ttu-id="1b076-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="1b076-857">Passeport Non</span></span>
- <span data-ttu-id="1b076-858">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-858">Passeport #</span></span>
- <span data-ttu-id="1b076-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-859">Passeport#</span></span>
- <span data-ttu-id="1b076-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="1b076-860">PasseportNon</span></span>
- <span data-ttu-id="1b076-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="1b076-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="1b076-862">Número de Identificación Personal de salud en Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="1b076-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-863">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-863">Format</span></span>

<span data-ttu-id="1b076-864">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-865">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-865">Pattern</span></span>

<span data-ttu-id="1b076-866">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-867">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-867">Checksum</span></span>

<span data-ttu-id="1b076-868">No</span><span class="sxs-lookup"><span data-stu-id="1b076-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-869">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-869">Definition</span></span>

<span data-ttu-id="1b076-p104">Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la expresión regular Regex_canada_phin busca contenido que coincide con el patrón. Al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces se encuentran..</span><span class="sxs-lookup"><span data-stu-id="1b076-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-872">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="1b076-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="1b076-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="1b076-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="1b076-874">social insurance number</span></span>
- <span data-ttu-id="1b076-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="1b076-875">health information act</span></span>
- <span data-ttu-id="1b076-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="1b076-876">income tax information</span></span>
- <span data-ttu-id="1b076-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="1b076-877">manitoba health</span></span>
- <span data-ttu-id="1b076-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="1b076-878">health registration</span></span>
- <span data-ttu-id="1b076-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="1b076-879">prescription purchases</span></span>
- <span data-ttu-id="1b076-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="1b076-880">benefit eligibility</span></span>
- <span data-ttu-id="1b076-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="1b076-881">personal health</span></span>
- <span data-ttu-id="1b076-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="1b076-882">power of attorney</span></span>
- <span data-ttu-id="1b076-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="1b076-883">registration number</span></span>
- <span data-ttu-id="1b076-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="1b076-884">personal health number</span></span>
- <span data-ttu-id="1b076-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="1b076-885">practitioner referral</span></span>
- <span data-ttu-id="1b076-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="1b076-886">wellness professional</span></span>
- <span data-ttu-id="1b076-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="1b076-887">patient referral</span></span>
- <span data-ttu-id="1b076-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="1b076-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="1b076-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="1b076-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="1b076-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="1b076-890">Nunavut</span></span>
- <span data-ttu-id="1b076-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="1b076-891">Quebec</span></span>
- <span data-ttu-id="1b076-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="1b076-892">Northwest Territories</span></span>
- <span data-ttu-id="1b076-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="1b076-893">Ontario</span></span>
- <span data-ttu-id="1b076-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="1b076-894">British Columbia</span></span>
- <span data-ttu-id="1b076-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="1b076-895">Alberta</span></span>
- <span data-ttu-id="1b076-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="1b076-896">Saskatchewan</span></span>
- <span data-ttu-id="1b076-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="1b076-897">Manitoba</span></span>
- <span data-ttu-id="1b076-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="1b076-898">Yukon</span></span>
- <span data-ttu-id="1b076-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="1b076-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="1b076-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="1b076-900">New Brunswick</span></span>
- <span data-ttu-id="1b076-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="1b076-901">Nova Scotia</span></span>
- <span data-ttu-id="1b076-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="1b076-902">Prince Edward Island</span></span>
- <span data-ttu-id="1b076-903">Canadá</span><span class="sxs-lookup"><span data-stu-id="1b076-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="1b076-904">Número de seguridad social de Canadá</span><span class="sxs-lookup"><span data-stu-id="1b076-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-905">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-905">Format</span></span>

<span data-ttu-id="1b076-906">Nueve dígitos con guiones opcionales o espacios</span><span class="sxs-lookup"><span data-stu-id="1b076-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-907">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-907">Pattern</span></span>

<span data-ttu-id="1b076-908">Con formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-908">Formatted:</span></span>
- <span data-ttu-id="1b076-909">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-909">Three digits</span></span> 
- <span data-ttu-id="1b076-910">Un guión o un espacio </span><span class="sxs-lookup"><span data-stu-id="1b076-910">A hyphen or space</span></span> 
- <span data-ttu-id="1b076-911">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-911">Three digits</span></span> 
- <span data-ttu-id="1b076-912">Un guión o un espacio </span><span class="sxs-lookup"><span data-stu-id="1b076-912">A hyphen or space</span></span> 
- <span data-ttu-id="1b076-913">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-913">Three digits</span></span>

<span data-ttu-id="1b076-914">Sin formato: Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-915">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-915">Checksum</span></span>

<span data-ttu-id="1b076-916">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-917">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-917">Definition</span></span>

<span data-ttu-id="1b076-918">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-919">La función Func_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-920">Al menos dos de cualquier combinación de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b076-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="1b076-921">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="1b076-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="1b076-922">Se encuentra una palabra clave de Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="1b076-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="1b076-923">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="1b076-924">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-924">The checksum passes.</span></span>

<span data-ttu-id="1b076-925">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-926">La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-927">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="1b076-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="1b076-928">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-929">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="1b076-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="1b076-930">Keyword_sin</span></span>

- <span data-ttu-id="1b076-931">seno</span><span class="sxs-lookup"><span data-stu-id="1b076-931">sin</span></span> 
- <span data-ttu-id="1b076-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="1b076-932">social insurance</span></span> 
- <span data-ttu-id="1b076-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="1b076-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="1b076-934">sins
</span><span class="sxs-lookup"><span data-stu-id="1b076-934">sins</span></span> 
- <span data-ttu-id="1b076-935">ssn</span><span class="sxs-lookup"><span data-stu-id="1b076-935">ssn</span></span> 
- <span data-ttu-id="1b076-936">números de seguridad social</span><span class="sxs-lookup"><span data-stu-id="1b076-936">ssns</span></span> 
- <span data-ttu-id="1b076-937">seguridad social</span><span class="sxs-lookup"><span data-stu-id="1b076-937">social security</span></span> 
- <span data-ttu-id="1b076-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="1b076-938">numero d'assurance social</span></span> 
- <span data-ttu-id="1b076-939">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="1b076-939">national identification number</span></span> 
- <span data-ttu-id="1b076-940">
national id</span><span class="sxs-lookup"><span data-stu-id="1b076-940">national id</span></span> 
- <span data-ttu-id="1b076-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="1b076-941">sin#</span></span> 
- <span data-ttu-id="1b076-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="1b076-942">soc ins</span></span> 
- <span data-ttu-id="1b076-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="1b076-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="1b076-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="1b076-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="1b076-945">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="1b076-945">driver's license</span></span> 
- <span data-ttu-id="1b076-946">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-946">drivers license</span></span> 
- <span data-ttu-id="1b076-947">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-947">driver's licence</span></span> 
- <span data-ttu-id="1b076-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b076-948">drivers licence</span></span> 
- <span data-ttu-id="1b076-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="1b076-949">DOB</span></span> 
- <span data-ttu-id="1b076-950">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="1b076-950">Birthdate</span></span> 
- <span data-ttu-id="1b076-951">Cumpleaños </span><span class="sxs-lookup"><span data-stu-id="1b076-951">Birthday</span></span> 
- <span data-ttu-id="1b076-952">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="1b076-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="1b076-953">Número de tarjeta de identidad de Chile</span><span class="sxs-lookup"><span data-stu-id="1b076-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-954">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-954">Format</span></span>

<span data-ttu-id="1b076-955">7-8 dígitos y delimitadores un dígito de control o una letra</span><span class="sxs-lookup"><span data-stu-id="1b076-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-956">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-956">Pattern</span></span>

<span data-ttu-id="1b076-957">7 u 8 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="1b076-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="1b076-958">1 o 2 dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-958">1-2 digits</span></span> 
- <span data-ttu-id="1b076-959">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-959">A period</span></span> 
- <span data-ttu-id="1b076-960">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-960">Three digits</span></span> 
- <span data-ttu-id="1b076-961">Un punto </span><span class="sxs-lookup"><span data-stu-id="1b076-961">A period</span></span> 
- <span data-ttu-id="1b076-962">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-962">Three digits</span></span> 
- <span data-ttu-id="1b076-963">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-963">A dash</span></span> 
- <span data-ttu-id="1b076-964">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-965">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-965">Checksum</span></span>

<span data-ttu-id="1b076-966">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-967">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-967">Definition</span></span>

<span data-ttu-id="1b076-968">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-969">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-970">Se encuentra una palabra clave de Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="1b076-971">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-971">The checksum passes.</span></span>

<span data-ttu-id="1b076-972">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-973">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-974">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-975">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="1b076-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="1b076-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="1b076-977">Número de identificación nacional
</span><span class="sxs-lookup"><span data-stu-id="1b076-977">National Identification Number</span></span> 
- <span data-ttu-id="1b076-978">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="1b076-978">Identity card</span></span> 
- <span data-ttu-id="1b076-979">ID</span><span class="sxs-lookup"><span data-stu-id="1b076-979">ID</span></span> 
- <span data-ttu-id="1b076-980">Identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-980">Identification</span></span> 
- <span data-ttu-id="1b076-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="1b076-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="1b076-982">EJECUTAR</span><span class="sxs-lookup"><span data-stu-id="1b076-982">RUN</span></span> 
- <span data-ttu-id="1b076-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="1b076-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="1b076-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="1b076-984">RUT</span></span> 
- <span data-ttu-id="1b076-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="1b076-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="1b076-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="1b076-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="1b076-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="1b076-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="1b076-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="1b076-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="1b076-989">	Número de tarjeta de identidad de residente de China (PRC)</span><span class="sxs-lookup"><span data-stu-id="1b076-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-990">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-990">Format</span></span>

<span data-ttu-id="1b076-991">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-992">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-992">Pattern</span></span>

<span data-ttu-id="1b076-993">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-993">18 digits:</span></span>
- <span data-ttu-id="1b076-994">Seis dígitos que son un código de dirección </span><span class="sxs-lookup"><span data-stu-id="1b076-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="1b076-995">Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="1b076-996">Tres dígitos que son un código de pedido </span><span class="sxs-lookup"><span data-stu-id="1b076-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="1b076-997">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-998">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-998">Checksum</span></span>

<span data-ttu-id="1b076-999">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1000">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1000">Definition</span></span>

<span data-ttu-id="1b076-1001">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1002">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1003">Se encuentra una palabra clave de Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="1b076-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="1b076-1004">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1004">The checksum passes.</span></span>

<span data-ttu-id="1b076-1005">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1006">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1007">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1008">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="1b076-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="1b076-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="1b076-1010">Tarjeta de identidad de residente
</span><span class="sxs-lookup"><span data-stu-id="1b076-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="1b076-1011">República Popular China
</span><span class="sxs-lookup"><span data-stu-id="1b076-1011">PRC</span></span> 
- <span data-ttu-id="1b076-1012">Tarjeta de identificación nacional
</span><span class="sxs-lookup"><span data-stu-id="1b076-1012">National Identification Card</span></span> 
- <span data-ttu-id="1b076-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="1b076-1013">身份证</span></span> 
- <span data-ttu-id="1b076-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="1b076-1014">居民 身份证</span></span> 
- <span data-ttu-id="1b076-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="1b076-1015">居民身份证</span></span> 
- <span data-ttu-id="1b076-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="1b076-1016">鉴定</span></span> 
- <span data-ttu-id="1b076-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="1b076-1017">身分證</span></span> 
- <span data-ttu-id="1b076-1018">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="1b076-1018">居民 身份證</span></span>
- <span data-ttu-id="1b076-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="1b076-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="1b076-1020">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="1b076-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1021">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1021">Format</span></span>

<span data-ttu-id="1b076-1022">16 dígitos que se pueden dar formato o sin formato (dddddddddddddddd) y debe pasar la prueba Luhn.</span><span class="sxs-lookup"><span data-stu-id="1b076-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1023">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1023">Pattern</span></span>

<span data-ttu-id="1b076-1024">Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.</span><span class="sxs-lookup"><span data-stu-id="1b076-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1025">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1025">Checksum</span></span>

<span data-ttu-id="1b076-1026">Sí, la suma de comprobación de Luhn</span><span class="sxs-lookup"><span data-stu-id="1b076-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1027">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1027">Definition</span></span>

<span data-ttu-id="1b076-1028">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1029">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1030">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-1030">One of the following is true:</span></span>
    - <span data-ttu-id="1b076-1031">Se encuentra una palabra clave de Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="1b076-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="1b076-1032">Se encuentra una palabra clave de Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="1b076-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="1b076-1033">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="1b076-1034">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1034">The checksum passes.</span></span>

<span data-ttu-id="1b076-1035">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1036">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1037">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1038">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="1b076-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="1b076-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="1b076-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="1b076-1040">card verification</span></span>
- <span data-ttu-id="1b076-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="1b076-1041">card identification number</span></span>
- <span data-ttu-id="1b076-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="1b076-1042">cvn</span></span>
- <span data-ttu-id="1b076-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="1b076-1043">cid</span></span>
- <span data-ttu-id="1b076-1044">CVC2 obtenidos</span><span class="sxs-lookup"><span data-stu-id="1b076-1044">cvc2</span></span>
- <span data-ttu-id="1b076-1045">cvv2</span><span class="sxs-lookup"><span data-stu-id="1b076-1045">cvv2</span></span>
- <span data-ttu-id="1b076-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="1b076-1046">pin block</span></span>
- <span data-ttu-id="1b076-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="1b076-1047">security code</span></span>
- <span data-ttu-id="1b076-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1048">security number</span></span>
- <span data-ttu-id="1b076-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="1b076-1049">security no</span></span>
- <span data-ttu-id="1b076-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1050">issue number</span></span>
- <span data-ttu-id="1b076-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="1b076-1051">issue no</span></span>
- <span data-ttu-id="1b076-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="1b076-1052">cryptogramme</span></span>
- <span data-ttu-id="1b076-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="1b076-1053">numéro de sécurité</span></span>
- <span data-ttu-id="1b076-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="1b076-1054">numero de securite</span></span>
- <span data-ttu-id="1b076-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="1b076-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="1b076-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1057">prüfziffer</span></span>
- <span data-ttu-id="1b076-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1058">prufziffer</span></span>
- <span data-ttu-id="1b076-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="1b076-1059">sicherheits Kode</span></span>
- <span data-ttu-id="1b076-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="1b076-1060">sicherheitscode</span></span>
- <span data-ttu-id="1b076-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="1b076-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1062">verfalldatum</span></span>
- <span data-ttu-id="1b076-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="1b076-1063">codice di verifica</span></span>
- <span data-ttu-id="1b076-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="1b076-p105">cod. sicurezza</span></span>
- <span data-ttu-id="1b076-1066">COD sicurezza</span><span class="sxs-lookup"><span data-stu-id="1b076-1066">cod sicurezza</span></span>
- <span data-ttu-id="1b076-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1b076-1067">n autorizzazione</span></span>
- <span data-ttu-id="1b076-1068">código
</span><span class="sxs-lookup"><span data-stu-id="1b076-1068">código</span></span>
- <span data-ttu-id="1b076-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="1b076-1069">codigo</span></span>
- <span data-ttu-id="1b076-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="1b076-p106">cod. seg</span></span>
- <span data-ttu-id="1b076-1072">COD seg</span><span class="sxs-lookup"><span data-stu-id="1b076-1072">cod seg</span></span>
- <span data-ttu-id="1b076-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="1b076-1073">código de segurança</span></span>
- <span data-ttu-id="1b076-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="1b076-1074">codigo de seguranca</span></span>
- <span data-ttu-id="1b076-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="1b076-1075">codigo de segurança</span></span>
- <span data-ttu-id="1b076-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="1b076-1076">código de seguranca</span></span>
- <span data-ttu-id="1b076-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="1b076-p107">cód. segurança</span></span>
- <span data-ttu-id="1b076-p108">Cod. seguranca cod. segurança</span><span class="sxs-lookup"><span data-stu-id="1b076-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="1b076-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="1b076-p109">cód. seguranca</span></span>
- <span data-ttu-id="1b076-1084">campo Cód. segurança</span><span class="sxs-lookup"><span data-stu-id="1b076-1084">cód segurança</span></span>
- <span data-ttu-id="1b076-1085">bacalao seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="1b076-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="1b076-1086">campo Cód. seguranca</span><span class="sxs-lookup"><span data-stu-id="1b076-1086">cód seguranca</span></span>
- <span data-ttu-id="1b076-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="1b076-1087">número de verificação</span></span>
- <span data-ttu-id="1b076-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1088">numero de verificacao</span></span>
- <span data-ttu-id="1b076-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="1b076-1089">ablauf</span></span>
- <span data-ttu-id="1b076-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="1b076-1090">gültig bis</span></span>
- <span data-ttu-id="1b076-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="1b076-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="1b076-1092">gultig bis</span></span>
- <span data-ttu-id="1b076-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="1b076-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="1b076-1094">scadenza</span></span>
- <span data-ttu-id="1b076-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="1b076-1095">data scad</span></span>
- <span data-ttu-id="1b076-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="1b076-1096">fecha de expiracion</span></span>
- <span data-ttu-id="1b076-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="1b076-1097">fecha de venc</span></span>
- <span data-ttu-id="1b076-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="1b076-1098">vencimiento</span></span>
- <span data-ttu-id="1b076-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1099">válido hasta</span></span>
- <span data-ttu-id="1b076-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1100">valido hasta</span></span>
- <span data-ttu-id="1b076-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="1b076-1101">vto</span></span>
- <span data-ttu-id="1b076-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="1b076-1102">data de expiração</span></span>
- <span data-ttu-id="1b076-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1103">data de expiracao</span></span>
- <span data-ttu-id="1b076-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="1b076-1104">data em que expira</span></span>
- <span data-ttu-id="1b076-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="1b076-1105">validade</span></span>
- <span data-ttu-id="1b076-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="1b076-1106">valor</span></span>
- <span data-ttu-id="1b076-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="1b076-1107">vencimento</span></span>
- <span data-ttu-id="1b076-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="1b076-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="1b076-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="1b076-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="1b076-1110">amex</span><span class="sxs-lookup"><span data-stu-id="1b076-1110">amex</span></span>
- <span data-ttu-id="1b076-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="1b076-1111">american express</span></span>
- <span data-ttu-id="1b076-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="1b076-1112">americanexpress</span></span>
- <span data-ttu-id="1b076-1113">Visa</span><span class="sxs-lookup"><span data-stu-id="1b076-1113">Visa</span></span>
- <span data-ttu-id="1b076-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1114">mastercard</span></span>
- <span data-ttu-id="1b076-1115">master card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1115">master card</span></span>
- <span data-ttu-id="1b076-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="1b076-1116">mc</span></span> 
- <span data-ttu-id="1b076-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="1b076-1117">mastercards</span></span>
- <span data-ttu-id="1b076-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="1b076-1118">master cards</span></span>
- <span data-ttu-id="1b076-1119">Club del comensal</span><span class="sxs-lookup"><span data-stu-id="1b076-1119">diner's Club</span></span>
- <span data-ttu-id="1b076-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="1b076-1120">diners club</span></span>
- <span data-ttu-id="1b076-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="1b076-1121">dinersclub</span></span>
- <span data-ttu-id="1b076-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1122">discover card</span></span>
- <span data-ttu-id="1b076-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1123">discovercard</span></span>
- <span data-ttu-id="1b076-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1124">discover cards</span></span>
- <span data-ttu-id="1b076-1125">JCB</span><span class="sxs-lookup"><span data-stu-id="1b076-1125">JCB</span></span>
- <span data-ttu-id="1b076-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="1b076-1126">japanese card bureau</span></span>
- <span data-ttu-id="1b076-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="1b076-1127">carte blanche</span></span>
- <span data-ttu-id="1b076-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="1b076-1128">carteblanche</span></span>
- <span data-ttu-id="1b076-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1129">credit card</span></span>
- <span data-ttu-id="1b076-1130">CC #</span><span class="sxs-lookup"><span data-stu-id="1b076-1130">cc#</span></span>
- <span data-ttu-id="1b076-1131">cc #:</span><span class="sxs-lookup"><span data-stu-id="1b076-1131">cc#:</span></span>
- <span data-ttu-id="1b076-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="1b076-1132">expiration date</span></span>
- <span data-ttu-id="1b076-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="1b076-1133">exp date</span></span>
- <span data-ttu-id="1b076-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="1b076-1134">expiry date</span></span>
- <span data-ttu-id="1b076-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="1b076-1135">date d’expiration</span></span>
- <span data-ttu-id="1b076-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="1b076-1136">date d'exp</span></span>
- <span data-ttu-id="1b076-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="1b076-1137">date expiration</span></span>
- <span data-ttu-id="1b076-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1138">bank card</span></span>
- <span data-ttu-id="1b076-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="1b076-1139">bankcard</span></span>
- <span data-ttu-id="1b076-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1140">card number</span></span>
- <span data-ttu-id="1b076-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="1b076-1141">card num</span></span>
- <span data-ttu-id="1b076-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-1142">cardnumber</span></span>
- <span data-ttu-id="1b076-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="1b076-1143">cardnumbers</span></span>
- <span data-ttu-id="1b076-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="1b076-1144">card numbers</span></span>
- <span data-ttu-id="1b076-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1145">creditcard</span></span>
- <span data-ttu-id="1b076-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1146">credit cards</span></span>
- <span data-ttu-id="1b076-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1147">creditcards</span></span>
- <span data-ttu-id="1b076-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="1b076-1148">ccn</span></span>
- <span data-ttu-id="1b076-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="1b076-1149">card holder</span></span>
- <span data-ttu-id="1b076-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="1b076-1150">cardholder</span></span>
- <span data-ttu-id="1b076-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="1b076-1151">card holders</span></span>
- <span data-ttu-id="1b076-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="1b076-1152">cardholders</span></span>
- <span data-ttu-id="1b076-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1153">check card</span></span>
- <span data-ttu-id="1b076-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1154">checkcard</span></span>
- <span data-ttu-id="1b076-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1155">check cards</span></span>
- <span data-ttu-id="1b076-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1156">checkcards</span></span>
- <span data-ttu-id="1b076-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1157">debit card</span></span>
- <span data-ttu-id="1b076-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1158">debitcard</span></span>
- <span data-ttu-id="1b076-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1159">debit cards</span></span>
- <span data-ttu-id="1b076-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1160">debitcards</span></span>
- <span data-ttu-id="1b076-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1161">atm card</span></span>
- <span data-ttu-id="1b076-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1162">atmcard</span></span>
- <span data-ttu-id="1b076-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1163">atm cards</span></span>
- <span data-ttu-id="1b076-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1164">atmcards</span></span>
- <span data-ttu-id="1b076-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="1b076-1165">enroute</span></span>
- <span data-ttu-id="1b076-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="1b076-1166">en route</span></span>
- <span data-ttu-id="1b076-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="1b076-1167">card type</span></span>
- <span data-ttu-id="1b076-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="1b076-1168">carte bancaire</span></span>
- <span data-ttu-id="1b076-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="1b076-1169">carte de crédit</span></span>
- <span data-ttu-id="1b076-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="1b076-1170">carte de credit</span></span>
- <span data-ttu-id="1b076-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1171">numéro de carte</span></span>
- <span data-ttu-id="1b076-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1172">numero de carte</span></span>
- <span data-ttu-id="1b076-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1173">nº de la carte</span></span>
- <span data-ttu-id="1b076-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1174">nº de carte</span></span>
- <span data-ttu-id="1b076-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1175">kreditkarte</span></span>
- <span data-ttu-id="1b076-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1176">karte</span></span>
- <span data-ttu-id="1b076-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="1b076-1177">karteninhaber</span></span>
- <span data-ttu-id="1b076-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="1b076-1178">karteninhabers</span></span>
- <span data-ttu-id="1b076-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="1b076-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="1b076-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="1b076-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="1b076-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="1b076-1181">kreditkartentyp</span></span>
- <span data-ttu-id="1b076-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="1b076-1182">eigentümername</span></span>
- <span data-ttu-id="1b076-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1183">kartennr</span></span> 
- <span data-ttu-id="1b076-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1184">kartennummer</span></span>
- <span data-ttu-id="1b076-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1185">kreditkartennummer</span></span>
- <span data-ttu-id="1b076-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="1b076-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1187">carta di credito</span></span>
- <span data-ttu-id="1b076-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1188">carta credito</span></span>
- <span data-ttu-id="1b076-1189">carta</span><span class="sxs-lookup"><span data-stu-id="1b076-1189">carta</span></span>
- <span data-ttu-id="1b076-1190">carta n</span><span class="sxs-lookup"><span data-stu-id="1b076-1190">n carta</span></span>
- <span data-ttu-id="1b076-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-p110">nr. carta</span></span>
- <span data-ttu-id="1b076-1193">carta n</span><span class="sxs-lookup"><span data-stu-id="1b076-1193">nr carta</span></span>
- <span data-ttu-id="1b076-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1194">numero carta</span></span>
- <span data-ttu-id="1b076-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1195">numero della carta</span></span>
- <span data-ttu-id="1b076-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1196">numero di carta</span></span>
- <span data-ttu-id="1b076-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1197">tarjeta credito</span></span>
- <span data-ttu-id="1b076-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1198">tarjeta de credito</span></span>
- <span data-ttu-id="1b076-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="1b076-1199">tarjeta crédito</span></span>
- <span data-ttu-id="1b076-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="1b076-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="1b076-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="1b076-1201">tarjeta de atm</span></span>
- <span data-ttu-id="1b076-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="1b076-1202">tarjeta atm</span></span>
- <span data-ttu-id="1b076-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1203">tarjeta debito</span></span>
- <span data-ttu-id="1b076-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1204">tarjeta de debito</span></span>
- <span data-ttu-id="1b076-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="1b076-1205">tarjeta débito</span></span>
- <span data-ttu-id="1b076-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="1b076-1206">tarjeta de débito</span></span>
- <span data-ttu-id="1b076-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1207">nº de tarjeta</span></span>
- <span data-ttu-id="1b076-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-p111">no. de tarjeta</span></span>
- <span data-ttu-id="1b076-1210">No hay tarjeta de</span><span class="sxs-lookup"><span data-stu-id="1b076-1210">no de tarjeta</span></span>
- <span data-ttu-id="1b076-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1211">numero de tarjeta</span></span>
- <span data-ttu-id="1b076-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1212">número de tarjeta</span></span>
- <span data-ttu-id="1b076-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="1b076-1213">tarjeta no</span></span>
- <span data-ttu-id="1b076-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="1b076-1214">tarjetahabiente</span></span>
- <span data-ttu-id="1b076-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1215">cartão de crédito</span></span>
- <span data-ttu-id="1b076-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1216">cartão de credito</span></span>
- <span data-ttu-id="1b076-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1217">cartao de crédito</span></span>
- <span data-ttu-id="1b076-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1218">cartao de credito</span></span>
- <span data-ttu-id="1b076-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1219">cartão de débito</span></span>
- <span data-ttu-id="1b076-1220">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1220">cartao de débito</span></span>
- <span data-ttu-id="1b076-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1221">cartão de debito</span></span>
- <span data-ttu-id="1b076-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1222">cartao de debito</span></span>
- <span data-ttu-id="1b076-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="1b076-1223">débito automático</span></span>
- <span data-ttu-id="1b076-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="1b076-1224">debito automatico</span></span>
- <span data-ttu-id="1b076-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="1b076-1225">número do cartão</span></span>
- <span data-ttu-id="1b076-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-1226">numero do cartão</span></span> 
- <span data-ttu-id="1b076-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="1b076-1227">número do cartao</span></span>
- <span data-ttu-id="1b076-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="1b076-1228">numero do cartao</span></span>
- <span data-ttu-id="1b076-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-1229">número de cartão</span></span>
- <span data-ttu-id="1b076-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-1230">numero de cartão</span></span>
- <span data-ttu-id="1b076-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1231">número de cartao</span></span>
- <span data-ttu-id="1b076-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1232">numero de cartao</span></span>
- <span data-ttu-id="1b076-1233">Nº cartão</span><span class="sxs-lookup"><span data-stu-id="1b076-1233">nº do cartão</span></span>
- <span data-ttu-id="1b076-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1234">nº do cartao</span></span>
- <span data-ttu-id="1b076-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-p112">nº. do cartão</span></span>
- <span data-ttu-id="1b076-1237">No hay cartão</span><span class="sxs-lookup"><span data-stu-id="1b076-1237">no do cartão</span></span>
- <span data-ttu-id="1b076-1238">No hay cartao</span><span class="sxs-lookup"><span data-stu-id="1b076-1238">no do cartao</span></span>
- <span data-ttu-id="1b076-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-p113">no. do cartão</span></span>
- <span data-ttu-id="1b076-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="1b076-1243">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="1b076-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1244">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1244">Format</span></span>

<span data-ttu-id="1b076-1245">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1246">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1246">Pattern</span></span>

<span data-ttu-id="1b076-1247">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1248">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1248">Checksum</span></span>

<span data-ttu-id="1b076-1249">No</span><span class="sxs-lookup"><span data-stu-id="1b076-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1250">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1250">Definition</span></span>

<span data-ttu-id="1b076-1251">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1252">La función Func_croatia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1253">Se encuentra una palabra clave de Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-1254">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="1b076-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="1b076-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="1b076-1256">Tarjeta de identidad croata</span><span class="sxs-lookup"><span data-stu-id="1b076-1256">Croatian identity card</span></span>
- <span data-ttu-id="1b076-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="1b076-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="1b076-1258">	Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="1b076-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1259">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1259">Format</span></span>

<span data-ttu-id="1b076-1260">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1261">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1261">Pattern</span></span>

<span data-ttu-id="1b076-1262">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-1262">10 digits:</span></span>
- <span data-ttu-id="1b076-1263">Seis dígitos en forma DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="1b076-1264">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1265">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1265">Checksum</span></span>

<span data-ttu-id="1b076-1266">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1267">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1267">Definition</span></span>

<span data-ttu-id="1b076-1268">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1269">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1270">Se encuentra una palabra clave de Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="1b076-1271">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1271">The checksum passes.</span></span>

<span data-ttu-id="1b076-1272">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1273">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1274">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1275">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="1b076-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="1b076-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="1b076-1277">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="1b076-1277">Personal Identification Number</span></span>
- <span data-ttu-id="1b076-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="1b076-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="1b076-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="1b076-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="1b076-1280">	número de tarjeta de identidad nacional checa</span><span class="sxs-lookup"><span data-stu-id="1b076-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1281">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1281">Format</span></span>

<span data-ttu-id="1b076-1282">10 dígitos que contienen una barra diagonal</span><span class="sxs-lookup"><span data-stu-id="1b076-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1283">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1283">Pattern</span></span>

<span data-ttu-id="1b076-1284">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-1284">10 digits:</span></span>
- <span data-ttu-id="1b076-1285">Seis dígitos que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="1b076-1286">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="1b076-1286">A forward slash</span></span> 
- <span data-ttu-id="1b076-1287">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1288">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1288">Checksum</span></span>

<span data-ttu-id="1b076-1289">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1290">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1290">Definition</span></span>

<span data-ttu-id="1b076-p115">Una directiva de DLP es 85% seguro de que ha detectado este tipo de información confidencial if, dentro de una proximidad de 300 caracteres: la función Func_czech_id_card busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_czech_id_card. Pasa la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="1b076-1294">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1294">Keywords</span></span>

- <span data-ttu-id="1b076-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="1b076-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="1b076-1296">tarjeta de identidad nacional checa</span><span class="sxs-lookup"><span data-stu-id="1b076-1296">Czech national identity card</span></span>
- <span data-ttu-id="1b076-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="1b076-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="1b076-1298">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="1b076-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1299">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1299">Format</span></span>

<span data-ttu-id="1b076-1300">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="1b076-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1301">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1301">Pattern</span></span>

<span data-ttu-id="1b076-1302">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-1302">10 digits:</span></span>
- <span data-ttu-id="1b076-1303">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="1b076-1304">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-1304">A hyphen</span></span> 
- <span data-ttu-id="1b076-1305">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1306">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1306">Checksum</span></span>

<span data-ttu-id="1b076-1307">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1308">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1308">Definition</span></span>

<span data-ttu-id="1b076-p116">Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la expresión regular Regex_denmark_id busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_denmark_id. Pasa la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-1312">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="1b076-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="1b076-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="1b076-1314">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="1b076-1314">Personal Identification Number</span></span>
- <span data-ttu-id="1b076-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="1b076-1315">CPR</span></span>
- <span data-ttu-id="1b076-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="1b076-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="1b076-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="1b076-1318">Número de la Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="1b076-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1319">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1319">Format</span></span>

<span data-ttu-id="1b076-1320">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1321">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1321">Pattern</span></span>

<span data-ttu-id="1b076-1322">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b076-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="1b076-1323">Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito</span><span class="sxs-lookup"><span data-stu-id="1b076-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="1b076-1324">Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito.</span><span class="sxs-lookup"><span data-stu-id="1b076-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="1b076-1325">Siete dígitos, el último de los cuales es el dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1326">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1326">Checksum</span></span>

<span data-ttu-id="1b076-1327">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1328">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1328">Definition</span></span>

<span data-ttu-id="1b076-1329">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1330">La función Func_dea_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1331">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-1332">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1332">Keywords</span></span>

<span data-ttu-id="1b076-1333">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1b076-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="1b076-1334">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="1b076-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1335">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1335">Format</span></span>

<span data-ttu-id="1b076-1336">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1337">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1337">Pattern</span></span>

<span data-ttu-id="1b076-1338">Patrón muy complejo y robusto</span><span class="sxs-lookup"><span data-stu-id="1b076-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1339">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1339">Checksum</span></span>

<span data-ttu-id="1b076-1340">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1341">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1341">Definition</span></span>

<span data-ttu-id="1b076-1342">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1343">La función Func_eu_debit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1344">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="1b076-1345">Se encuentra una palabra clave de Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="1b076-1346">Se encuentra una palabra clave de Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="1b076-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="1b076-1347">Se encuentra una palabra clave de Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="1b076-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="1b076-1348">Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="1b076-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="1b076-1349">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="1b076-1350">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1351">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="1b076-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="1b076-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="1b076-1353">número de cuenta</span><span class="sxs-lookup"><span data-stu-id="1b076-1353">account number</span></span> 
- <span data-ttu-id="1b076-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1354">card number</span></span> 
- <span data-ttu-id="1b076-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="1b076-1355">card no.</span></span> 
- <span data-ttu-id="1b076-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1356">security number</span></span> 
- <span data-ttu-id="1b076-1357">CC #</span><span class="sxs-lookup"><span data-stu-id="1b076-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="1b076-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="1b076-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="1b076-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1359">acct nbr</span></span> 
- <span data-ttu-id="1b076-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="1b076-1360">acct num</span></span> 
- <span data-ttu-id="1b076-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="1b076-1361">acct no</span></span> 
- <span data-ttu-id="1b076-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="1b076-1362">american express</span></span> 
- <span data-ttu-id="1b076-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="1b076-1363">americanexpress</span></span> 
- <span data-ttu-id="1b076-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="1b076-1364">americano espresso</span></span> 
- <span data-ttu-id="1b076-1365">amex</span><span class="sxs-lookup"><span data-stu-id="1b076-1365">amex</span></span> 
- <span data-ttu-id="1b076-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1366">atm card</span></span> 
- <span data-ttu-id="1b076-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1367">atm cards</span></span> 
- <span data-ttu-id="1b076-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1368">atm kaart</span></span> 
- <span data-ttu-id="1b076-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1369">atmcard</span></span> 
- <span data-ttu-id="1b076-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1370">atmcards</span></span> 
- <span data-ttu-id="1b076-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1371">atmkaart</span></span> 
- <span data-ttu-id="1b076-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="1b076-1372">atmkaarten</span></span> 
- <span data-ttu-id="1b076-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="1b076-1373">bancontact</span></span> 
- <span data-ttu-id="1b076-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1374">bank card</span></span> 
- <span data-ttu-id="1b076-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1375">bankkaart</span></span> 
- <span data-ttu-id="1b076-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="1b076-1376">card holder</span></span> 
- <span data-ttu-id="1b076-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="1b076-1377">card holders</span></span> 
- <span data-ttu-id="1b076-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="1b076-1378">card num</span></span> 
- <span data-ttu-id="1b076-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1379">card number</span></span> 
- <span data-ttu-id="1b076-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="1b076-1380">card numbers</span></span> 
- <span data-ttu-id="1b076-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="1b076-1381">card type</span></span> 
- <span data-ttu-id="1b076-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="1b076-1382">cardano numerico</span></span> 
- <span data-ttu-id="1b076-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="1b076-1383">cardholder</span></span> 
- <span data-ttu-id="1b076-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="1b076-1384">cardholders</span></span> 
- <span data-ttu-id="1b076-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-1385">cardnumber</span></span> 
- <span data-ttu-id="1b076-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="1b076-1386">cardnumbers</span></span> 
- <span data-ttu-id="1b076-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="1b076-1387">carta bianca</span></span> 
- <span data-ttu-id="1b076-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1388">carta credito</span></span> 
- <span data-ttu-id="1b076-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1389">carta di credito</span></span> 
- <span data-ttu-id="1b076-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1390">cartao de credito</span></span> 
- <span data-ttu-id="1b076-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1391">cartao de crédito</span></span> 
- <span data-ttu-id="1b076-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1392">cartao de debito</span></span> 
- <span data-ttu-id="1b076-1393">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1393">cartao de débito</span></span> 
- <span data-ttu-id="1b076-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="1b076-1394">carte bancaire</span></span> 
- <span data-ttu-id="1b076-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="1b076-1395">carte blanche</span></span> 
- <span data-ttu-id="1b076-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="1b076-1396">carte bleue</span></span> 
- <span data-ttu-id="1b076-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="1b076-1397">carte de credit</span></span> 
- <span data-ttu-id="1b076-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="1b076-1398">carte de crédit</span></span> 
- <span data-ttu-id="1b076-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1399">carte di credito</span></span> 
- <span data-ttu-id="1b076-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="1b076-1400">carteblanche</span></span> 
- <span data-ttu-id="1b076-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1401">cartão de credito</span></span> 
- <span data-ttu-id="1b076-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1402">cartão de crédito</span></span> 
- <span data-ttu-id="1b076-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1403">cartão de debito</span></span> 
- <span data-ttu-id="1b076-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1404">cartão de débito</span></span> 
- <span data-ttu-id="1b076-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="1b076-1405">cb</span></span> 
- <span data-ttu-id="1b076-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="1b076-1406">ccn</span></span> 
- <span data-ttu-id="1b076-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1407">check card</span></span> 
- <span data-ttu-id="1b076-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1408">check cards</span></span> 
- <span data-ttu-id="1b076-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1409">checkcard</span></span>
- <span data-ttu-id="1b076-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1410">checkcards</span></span> 
- <span data-ttu-id="1b076-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1411">chequekaart</span></span> 
- <span data-ttu-id="1b076-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="1b076-1412">cirrus</span></span> 
- <span data-ttu-id="1b076-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="1b076-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="1b076-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1414">controlekaart</span></span> 
- <span data-ttu-id="1b076-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="1b076-1415">controlekaarten</span></span> 
- <span data-ttu-id="1b076-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1416">credit card</span></span> 
- <span data-ttu-id="1b076-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1417">credit cards</span></span> 
- <span data-ttu-id="1b076-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1418">creditcard</span></span> 
- <span data-ttu-id="1b076-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1419">creditcards</span></span> 
- <span data-ttu-id="1b076-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1420">debetkaart</span></span> 
- <span data-ttu-id="1b076-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="1b076-1421">debetkaarten</span></span> 
- <span data-ttu-id="1b076-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1422">debit card</span></span> 
- <span data-ttu-id="1b076-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1423">debit cards</span></span> 
- <span data-ttu-id="1b076-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1424">debitcard</span></span> 
- <span data-ttu-id="1b076-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1425">debitcards</span></span> 
- <span data-ttu-id="1b076-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="1b076-1426">debito automatico</span></span> 
- <span data-ttu-id="1b076-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="1b076-1427">diners club</span></span> 
- <span data-ttu-id="1b076-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="1b076-1428">dinersclub</span></span> 
- <span data-ttu-id="1b076-1429">descubrir</span><span class="sxs-lookup"><span data-stu-id="1b076-1429">discover</span></span> 
- <span data-ttu-id="1b076-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1430">discover card</span></span> 
- <span data-ttu-id="1b076-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1431">discover cards</span></span> 
- <span data-ttu-id="1b076-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1432">discovercard</span></span> 
- <span data-ttu-id="1b076-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1433">discovercards</span></span> 
- <span data-ttu-id="1b076-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="1b076-1434">débito automático</span></span>
- <span data-ttu-id="1b076-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="1b076-1435">edc</span></span> 
- <span data-ttu-id="1b076-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="1b076-1436">eigentümername</span></span> 
- <span data-ttu-id="1b076-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1437">european debit card</span></span> 
- <span data-ttu-id="1b076-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1438">hoofdkaart</span></span> 
- <span data-ttu-id="1b076-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="1b076-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="1b076-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="1b076-1440">in viaggio</span></span> 
- <span data-ttu-id="1b076-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="1b076-1441">japanese card bureau</span></span> 
- <span data-ttu-id="1b076-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="1b076-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="1b076-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="1b076-1443">jcb</span></span> 
- <span data-ttu-id="1b076-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="1b076-1444">kaart</span></span> 
- <span data-ttu-id="1b076-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="1b076-1445">kaart num</span></span> 
- <span data-ttu-id="1b076-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="1b076-1446">kaartaantal</span></span> 
- <span data-ttu-id="1b076-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="1b076-1447">kaartaantallen</span></span> 
- <span data-ttu-id="1b076-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="1b076-1448">kaarthouder</span></span> 
- <span data-ttu-id="1b076-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="1b076-1449">kaarthouders</span></span> 
- <span data-ttu-id="1b076-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1450">karte</span></span>  
- <span data-ttu-id="1b076-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="1b076-1451">karteninhaber</span></span> 
- <span data-ttu-id="1b076-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="1b076-1452">karteninhabers</span></span>
- <span data-ttu-id="1b076-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1453">kartennr</span></span> 
- <span data-ttu-id="1b076-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1454">kartennummer</span></span> 
- <span data-ttu-id="1b076-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1455">kreditkarte</span></span> 
- <span data-ttu-id="1b076-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="1b076-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="1b076-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="1b076-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="1b076-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="1b076-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="1b076-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="1b076-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="1b076-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="1b076-1461">maestro</span></span> 
- <span data-ttu-id="1b076-1462">master card
</span><span class="sxs-lookup"><span data-stu-id="1b076-1462">master card</span></span> 
- <span data-ttu-id="1b076-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="1b076-1463">master cards</span></span> 
- <span data-ttu-id="1b076-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="1b076-1464">mastercard</span></span> 
- <span data-ttu-id="1b076-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="1b076-1465">mastercards</span></span> 
- <span data-ttu-id="1b076-1466">MC</span><span class="sxs-lookup"><span data-stu-id="1b076-1466">mc</span></span> 
- <span data-ttu-id="1b076-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="1b076-1467">mister cash</span></span> 
- <span data-ttu-id="1b076-1468">carta n</span><span class="sxs-lookup"><span data-stu-id="1b076-1468">n carta</span></span> 
- <span data-ttu-id="1b076-1469">carta</span><span class="sxs-lookup"><span data-stu-id="1b076-1469">carta</span></span> 
- <span data-ttu-id="1b076-1470">No hay tarjeta de</span><span class="sxs-lookup"><span data-stu-id="1b076-1470">no de tarjeta</span></span> 
- <span data-ttu-id="1b076-1471">No hay cartao</span><span class="sxs-lookup"><span data-stu-id="1b076-1471">no do cartao</span></span> 
- <span data-ttu-id="1b076-1472">No hay cartão</span><span class="sxs-lookup"><span data-stu-id="1b076-1472">no do cartão</span></span> 
- <span data-ttu-id="1b076-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="1b076-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-p118">no. do cartao</span></span> 
- <span data-ttu-id="1b076-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-p119">no. do cartão</span></span> 
- <span data-ttu-id="1b076-1479">carta n</span><span class="sxs-lookup"><span data-stu-id="1b076-1479">nr carta</span></span> 
- <span data-ttu-id="1b076-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-p120">nr. carta</span></span> 
- <span data-ttu-id="1b076-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1482">numeri di scheda</span></span> 
- <span data-ttu-id="1b076-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1483">numero carta</span></span> 
- <span data-ttu-id="1b076-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1484">numero de cartao</span></span> 
- <span data-ttu-id="1b076-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1485">numero de carte</span></span> 
- <span data-ttu-id="1b076-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-1486">numero de cartão</span></span> 
- <span data-ttu-id="1b076-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1487">numero de tarjeta</span></span>
- <span data-ttu-id="1b076-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1488">numero della carta</span></span> 
- <span data-ttu-id="1b076-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1489">numero di carta</span></span> 
- <span data-ttu-id="1b076-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1490">numero di scheda</span></span> 
- <span data-ttu-id="1b076-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1491">numero do cartao</span></span> 
- <span data-ttu-id="1b076-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-1492">numero do cartão</span></span> 
- <span data-ttu-id="1b076-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1493">numéro de carte</span></span> 
- <span data-ttu-id="1b076-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1494">nº carta</span></span> 
- <span data-ttu-id="1b076-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1495">nº de carte</span></span> 
- <span data-ttu-id="1b076-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="1b076-1496">nº de la carte</span></span> 
- <span data-ttu-id="1b076-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="1b076-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1498">nº do cartao</span></span> 
- <span data-ttu-id="1b076-1499">Nº cartão</span><span class="sxs-lookup"><span data-stu-id="1b076-1499">nº do cartão</span></span> 
- <span data-ttu-id="1b076-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-p121">nº. do cartão</span></span> 
- <span data-ttu-id="1b076-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1502">número de cartao</span></span> 
- <span data-ttu-id="1b076-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="1b076-1503">número de cartão</span></span> 
- <span data-ttu-id="1b076-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1504">número de tarjeta</span></span> 
- <span data-ttu-id="1b076-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="1b076-1505">número do cartao</span></span> 
- <span data-ttu-id="1b076-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="1b076-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="1b076-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="1b076-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="1b076-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="1b076-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="1b076-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="1b076-1509">scheda della banca</span></span> 
- <span data-ttu-id="1b076-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="1b076-1510">scheda di controllo</span></span> 
- <span data-ttu-id="1b076-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1511">scheda di debito</span></span> 
- <span data-ttu-id="1b076-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="1b076-1512">scheda matrice</span></span> 
- <span data-ttu-id="1b076-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="1b076-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="1b076-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="1b076-1514">schede di controllo</span></span> 
- <span data-ttu-id="1b076-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1515">schede di debito</span></span> 
- <span data-ttu-id="1b076-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="1b076-1516">schede matrici</span></span> 
- <span data-ttu-id="1b076-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="1b076-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="1b076-1518">scoprono le schede</span></span> 
- <span data-ttu-id="1b076-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="1b076-1519">solo</span></span> 
- <span data-ttu-id="1b076-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1520">supporti di scheda</span></span> 
- <span data-ttu-id="1b076-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1521">supporto di scheda</span></span> 
- <span data-ttu-id="1b076-1522">conmutador</span><span class="sxs-lookup"><span data-stu-id="1b076-1522">switch</span></span> 
- <span data-ttu-id="1b076-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="1b076-1523">tarjeta atm</span></span> 
- <span data-ttu-id="1b076-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1524">tarjeta credito</span></span> 
- <span data-ttu-id="1b076-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="1b076-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="1b076-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="1b076-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="1b076-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="1b076-1528">tarjeta debito</span></span> 
- <span data-ttu-id="1b076-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="1b076-1529">tarjeta no</span></span>
- <span data-ttu-id="1b076-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="1b076-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="1b076-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1531">tipo della scheda</span></span> 
- <span data-ttu-id="1b076-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="1b076-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="1b076-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1533">scheda</span></span> 
- <span data-ttu-id="1b076-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="1b076-1534">v pay</span></span> 
- <span data-ttu-id="1b076-1535">v-pago</span><span class="sxs-lookup"><span data-stu-id="1b076-1535">v-pay</span></span> 
- <span data-ttu-id="1b076-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="1b076-1536">visa</span></span> 
- <span data-ttu-id="1b076-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="1b076-1537">visa plus</span></span> 
- <span data-ttu-id="1b076-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="1b076-1538">visa electron</span></span> 
- <span data-ttu-id="1b076-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="1b076-1539">visto</span></span> 
- <span data-ttu-id="1b076-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1540">visum</span></span> 
- <span data-ttu-id="1b076-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="1b076-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="1b076-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="1b076-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="1b076-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="1b076-1543">card identification number</span></span>
- <span data-ttu-id="1b076-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="1b076-1544">card verification</span></span> 
- <span data-ttu-id="1b076-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="1b076-1545">cardi la verifica</span></span> 
- <span data-ttu-id="1b076-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="1b076-1546">cid</span></span> 
- <span data-ttu-id="1b076-1547">COD seg</span><span class="sxs-lookup"><span data-stu-id="1b076-1547">cod seg</span></span> 
- <span data-ttu-id="1b076-1548">COD seguranca</span><span class="sxs-lookup"><span data-stu-id="1b076-1548">cod seguranca</span></span> 
- <span data-ttu-id="1b076-1549">COD segurança</span><span class="sxs-lookup"><span data-stu-id="1b076-1549">cod segurança</span></span> 
- <span data-ttu-id="1b076-1550">COD sicurezza</span><span class="sxs-lookup"><span data-stu-id="1b076-1550">cod sicurezza</span></span> 
- <span data-ttu-id="1b076-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="1b076-p122">cod. seg</span></span> 
- <span data-ttu-id="1b076-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="1b076-p123">cod. seguranca</span></span> 
- <span data-ttu-id="1b076-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="1b076-p124">cod. segurança</span></span> 
- <span data-ttu-id="1b076-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="1b076-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="1b076-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="1b076-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="1b076-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="1b076-1560">codice di verifica</span></span> 
- <span data-ttu-id="1b076-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="1b076-1561">codigo</span></span> 
- <span data-ttu-id="1b076-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="1b076-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="1b076-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="1b076-1563">codigo de segurança</span></span> 
- <span data-ttu-id="1b076-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="1b076-1564">crittogramma</span></span> 
- <span data-ttu-id="1b076-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="1b076-1565">cryptogram</span></span> 
- <span data-ttu-id="1b076-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="1b076-1566">cryptogramme</span></span> 
- <span data-ttu-id="1b076-1567">CV2</span><span class="sxs-lookup"><span data-stu-id="1b076-1567">cv2</span></span> 
- <span data-ttu-id="1b076-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="1b076-1568">cvc</span></span> 
- <span data-ttu-id="1b076-1569">CVC2 obtenidos</span><span class="sxs-lookup"><span data-stu-id="1b076-1569">cvc2</span></span> 
- <span data-ttu-id="1b076-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="1b076-1570">cvn</span></span> 
- <span data-ttu-id="1b076-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="1b076-1571">cvv</span></span> 
- <span data-ttu-id="1b076-1572">cvv2</span><span class="sxs-lookup"><span data-stu-id="1b076-1572">cvv2</span></span> 
- <span data-ttu-id="1b076-1573">campo Cód. seguranca</span><span class="sxs-lookup"><span data-stu-id="1b076-1573">cód seguranca</span></span> 
- <span data-ttu-id="1b076-1574">campo Cód. segurança</span><span class="sxs-lookup"><span data-stu-id="1b076-1574">cód segurança</span></span> 
- <span data-ttu-id="1b076-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="1b076-p126">cód. seguranca</span></span> 
- <span data-ttu-id="1b076-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="1b076-p127">cód. segurança</span></span> 
- <span data-ttu-id="1b076-1579">código
</span><span class="sxs-lookup"><span data-stu-id="1b076-1579">código</span></span> 
- <span data-ttu-id="1b076-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="1b076-1580">código de seguranca</span></span> 
- <span data-ttu-id="1b076-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="1b076-1581">código de segurança</span></span> 
- <span data-ttu-id="1b076-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="1b076-1582">de kaart controle</span></span> 
- <span data-ttu-id="1b076-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="1b076-1583">geeft nr uit</span></span> 
- <span data-ttu-id="1b076-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="1b076-1584">issue no</span></span> 
- <span data-ttu-id="1b076-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1585">issue number</span></span> 
- <span data-ttu-id="1b076-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="1b076-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="1b076-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="1b076-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="1b076-1589">kwestieaantal</span></span> 
- <span data-ttu-id="1b076-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="1b076-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="1b076-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="1b076-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="1b076-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="1b076-1594">numero de securite</span></span> 
- <span data-ttu-id="1b076-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1595">numero de verificacao</span></span> 
- <span data-ttu-id="1b076-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="1b076-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="1b076-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="1b076-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="1b076-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="1b076-1598">scheda</span></span> 
- <span data-ttu-id="1b076-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="1b076-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="1b076-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="1b076-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="1b076-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="1b076-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="1b076-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="1b076-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="1b076-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="1b076-1603">número de verificação</span></span> 
- <span data-ttu-id="1b076-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="1b076-1604">perno il blocco</span></span> 
- <span data-ttu-id="1b076-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="1b076-1605">pin block</span></span> 
- <span data-ttu-id="1b076-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1606">prufziffer</span></span> 
- <span data-ttu-id="1b076-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1607">prüfziffer</span></span> 
- <span data-ttu-id="1b076-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="1b076-1608">security code</span></span> 
- <span data-ttu-id="1b076-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="1b076-1609">security no</span></span> 
- <span data-ttu-id="1b076-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1610">security number</span></span> 
- <span data-ttu-id="1b076-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="1b076-1611">sicherheits kode</span></span> 
- <span data-ttu-id="1b076-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="1b076-1612">sicherheitscode</span></span> 
- <span data-ttu-id="1b076-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="1b076-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="1b076-1614">speldblok</span></span> 
- <span data-ttu-id="1b076-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1615">veiligheid nr</span></span> 
- <span data-ttu-id="1b076-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="1b076-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="1b076-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="1b076-1617">veiligheidscode</span></span> 
- <span data-ttu-id="1b076-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="1b076-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="1b076-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="1b076-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="1b076-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="1b076-1621">ablauf</span></span> 
- <span data-ttu-id="1b076-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="1b076-1622">data de expiracao</span></span> 
- <span data-ttu-id="1b076-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="1b076-1623">data de expiração</span></span> 
- <span data-ttu-id="1b076-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="1b076-1624">data del exp</span></span> 
- <span data-ttu-id="1b076-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="1b076-1625">data di exp</span></span> 
- <span data-ttu-id="1b076-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="1b076-1626">data di scadenza</span></span> 
- <span data-ttu-id="1b076-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="1b076-1627">data em que expira</span></span> 
- <span data-ttu-id="1b076-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="1b076-1628">data scad</span></span> 
- <span data-ttu-id="1b076-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="1b076-1629">data scadenza</span></span> 
- <span data-ttu-id="1b076-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="1b076-1630">date de validité</span></span> 
- <span data-ttu-id="1b076-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="1b076-1631">datum afloop</span></span> 
- <span data-ttu-id="1b076-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="1b076-1632">datum van exp</span></span> 
- <span data-ttu-id="1b076-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="1b076-1633">de afloop</span></span> 
- <span data-ttu-id="1b076-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="1b076-1634">espira</span></span> 
- <span data-ttu-id="1b076-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="1b076-1635">espira</span></span> 
- <span data-ttu-id="1b076-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="1b076-1636">exp date</span></span> 
- <span data-ttu-id="1b076-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1637">exp datum</span></span> 
- <span data-ttu-id="1b076-1638">expiración</span><span class="sxs-lookup"><span data-stu-id="1b076-1638">expiration</span></span> 
- <span data-ttu-id="1b076-1639">expirar
</span><span class="sxs-lookup"><span data-stu-id="1b076-1639">expire</span></span> 
- <span data-ttu-id="1b076-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="1b076-1640">expires</span></span> 
- <span data-ttu-id="1b076-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="1b076-1641">expiry</span></span> 
- <span data-ttu-id="1b076-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="1b076-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="1b076-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="1b076-1643">fecha de venc</span></span> 
- <span data-ttu-id="1b076-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="1b076-1644">gultig bis</span></span> 
- <span data-ttu-id="1b076-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="1b076-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="1b076-1646">gültig bis</span></span> 
- <span data-ttu-id="1b076-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="1b076-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="1b076-1648">la scadenza</span></span> 
- <span data-ttu-id="1b076-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="1b076-1649">scadenza</span></span> 
- <span data-ttu-id="1b076-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="1b076-1650">valable</span></span> 
- <span data-ttu-id="1b076-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="1b076-1651">validade</span></span> 
- <span data-ttu-id="1b076-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1652">valido hasta</span></span> 
- <span data-ttu-id="1b076-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="1b076-1653">valor</span></span> 
- <span data-ttu-id="1b076-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="1b076-1654">venc</span></span> 
- <span data-ttu-id="1b076-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="1b076-1655">vencimento</span></span> 
- <span data-ttu-id="1b076-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="1b076-1656">vencimiento</span></span> 
- <span data-ttu-id="1b076-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="1b076-1657">verloopt</span></span> 
- <span data-ttu-id="1b076-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="1b076-1658">vervaldag</span></span> 
- <span data-ttu-id="1b076-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1659">vervaldatum</span></span> 
- <span data-ttu-id="1b076-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="1b076-1660">vto</span></span> 
- <span data-ttu-id="1b076-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="1b076-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="1b076-1662">Número de licencia del controlador de la UE</span><span class="sxs-lookup"><span data-stu-id="1b076-1662">EU Driver's License Number</span></span>

<span data-ttu-id="1b076-1663">Para obtener más información, vea el [tipo de información confidencial del número de licencia del controlador de la UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="1b076-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="1b076-1664">Número de identificación de la UE nacional</span><span class="sxs-lookup"><span data-stu-id="1b076-1664">EU National Identification Number</span></span>

<span data-ttu-id="1b076-1665">Para obtener más información, vea el [tipo de información confidencial del número de identificación nacional de la UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="1b076-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="1b076-1666">Número de cuenta de Passport de la UE</span><span class="sxs-lookup"><span data-stu-id="1b076-1666">EU Passport Number</span></span>

<span data-ttu-id="1b076-1667">Para obtener más información, vea el [tipo de información confidencial del número de cuenta de Passport de la UE](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="1b076-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="1b076-1668">Identificador de número de seguridad Social de la UE o equivalente</span><span class="sxs-lookup"><span data-stu-id="1b076-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="1b076-1669">Para obtener más información, vea el [número de seguridad Social de la UE o tipo de información confidencial de identificador equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="1b076-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="1b076-1670">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="1b076-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="1b076-1671">Para obtener más información, vea el [tipo de información confidencial del número de identificación de impuestos de la UE](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="1b076-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="1b076-1672">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="1b076-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1673">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1673">Format</span></span>

<span data-ttu-id="1b076-1674">Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1675">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1675">Pattern</span></span>

<span data-ttu-id="1b076-1676">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b076-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="1b076-1677">Seis dígitos en el formato DDMMAA que son una fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="1b076-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="1b076-1678">Marcador del siglo (ya sea '-', '+' o 'a')</span><span class="sxs-lookup"><span data-stu-id="1b076-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="1b076-1679">Número de identificación personal de tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="1b076-1680">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1681">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1681">Checksum</span></span>

<span data-ttu-id="1b076-1682">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1683">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1683">Definition</span></span>

<span data-ttu-id="1b076-1684">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1685">La función Func_finnish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1686">Se encuentra una palabra clave de Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="1b076-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="1b076-1687">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-1688">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1688">Keywords</span></span>

- <span data-ttu-id="1b076-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="1b076-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="1b076-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="1b076-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="1b076-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="1b076-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="1b076-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="1b076-1692">Personbeteckning</span></span>
- <span data-ttu-id="1b076-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="1b076-1694">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="1b076-1694">Finland Passport Number</span></span>

<span data-ttu-id="1b076-p130">Formato de combinación de nueve letras y dígitos combinación de patrón de nueve letras y dígitos: directiva de dos letras (no entre mayúsculas y minúsculas) siete dígitos DLP de una definición de suma de comprobación No está seguro de que ha detectado este tipo de información confidencial si al 75%, comprendido en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_finland_passport_number. <!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity> Erta pasiva de Passport de Keyword_finland_passport_number palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="1b076-1699">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="1b076-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1700">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1700">Format</span></span>

<span data-ttu-id="1b076-1701">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1702">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1702">Pattern</span></span>

<span data-ttu-id="1b076-1703">12 dígitos con validación para descontar patrones similares como los números de teléfono franceses</span><span class="sxs-lookup"><span data-stu-id="1b076-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1704">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1704">Checksum</span></span>

<span data-ttu-id="1b076-1705">No</span><span class="sxs-lookup"><span data-stu-id="1b076-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1706">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1706">Definition</span></span>

<span data-ttu-id="1b076-1707">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1708">La función Func_french_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1709">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="1b076-1710">Se encuentra una palabra clave de Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="1b076-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="1b076-1711">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1712">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="1b076-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="1b076-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="1b076-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b076-1714">drivers licence</span></span>
- <span data-ttu-id="1b076-1715">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-1715">drivers license</span></span>
- <span data-ttu-id="1b076-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-1716">driving licence</span></span>
- <span data-ttu-id="1b076-1717">licencia fuerzas</span><span class="sxs-lookup"><span data-stu-id="1b076-1717">driving license</span></span>
- <span data-ttu-id="1b076-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="1b076-1718">permis de conduire</span></span>
- <span data-ttu-id="1b076-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="1b076-1719">licence number</span></span>
- <span data-ttu-id="1b076-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="1b076-1720">license number</span></span>
- <span data-ttu-id="1b076-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="1b076-1721">licence numbers</span></span>
- <span data-ttu-id="1b076-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="1b076-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="1b076-1723">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="1b076-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1724">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1724">Format</span></span>

<span data-ttu-id="1b076-1725">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1726">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1726">Pattern</span></span>

<span data-ttu-id="1b076-1727">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1728">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1728">Checksum</span></span>

<span data-ttu-id="1b076-1729">No</span><span class="sxs-lookup"><span data-stu-id="1b076-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1730">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1730">Definition</span></span>

<span data-ttu-id="1b076-1731">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1732">La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-1733">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1733">Keywords</span></span>

<span data-ttu-id="1b076-1734">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1b076-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="1b076-1735">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="1b076-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1736">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1736">Format</span></span>

<span data-ttu-id="1b076-1737">Nueve dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="1b076-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1738">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1738">Pattern</span></span>

<span data-ttu-id="1b076-1739">Nueve dígitos y letras:</span><span class="sxs-lookup"><span data-stu-id="1b076-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="1b076-1740">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1740">Two digits</span></span> 
- <span data-ttu-id="1b076-1741">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="1b076-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-1742">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1743">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1743">Checksum</span></span>

<span data-ttu-id="1b076-1744">No</span><span class="sxs-lookup"><span data-stu-id="1b076-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1745">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1745">Definition</span></span>

<span data-ttu-id="1b076-1746">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1747">La función Func_fr_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1748">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="1b076-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-1749">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="1b076-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-1750">Keyword_passport</span></span>

- <span data-ttu-id="1b076-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="1b076-1751">Passport Number</span></span>
- <span data-ttu-id="1b076-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="1b076-1752">Passport No</span></span>
- <span data-ttu-id="1b076-1753">Passport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-1753">Passport #</span></span>
- <span data-ttu-id="1b076-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-1754">Passport#</span></span>
- <span data-ttu-id="1b076-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="1b076-1755">PassportID</span></span>
- <span data-ttu-id="1b076-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="1b076-1756">Passportno</span></span>
- <span data-ttu-id="1b076-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-1757">passportnumber</span></span>
- <span data-ttu-id="1b076-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="1b076-1758">パスポート</span></span>
- <span data-ttu-id="1b076-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-1759">パスポート番号</span></span>
- <span data-ttu-id="1b076-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="1b076-1760">パスポートのNum</span></span>
- <span data-ttu-id="1b076-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-1761">パスポート ＃</span></span> 
- <span data-ttu-id="1b076-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="1b076-1762">Numéro de passeport</span></span>
- <span data-ttu-id="1b076-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="1b076-1763">Passeport n °</span></span>
- <span data-ttu-id="1b076-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="1b076-1764">Passeport Non</span></span>
- <span data-ttu-id="1b076-1765">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-1765">Passeport #</span></span>
- <span data-ttu-id="1b076-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-1766">Passeport#</span></span>
- <span data-ttu-id="1b076-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="1b076-1767">PasseportNon</span></span>
- <span data-ttu-id="1b076-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="1b076-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="1b076-1769">Número de seguridad social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="1b076-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1770">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1770">Format</span></span>

<span data-ttu-id="1b076-1771">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1772">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1772">Pattern</span></span>

<span data-ttu-id="1b076-1773">Debe coincidir uno de los dos patrones:</span><span class="sxs-lookup"><span data-stu-id="1b076-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="1b076-1774">13 dígitos seguidos de un espacio seguido de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1774">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="1b076-1775">o</span><span class="sxs-lookup"><span data-stu-id="1b076-1775">or</span></span>
- <span data-ttu-id="1b076-1776">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1777">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1777">Checksum</span></span>

<span data-ttu-id="1b076-1778">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1779">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1779">Definition</span></span>

<span data-ttu-id="1b076-1780">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1781">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1782">Se encuentra una palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="1b076-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="1b076-1783">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1783">The checksum passes.</span></span>

<span data-ttu-id="1b076-1784">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1785">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1786">No se encuentra ninguna palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="1b076-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="1b076-1787">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1788">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="1b076-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="1b076-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="1b076-1790">insee</span><span class="sxs-lookup"><span data-stu-id="1b076-1790">insee</span></span>
- <span data-ttu-id="1b076-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="1b076-1791">securité sociale</span></span>
- <span data-ttu-id="1b076-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="1b076-1792">securite sociale</span></span>
- <span data-ttu-id="1b076-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="1b076-1793">national id</span></span>
- <span data-ttu-id="1b076-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="1b076-1794">national identification</span></span>
- <span data-ttu-id="1b076-1795">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="1b076-1795">numéro d'identité</span></span>
- <span data-ttu-id="1b076-1796">sin FEC ' identité</span><span class="sxs-lookup"><span data-stu-id="1b076-1796">no d'identité</span></span>
- <span data-ttu-id="1b076-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="1b076-p131">no. d'identité</span></span>
- <span data-ttu-id="1b076-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="1b076-1799">numero d'identite</span></span>
- <span data-ttu-id="1b076-1800">No hay d'identite</span><span class="sxs-lookup"><span data-stu-id="1b076-1800">no d'identite</span></span>
- <span data-ttu-id="1b076-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="1b076-p132">no. d'identite</span></span>
- <span data-ttu-id="1b076-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="1b076-1803">social security number</span></span>
- <span data-ttu-id="1b076-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="1b076-1804">social security code</span></span>
- <span data-ttu-id="1b076-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="1b076-1805">social insurance number</span></span>
- <span data-ttu-id="1b076-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="1b076-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="1b076-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="1b076-1807">d'identité nationale</span></span>
- <span data-ttu-id="1b076-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="1b076-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="1b076-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="1b076-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="1b076-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="1b076-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="1b076-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="1b076-1811">numéro de sécu</span></span>
- <span data-ttu-id="1b076-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="1b076-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="1b076-1813">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="1b076-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1814">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1814">Format</span></span>

<span data-ttu-id="1b076-1815">Combinación de 11 dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="1b076-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1816">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1816">Pattern</span></span>

<span data-ttu-id="1b076-1817">11 dígitos y letras (no distingue entre mayúsculas y minúsculas):</span><span class="sxs-lookup"><span data-stu-id="1b076-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="1b076-1818">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="1b076-1818">A digit or letter</span></span> 
- <span data-ttu-id="1b076-1819">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1819">Two digits</span></span> 
- <span data-ttu-id="1b076-1820">Seis dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="1b076-1820">Six digits or letters</span></span> 
- <span data-ttu-id="1b076-1821">Un dígito</span><span class="sxs-lookup"><span data-stu-id="1b076-1821">A digit</span></span> 
- <span data-ttu-id="1b076-1822">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="1b076-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1823">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1823">Checksum</span></span>

<span data-ttu-id="1b076-1824">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1825">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1825">Definition</span></span>

<span data-ttu-id="1b076-1826">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1827">La función Func_german_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1828">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="1b076-1829">Se encuentra una palabra clave de Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="1b076-1830">Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="1b076-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="1b076-1831">Se encuentra una palabra clave de Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="1b076-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="1b076-1832">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1833">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="1b076-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="1b076-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="1b076-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="1b076-1835">Führerschein</span></span>
- <span data-ttu-id="1b076-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="1b076-1836">Fuhrerschein</span></span>
- <span data-ttu-id="1b076-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="1b076-1837">Fuehrerschein</span></span>
- <span data-ttu-id="1b076-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="1b076-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="1b076-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="1b076-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="1b076-1841">Führerschein-</span></span> 
- <span data-ttu-id="1b076-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="1b076-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="1b076-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="1b076-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="1b076-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="1b076-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="1b076-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="1b076-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="1b076-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="1b076-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="1b076-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="1b076-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="1b076-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="1b076-1850">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="1b076-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="1b076-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="1b076-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="1b076-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="1b076-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="1b076-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="1b076-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="1b076-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="1b076-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="1b076-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="1b076-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="1b076-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="1b076-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="1b076-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="1b076-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="1b076-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="1b076-1862">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="1b076-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="1b076-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="1b076-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="1b076-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="1b076-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="1b076-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="1b076-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="1b076-1868">DL</span><span class="sxs-lookup"><span data-stu-id="1b076-1868">DL</span></span> 
- <span data-ttu-id="1b076-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="1b076-1869">DLS</span></span>
- <span data-ttu-id="1b076-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="1b076-1870">Driv Lic</span></span> 
- <span data-ttu-id="1b076-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="1b076-1871">Driv Licen</span></span> 
- <span data-ttu-id="1b076-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="1b076-1872">Driv License</span></span>
- <span data-ttu-id="1b076-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="1b076-1873">Driv Licenses</span></span> 
- <span data-ttu-id="1b076-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-1874">Driv Licence</span></span> 
- <span data-ttu-id="1b076-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-1875">Driv Licences</span></span> 
- <span data-ttu-id="1b076-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="1b076-1876">Driv Lic</span></span> 
- <span data-ttu-id="1b076-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="1b076-1877">Driver Licen</span></span> 
- <span data-ttu-id="1b076-1878">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-1878">Driver License</span></span> 
- <span data-ttu-id="1b076-1879">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-1879">Driver Licenses</span></span> 
- <span data-ttu-id="1b076-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-1880">Driver Licence</span></span> 
- <span data-ttu-id="1b076-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-1881">Driver Licences</span></span> 
- <span data-ttu-id="1b076-1882">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-1882">Drivers Lic</span></span> 
- <span data-ttu-id="1b076-1883">Controladores Licen</span><span class="sxs-lookup"><span data-stu-id="1b076-1883">Drivers Licen</span></span> 
- <span data-ttu-id="1b076-1884">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-1884">Drivers License</span></span> 
- <span data-ttu-id="1b076-1885">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="1b076-1886">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-1886">Drivers Licence</span></span> 
- <span data-ttu-id="1b076-1887">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-1887">Drivers Licences</span></span> 
- <span data-ttu-id="1b076-1888">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-1888">Driver's Lic</span></span> 
- <span data-ttu-id="1b076-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="1b076-1889">Driver's Licen</span></span> 
- <span data-ttu-id="1b076-1890">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="1b076-1890">Driver's License</span></span> 
- <span data-ttu-id="1b076-1891">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="1b076-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-1892">Driver's Licence</span></span> 
- <span data-ttu-id="1b076-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-1893">Driver's Licences</span></span> 
- <span data-ttu-id="1b076-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="1b076-1894">Driving Lic</span></span> 
- <span data-ttu-id="1b076-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="1b076-1895">Driving Licen</span></span> 
- <span data-ttu-id="1b076-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="1b076-1896">Driving License</span></span> 
- <span data-ttu-id="1b076-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="1b076-1897">Driving Licenses</span></span> 
- <span data-ttu-id="1b076-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="1b076-1898">Driving Licence</span></span> 
- <span data-ttu-id="1b076-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="1b076-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="1b076-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="1b076-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="1b076-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="1b076-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="1b076-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="1b076-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1904">No-Führerschein</span></span> 
- <span data-ttu-id="1b076-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="1b076-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="1b076-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1907">N-Führerschein</span></span> 
- <span data-ttu-id="1b076-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="1b076-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="1b076-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="1b076-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="1b076-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="1b076-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="1b076-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1913">No-Führerschein</span></span> 
- <span data-ttu-id="1b076-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="1b076-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="1b076-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1916">N-Führerschein</span></span> 
- <span data-ttu-id="1b076-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="1b076-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="1b076-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="1b076-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="1b076-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="1b076-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="1b076-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="1b076-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="1b076-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="1b076-1921">ausstellungsort</span></span>
- <span data-ttu-id="1b076-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="1b076-1922">ausstellende behöde</span></span>
- <span data-ttu-id="1b076-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="1b076-1923">ausstellende behorde</span></span>
- <span data-ttu-id="1b076-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="1b076-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="1b076-1925">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="1b076-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1926">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1926">Format</span></span>

<span data-ttu-id="1b076-1927">10 dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="1b076-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1928">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1928">Pattern</span></span>

<span data-ttu-id="1b076-1929">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b076-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="1b076-1930">El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="1b076-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="1b076-1931">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1931">Three digits</span></span> 
- <span data-ttu-id="1b076-1932">Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="1b076-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="1b076-1933">Un dígito</span><span class="sxs-lookup"><span data-stu-id="1b076-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1934">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1934">Checksum</span></span>

<span data-ttu-id="1b076-1935">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1936">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1936">Definition</span></span>

<span data-ttu-id="1b076-1937">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1938">La función Func_german_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1939">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="1b076-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="1b076-1940">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1940">The checksum passes.</span></span>

<span data-ttu-id="1b076-1941">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1942">La función Func_german_passport_data encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1943">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="1b076-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="1b076-1944">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-1945">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="1b076-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="1b076-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="1b076-1947">reisepass</span></span>
- <span data-ttu-id="1b076-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="1b076-1948">reisepasse</span></span>
- <span data-ttu-id="1b076-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1949">reisepassnummer</span></span>
- <span data-ttu-id="1b076-1950">passport</span><span class="sxs-lookup"><span data-stu-id="1b076-1950">passport</span></span>
- <span data-ttu-id="1b076-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="1b076-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="1b076-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="1b076-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="1b076-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="1b076-1953">geburtsdatum</span></span>
- <span data-ttu-id="1b076-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="1b076-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="1b076-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="1b076-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="1b076-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="1b076-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="1b076-1957">No-Reisepass n-Reisepass</span><span class="sxs-lookup"><span data-stu-id="1b076-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="1b076-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="1b076-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="1b076-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="1b076-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="1b076-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="1b076-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="1b076-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="1b076-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="1b076-1962">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="1b076-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1963">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1963">Format</span></span>

<span data-ttu-id="1b076-1964">Desde el 1 de noviembre de 2010: nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="1b076-1965">Desde el 1 de abril de 1987 hasta 31 dígitos de 2010:10 de octubre</span><span class="sxs-lookup"><span data-stu-id="1b076-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1966">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1966">Pattern</span></span>

<span data-ttu-id="1b076-1967">Desde el 1 de noviembre de 2010:</span><span class="sxs-lookup"><span data-stu-id="1b076-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="1b076-1968">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-1969">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1969">Eight digits</span></span>

<span data-ttu-id="1b076-1970">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:</span><span class="sxs-lookup"><span data-stu-id="1b076-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="1b076-1971">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1972">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1972">Checksum</span></span>

<span data-ttu-id="1b076-1973">No</span><span class="sxs-lookup"><span data-stu-id="1b076-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-1974">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-1974">Definition</span></span>

<span data-ttu-id="1b076-1975">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-1976">La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-1977">Se encuentra una palabra clave de Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-1978">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="1b076-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="1b076-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="1b076-1980">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="1b076-1980">Identity Card</span></span>
- <span data-ttu-id="1b076-1981">ID</span><span class="sxs-lookup"><span data-stu-id="1b076-1981">ID</span></span>
- <span data-ttu-id="1b076-1982">Identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-1982">Identification</span></span>
- <span data-ttu-id="1b076-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="1b076-1983">Personalausweis</span></span>
- <span data-ttu-id="1b076-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="1b076-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="1b076-1985">Ausweis</span></span>
- <span data-ttu-id="1b076-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="1b076-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="1b076-1987">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="1b076-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="1b076-1988">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-1988">Format</span></span>

<span data-ttu-id="1b076-1989">Combinación de 7 u 8 letras y números más un guión</span><span class="sxs-lookup"><span data-stu-id="1b076-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-1990">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-1990">Pattern</span></span>

<span data-ttu-id="1b076-1991">Siete letras y números (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="1b076-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="1b076-1992">Una letra (cualquier letra del alfabeto griego) </span><span class="sxs-lookup"><span data-stu-id="1b076-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="1b076-1993">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-1993">A dash</span></span> 
- <span data-ttu-id="1b076-1994">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1994">Six digits</span></span>

<span data-ttu-id="1b076-1995">Ocho letras y números (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="1b076-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="1b076-1996">Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="1b076-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="1b076-1997">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-1997">A dash</span></span> 
- <span data-ttu-id="1b076-1998">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-1999">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-1999">Checksum</span></span>

<span data-ttu-id="1b076-2000">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2001">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2001">Definition</span></span>

<span data-ttu-id="1b076-2002">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2003">La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2004">Se encuentra una palabra clave de Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2005">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="1b076-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="1b076-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="1b076-2007">Tarjeta de identidad griega</span><span class="sxs-lookup"><span data-stu-id="1b076-2007">Greek identity Card</span></span>
- <span data-ttu-id="1b076-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="1b076-2008">Tautotita</span></span>
- <span data-ttu-id="1b076-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="1b076-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="1b076-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="1b076-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="1b076-2011">Número de tarjeta de identidad de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="1b076-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2012">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2012">Format</span></span>

<span data-ttu-id="1b076-2013">Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final</span><span class="sxs-lookup"><span data-stu-id="1b076-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2014">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2014">Pattern</span></span>

<span data-ttu-id="1b076-2015">Combinación de 8 o 9 letras:</span><span class="sxs-lookup"><span data-stu-id="1b076-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="1b076-2016">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="1b076-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2017">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2017">Six digits</span></span> 
- <span data-ttu-id="1b076-2018">El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1b076-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2019">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2019">Checksum</span></span>

<span data-ttu-id="1b076-2020">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2021">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2021">Definition</span></span>

<span data-ttu-id="1b076-2022">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2023">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2024">Se encuentra una palabra clave de Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="1b076-2025">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2025">The checksum passes.</span></span>

<span data-ttu-id="1b076-2026">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2027">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2028">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2029">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="1b076-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="1b076-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="1b076-2031">Tarjeta de identidad de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="1b076-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="1b076-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="1b076-2032">HKID</span></span>
- <span data-ttu-id="1b076-2033">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-2033">ID card</span></span>
- <span data-ttu-id="1b076-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="1b076-2034">香港身份證</span></span> 
- <span data-ttu-id="1b076-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="1b076-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="1b076-2036">Número de cuenta permanente de India (PAN)</span><span class="sxs-lookup"><span data-stu-id="1b076-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2037">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2037">Format</span></span>

<span data-ttu-id="1b076-2038">10 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2039">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2039">Pattern</span></span>

<span data-ttu-id="1b076-2040">10 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2040">10 letters or digits:</span></span>
- <span data-ttu-id="1b076-2041">Cinco letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="1b076-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2042">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2042">Four digits</span></span> 
- <span data-ttu-id="1b076-2043">Una letra que es un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="1b076-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2044">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2044">Checksum</span></span>

<span data-ttu-id="1b076-2045">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2046">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2046">Definition</span></span>

<span data-ttu-id="1b076-2047">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2048">La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2049">Se encuentra una palabra clave de Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="1b076-2050">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2051">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="1b076-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="1b076-2053">Número de cuenta permanente
</span><span class="sxs-lookup"><span data-stu-id="1b076-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="1b076-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="1b076-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="1b076-2055">Número de identificación único (Aadhaar) de la India</span><span class="sxs-lookup"><span data-stu-id="1b076-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2056">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2056">Format</span></span>

<span data-ttu-id="1b076-2057">12 dígitos que contienen espacios o guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="1b076-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2058">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2058">Pattern</span></span>

<span data-ttu-id="1b076-2059">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2059">12 digits:</span></span>
- <span data-ttu-id="1b076-2060">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2060">Four digits</span></span> 
- <span data-ttu-id="1b076-2061">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="1b076-2061">An optional space or dash</span></span> 
- <span data-ttu-id="1b076-2062">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2062">Four digits</span></span> 
- <span data-ttu-id="1b076-2063">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="1b076-2063">An optional space or dash</span></span> 
- <span data-ttu-id="1b076-2064">El dígito final que es el dígito de control</span><span class="sxs-lookup"><span data-stu-id="1b076-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2065">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2065">Checksum</span></span>

<span data-ttu-id="1b076-2066">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2067">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2067">Definition</span></span>

<span data-ttu-id="1b076-p133">Una directiva de DLP es 85% seguro de que ha detectado este tipo de información confidencial if, dentro de una proximidad de 300 caracteres: la función Func_india_aadhaar busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_india_aadhar. Pasa la suma de comprobación. Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la función Func_india_aadhaar busca contenido que coincide con el patrón. Pasa la suma de comprobación. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="1b076-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="1b076-2074">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="1b076-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="1b076-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="1b076-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="1b076-2076">Aadhar</span></span>
- <span data-ttu-id="1b076-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="1b076-2077">Aadhaar</span></span>
- <span data-ttu-id="1b076-2078">UID</span><span class="sxs-lookup"><span data-stu-id="1b076-2078">UID</span></span>
- <span data-ttu-id="1b076-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="1b076-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="1b076-2080">Número de tarjeta de identidad (KTP) de Indonesia</span><span class="sxs-lookup"><span data-stu-id="1b076-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2081">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2081">Format</span></span>

<span data-ttu-id="1b076-2082">16 dígitos que contienen puntos opcionales</span><span class="sxs-lookup"><span data-stu-id="1b076-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2083">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2083">Pattern</span></span>

<span data-ttu-id="1b076-2084">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2084">16 digits:</span></span>
- <span data-ttu-id="1b076-2085">Código de la provincia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2085">Two-digit province code</span></span> 
- <span data-ttu-id="1b076-2086">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2086">A period (optional)</span></span> 
- <span data-ttu-id="1b076-2087">Código de ciudad o regencia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="1b076-2088">Código de subdistrito de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="1b076-2089">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2089">A period (optional)</span></span> 
- <span data-ttu-id="1b076-2090">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="1b076-2091">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2091">A period (optional)</span></span> 
- <span data-ttu-id="1b076-2092">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2093">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2093">Checksum</span></span>

<span data-ttu-id="1b076-2094">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2095">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2095">Definition</span></span>

<span data-ttu-id="1b076-2096">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2097">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2098">Se encuentra una palabra clave de Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="1b076-2099">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2100">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2101">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="1b076-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="1b076-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="1b076-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="1b076-2103">KTP</span></span>
- <span data-ttu-id="1b076-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="1b076-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="1b076-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="1b076-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="1b076-2106">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="1b076-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2107">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2107">Format</span></span>

<span data-ttu-id="1b076-2108">Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)
</span><span class="sxs-lookup"><span data-stu-id="1b076-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2109">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2109">Pattern</span></span>

<span data-ttu-id="1b076-2110">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b076-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="1b076-2111">Código de país de dos letras</span><span class="sxs-lookup"><span data-stu-id="1b076-2111">Two-letter country code</span></span>
- <span data-ttu-id="1b076-2112">Dos dígitos de control (seguidos de un espacio opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="1b076-2113">1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)</span><span class="sxs-lookup"><span data-stu-id="1b076-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="1b076-2114">1-3 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2114">1-3 letters or digits</span></span>

<span data-ttu-id="1b076-p134">El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:</span><span class="sxs-lookup"><span data-stu-id="1b076-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="1b076-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="1b076-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2118">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2118">Checksum</span></span>

<span data-ttu-id="1b076-2119">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2120">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2120">Definition</span></span>

<span data-ttu-id="1b076-2121">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2122">La función Func_iban encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2123">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2124">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2124">Keywords</span></span>

<span data-ttu-id="1b076-2125">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1b076-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="1b076-2126">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="1b076-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2127">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="1b076-2128">IPv4:</span><span class="sxs-lookup"><span data-stu-id="1b076-2128">IPv4:</span></span>
<span data-ttu-id="1b076-2129">Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="1b076-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="1b076-2130">IPv6:</span><span class="sxs-lookup"><span data-stu-id="1b076-2130">IPv6:</span></span>
<span data-ttu-id="1b076-2131"> Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)</span><span class="sxs-lookup"><span data-stu-id="1b076-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2132">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2133">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2133">Checksum</span></span>

<span data-ttu-id="1b076-2134">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2135">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2135">Definition</span></span>

<span data-ttu-id="1b076-2136">Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2137">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2138">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="1b076-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="1b076-2139">Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2140">La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2141">Se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="1b076-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="1b076-2142">Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2143">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2144">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="1b076-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2145">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="1b076-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="1b076-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="1b076-2147">IP (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="1b076-2148">dirección IP
</span><span class="sxs-lookup"><span data-stu-id="1b076-2148">ip address</span></span> 
- <span data-ttu-id="1b076-2149">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="1b076-2149">ip addresses</span></span>
- <span data-ttu-id="1b076-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="1b076-2150">internet protocol</span></span>
- <span data-ttu-id="1b076-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="1b076-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="1b076-2152">Clasificación internacional de enfermedades (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="1b076-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2153">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2153">Format</span></span>

<span data-ttu-id="1b076-2154">Diccionario</span><span class="sxs-lookup"><span data-stu-id="1b076-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2155">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2155">Pattern</span></span>

<span data-ttu-id="1b076-2156">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2157">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2157">Checksum</span></span>

<span data-ttu-id="1b076-2158">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2159">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2159">Definition</span></span>

<span data-ttu-id="1b076-2160">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2161">Se ha encontrado una palabra clave de Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="1b076-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="1b076-2162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2162">Keywords</span></span>

<span data-ttu-id="1b076-p135">Cualquiera de los términos del diccionario de palabra clave Dictionary_icd_10_cm, que se basa en la [clasificación internacional de enfermedades, revisión décima, modificación ensayos (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo sólo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="1b076-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="1b076-2165">Clasificación internacional de enfermedades (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="1b076-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2166">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2166">Format</span></span>

<span data-ttu-id="1b076-2167">Diccionario</span><span class="sxs-lookup"><span data-stu-id="1b076-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2168">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2168">Pattern</span></span>

<span data-ttu-id="1b076-2169">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2170">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2170">Checksum</span></span>

<span data-ttu-id="1b076-2171">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2172">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2172">Definition</span></span>

<span data-ttu-id="1b076-2173">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2174">Se ha encontrado una palabra clave de Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="1b076-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2175">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2175">Keywords</span></span>

<span data-ttu-id="1b076-p136">Cualquiera de los términos del diccionario de palabra clave Dictionary_icd_9_cm, que se basa en la [clasificación internacional de enfermedades, revisión del noveno, modificación ensayos (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo sólo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="1b076-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="1b076-2178">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="1b076-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2179">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2179">Format</span></span>

<span data-ttu-id="1b076-2180">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="1b076-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="1b076-2181">Siete dígitos seguidos por 1 o 2 letras </span><span class="sxs-lookup"><span data-stu-id="1b076-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="1b076-2182">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="1b076-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="1b076-2183">Siete dígitos seguidos por dos letras</span><span class="sxs-lookup"><span data-stu-id="1b076-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2184">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2184">Pattern</span></span>

<span data-ttu-id="1b076-2185">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="1b076-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="1b076-2186">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2186">Seven digits</span></span> 
- <span data-ttu-id="1b076-2187">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="1b076-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="1b076-2188">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="1b076-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="1b076-2189">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2189">Seven digits</span></span> 
- <span data-ttu-id="1b076-2190">Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético </span><span class="sxs-lookup"><span data-stu-id="1b076-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="1b076-2191">La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2192">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2192">Checksum</span></span>

<span data-ttu-id="1b076-2193">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2194">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2194">Definition</span></span>

<span data-ttu-id="1b076-2195">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2196">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2197">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-2197">One of the following is true:</span></span>
    - <span data-ttu-id="1b076-2198">Se encuentra una palabra clave de Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="1b076-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="1b076-2199">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="1b076-2200">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2200">The checksum passes.</span></span>

<span data-ttu-id="1b076-2201">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2202">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2203">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2204">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="1b076-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="1b076-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="1b076-2206">Número de servicio público personal 
</span><span class="sxs-lookup"><span data-stu-id="1b076-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="1b076-2207">Número de PPS
</span><span class="sxs-lookup"><span data-stu-id="1b076-2207">PPS Number</span></span> 
- <span data-ttu-id="1b076-2208">Núm. PPS
</span><span class="sxs-lookup"><span data-stu-id="1b076-2208">PPS Num</span></span> 
- <span data-ttu-id="1b076-2209">N.º PPS
</span><span class="sxs-lookup"><span data-stu-id="1b076-2209">PPS No.</span></span> 
- <span data-ttu-id="1b076-2210">N.ro PPS
</span><span class="sxs-lookup"><span data-stu-id="1b076-2210">PPS #</span></span> 
- <span data-ttu-id="1b076-2211">PPS #</span><span class="sxs-lookup"><span data-stu-id="1b076-2211">PPS#</span></span> 
- <span data-ttu-id="1b076-2212">NPPS
</span><span class="sxs-lookup"><span data-stu-id="1b076-2212">PPSN</span></span> 
- <span data-ttu-id="1b076-2213">Tarjeta de servicios públicos
</span><span class="sxs-lookup"><span data-stu-id="1b076-2213">Public Services Card</span></span> 
- <span data-ttu-id="1b076-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="1b076-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="1b076-p137">Uimh. PSP
</span><span class="sxs-lookup"><span data-stu-id="1b076-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="1b076-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="1b076-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="1b076-2218">Número de cuenta bancaria de Israel</span><span class="sxs-lookup"><span data-stu-id="1b076-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2219">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2219">Format</span></span>

<span data-ttu-id="1b076-2220">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2221">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2221">Pattern</span></span>

<span data-ttu-id="1b076-2222">Con formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-2222">Formatted:</span></span>
- <span data-ttu-id="1b076-2223">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2223">Two digits</span></span> 
- <span data-ttu-id="1b076-2224">Guion</span><span class="sxs-lookup"><span data-stu-id="1b076-2224">A dash</span></span> 
- <span data-ttu-id="1b076-2225">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2225">Three digits</span></span> 
- <span data-ttu-id="1b076-2226">Guion</span><span class="sxs-lookup"><span data-stu-id="1b076-2226">A dash</span></span> 
- <span data-ttu-id="1b076-2227">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2227">Eight digits</span></span>

<span data-ttu-id="1b076-2228">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-2228">Unformatted:</span></span>
- <span data-ttu-id="1b076-2229">	13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2230">Checksum</span></span>

<span data-ttu-id="1b076-2231">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2232">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2232">Definition</span></span>

<span data-ttu-id="1b076-2233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2234">La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2235">Se encuentra una palabra clave de Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="1b076-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="1b076-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2238">Bank Account Number</span></span> 
- <span data-ttu-id="1b076-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="1b076-2239">Bank Account</span></span> 
- <span data-ttu-id="1b076-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2240">Account Number</span></span> 
- <span data-ttu-id="1b076-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="1b076-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="1b076-2242">Identificación nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="1b076-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2243">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2243">Format</span></span>

<span data-ttu-id="1b076-2244">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2245">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2245">Pattern</span></span>

<span data-ttu-id="1b076-2246">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2247">Checksum</span></span>

<span data-ttu-id="1b076-2248">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2249">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2249">Definition</span></span>

<span data-ttu-id="1b076-2250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2251">La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2252">Se encuentra una palabra clave de Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="1b076-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="1b076-2253">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2254">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="1b076-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="1b076-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="1b076-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="1b076-2256">מספר זהות</span></span> 
- <span data-ttu-id="1b076-2257">National ID Number</span><span class="sxs-lookup"><span data-stu-id="1b076-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="1b076-2258">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="1b076-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2259">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2259">Format</span></span>

<span data-ttu-id="1b076-2260">Una combinación de 10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2261">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2261">Pattern</span></span>

- <span data-ttu-id="1b076-2262">Una combinación de 10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="1b076-2263">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2264">La letra "A" o "V" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2265">Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado</span><span class="sxs-lookup"><span data-stu-id="1b076-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="1b076-2266">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2267">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2267">Checksum</span></span>

<span data-ttu-id="1b076-2268">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2269">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2269">Definition</span></span>

<span data-ttu-id="1b076-2270">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2271">La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2272">Se encuentra una palabra clave de Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2273">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="1b076-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="1b076-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="1b076-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="1b076-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="1b076-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="1b076-2277">Número de cuenta bancaria de Japón</span><span class="sxs-lookup"><span data-stu-id="1b076-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2278">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2278">Format</span></span>

<span data-ttu-id="1b076-2279">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2280">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2280">Pattern</span></span>

<span data-ttu-id="1b076-2281">Número de cuenta bancaria:</span><span class="sxs-lookup"><span data-stu-id="1b076-2281">Bank account number:</span></span>
- <span data-ttu-id="1b076-2282">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2282">Seven or eight digits</span></span>
- <span data-ttu-id="1b076-2283">Código de sucursal del banco:</span><span class="sxs-lookup"><span data-stu-id="1b076-2283">Bank account branch code:</span></span>
- <span data-ttu-id="1b076-2284">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2284">Four digits</span></span> 
- <span data-ttu-id="1b076-2285">Un espacio o un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="1b076-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="1b076-2286">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2286">Three digits</span></span>

<span data-ttu-id="1b076-2287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2287">Checksum</span></span>

<span data-ttu-id="1b076-2288">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2289">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2289">Definition</span></span>

<span data-ttu-id="1b076-2290">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2291">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2292">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="1b076-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="1b076-2293">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-2293">One of the following is true:</span></span>
- <span data-ttu-id="1b076-2294">La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2295">Se encuentra una palabra clave de Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="1b076-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="1b076-2296">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2297">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2298">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="1b076-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2299">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="1b076-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="1b076-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="1b076-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2301">Checking Account Number</span></span> 
- <span data-ttu-id="1b076-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="1b076-2302">Checking Account</span></span> 
- <span data-ttu-id="1b076-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2303">Checking Account #</span></span> 
- <span data-ttu-id="1b076-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="1b076-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2305">Checking Acct #</span></span> 
- <span data-ttu-id="1b076-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="1b076-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2307">Checking Account No.</span></span> 
- <span data-ttu-id="1b076-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2308">Bank Account Number</span></span> 
- <span data-ttu-id="1b076-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="1b076-2309">Bank Account</span></span> 
- <span data-ttu-id="1b076-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2310">Bank Account #</span></span> 
- <span data-ttu-id="1b076-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="1b076-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2312">Bank Acct #</span></span> 
- <span data-ttu-id="1b076-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="1b076-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2314">Bank Account No.</span></span> 
- <span data-ttu-id="1b076-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2315">Savings Account Number</span></span> 
- <span data-ttu-id="1b076-2316">Cuenta de ahorro</span><span class="sxs-lookup"><span data-stu-id="1b076-2316">Savings Account</span></span> 
- <span data-ttu-id="1b076-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2317">Savings Account #</span></span> 
- <span data-ttu-id="1b076-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="1b076-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2319">Savings Acct #</span></span> 
- <span data-ttu-id="1b076-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="1b076-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2321">Savings Account No.</span></span> 
- <span data-ttu-id="1b076-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2322">Debit Account Number</span></span> 
- <span data-ttu-id="1b076-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="1b076-2323">Debit Account</span></span> 
- <span data-ttu-id="1b076-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2324">Debit Account #</span></span> 
- <span data-ttu-id="1b076-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="1b076-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2326">Debit Acct #</span></span> 
- <span data-ttu-id="1b076-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="1b076-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2328">Debit Account No.</span></span> 
- <span data-ttu-id="1b076-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="1b076-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="1b076-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="1b076-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="1b076-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="1b076-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="1b076-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="1b076-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="1b076-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="1b076-2333">口座番号の確認</span></span> 
- <span data-ttu-id="1b076-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="1b076-2334">銀行口座番号</span></span> 
- <span data-ttu-id="1b076-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="1b076-2335">銀行口座</span></span> 
- <span data-ttu-id="1b076-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2336">銀行口座＃</span></span> 
- <span data-ttu-id="1b076-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="1b076-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="1b076-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="1b076-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="1b076-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="1b076-2340">銀行口座番号</span></span>
- <span data-ttu-id="1b076-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="1b076-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="1b076-2342">預金口座</span></span> 
- <span data-ttu-id="1b076-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="1b076-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="1b076-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="1b076-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="1b076-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="1b076-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="1b076-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="1b076-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="1b076-2349">口座番号</span></span> 
- <span data-ttu-id="1b076-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2350">口座番号＃</span></span> 
- <span data-ttu-id="1b076-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="1b076-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="1b076-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="1b076-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="1b076-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="1b076-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="1b076-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="1b076-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="1b076-2357">Número de licencia de conductor de Japón</span><span class="sxs-lookup"><span data-stu-id="1b076-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2358">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2358">Format</span></span>

<span data-ttu-id="1b076-2359">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2360">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2360">Pattern</span></span>

<span data-ttu-id="1b076-2361">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2362">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2362">Checksum</span></span>

<span data-ttu-id="1b076-2363">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2364">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2364">Definition</span></span>

<span data-ttu-id="1b076-2365">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2366">La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2367">Se encuentra una palabra clave de Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2368">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="1b076-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="1b076-2370">dl#</span><span class="sxs-lookup"><span data-stu-id="1b076-2370">dl#</span></span> 
- <span data-ttu-id="1b076-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="1b076-2371">DL＃</span></span> 
- <span data-ttu-id="1b076-2372">dls#</span><span class="sxs-lookup"><span data-stu-id="1b076-2372">dls#</span></span> 
- <span data-ttu-id="1b076-2373">LISTAS DE DISTRIBUCIÓN #</span><span class="sxs-lookup"><span data-stu-id="1b076-2373">DLS＃</span></span> 
- <span data-ttu-id="1b076-2374">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="1b076-2374">driver license</span></span> 
- <span data-ttu-id="1b076-2375">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="1b076-2375">driver licenses</span></span> 
- <span data-ttu-id="1b076-2376">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-2376">drivers license</span></span> 
- <span data-ttu-id="1b076-2377">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="1b076-2377">driver's license</span></span> 
- <span data-ttu-id="1b076-2378">permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-2378">drivers licenses</span></span> 
- <span data-ttu-id="1b076-2379">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="1b076-2379">driver's licenses</span></span> 
- <span data-ttu-id="1b076-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-2380">driving licence</span></span> 
- <span data-ttu-id="1b076-2381">lic#</span><span class="sxs-lookup"><span data-stu-id="1b076-2381">lic#</span></span> 
- <span data-ttu-id="1b076-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="1b076-2382">LIC＃</span></span> 
- <span data-ttu-id="1b076-2383">lics#</span><span class="sxs-lookup"><span data-stu-id="1b076-2383">lics#</span></span> 
- <span data-ttu-id="1b076-2384">identificador de estado</span><span class="sxs-lookup"><span data-stu-id="1b076-2384">state id</span></span> 
- <span data-ttu-id="1b076-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="1b076-2385">state identification</span></span> 
- <span data-ttu-id="1b076-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2386">state identification number</span></span> 
- <span data-ttu-id="1b076-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2387">低所得国＃</span></span> 
- <span data-ttu-id="1b076-2388">免許証</span><span class="sxs-lookup"><span data-stu-id="1b076-2388">免許証</span></span> 
- <span data-ttu-id="1b076-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="1b076-2389">状態ID</span></span>
- <span data-ttu-id="1b076-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="1b076-2390">状態の識別</span></span> 
- <span data-ttu-id="1b076-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2391">状態の識別番号</span></span> 
- <span data-ttu-id="1b076-2392">運転免許</span><span class="sxs-lookup"><span data-stu-id="1b076-2392">運転免許</span></span> 
- <span data-ttu-id="1b076-2393">運転免許証</span><span class="sxs-lookup"><span data-stu-id="1b076-2393">運転免許証</span></span> 
- <span data-ttu-id="1b076-2394">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="1b076-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="1b076-2395">Número de pasaporte de Japón</span><span class="sxs-lookup"><span data-stu-id="1b076-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2396">Format</span></span>

<span data-ttu-id="1b076-2397">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2398">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2398">Pattern</span></span>

<span data-ttu-id="1b076-2399">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2400">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2400">Checksum</span></span>

<span data-ttu-id="1b076-2401">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2402">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2402">Definition</span></span>

<span data-ttu-id="1b076-2403">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2404">La función Func_jp_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2405">Se encuentra una palabra clave de Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="1b076-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2406">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="1b076-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="1b076-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="1b076-2408">パスポート</span></span> 
- <span data-ttu-id="1b076-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2409">パスポート番号</span></span> 
- <span data-ttu-id="1b076-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="1b076-2410">パスポートのNum</span></span> 
- <span data-ttu-id="1b076-2411">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="1b076-2412">Número de registro de residente de Japón</span><span class="sxs-lookup"><span data-stu-id="1b076-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2413">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2413">Format</span></span>

<span data-ttu-id="1b076-2414">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2415">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2415">Pattern</span></span>

<span data-ttu-id="1b076-2416">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2417">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2417">Checksum</span></span>

<span data-ttu-id="1b076-2418">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2419">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2419">Definition</span></span>

<span data-ttu-id="1b076-2420">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2421">La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2422">Se encuentra una palabra clave de Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2423">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="1b076-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="1b076-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="1b076-2425">Resident Registration Number</span></span>
- <span data-ttu-id="1b076-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2426">Resident Register Number</span></span> 
- <span data-ttu-id="1b076-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="1b076-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="1b076-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2429">Resident Register No.</span></span> 
- <span data-ttu-id="1b076-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="1b076-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="1b076-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="1b076-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="1b076-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="1b076-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="1b076-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="1b076-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="1b076-2436">Número de Seguridad Social de Japón (SIN)</span><span class="sxs-lookup"><span data-stu-id="1b076-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2437">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2437">Format</span></span>

<span data-ttu-id="1b076-2438">De 7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2439">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2439">Pattern</span></span>

<span data-ttu-id="1b076-2440">7-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2440">7-12 digits:</span></span>
- <span data-ttu-id="1b076-2441">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2441">Four digits</span></span> 
- <span data-ttu-id="1b076-2442">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="1b076-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="1b076-2443">Seis dígitos o</span><span class="sxs-lookup"><span data-stu-id="1b076-2443">Six digits OR</span></span>
- <span data-ttu-id="1b076-2444">De 7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2445">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2445">Checksum</span></span>

<span data-ttu-id="1b076-2446">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2447">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2447">Definition</span></span>

<span data-ttu-id="1b076-2448">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2449">La función Func_jp_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2450">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="1b076-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="1b076-2451">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2452">La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2453">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="1b076-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2454">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="1b076-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="1b076-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="1b076-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="1b076-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="1b076-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="1b076-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="1b076-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="1b076-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="1b076-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="1b076-2461">Número de la tarjeta de identificación de Malasia</span><span class="sxs-lookup"><span data-stu-id="1b076-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2462">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2462">Format</span></span>

<span data-ttu-id="1b076-2463">12 dígitos que contienen guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="1b076-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2464">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2464">Pattern</span></span>

<span data-ttu-id="1b076-2465">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2465">12 digits:</span></span>
- <span data-ttu-id="1b076-2466">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="1b076-2467">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2467">A dash (optional)</span></span> 
- <span data-ttu-id="1b076-2468">Código de dos letras del lugar de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="1b076-2469">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2469">A dash (optional)</span></span> 
- <span data-ttu-id="1b076-2470">Tres dígitos aleatorios </span><span class="sxs-lookup"><span data-stu-id="1b076-2470">Three random digits</span></span> 
- <span data-ttu-id="1b076-2471">Código de género de un dígito</span><span class="sxs-lookup"><span data-stu-id="1b076-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2472">Checksum</span></span>

<span data-ttu-id="1b076-2473">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2474">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2474">Definition</span></span>

<span data-ttu-id="1b076-2475">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2476">La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2477">Se encuentra una palabra clave de Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="1b076-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="1b076-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="1b076-2480">MyKad</span></span> 
- <span data-ttu-id="1b076-2481">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="1b076-2481">Identity Card</span></span> 
- <span data-ttu-id="1b076-2482">Tarjeta de Id.</span><span class="sxs-lookup"><span data-stu-id="1b076-2482">ID Card</span></span> 
- <span data-ttu-id="1b076-2483">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-2483">Identification Card</span></span> 
- <span data-ttu-id="1b076-2484">Tarjeta de solicitud digital
</span><span class="sxs-lookup"><span data-stu-id="1b076-2484">Digital Application Card</span></span> 
- <span data-ttu-id="1b076-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="1b076-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="1b076-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="1b076-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="1b076-2487">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="1b076-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2488">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2488">Format</span></span>

<span data-ttu-id="1b076-2489">8 o 9 dígitos que contienen espacios opcionales</span><span class="sxs-lookup"><span data-stu-id="1b076-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2490">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2490">Pattern</span></span>

<span data-ttu-id="1b076-2491">8 o 9 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2491">8-9 digits:</span></span>
- <span data-ttu-id="1b076-2492">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2492">Three digits</span></span> 
- <span data-ttu-id="1b076-2493">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2493">A space (optional)</span></span> 
- <span data-ttu-id="1b076-2494">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2494">Three digits</span></span> 
- <span data-ttu-id="1b076-2495">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="1b076-2495">A space (optional)</span></span> 
- <span data-ttu-id="1b076-2496">2 o 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2497">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2497">Checksum</span></span>

<span data-ttu-id="1b076-2498">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2499">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2499">Definition</span></span>

<span data-ttu-id="1b076-2500">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2501">La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2502">Se encuentra una palabra clave de Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="1b076-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="1b076-2503">La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="1b076-2504">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2505">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="1b076-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="1b076-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="1b076-2507">Número de servicio de ciudadanía
</span><span class="sxs-lookup"><span data-stu-id="1b076-2507">Citizen service number</span></span> 
- <span data-ttu-id="1b076-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="1b076-2508">BSN</span></span> 
- <span data-ttu-id="1b076-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="1b076-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-2510">Sofinummer</span></span> 
- <span data-ttu-id="1b076-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="1b076-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="1b076-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="1b076-2513">Número de Ministerio de salud de Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="1b076-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2514">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2514">Format</span></span>

<span data-ttu-id="1b076-2515">Tres letras, un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2516">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2516">Pattern</span></span>

<span data-ttu-id="1b076-2517">Tres letras (no distinguir mayúsculas de minúsculas) un cuatro dígitos (opcional) espacio</span><span class="sxs-lookup"><span data-stu-id="1b076-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2518">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2518">Checksum</span></span>

<span data-ttu-id="1b076-2519">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2520">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2520">Definition</span></span>

<span data-ttu-id="1b076-2521">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2522">La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2523">Se encuentra una palabra clave de Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="1b076-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="1b076-2524">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2524">The checksum passes.</span></span>

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

<span data-ttu-id="1b076-2525">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2525">Keywords</span></span>

<span data-ttu-id="1b076-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="1b076-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="1b076-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="1b076-2527">NHI</span></span> 
- <span data-ttu-id="1b076-2528">Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="1b076-2528">New Zealand</span></span> 
- <span data-ttu-id="1b076-2529">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="1b076-2529">Health</span></span> 
- <span data-ttu-id="1b076-2530">tratamiento
</span><span class="sxs-lookup"><span data-stu-id="1b076-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="1b076-2531">Número de identificación de Noruega</span><span class="sxs-lookup"><span data-stu-id="1b076-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2532">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2532">Format</span></span>

<span data-ttu-id="1b076-2533">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2534">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2534">Pattern</span></span>

<span data-ttu-id="1b076-2535">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2535">11 digits:</span></span>
- <span data-ttu-id="1b076-2536">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="1b076-2537">Número individual de tres dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="1b076-2538">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="1b076-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2539">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2539">Checksum</span></span>

<span data-ttu-id="1b076-2540">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2541">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2541">Definition</span></span>

<span data-ttu-id="1b076-2542">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2543">La función Func_norway_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2544">Se encuentra una palabra clave de Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="1b076-2545">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2545">The checksum passes.</span></span>
- <span data-ttu-id="1b076-2546">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2547">La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2548">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2549">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="1b076-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="1b076-2551">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="1b076-2551">Personal identification number</span></span>
- <span data-ttu-id="1b076-2552">Número de id. noruego</span><span class="sxs-lookup"><span data-stu-id="1b076-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="1b076-2553">Número de id.</span><span class="sxs-lookup"><span data-stu-id="1b076-2553">ID Number</span></span>
- <span data-ttu-id="1b076-2554">Identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-2554">Identification</span></span>
- <span data-ttu-id="1b076-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-2555">Personnummer</span></span>
- <span data-ttu-id="1b076-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="1b076-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="1b076-2557">Número de id. universal unificado de Filipinas</span><span class="sxs-lookup"><span data-stu-id="1b076-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2558">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2558">Format</span></span>

<span data-ttu-id="1b076-2559">12 dígitos separados por guiones</span><span class="sxs-lookup"><span data-stu-id="1b076-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2560">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2560">Pattern</span></span>

<span data-ttu-id="1b076-2561">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2561">12 digits:</span></span>
- <span data-ttu-id="1b076-2562">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2562">Four digits</span></span> 
- <span data-ttu-id="1b076-2563">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-2563">A hyphen</span></span> 
- <span data-ttu-id="1b076-2564">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2564">Seven digits</span></span> 
- <span data-ttu-id="1b076-2565">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-2565">A hyphen</span></span> 
- <span data-ttu-id="1b076-2566">Un dígito</span><span class="sxs-lookup"><span data-stu-id="1b076-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2567">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2567">Checksum</span></span>

<span data-ttu-id="1b076-2568">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2569">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2569">Definition</span></span>

<span data-ttu-id="1b076-2570">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2571">La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2572">Se encuentra una palabra clave de Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="1b076-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2573">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="1b076-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="1b076-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="1b076-2575">Id. universal unificado
</span><span class="sxs-lookup"><span data-stu-id="1b076-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="1b076-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="1b076-2576">UMID</span></span> 
- <span data-ttu-id="1b076-2577">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="1b076-2577">Identity Card</span></span> 
- <span data-ttu-id="1b076-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="1b076-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="1b076-2579">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="1b076-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2580">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2580">Format</span></span>

<span data-ttu-id="1b076-2581">Tres letras y seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2582">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2582">Pattern</span></span>

<span data-ttu-id="1b076-2583">Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2584">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2584">Checksum</span></span>

<span data-ttu-id="1b076-2585">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2586">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2586">Definition</span></span>

<span data-ttu-id="1b076-p138">Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la función Func_polish_national_id busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_polish_national_id_passport_number. Pasa la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2590">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="1b076-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="1b076-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="1b076-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="1b076-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="1b076-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="1b076-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="1b076-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="1b076-2596">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="1b076-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2597">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2597">Format</span></span>

<span data-ttu-id="1b076-2598">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2599">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2599">Pattern</span></span>

<span data-ttu-id="1b076-2600">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2601">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2601">Checksum</span></span>

<span data-ttu-id="1b076-2602">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2603">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2603">Definition</span></span>

<span data-ttu-id="1b076-2604">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2605">La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2606">Se encuentra una palabra clave de Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="1b076-2607">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2608">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="1b076-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="1b076-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="1b076-2610">Nr PESEL</span></span>
- <span data-ttu-id="1b076-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="1b076-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="1b076-2612">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="1b076-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2613">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2613">Format</span></span>

<span data-ttu-id="1b076-2614">Dos letras y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2615">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2615">Pattern</span></span>

<span data-ttu-id="1b076-2616">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2617">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2617">Checksum</span></span>

<span data-ttu-id="1b076-2618">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2619">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2619">Definition</span></span>

<span data-ttu-id="1b076-2620">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2621">La función Func_polish_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2622">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="1b076-2623">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2624">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="1b076-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="1b076-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="1b076-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="1b076-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="1b076-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="1b076-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="1b076-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="1b076-2630">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="1b076-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2631">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2631">Format</span></span>

<span data-ttu-id="1b076-2632">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2633">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2633">Pattern</span></span>

<span data-ttu-id="1b076-2634">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2635">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2635">Checksum</span></span>

<span data-ttu-id="1b076-2636">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2637">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2637">Definition</span></span>

<span data-ttu-id="1b076-2638">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2639">La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2640">Se encuentra una palabra clave de Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="1b076-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2641">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="1b076-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="1b076-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="1b076-2643">Tarjeta del ciudadano</span><span class="sxs-lookup"><span data-stu-id="1b076-2643">Citizen Card</span></span>
- <span data-ttu-id="1b076-2644">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="1b076-2644">National ID Card</span></span>
- <span data-ttu-id="1b076-2645">CC</span><span class="sxs-lookup"><span data-stu-id="1b076-2645">CC</span></span>
- <span data-ttu-id="1b076-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="1b076-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="1b076-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="1b076-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="1b076-2648">Identificación nacional de Arabia Saudí</span><span class="sxs-lookup"><span data-stu-id="1b076-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2649">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2649">Format</span></span>

<span data-ttu-id="1b076-2650">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2651">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2651">Pattern</span></span>

<span data-ttu-id="1b076-2652">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2653">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2653">Checksum</span></span>

<span data-ttu-id="1b076-2654">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2655">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2655">Definition</span></span>

<span data-ttu-id="1b076-2656">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2657">La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2658">Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="1b076-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2659">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="1b076-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="1b076-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="1b076-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="1b076-2661">Identification Card</span></span> 
- <span data-ttu-id="1b076-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2662">I card number</span></span> 
- <span data-ttu-id="1b076-2663">número de Id.</span><span class="sxs-lookup"><span data-stu-id="1b076-2663">ID number</span></span> 
- <span data-ttu-id="1b076-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="1b076-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="1b076-2665">Número de tarjeta de identidad de registro nacional (NRIC) de Singapur</span><span class="sxs-lookup"><span data-stu-id="1b076-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2666">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2666">Format</span></span>

<span data-ttu-id="1b076-2667">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2668">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2668">Pattern</span></span>

- <span data-ttu-id="1b076-2669">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="1b076-2670">La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="1b076-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2671">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2671">Seven digits</span></span> 
- <span data-ttu-id="1b076-2672">Un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="1b076-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2673">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2673">Checksum</span></span>

<span data-ttu-id="1b076-2674">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2675">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2675">Definition</span></span>

<span data-ttu-id="1b076-2676">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2677">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2678">Se encuentra una palabra clave de Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="1b076-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="1b076-2679">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2679">The checksum passes.</span></span>

<span data-ttu-id="1b076-2680">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2681">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2682">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2683">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="1b076-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="1b076-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="1b076-2685">Tarjeta de identidad de registro nacional
</span><span class="sxs-lookup"><span data-stu-id="1b076-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="1b076-2686">Número de tarjeta de identidad
</span><span class="sxs-lookup"><span data-stu-id="1b076-2686">Identity Card Number</span></span> 
- <span data-ttu-id="1b076-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="1b076-2687">NRIC</span></span> 
- <span data-ttu-id="1b076-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="1b076-2688">IC</span></span> 
- <span data-ttu-id="1b076-2689">Número de identificación de extranjeros
</span><span class="sxs-lookup"><span data-stu-id="1b076-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="1b076-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="1b076-2690">FIN</span></span> 
- <span data-ttu-id="1b076-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="1b076-2691">身份证</span></span> 
- <span data-ttu-id="1b076-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="1b076-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="1b076-2693">Número de identificación de Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="1b076-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2694">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2694">Format</span></span>

<span data-ttu-id="1b076-2695">13 dígitos que pueden contener espacios</span><span class="sxs-lookup"><span data-stu-id="1b076-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2696">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2696">Pattern</span></span>

<span data-ttu-id="1b076-2697">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2697">13 digits:</span></span>
- <span data-ttu-id="1b076-2698">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="1b076-2699">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2699">Four digits</span></span> 
- <span data-ttu-id="1b076-2700">Un indicador de ciudadanía de un solo dígito </span><span class="sxs-lookup"><span data-stu-id="1b076-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="1b076-2701">El dígito "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="1b076-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="1b076-2702">Un dígito que es un dígito de suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2703">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2703">Checksum</span></span>

<span data-ttu-id="1b076-2704">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2705">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2705">Definition</span></span>

<span data-ttu-id="1b076-2706">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2707">La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2708">Se encuentra una palabra clave de Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="1b076-2709">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2710">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="1b076-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="1b076-2712">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="1b076-2712">Identity card</span></span>
- <span data-ttu-id="1b076-2713">ID</span><span class="sxs-lookup"><span data-stu-id="1b076-2713">ID</span></span>
- <span data-ttu-id="1b076-2714">Identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="1b076-2715">Número de registro de residente de Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="1b076-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2716">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2716">Format</span></span>

<span data-ttu-id="1b076-2717">13 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="1b076-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2718">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2718">Pattern</span></span>

<span data-ttu-id="1b076-2719">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2719">13 digits:</span></span>
- <span data-ttu-id="1b076-2720">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="1b076-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="1b076-2721">Un guión </span><span class="sxs-lookup"><span data-stu-id="1b076-2721">A hyphen</span></span> 
- <span data-ttu-id="1b076-2722">Un dígito determinado por el siglo y el sexo </span><span class="sxs-lookup"><span data-stu-id="1b076-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="1b076-2723">Código de región de nacimiento de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="1b076-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="1b076-2724">Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos </span><span class="sxs-lookup"><span data-stu-id="1b076-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="1b076-2725">Un dígito de control.</span><span class="sxs-lookup"><span data-stu-id="1b076-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2726">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2726">Checksum</span></span>

<span data-ttu-id="1b076-2727">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2728">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2728">Definition</span></span>

<span data-ttu-id="1b076-2729">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2730">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2731">Se encuentra una palabra clave de Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="1b076-2732">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2732">The checksum passes.</span></span>

<span data-ttu-id="1b076-2733">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2734">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2735">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2736">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="1b076-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="1b076-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="1b076-2738">Tarjeta de id. nacional
</span><span class="sxs-lookup"><span data-stu-id="1b076-2738">National ID card</span></span> 
- <span data-ttu-id="1b076-2739">Número de registro de ciudadano
</span><span class="sxs-lookup"><span data-stu-id="1b076-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="1b076-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="1b076-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="1b076-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="1b076-2741">RRN</span></span> 
- <span data-ttu-id="1b076-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="1b076-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="1b076-2743">Número de seguridad social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="1b076-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2744">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2744">Format</span></span>

<span data-ttu-id="1b076-2745">11 o 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2746">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2746">Pattern</span></span>

<span data-ttu-id="1b076-2747">12 de 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2747">11-12 digits:</span></span>
- <span data-ttu-id="1b076-2748">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2748">Two digits</span></span> 
- <span data-ttu-id="1b076-2749">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="1b076-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="1b076-2750">7-8 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2750">7-8 digits</span></span> 
- <span data-ttu-id="1b076-2751">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="1b076-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="1b076-2752">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2753">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2753">Checksum</span></span>

<span data-ttu-id="1b076-2754">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2755">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2755">Definition</span></span>

<span data-ttu-id="1b076-2756">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2757">La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2758">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2759">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2759">Keywords</span></span>

<span data-ttu-id="1b076-2760">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1b076-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="1b076-2761">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="1b076-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2762">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2762">Format</span></span>

<span data-ttu-id="1b076-2763">10 o 12 dígitos y un delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="1b076-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2764">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2764">Pattern</span></span>

<span data-ttu-id="1b076-2765">10 o 12 dígitos y un delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="1b076-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="1b076-2766">2-4 dígitos (opcionales)</span><span class="sxs-lookup"><span data-stu-id="1b076-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="1b076-2767">Seis dígitos en fecha de formato AAMMDD</span><span class="sxs-lookup"><span data-stu-id="1b076-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="1b076-2768">Delimitador de "-" o "+" (opcional), más</span><span class="sxs-lookup"><span data-stu-id="1b076-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="1b076-2769">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2770">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2770">Checksum</span></span>

<span data-ttu-id="1b076-2771">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2772">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2772">Definition</span></span>

<span data-ttu-id="1b076-2773">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2774">La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2775">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2776">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2776">Keywords</span></span>

<span data-ttu-id="1b076-2777">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="1b076-2778">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="1b076-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2779">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2779">Format</span></span>

<span data-ttu-id="1b076-2780">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2781">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2781">Pattern</span></span>

<span data-ttu-id="1b076-2782">Ocho dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2783">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2783">Checksum</span></span>

<span data-ttu-id="1b076-2784">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2785">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2785">Definition</span></span>

<span data-ttu-id="1b076-2786">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2787">La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2788">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-2788">One of the following is true:</span></span>
    - <span data-ttu-id="1b076-2789">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="1b076-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="1b076-2790">Se encuentra una palabra clave de Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="1b076-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-2791">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="1b076-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="1b076-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="1b076-2793">visa requirements</span></span> 
- <span data-ttu-id="1b076-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="1b076-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="1b076-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="1b076-2795">Schengen visas</span></span> 
- <span data-ttu-id="1b076-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="1b076-2796">Schengen visa</span></span> 
- <span data-ttu-id="1b076-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="1b076-2797">Visa Processing</span></span> 
- <span data-ttu-id="1b076-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="1b076-2798">Visa Type</span></span> 
- <span data-ttu-id="1b076-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="1b076-2799">Single Entry</span></span> 
- <span data-ttu-id="1b076-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="1b076-2800">Multiple Entry</span></span> 
- <span data-ttu-id="1b076-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="1b076-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="1b076-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-2802">Keyword_passport</span></span>

- <span data-ttu-id="1b076-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="1b076-2803">Passport Number</span></span> 
- <span data-ttu-id="1b076-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="1b076-2804">Passport No</span></span> 
- <span data-ttu-id="1b076-2805">Passport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2805">Passport #</span></span> 
- <span data-ttu-id="1b076-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-2806">Passport#</span></span> 
- <span data-ttu-id="1b076-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="1b076-2807">PassportID</span></span> 
- <span data-ttu-id="1b076-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="1b076-2808">Passportno</span></span> 
- <span data-ttu-id="1b076-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-2809">passportnumber</span></span> 
- <span data-ttu-id="1b076-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="1b076-2810">パスポート</span></span> 
- <span data-ttu-id="1b076-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2811">パスポート番号</span></span> 
- <span data-ttu-id="1b076-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="1b076-2812">パスポートのNum</span></span> 
- <span data-ttu-id="1b076-2813">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2813">パスポート＃</span></span> 
- <span data-ttu-id="1b076-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="1b076-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="1b076-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="1b076-2815">Passeport n °</span></span> 
- <span data-ttu-id="1b076-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="1b076-2816">Passeport Non</span></span> 
- <span data-ttu-id="1b076-2817">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2817">Passeport #</span></span> 
- <span data-ttu-id="1b076-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-2818">Passeport#</span></span> 
- <span data-ttu-id="1b076-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="1b076-2819">PasseportNon</span></span> 
- <span data-ttu-id="1b076-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="1b076-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="1b076-2821">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="1b076-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2822">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2822">Format</span></span>

<span data-ttu-id="1b076-2823">Cuatro letras seguidas de 5 a 31 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2824">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2824">Pattern</span></span>

<span data-ttu-id="1b076-2825">Cuatro letras seguidas de 5-31 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="1b076-2826">Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2827">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="1b076-2827">An optional space</span></span> 
- <span data-ttu-id="1b076-2828">4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))</span><span class="sxs-lookup"><span data-stu-id="1b076-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="1b076-2829">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="1b076-2829">An optional space</span></span> 
- <span data-ttu-id="1b076-2830">1-3 letras o dígitos (el resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="1b076-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2831">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2831">Checksum</span></span>

<span data-ttu-id="1b076-2832">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2833">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2833">Definition</span></span>

<span data-ttu-id="1b076-2834">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2835">La expresión regular Regex_swift encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2836">Se encuentra una palabra clave de Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="1b076-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2837">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="1b076-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="1b076-2838">Keyword_swift</span></span>

- <span data-ttu-id="1b076-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="1b076-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="1b076-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="1b076-2840">iso 9362</span></span> 
- <span data-ttu-id="1b076-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="1b076-2841">iso9362</span></span> 
- <span data-ttu-id="1b076-2842">SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="1b076-2842">swift\#</span></span> 
- <span data-ttu-id="1b076-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="1b076-2843">swiftcode</span></span> 
- <span data-ttu-id="1b076-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-2844">swiftnumber</span></span> 
- <span data-ttu-id="1b076-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="1b076-2846">código SWIFT</span><span class="sxs-lookup"><span data-stu-id="1b076-2846">swift code</span></span> 
- <span data-ttu-id="1b076-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2847">swift number #</span></span> 
- <span data-ttu-id="1b076-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2848">swift routing number</span></span> 
- <span data-ttu-id="1b076-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="1b076-2849">bic number</span></span> 
- <span data-ttu-id="1b076-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="1b076-2850">bic code</span></span> 
- <span data-ttu-id="1b076-2851">BIC\#</span><span class="sxs-lookup"><span data-stu-id="1b076-2851">bic \#</span></span> 
- <span data-ttu-id="1b076-2852">BIC\#</span><span class="sxs-lookup"><span data-stu-id="1b076-2852">bic\#</span></span> 
- <span data-ttu-id="1b076-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="1b076-2853">bank identifier code</span></span> 
- <span data-ttu-id="1b076-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="1b076-2854">標準化9362</span></span> 
- <span data-ttu-id="1b076-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-2855">迅速＃</span></span> 
- <span data-ttu-id="1b076-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="1b076-2856">SWIFTコード</span></span> 
- <span data-ttu-id="1b076-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2857">SWIFT番号</span></span> 
- <span data-ttu-id="1b076-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="1b076-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-2859">BIC番号</span></span> 
- <span data-ttu-id="1b076-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="1b076-2860">BICコード</span></span> 
- <span data-ttu-id="1b076-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="1b076-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="1b076-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="1b076-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="1b076-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="1b076-2863">rapide \#</span></span> 
- <span data-ttu-id="1b076-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="1b076-2864">code SWIFT</span></span> 
- <span data-ttu-id="1b076-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="1b076-2865">le numéro de swift</span></span> 
- <span data-ttu-id="1b076-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="1b076-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="1b076-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="1b076-2867">le numéro BIC</span></span> 
- <span data-ttu-id="1b076-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="1b076-2868">\# BIC</span></span> 
- <span data-ttu-id="1b076-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="1b076-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="1b076-2870">Identificación nacional de Taiwán</span><span class="sxs-lookup"><span data-stu-id="1b076-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2871">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2871">Format</span></span>

<span data-ttu-id="1b076-2872">Una letra  seguida de nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2873">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2873">Pattern</span></span>

<span data-ttu-id="1b076-2874">Una letra seguida de nueve dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="1b076-2875">Una letra (en inglés, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2876">El dígito "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="1b076-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="1b076-2877">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2878">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2878">Checksum</span></span>

<span data-ttu-id="1b076-2879">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2880">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2880">Definition</span></span>

<span data-ttu-id="1b076-2881">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2882">La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2883">Se encuentra una palabra clave de Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="1b076-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="1b076-2884">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2885">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="1b076-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="1b076-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="1b076-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="1b076-2887">身份證字號</span></span> 
- <span data-ttu-id="1b076-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="1b076-2888">身份證</span></span> 
- <span data-ttu-id="1b076-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="1b076-2889">身份證號碼</span></span> 
- <span data-ttu-id="1b076-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="1b076-2890">身份證號</span></span> 
- <span data-ttu-id="1b076-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="1b076-2891">身分證字號</span></span> 
- <span data-ttu-id="1b076-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="1b076-2892">身分證</span></span> 
- <span data-ttu-id="1b076-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="1b076-2893">身分證號碼</span></span> 
- <span data-ttu-id="1b076-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="1b076-2894">身份證號</span></span> 
- <span data-ttu-id="1b076-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="1b076-2895">身分證統一編號</span></span> 
- <span data-ttu-id="1b076-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="1b076-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="1b076-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="1b076-2897">簽名</span></span> 
- <span data-ttu-id="1b076-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="1b076-2898">蓋章</span></span> 
- <span data-ttu-id="1b076-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="1b076-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="1b076-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="1b076-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="1b076-2901">Número de pasaporte de Taiwán</span><span class="sxs-lookup"><span data-stu-id="1b076-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2902">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2902">Format</span></span>

- <span data-ttu-id="1b076-2903">Número de pasaporte biométrica: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="1b076-2904">Número de cuenta de passport no biométrica: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2905">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2905">Pattern</span></span>
<span data-ttu-id="1b076-2906">Número de cuenta de passport biométrica:</span><span class="sxs-lookup"><span data-stu-id="1b076-2906">Biometric passport number:</span></span>
- <span data-ttu-id="1b076-2907">El dígito "3" </span><span class="sxs-lookup"><span data-stu-id="1b076-2907">The digit "3"</span></span> 
- <span data-ttu-id="1b076-2908">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2908">Eight digits</span></span>

<span data-ttu-id="1b076-2909">Número de cuenta de passport no biométrica:</span><span class="sxs-lookup"><span data-stu-id="1b076-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="1b076-2910">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2911">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2911">Checksum</span></span>

<span data-ttu-id="1b076-2912">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2913">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2913">Definition</span></span>

<span data-ttu-id="1b076-2914">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2915">La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2916">Se encuentra una palabra clave de Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="1b076-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2917">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="1b076-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="1b076-2919">Número de pasaporte ROC
</span><span class="sxs-lookup"><span data-stu-id="1b076-2919">ROC passport number</span></span> 
- <span data-ttu-id="1b076-2920">Número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="1b076-2920">Passport number</span></span> 
- <span data-ttu-id="1b076-2921">Cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="1b076-2921">Passport no</span></span> 
- <span data-ttu-id="1b076-2922">N.ro pasaporte
</span><span class="sxs-lookup"><span data-stu-id="1b076-2922">Passport Num</span></span> 
- <span data-ttu-id="1b076-2923">Passport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-2923">Passport #</span></span> 
- <span data-ttu-id="1b076-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="1b076-2924">护照</span></span> 
- <span data-ttu-id="1b076-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="1b076-2925">中華民國護照</span></span> 
- <span data-ttu-id="1b076-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="1b076-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="1b076-2927">Número de certificado de residente (ARC/TARC) de Taiwán</span><span class="sxs-lookup"><span data-stu-id="1b076-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2928">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2928">Format</span></span>

<span data-ttu-id="1b076-2929">10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2930">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2930">Pattern</span></span>

<span data-ttu-id="1b076-2931">10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2931">10 letters and digits:</span></span>
- <span data-ttu-id="1b076-2932">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="1b076-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="1b076-2933">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2934">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2934">Checksum</span></span>

<span data-ttu-id="1b076-2935">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2936">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2936">Definition</span></span>

<span data-ttu-id="1b076-2937">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2938">La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2939">Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="1b076-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2940">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="1b076-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="1b076-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="1b076-2942">Certificado de residente
</span><span class="sxs-lookup"><span data-stu-id="1b076-2942">Resident Certificate</span></span> 
- <span data-ttu-id="1b076-2943">Cert residente</span><span class="sxs-lookup"><span data-stu-id="1b076-2943">Resident Cert</span></span> 
- <span data-ttu-id="1b076-2944">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="1b076-2944">Resident Cert.</span></span> 
- <span data-ttu-id="1b076-2945">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-2945">Identification card</span></span> 
- <span data-ttu-id="1b076-2946">Certificado de residente extranjero
</span><span class="sxs-lookup"><span data-stu-id="1b076-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="1b076-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="1b076-2947">ARC</span></span> 
- <span data-ttu-id="1b076-2948">Certificado de residente en el área de Taiwán
</span><span class="sxs-lookup"><span data-stu-id="1b076-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="1b076-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="1b076-2949">TARC</span></span> 
- <span data-ttu-id="1b076-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="1b076-2950">居留證</span></span> 
- <span data-ttu-id="1b076-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="1b076-2951">外僑居留證</span></span> 
- <span data-ttu-id="1b076-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="1b076-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="1b076-p141">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="1b076-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2955">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2955">Format</span></span>

<span data-ttu-id="1b076-2956">Combinación de 18 letras y dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="1b076-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2957">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2957">Pattern</span></span>

<span data-ttu-id="1b076-2958">18 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-2958">18 letters and digits:</span></span>
- <span data-ttu-id="1b076-2959">Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="1b076-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="1b076-2960">Un dígito</span><span class="sxs-lookup"><span data-stu-id="1b076-2960">One digit</span></span> 
- <span data-ttu-id="1b076-2961">Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="1b076-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="1b076-2962">Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="1b076-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="1b076-2963">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2964">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2964">Checksum</span></span>

<span data-ttu-id="1b076-2965">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2966">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2966">Definition</span></span>

<span data-ttu-id="1b076-2967">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2968">La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2969">Se encuentra una palabra clave de Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="1b076-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="1b076-2970">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-2971">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="1b076-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="1b076-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="1b076-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="1b076-2973">DVLA</span></span> 
- <span data-ttu-id="1b076-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="1b076-2974">light vans</span></span> 
- <span data-ttu-id="1b076-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="1b076-2975">quadbikes</span></span> 
- <span data-ttu-id="1b076-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="1b076-2976">motor cars</span></span> 
- <span data-ttu-id="1b076-2977">125CC</span><span class="sxs-lookup"><span data-stu-id="1b076-2977">125cc</span></span> 
- <span data-ttu-id="1b076-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="1b076-2978">sidecar</span></span> 
- <span data-ttu-id="1b076-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="1b076-2979">tricycles</span></span> 
- <span data-ttu-id="1b076-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="1b076-2980">motorcycles</span></span> 
- <span data-ttu-id="1b076-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-2981">photocard licence</span></span> 
- <span data-ttu-id="1b076-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="1b076-2982">learner drivers</span></span> 
- <span data-ttu-id="1b076-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="1b076-2983">licence holder</span></span> 
- <span data-ttu-id="1b076-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="1b076-2984">licence holders</span></span> 
- <span data-ttu-id="1b076-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="1b076-2985">driving licences</span></span> 
- <span data-ttu-id="1b076-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="1b076-2986">driving licence</span></span> 
- <span data-ttu-id="1b076-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="1b076-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="1b076-p142">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="1b076-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-2990">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-2990">Format</span></span>

<span data-ttu-id="1b076-2991">Dos letras seguidas por entre 1 y 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-2992">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-2992">Pattern</span></span>

<span data-ttu-id="1b076-2993">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números</span><span class="sxs-lookup"><span data-stu-id="1b076-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-2994">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-2994">Checksum</span></span>

<span data-ttu-id="1b076-2995">No</span><span class="sxs-lookup"><span data-stu-id="1b076-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-2996">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-2996">Definition</span></span>

<span data-ttu-id="1b076-2997">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-2998">La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-2999">Se encuentra una palabra clave de Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="1b076-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-3000">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="1b076-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="1b076-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="1b076-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="1b076-3002">council nomination</span></span> 
- <span data-ttu-id="1b076-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="1b076-3003">nomination form</span></span> 
- <span data-ttu-id="1b076-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="1b076-3004">electoral register</span></span> 
- <span data-ttu-id="1b076-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="1b076-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="1b076-p143">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="1b076-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-3008">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3008">Format</span></span>

<span data-ttu-id="1b076-3009">De 10 a 17 dígitos separados por espacios</span><span class="sxs-lookup"><span data-stu-id="1b076-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-3010">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-3010">Pattern</span></span>

<span data-ttu-id="1b076-3011">10-17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1b076-3011">10-17 digits:</span></span>
- <span data-ttu-id="1b076-3012">3 o 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="1b076-3013">Un espacio</span><span class="sxs-lookup"><span data-stu-id="1b076-3013">A space</span></span> 
- <span data-ttu-id="1b076-3014">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3014">Three digits</span></span> 
- <span data-ttu-id="1b076-3015">Un espacio</span><span class="sxs-lookup"><span data-stu-id="1b076-3015">A space</span></span> 
- <span data-ttu-id="1b076-3016">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-3017">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-3017">Checksum</span></span>

<span data-ttu-id="1b076-3018">Sí</span><span class="sxs-lookup"><span data-stu-id="1b076-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-3019">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-3019">Definition</span></span>

<span data-ttu-id="1b076-3020">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3021">La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3022">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-3022">One of the following is true:</span></span>
    - <span data-ttu-id="1b076-3023">Se encuentra una palabra clave de Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="1b076-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="1b076-3024">Se encuentra una palabra clave de Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="1b076-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="1b076-3025">Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="1b076-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="1b076-3026">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1b076-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-3027">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="1b076-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="1b076-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="1b076-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="1b076-3029">national health service</span></span> 
- <span data-ttu-id="1b076-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="1b076-3030">nhs</span></span> 
- <span data-ttu-id="1b076-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="1b076-3031">health services authority</span></span> 
- <span data-ttu-id="1b076-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="1b076-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="1b076-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="1b076-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="1b076-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="1b076-3034">patient id</span></span> 
- <span data-ttu-id="1b076-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="1b076-3035">patient identification</span></span> 
- <span data-ttu-id="1b076-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="1b076-3036">patient no</span></span> 
- <span data-ttu-id="1b076-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="1b076-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="1b076-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="1b076-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="1b076-3039">DG</span><span class="sxs-lookup"><span data-stu-id="1b076-3039">GP</span></span> 
- <span data-ttu-id="1b076-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="1b076-3040">DOB</span></span> 
- <span data-ttu-id="1b076-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="1b076-3041">D.O.B</span></span> 
- <span data-ttu-id="1b076-3042">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="1b076-3042">Date of Birth</span></span> 
- <span data-ttu-id="1b076-3043">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="1b076-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="1b076-p144">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="1b076-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-3046">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3046">Format</span></span>

<span data-ttu-id="1b076-3047">los 7 caracteres o 9 separadas por espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="1b076-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-3048">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-3048">Pattern</span></span>

<span data-ttu-id="1b076-3049">Dos modelos posibles:</span><span class="sxs-lookup"><span data-stu-id="1b076-3049">Two possible patterns:</span></span>

- <span data-ttu-id="1b076-3050">Dos letras (NINOs válidos utilizar sólo determinados caracteres en este prefijo, que valida este patrón; no mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="1b076-3051">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3051">Six digits</span></span>
- <span data-ttu-id="1b076-3052">Puede ser 'A', 'B', 'C', o tenía ' (como el prefijo, sólo ciertos caracteres se permiten en el sufijo; no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1b076-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="1b076-3053">OR</span><span class="sxs-lookup"><span data-stu-id="1b076-3053">OR</span></span>

- <span data-ttu-id="1b076-3054">Dos letras</span><span class="sxs-lookup"><span data-stu-id="1b076-3054">Two letters</span></span>
- <span data-ttu-id="1b076-3055">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-3055">A space or dash</span></span>
- <span data-ttu-id="1b076-3056">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3056">Two digits</span></span>
- <span data-ttu-id="1b076-3057">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-3057">A space or dash</span></span>
- <span data-ttu-id="1b076-3058">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3058">Two digits</span></span>
- <span data-ttu-id="1b076-3059">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-3059">A space or dash</span></span>
- <span data-ttu-id="1b076-3060">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3060">Two digits</span></span>
- <span data-ttu-id="1b076-3061">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-3061">A space or dash</span></span>
- <span data-ttu-id="1b076-3062">Puede ser 'A', 'B', 'C', o tenía '</span><span class="sxs-lookup"><span data-stu-id="1b076-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-3063">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-3063">Checksum</span></span>

<span data-ttu-id="1b076-3064">No</span><span class="sxs-lookup"><span data-stu-id="1b076-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-3065">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-3065">Definition</span></span>

<span data-ttu-id="1b076-3066">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3067">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3068">Se encuentra una palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="1b076-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="1b076-3069">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3070">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3071">No se encuentra ninguna palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="1b076-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-3072">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="1b076-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="1b076-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="1b076-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3074">national insurance number</span></span> 
- <span data-ttu-id="1b076-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="1b076-3075">national insurance contributions</span></span> 
- <span data-ttu-id="1b076-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="1b076-3076">protection act</span></span> 
- <span data-ttu-id="1b076-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="1b076-3077">insurance</span></span> 
- <span data-ttu-id="1b076-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3078">social security number</span></span> 
- <span data-ttu-id="1b076-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="1b076-3079">insurance application</span></span> 
- <span data-ttu-id="1b076-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="1b076-3080">medical application</span></span> 
- <span data-ttu-id="1b076-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="1b076-3081">social insurance</span></span> 
- <span data-ttu-id="1b076-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="1b076-3082">medical attention</span></span> 
- <span data-ttu-id="1b076-3083">seguridad social</span><span class="sxs-lookup"><span data-stu-id="1b076-3083">social security</span></span> 
- <span data-ttu-id="1b076-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="1b076-3084">great britain</span></span> 
- <span data-ttu-id="1b076-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="1b076-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="1b076-p145">Número de pasaporte EE. UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="1b076-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-3088">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3088">Format</span></span>

<span data-ttu-id="1b076-3089">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-3090">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-3090">Pattern</span></span>

<span data-ttu-id="1b076-3091">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-3092">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-3092">Checksum</span></span>

<span data-ttu-id="1b076-3093">No</span><span class="sxs-lookup"><span data-stu-id="1b076-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-3094">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-3094">Definition</span></span>

<span data-ttu-id="1b076-3095">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3096">La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3097">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="1b076-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-3098">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="1b076-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="1b076-3099">Keyword_passport</span></span>

- <span data-ttu-id="1b076-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="1b076-3100">Passport Number</span></span> 
- <span data-ttu-id="1b076-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="1b076-3101">Passport No</span></span> 
- <span data-ttu-id="1b076-3102">Passport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3102">Passport #</span></span> 
- <span data-ttu-id="1b076-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3103">Passport#</span></span> 
- <span data-ttu-id="1b076-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="1b076-3104">PassportID</span></span> 
- <span data-ttu-id="1b076-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="1b076-3105">Passportno</span></span> 
- <span data-ttu-id="1b076-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="1b076-3106">passportnumber</span></span> 
- <span data-ttu-id="1b076-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="1b076-3107">パスポート</span></span> 
- <span data-ttu-id="1b076-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="1b076-3108">パスポート番号</span></span> 
- <span data-ttu-id="1b076-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="1b076-3109">パスポートのNum</span></span> 
- <span data-ttu-id="1b076-3110">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="1b076-3110">パスポート＃</span></span> 
- <span data-ttu-id="1b076-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="1b076-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="1b076-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="1b076-3112">Passeport n °</span></span> 
- <span data-ttu-id="1b076-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="1b076-3113">Passeport Non</span></span> 
- <span data-ttu-id="1b076-3114">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3114">Passeport #</span></span> 
- <span data-ttu-id="1b076-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3115">Passeport#</span></span> 
- <span data-ttu-id="1b076-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="1b076-3116">PasseportNon</span></span> 
- <span data-ttu-id="1b076-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="1b076-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="1b076-3118">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="1b076-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-3119">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3119">Format</span></span>

<span data-ttu-id="1b076-3120">Entre 8 y 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-3121">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-3121">Pattern</span></span>

<span data-ttu-id="1b076-3122">Entre 8 y 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="1b076-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-3123">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-3123">Checksum</span></span>

<span data-ttu-id="1b076-3124">No</span><span class="sxs-lookup"><span data-stu-id="1b076-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-3125">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-3125">Definition</span></span>

<span data-ttu-id="1b076-3126">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3127">La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3128">Se encuentra una palabra clave de Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="1b076-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b076-3129">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="1b076-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="1b076-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="1b076-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3131">Checking Account Number</span></span> 
- <span data-ttu-id="1b076-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="1b076-3132">Checking Account</span></span> 
- <span data-ttu-id="1b076-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3133">Checking Account #</span></span> 
- <span data-ttu-id="1b076-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="1b076-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3135">Checking Acct #</span></span> 
- <span data-ttu-id="1b076-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="1b076-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3137">Checking Account No.</span></span> 
- <span data-ttu-id="1b076-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3138">Bank Account Number</span></span> 
- <span data-ttu-id="1b076-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3139">Bank Account #</span></span> 
- <span data-ttu-id="1b076-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="1b076-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3141">Bank Acct #</span></span> 
- <span data-ttu-id="1b076-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="1b076-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3143">Bank Account No.</span></span> 
- <span data-ttu-id="1b076-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3144">Savings Account Number</span></span> 
- <span data-ttu-id="1b076-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3145">Savings Account.</span></span> 
- <span data-ttu-id="1b076-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3146">Savings Account #</span></span> 
- <span data-ttu-id="1b076-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="1b076-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3148">Savings Acct #</span></span> 
- <span data-ttu-id="1b076-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="1b076-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3150">Savings Account No.</span></span> 
- <span data-ttu-id="1b076-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3151">Debit Account Number</span></span> 
- <span data-ttu-id="1b076-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="1b076-3152">Debit Account</span></span> 
- <span data-ttu-id="1b076-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3153">Debit Account #</span></span> 
- <span data-ttu-id="1b076-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="1b076-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3155">Debit Acct #</span></span> 
- <span data-ttu-id="1b076-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="1b076-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="1b076-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="1b076-3158">Número de licencia de conductor de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="1b076-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="1b076-3159">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3159">Format</span></span>

<span data-ttu-id="1b076-3160">Depende del estado</span><span class="sxs-lookup"><span data-stu-id="1b076-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-3161">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-3161">Pattern</span></span>

<span data-ttu-id="1b076-3162">Depende del estado, por ejemplo, Nueva York:</span><span class="sxs-lookup"><span data-stu-id="1b076-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="1b076-3163">Nueve dígitos como ddd ddd ddd coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="1b076-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="1b076-3164">Nueve dígitos como ddddddddd no coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="1b076-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-3165">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-3165">Checksum</span></span>

<span data-ttu-id="1b076-3166">No</span><span class="sxs-lookup"><span data-stu-id="1b076-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-3167">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-3167">Definition</span></span>

<span data-ttu-id="1b076-3168">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3169">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3170">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="1b076-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="1b076-3171">Se encuentra una palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="1b076-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="1b076-3172">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3173">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3174">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="1b076-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="1b076-3175">Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="1b076-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="1b076-3176">No se encuentra ninguna palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="1b076-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-3177">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="1b076-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="1b076-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="1b076-3179">DL</span><span class="sxs-lookup"><span data-stu-id="1b076-3179">DL</span></span> 
- <span data-ttu-id="1b076-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="1b076-3180">DLS</span></span> 
- <span data-ttu-id="1b076-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="1b076-3181">CDL</span></span> 
- <span data-ttu-id="1b076-3182">CDLS</span><span class="sxs-lookup"><span data-stu-id="1b076-3182">CDLS</span></span> 
- <span data-ttu-id="1b076-3183">ID</span><span class="sxs-lookup"><span data-stu-id="1b076-3183">ID</span></span> 
- <span data-ttu-id="1b076-3184">Identificadores de</span><span class="sxs-lookup"><span data-stu-id="1b076-3184">IDs</span></span> 
- <span data-ttu-id="1b076-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="1b076-3185">DL#</span></span> 
- <span data-ttu-id="1b076-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3186">DLS#</span></span> 
- <span data-ttu-id="1b076-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3187">CDL#</span></span> 
- <span data-ttu-id="1b076-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3188">CDLS#</span></span> 
- <span data-ttu-id="1b076-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="1b076-3189">ID#</span></span>
- <span data-ttu-id="1b076-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3190">IDs#</span></span> 
- <span data-ttu-id="1b076-3191">número de Id.</span><span class="sxs-lookup"><span data-stu-id="1b076-3191">ID number</span></span> 
- <span data-ttu-id="1b076-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="1b076-3192">ID numbers</span></span> 
- <span data-ttu-id="1b076-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="1b076-3193">LIC</span></span> 
- <span data-ttu-id="1b076-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="1b076-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="1b076-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="1b076-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="1b076-3196">DriverLic</span></span> 
- <span data-ttu-id="1b076-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="1b076-3197">DriverLics</span></span> 
- <span data-ttu-id="1b076-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="1b076-3198">DriverLicense</span></span> 
- <span data-ttu-id="1b076-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-3199">DriverLicenses</span></span> 
- <span data-ttu-id="1b076-3200">Lic de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-3200">Driver Lic</span></span> 
- <span data-ttu-id="1b076-3201">LIC de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-3201">Driver Lics</span></span> 
- <span data-ttu-id="1b076-3202">Licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-3202">Driver License</span></span> 
- <span data-ttu-id="1b076-3203">Licencias de controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-3203">Driver Licenses</span></span> 
- <span data-ttu-id="1b076-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="1b076-3204">DriversLic</span></span> 
- <span data-ttu-id="1b076-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="1b076-3205">DriversLics</span></span> 
- <span data-ttu-id="1b076-3206">PermisoDeConducción</span><span class="sxs-lookup"><span data-stu-id="1b076-3206">DriversLicense</span></span> 
- <span data-ttu-id="1b076-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-3207">DriversLicenses</span></span> 
- <span data-ttu-id="1b076-3208">Lic de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-3208">Drivers Lic</span></span> 
- <span data-ttu-id="1b076-3209">LIC de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-3209">Drivers Lics</span></span> 
- <span data-ttu-id="1b076-3210">Licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-3210">Drivers License</span></span> 
- <span data-ttu-id="1b076-3211">Licencias de controladores</span><span class="sxs-lookup"><span data-stu-id="1b076-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="1b076-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="1b076-3212">Driver'Lic</span></span> 
- <span data-ttu-id="1b076-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="1b076-3213">Driver'Lics</span></span> 
- <span data-ttu-id="1b076-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="1b076-3214">Driver'License</span></span> 
- <span data-ttu-id="1b076-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="1b076-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="1b076-3216">Controlador ' Lic</span><span class="sxs-lookup"><span data-stu-id="1b076-3216">Driver' Lic</span></span> 
- <span data-ttu-id="1b076-3217">Controlador ' LIC</span><span class="sxs-lookup"><span data-stu-id="1b076-3217">Driver' Lics</span></span> 
- <span data-ttu-id="1b076-3218">Controlador ' licencia</span><span class="sxs-lookup"><span data-stu-id="1b076-3218">Driver' License</span></span> 
- <span data-ttu-id="1b076-3219">Controlador ' licencias</span><span class="sxs-lookup"><span data-stu-id="1b076-3219">Driver' Licenses</span></span>
- <span data-ttu-id="1b076-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="1b076-3220">Driver'sLic</span></span> 
- <span data-ttu-id="1b076-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="1b076-3221">Driver'sLics</span></span> 
- <span data-ttu-id="1b076-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="1b076-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="1b076-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="1b076-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="1b076-3224">Lic del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-3224">Driver's Lic</span></span> 
- <span data-ttu-id="1b076-3225">LIC del controlador</span><span class="sxs-lookup"><span data-stu-id="1b076-3225">Driver's Lics</span></span> 
- <span data-ttu-id="1b076-3226">De conducir permiso</span><span class="sxs-lookup"><span data-stu-id="1b076-3226">Driver's License</span></span> 
- <span data-ttu-id="1b076-3227">Permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="1b076-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="1b076-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="1b076-3228">identification number</span></span> 
- <span data-ttu-id="1b076-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="1b076-3229">identification numbers</span></span> 
- <span data-ttu-id="1b076-3230">identification #
</span><span class="sxs-lookup"><span data-stu-id="1b076-3230">identification #</span></span> 
- <span data-ttu-id="1b076-3231">tarjeta de Id.</span><span class="sxs-lookup"><span data-stu-id="1b076-3231">id card</span></span> 
- <span data-ttu-id="1b076-3232">identificador de tarjetas</span><span class="sxs-lookup"><span data-stu-id="1b076-3232">id cards</span></span> 
- <span data-ttu-id="1b076-3233">tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-3233">identification card</span></span> 
- <span data-ttu-id="1b076-3234">tarjetas de identificación</span><span class="sxs-lookup"><span data-stu-id="1b076-3234">identification cards</span></span> 
- <span data-ttu-id="1b076-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-3235">DriverLic#</span></span> 
- <span data-ttu-id="1b076-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-3236">DriverLics#</span></span> 
- <span data-ttu-id="1b076-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="1b076-3237">DriverLicense#</span></span> 
- <span data-ttu-id="1b076-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="1b076-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="1b076-3239">Driver Lic#</span></span> 
- <span data-ttu-id="1b076-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3240">Driver Lics#</span></span> 
- <span data-ttu-id="1b076-3241">Controlador licencia #</span><span class="sxs-lookup"><span data-stu-id="1b076-3241">Driver License#</span></span> 
- <span data-ttu-id="1b076-3242">Controlador licencias #</span><span class="sxs-lookup"><span data-stu-id="1b076-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="1b076-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-3243">DriversLic#</span></span> 
- <span data-ttu-id="1b076-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-3244">DriversLics#</span></span> 
- <span data-ttu-id="1b076-3245">PermisoDeConducción #</span><span class="sxs-lookup"><span data-stu-id="1b076-3245">DriversLicense#</span></span> 
- <span data-ttu-id="1b076-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="1b076-3247">Controladores Lic #</span><span class="sxs-lookup"><span data-stu-id="1b076-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="1b076-3248">Controladores LIC #</span><span class="sxs-lookup"><span data-stu-id="1b076-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="1b076-3249">Licencia de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-3249">Drivers License#</span></span> 
- <span data-ttu-id="1b076-3250">Licencias de controladores #</span><span class="sxs-lookup"><span data-stu-id="1b076-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="1b076-3251">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="1b076-3252">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="1b076-3253">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3253">Driver'License#</span></span> 
- <span data-ttu-id="1b076-3254">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="1b076-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="1b076-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="1b076-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3257">Driver' License#</span></span> 
- <span data-ttu-id="1b076-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="1b076-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="1b076-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="1b076-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="1b076-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="1b076-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="1b076-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="1b076-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="1b076-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="1b076-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="1b076-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="1b076-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3265">Driver's License#</span></span> 
- <span data-ttu-id="1b076-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="1b076-3267">tarjeta de identificación #</span><span class="sxs-lookup"><span data-stu-id="1b076-3267">id card#</span></span> 
- <span data-ttu-id="1b076-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3268">id cards#</span></span> 
- <span data-ttu-id="1b076-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3269">identification card#</span></span> 
- <span data-ttu-id="1b076-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="1b076-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="1b076-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="1b076-3272">Abreviatura del estado (por ejemplo, "NY")
</span><span class="sxs-lookup"><span data-stu-id="1b076-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="1b076-3273">Nombre del estado (por ejemplo, "New York")
</span><span class="sxs-lookup"><span data-stu-id="1b076-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="1b076-3274">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="1b076-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-3275">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3275">Format</span></span>

<span data-ttu-id="1b076-3276">Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="1b076-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-3277">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-3277">Pattern</span></span>

<span data-ttu-id="1b076-3278">Con formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-3278">Formatted:</span></span>
- <span data-ttu-id="1b076-3279">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="1b076-3279">The digit "9"</span></span> 
- <span data-ttu-id="1b076-3280">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3280">Two digits</span></span> 
- <span data-ttu-id="1b076-3281">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-3281">A space or dash</span></span> 
- <span data-ttu-id="1b076-3282">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="1b076-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="1b076-3283">Un dígito</span><span class="sxs-lookup"><span data-stu-id="1b076-3283">A digit</span></span> 
- <span data-ttu-id="1b076-3284">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="1b076-3284">A space, or dash</span></span> 
- <span data-ttu-id="1b076-3285">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3285">Four digits</span></span>

<span data-ttu-id="1b076-3286">Sin formato:</span><span class="sxs-lookup"><span data-stu-id="1b076-3286">Unformatted:</span></span>
- <span data-ttu-id="1b076-3287">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="1b076-3287">The digit "9"</span></span> 
- <span data-ttu-id="1b076-3288">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3288">Two digits</span></span> 
- <span data-ttu-id="1b076-3289">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="1b076-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="1b076-3290">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="1b076-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-3291">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-3291">Checksum</span></span>

<span data-ttu-id="1b076-3292">No</span><span class="sxs-lookup"><span data-stu-id="1b076-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="1b076-3293">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-3293">Definition</span></span>

<span data-ttu-id="1b076-3294">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3295">La función Func_formatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3296">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="1b076-3297">Se encuentra una palabra clave de Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="1b076-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="1b076-3298">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="1b076-3299">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="1b076-3300">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="1b076-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="1b076-3301">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3302">La función Func_unformatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3303">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="1b076-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="1b076-3304">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="1b076-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="1b076-3305">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="1b076-3306">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="1b076-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-3307">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="1b076-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="1b076-3308">Keyword_itin</span></span>

- <span data-ttu-id="1b076-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="1b076-3309">taxpayer</span></span> 
- <span data-ttu-id="1b076-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="1b076-3310">tax id</span></span> 
- <span data-ttu-id="1b076-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="1b076-3311">tax identification</span></span> 
- <span data-ttu-id="1b076-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="1b076-3312">itin</span></span> 
- <span data-ttu-id="1b076-3313">ssn</span><span class="sxs-lookup"><span data-stu-id="1b076-3313">ssn</span></span> 
- <span data-ttu-id="1b076-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="1b076-3314">tin</span></span> 
- <span data-ttu-id="1b076-3315">seguridad social</span><span class="sxs-lookup"><span data-stu-id="1b076-3315">social security</span></span> 
- <span data-ttu-id="1b076-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="1b076-3316">tax payer</span></span> 
- <span data-ttu-id="1b076-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="1b076-3317">itins</span></span> 
- <span data-ttu-id="1b076-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="1b076-3318">taxid</span></span> 
- <span data-ttu-id="1b076-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="1b076-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="1b076-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="1b076-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="1b076-3321">License</span><span class="sxs-lookup"><span data-stu-id="1b076-3321">License</span></span> 
- <span data-ttu-id="1b076-3322">DL</span><span class="sxs-lookup"><span data-stu-id="1b076-3322">DL</span></span> 
- <span data-ttu-id="1b076-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="1b076-3323">DOB</span></span> 
- <span data-ttu-id="1b076-3324">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="1b076-3324">Birthdate</span></span> 
- <span data-ttu-id="1b076-3325">Cumpleaños </span><span class="sxs-lookup"><span data-stu-id="1b076-3325">Birthday</span></span> 
- <span data-ttu-id="1b076-3326">Fecha de nacimiento
</span><span class="sxs-lookup"><span data-stu-id="1b076-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="1b076-3327">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="1b076-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="1b076-3328">Formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3328">Format</span></span>

<span data-ttu-id="1b076-3329">9 dígitos, que pueden ser un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="1b076-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="1b076-3330">Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="1b076-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="1b076-3331">Patrón</span><span class="sxs-lookup"><span data-stu-id="1b076-3331">Pattern</span></span>

<span data-ttu-id="1b076-3332">Cuatro funciones buscan SSN en cuatro patrones diferentes:</span><span class="sxs-lookup"><span data-stu-id="1b076-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="1b076-3333">Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="1b076-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="1b076-3334">Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="1b076-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="1b076-3335">Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="1b076-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="1b076-3336">Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="1b076-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="1b076-3337">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="1b076-3337">Checksum</span></span>

<span data-ttu-id="1b076-3338">No</span><span class="sxs-lookup"><span data-stu-id="1b076-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="1b076-3339">Definición</span><span class="sxs-lookup"><span data-stu-id="1b076-3339">Definition</span></span>

<span data-ttu-id="1b076-3340">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3341">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3342">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="1b076-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="1b076-3343">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3344">La función Func_unformatted_ssn busca contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3345">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="1b076-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="1b076-3346">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3347">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3348">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="1b076-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="1b076-3349">La función Func_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="1b076-3350">Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1b076-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="1b076-3351">La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="1b076-3352">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="1b076-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="1b076-3353">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="1b076-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="1b076-3354">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b076-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="1b076-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="1b076-3355">Keyword_ssn</span></span>

- <span data-ttu-id="1b076-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="1b076-3356">Social Security</span></span> 
- <span data-ttu-id="1b076-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3357">Social Security#</span></span> 
- <span data-ttu-id="1b076-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="1b076-3358">Soc Sec</span></span> 
- <span data-ttu-id="1b076-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="1b076-3359">SSN</span></span> 
- <span data-ttu-id="1b076-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="1b076-3360">SSNS</span></span> 
- <span data-ttu-id="1b076-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3361">SSN#</span></span> 
- <span data-ttu-id="1b076-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="1b076-3362">SS#</span></span> 
- <span data-ttu-id="1b076-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="1b076-3363">SSID</span></span> 
   

