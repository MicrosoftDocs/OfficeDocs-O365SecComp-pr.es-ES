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
ms.collection:
- M365-security-compliance
description: La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye 80 tipos de información confidencial listos para que pueda usarlos en las directivas de DLP. Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.
ms.openlocfilehash: e9811b285e98a791570dc91e275cb5cead4f8bc9
ms.sourcegitcommit: 6e8e2b43a4bea31c1e835c5b050824651c6a0094
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30537647"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="16f62-104">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="16f62-104">What the sensitive information types look for</span></span>

<span data-ttu-id="16f62-105">La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="16f62-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="16f62-106">Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.</span><span class="sxs-lookup"><span data-stu-id="16f62-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="16f62-107">Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función.</span><span class="sxs-lookup"><span data-stu-id="16f62-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="16f62-108">Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="16f62-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="16f62-109">El nivel de confianza y la proximidad también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="16f62-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="16f62-110">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="16f62-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-111">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-111">Format</span></span>

<span data-ttu-id="16f62-112">9 dígitos, que pueden tener un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="16f62-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-113">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-113">Pattern</span></span>

<span data-ttu-id="16f62-114">Con formato</span><span class="sxs-lookup"><span data-stu-id="16f62-114">Formatted:</span></span>
- <span data-ttu-id="16f62-115">Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="16f62-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="16f62-116">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-116">A hyphen</span></span>
- <span data-ttu-id="16f62-117">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-117">Four digits</span></span>
- <span data-ttu-id="16f62-118">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-118">A hyphen</span></span>
- <span data-ttu-id="16f62-119">Un dígito</span><span class="sxs-lookup"><span data-stu-id="16f62-119">A digit</span></span>

<span data-ttu-id="16f62-120">Sin formato: 9 dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="16f62-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="16f62-121">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-121">Checksum</span></span>

<span data-ttu-id="16f62-122">No</span><span class="sxs-lookup"><span data-stu-id="16f62-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-123">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-123">Definition</span></span>

<span data-ttu-id="16f62-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-125">La función Func_aba_routing encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-126">Se encuentra una palabra clave de Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="16f62-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="16f62-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="16f62-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="16f62-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="16f62-129">ABA</span><span class="sxs-lookup"><span data-stu-id="16f62-129">aba</span></span>
- <span data-ttu-id="16f62-130">aba #</span><span class="sxs-lookup"><span data-stu-id="16f62-130">aba #</span></span>
- <span data-ttu-id="16f62-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="16f62-131">aba routing #</span></span>
- <span data-ttu-id="16f62-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="16f62-132">aba routing number</span></span>
- <span data-ttu-id="16f62-133">ABA</span><span class="sxs-lookup"><span data-stu-id="16f62-133">aba#</span></span>
- <span data-ttu-id="16f62-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="16f62-134">abarouting#</span></span>
- <span data-ttu-id="16f62-135">aba number</span><span class="sxs-lookup"><span data-stu-id="16f62-135">aba number</span></span>
- <span data-ttu-id="16f62-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-136">abaroutingnumber</span></span>
- <span data-ttu-id="16f62-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="16f62-137">american bank association routing #</span></span>
- <span data-ttu-id="16f62-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="16f62-138">american bank association routing number</span></span>
- <span data-ttu-id="16f62-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="16f62-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="16f62-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="16f62-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="16f62-141">bank routing number</span></span>
- <span data-ttu-id="16f62-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="16f62-142">bankrouting#</span></span>
- <span data-ttu-id="16f62-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-143">bankroutingnumber</span></span>
- <span data-ttu-id="16f62-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="16f62-144">routing transit number</span></span>
- <span data-ttu-id="16f62-145">RTN</span><span class="sxs-lookup"><span data-stu-id="16f62-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="16f62-146">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="16f62-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-147">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-147">Format</span></span>

<span data-ttu-id="16f62-148">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="16f62-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-149">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-149">Pattern</span></span>

<span data-ttu-id="16f62-150">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-150">Eight digits:</span></span>
- <span data-ttu-id="16f62-151">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-151">Two digits</span></span>
- <span data-ttu-id="16f62-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-152">A period</span></span>
- <span data-ttu-id="16f62-153">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-153">Three digits</span></span>
- <span data-ttu-id="16f62-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-154">A period</span></span>
- <span data-ttu-id="16f62-155">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-156">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-156">Checksum</span></span>

<span data-ttu-id="16f62-157">No</span><span class="sxs-lookup"><span data-stu-id="16f62-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-158">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-158">Definition</span></span>

<span data-ttu-id="16f62-159">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-160">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-161">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="16f62-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="16f62-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="16f62-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="16f62-164">Número de identidad nacional de Argentina</span><span class="sxs-lookup"><span data-stu-id="16f62-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="16f62-165">Identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-165">Identity</span></span> 
- <span data-ttu-id="16f62-166">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="16f62-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="16f62-167">DNI</span><span class="sxs-lookup"><span data-stu-id="16f62-167">DNI</span></span> 
- <span data-ttu-id="16f62-168">Registro Nacional de NIC de personas</span><span class="sxs-lookup"><span data-stu-id="16f62-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="16f62-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="16f62-170">Registro nacional de las personas</span><span class="sxs-lookup"><span data-stu-id="16f62-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="16f62-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-171">Identidad</span></span> 
- <span data-ttu-id="16f62-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="16f62-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="16f62-173">Número de cuenta bancaria de Australia</span><span class="sxs-lookup"><span data-stu-id="16f62-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-174">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-174">Format</span></span>

<span data-ttu-id="16f62-175">De 6 a 10 dígitos con o sin número de sucursal bancaria de estado</span><span class="sxs-lookup"><span data-stu-id="16f62-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-176">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-176">Pattern</span></span>

<span data-ttu-id="16f62-177">El número de cuenta tiene entre 6 y 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="16f62-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="16f62-178">Número de sucursal bancaria de Australia:</span><span class="sxs-lookup"><span data-stu-id="16f62-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="16f62-179">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-179">Three digits</span></span> 
- <span data-ttu-id="16f62-180">Un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-180">A hyphen</span></span> 
- <span data-ttu-id="16f62-181">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-182">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-182">Checksum</span></span>

<span data-ttu-id="16f62-183">No</span><span class="sxs-lookup"><span data-stu-id="16f62-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-184">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-184">Definition</span></span>

<span data-ttu-id="16f62-185">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-186">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="16f62-187">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="16f62-188">La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="16f62-189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-190">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="16f62-191">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="16f62-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="16f62-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="16f62-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="16f62-194">swift bank code</span></span>
- <span data-ttu-id="16f62-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="16f62-195">correspondent bank</span></span>
- <span data-ttu-id="16f62-196">base currency</span><span class="sxs-lookup"><span data-stu-id="16f62-196">base currency</span></span>
- <span data-ttu-id="16f62-197">usa account</span><span class="sxs-lookup"><span data-stu-id="16f62-197">usa account</span></span>
- <span data-ttu-id="16f62-198">holder address</span><span class="sxs-lookup"><span data-stu-id="16f62-198">holder address</span></span>
- <span data-ttu-id="16f62-199">bank address</span><span class="sxs-lookup"><span data-stu-id="16f62-199">bank address</span></span>
- <span data-ttu-id="16f62-200">information account</span><span class="sxs-lookup"><span data-stu-id="16f62-200">information account</span></span>
- <span data-ttu-id="16f62-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="16f62-201">fund transfers</span></span>
- <span data-ttu-id="16f62-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="16f62-202">bank charges</span></span>
- <span data-ttu-id="16f62-203">bank details</span><span class="sxs-lookup"><span data-stu-id="16f62-203">bank details</span></span>
- <span data-ttu-id="16f62-204">banking information</span><span class="sxs-lookup"><span data-stu-id="16f62-204">banking information</span></span>
- <span data-ttu-id="16f62-205">full names</span><span class="sxs-lookup"><span data-stu-id="16f62-205">full names</span></span>
- <span data-ttu-id="16f62-206">OIEA</span><span class="sxs-lookup"><span data-stu-id="16f62-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="16f62-207">Número de licencia de conducción de Australia</span><span class="sxs-lookup"><span data-stu-id="16f62-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-208">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-208">Format</span></span>

<span data-ttu-id="16f62-209">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-210">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-210">Pattern</span></span>

<span data-ttu-id="16f62-211">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="16f62-212">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-213">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-213">Two digits</span></span> 
- <span data-ttu-id="16f62-214">Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="16f62-215">O</span><span class="sxs-lookup"><span data-stu-id="16f62-215">OR</span></span>

- <span data-ttu-id="16f62-216">1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-217">4-9 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-217">4-9 digits</span></span>

<span data-ttu-id="16f62-218">O</span><span class="sxs-lookup"><span data-stu-id="16f62-218">OR</span></span>

- <span data-ttu-id="16f62-219">Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-220">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-220">Checksum</span></span>

<span data-ttu-id="16f62-221">No</span><span class="sxs-lookup"><span data-stu-id="16f62-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-222">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-222">Definition</span></span>

<span data-ttu-id="16f62-223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-224">La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-225">Se encuentra una palabra clave de Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="16f62-226">No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="16f62-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="16f62-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16f62-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="16f62-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="16f62-229">international driving permits</span></span>
- <span data-ttu-id="16f62-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="16f62-230">australian automobile association</span></span>
- <span data-ttu-id="16f62-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="16f62-231">international driving permit</span></span>
- <span data-ttu-id="16f62-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="16f62-232">DriverLicence</span></span>
- <span data-ttu-id="16f62-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="16f62-233">DriverLicences</span></span>
- <span data-ttu-id="16f62-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-234">Driver Lic</span></span>
- <span data-ttu-id="16f62-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-235">Driver Licence</span></span>
- <span data-ttu-id="16f62-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-236">Driver Licences</span></span>
- <span data-ttu-id="16f62-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="16f62-237">DriversLic</span></span>
- <span data-ttu-id="16f62-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="16f62-238">DriversLicence</span></span>
- <span data-ttu-id="16f62-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="16f62-239">DriversLicences</span></span>
- <span data-ttu-id="16f62-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-240">Drivers Lic</span></span>
- <span data-ttu-id="16f62-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-241">Drivers Lics</span></span>
- <span data-ttu-id="16f62-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-242">Drivers Licence</span></span>
- <span data-ttu-id="16f62-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-243">Drivers Licences</span></span>
- <span data-ttu-id="16f62-244">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-244">Driver'Lic</span></span>
- <span data-ttu-id="16f62-245">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-245">Driver'Lics</span></span>
- <span data-ttu-id="16f62-246">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-246">Driver'Licence</span></span>
- <span data-ttu-id="16f62-247">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-247">Driver'Licences</span></span>
- <span data-ttu-id="16f62-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-248">Driver' Lic</span></span>
- <span data-ttu-id="16f62-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-249">Driver' Lics</span></span>
- <span data-ttu-id="16f62-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-250">Driver' Licence</span></span>
- <span data-ttu-id="16f62-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-251">Driver' Licences</span></span>
- <span data-ttu-id="16f62-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="16f62-252">Driver'sLic</span></span>
- <span data-ttu-id="16f62-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="16f62-253">Driver'sLics</span></span>
- <span data-ttu-id="16f62-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="16f62-254">Driver'sLicence</span></span>
- <span data-ttu-id="16f62-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="16f62-255">Driver'sLicences</span></span>
- <span data-ttu-id="16f62-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-256">Driver's Lic</span></span>
- <span data-ttu-id="16f62-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-257">Driver's Lics</span></span>
- <span data-ttu-id="16f62-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-258">Driver's Licence</span></span>
- <span data-ttu-id="16f62-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-259">Driver's Licences</span></span>
- <span data-ttu-id="16f62-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-260">DriverLic#</span></span>
- <span data-ttu-id="16f62-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-261">DriverLics#</span></span>
- <span data-ttu-id="16f62-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="16f62-262">DriverLicence#</span></span>
- <span data-ttu-id="16f62-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="16f62-263">DriverLicences#</span></span>
- <span data-ttu-id="16f62-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-264">Driver Lic#</span></span>
- <span data-ttu-id="16f62-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-265">Driver Lics#</span></span>
- <span data-ttu-id="16f62-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="16f62-266">Driver Licence#</span></span>
- <span data-ttu-id="16f62-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-267">Driver Licences#</span></span>
- <span data-ttu-id="16f62-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-268">DriversLic#</span></span>
- <span data-ttu-id="16f62-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-269">DriversLics#</span></span>
- <span data-ttu-id="16f62-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="16f62-270">DriversLicence#</span></span>
- <span data-ttu-id="16f62-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="16f62-271">DriversLicences#</span></span>
- <span data-ttu-id="16f62-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-272">Drivers Lic#</span></span>
- <span data-ttu-id="16f62-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-273">Drivers Lics#</span></span>
- <span data-ttu-id="16f62-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="16f62-274">Drivers Licence#</span></span>
- <span data-ttu-id="16f62-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-275">Drivers Licences#</span></span>
- <span data-ttu-id="16f62-276">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-276">Driver'Lic#</span></span>
- <span data-ttu-id="16f62-277">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-277">Driver'Lics#</span></span>
- <span data-ttu-id="16f62-278">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-278">Driver'Licence#</span></span>
- <span data-ttu-id="16f62-279">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-279">Driver'Licences#</span></span>
- <span data-ttu-id="16f62-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-280">Driver' Lic#</span></span>
- <span data-ttu-id="16f62-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-281">Driver' Lics#</span></span>
- <span data-ttu-id="16f62-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="16f62-282">Driver' Licence#</span></span>
- <span data-ttu-id="16f62-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-283">Driver' Licences#</span></span>
- <span data-ttu-id="16f62-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-284">Driver'sLic#</span></span>
- <span data-ttu-id="16f62-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-285">Driver'sLics#</span></span>
- <span data-ttu-id="16f62-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="16f62-286">Driver'sLicence#</span></span>
- <span data-ttu-id="16f62-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="16f62-287">Driver'sLicences#</span></span>
- <span data-ttu-id="16f62-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-288">Driver's Lic#</span></span>
- <span data-ttu-id="16f62-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-289">Driver's Lics#</span></span>
- <span data-ttu-id="16f62-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="16f62-290">Driver's Licence#</span></span>
- <span data-ttu-id="16f62-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="16f62-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="16f62-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="16f62-293">aaaa</span><span class="sxs-lookup"><span data-stu-id="16f62-293">aaa</span></span>
- <span data-ttu-id="16f62-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-294">DriverLicense</span></span>
- <span data-ttu-id="16f62-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-295">DriverLicenses</span></span>
- <span data-ttu-id="16f62-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="16f62-296">Driver License</span></span>
- <span data-ttu-id="16f62-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-297">Driver Licenses</span></span>
- <span data-ttu-id="16f62-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-298">DriversLicense</span></span>
- <span data-ttu-id="16f62-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-299">DriversLicenses</span></span>
- <span data-ttu-id="16f62-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16f62-300">Drivers License</span></span>
- <span data-ttu-id="16f62-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-301">Drivers Licenses</span></span>
- <span data-ttu-id="16f62-302">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-302">Driver'License</span></span>
- <span data-ttu-id="16f62-303">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-303">Driver'Licenses</span></span>
- <span data-ttu-id="16f62-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="16f62-304">Driver' License</span></span>
- <span data-ttu-id="16f62-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-305">Driver' Licenses</span></span>
- <span data-ttu-id="16f62-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-306">Driver'sLicense</span></span>
- <span data-ttu-id="16f62-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-307">Driver'sLicenses</span></span>
- <span data-ttu-id="16f62-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16f62-308">Driver's License</span></span>
- <span data-ttu-id="16f62-309">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-309">Driver's Licenses</span></span>
- <span data-ttu-id="16f62-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-310">DriverLicense#</span></span>
- <span data-ttu-id="16f62-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-311">DriverLicenses#</span></span>
- <span data-ttu-id="16f62-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16f62-312">Driver License#</span></span>
- <span data-ttu-id="16f62-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-313">Driver Licenses#</span></span>
- <span data-ttu-id="16f62-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-314">DriversLicense#</span></span>
- <span data-ttu-id="16f62-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-315">DriversLicenses#</span></span>
- <span data-ttu-id="16f62-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="16f62-316">Drivers License#</span></span>
- <span data-ttu-id="16f62-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-317">Drivers Licenses#</span></span>
- <span data-ttu-id="16f62-318">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-318">Driver'License#</span></span>
- <span data-ttu-id="16f62-319">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-319">Driver'Licenses#</span></span>
- <span data-ttu-id="16f62-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="16f62-320">Driver' License#</span></span>
- <span data-ttu-id="16f62-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-321">Driver' Licenses#</span></span>
- <span data-ttu-id="16f62-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-322">Driver'sLicense#</span></span>
- <span data-ttu-id="16f62-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="16f62-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="16f62-324">Driver's License#</span></span>
- <span data-ttu-id="16f62-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="16f62-326">Número de cuenta médica de Australia</span><span class="sxs-lookup"><span data-stu-id="16f62-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-327">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-327">Format</span></span>

<span data-ttu-id="16f62-328">Entre 10 y 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-329">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-329">Pattern</span></span>

<span data-ttu-id="16f62-330">Entre 10 y 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-330">10-11 digits:</span></span>
- <span data-ttu-id="16f62-331">el primer dígito está en el intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="16f62-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="16f62-332">El noveno dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="16f62-333">El décimo dígito es el dígito de emisión</span><span class="sxs-lookup"><span data-stu-id="16f62-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="16f62-334">El undécimo dígito (opcional) es el número individual</span><span class="sxs-lookup"><span data-stu-id="16f62-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-335">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-335">Checksum</span></span>

<span data-ttu-id="16f62-336">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-337">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-337">Definition</span></span>

<span data-ttu-id="16f62-338">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-339">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-340">Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="16f62-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="16f62-341">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-341">The checksum passes.</span></span>

<span data-ttu-id="16f62-342">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-343">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-344">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-345">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="16f62-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="16f62-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="16f62-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="16f62-347">bank account details</span></span>
- <span data-ttu-id="16f62-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="16f62-348">medicare payments</span></span>
- <span data-ttu-id="16f62-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="16f62-349">mortgage account</span></span>
- <span data-ttu-id="16f62-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="16f62-350">bank payments</span></span>
- <span data-ttu-id="16f62-351">information branch</span><span class="sxs-lookup"><span data-stu-id="16f62-351">information branch</span></span>
- <span data-ttu-id="16f62-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="16f62-352">credit card loan</span></span>
- <span data-ttu-id="16f62-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="16f62-353">department of human services</span></span>
- <span data-ttu-id="16f62-354">local service</span><span class="sxs-lookup"><span data-stu-id="16f62-354">local service</span></span>
- <span data-ttu-id="16f62-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="16f62-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="16f62-356">Número de pasaporte de Australia</span><span class="sxs-lookup"><span data-stu-id="16f62-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-357">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-357">Format</span></span>

<span data-ttu-id="16f62-358">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-359">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-359">Pattern</span></span>

<span data-ttu-id="16f62-360">Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-361">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-361">Checksum</span></span>

<span data-ttu-id="16f62-362">No</span><span class="sxs-lookup"><span data-stu-id="16f62-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-363">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-363">Definition</span></span>

<span data-ttu-id="16f62-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-365">La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-366">Se encuentra una palabra clave de Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-367">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="16f62-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-368">Keyword_passport</span></span>

- <span data-ttu-id="16f62-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16f62-369">Passport Number</span></span>
- <span data-ttu-id="16f62-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="16f62-370">Passport No</span></span>
- <span data-ttu-id="16f62-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="16f62-371">Passport #</span></span>
- <span data-ttu-id="16f62-372">Usuarios</span><span class="sxs-lookup"><span data-stu-id="16f62-372">Passport#</span></span>
- <span data-ttu-id="16f62-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="16f62-373">PassportID</span></span>
- <span data-ttu-id="16f62-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="16f62-374">Passportno</span></span>
- <span data-ttu-id="16f62-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-375">passportnumber</span></span>
- <span data-ttu-id="16f62-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="16f62-376">パスポート</span></span>
- <span data-ttu-id="16f62-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16f62-377">パスポート番号</span></span>
- <span data-ttu-id="16f62-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16f62-378">パスポートのNum</span></span>
- <span data-ttu-id="16f62-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="16f62-379">パスポート ＃</span></span> 
- <span data-ttu-id="16f62-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16f62-380">Numéro de passeport</span></span>
- <span data-ttu-id="16f62-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16f62-381">Passeport n °</span></span>
- <span data-ttu-id="16f62-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16f62-382">Passeport Non</span></span>
- <span data-ttu-id="16f62-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-383">Passeport #</span></span>
- <span data-ttu-id="16f62-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-384">Passeport#</span></span>
- <span data-ttu-id="16f62-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16f62-385">PasseportNon</span></span>
- <span data-ttu-id="16f62-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16f62-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="16f62-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="16f62-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="16f62-388">usuarios</span><span class="sxs-lookup"><span data-stu-id="16f62-388">passport</span></span>
- <span data-ttu-id="16f62-389">passport details</span><span class="sxs-lookup"><span data-stu-id="16f62-389">passport details</span></span>
- <span data-ttu-id="16f62-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="16f62-390">immigration and citizenship</span></span>
- <span data-ttu-id="16f62-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="16f62-391">commonwealth of australia</span></span>
- <span data-ttu-id="16f62-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="16f62-392">department of immigration</span></span>
- <span data-ttu-id="16f62-393">residential address</span><span class="sxs-lookup"><span data-stu-id="16f62-393">residential address</span></span>
- <span data-ttu-id="16f62-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="16f62-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="16f62-395">régimen</span><span class="sxs-lookup"><span data-stu-id="16f62-395">visa</span></span>
- <span data-ttu-id="16f62-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="16f62-396">national identity card</span></span>
- <span data-ttu-id="16f62-397">passport number</span><span class="sxs-lookup"><span data-stu-id="16f62-397">passport number</span></span>
- <span data-ttu-id="16f62-398">travel document</span><span class="sxs-lookup"><span data-stu-id="16f62-398">travel document</span></span>
- <span data-ttu-id="16f62-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="16f62-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="16f62-400">Número de archivo de impuestos de Australia</span><span class="sxs-lookup"><span data-stu-id="16f62-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-401">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-401">Format</span></span>

<span data-ttu-id="16f62-402">Entre 8 y 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-403">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-403">Pattern</span></span>

<span data-ttu-id="16f62-404">8-9 dígitos que normalmente se presentan con espacios como sigue:</span><span class="sxs-lookup"><span data-stu-id="16f62-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="16f62-405">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-405">Three digits</span></span> 
- <span data-ttu-id="16f62-406">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="16f62-406">An optional space</span></span> 
- <span data-ttu-id="16f62-407">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-407">Three digits</span></span> 
- <span data-ttu-id="16f62-408">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="16f62-408">An optional space</span></span> 
- <span data-ttu-id="16f62-409">2-3 dígitos donde el último dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-410">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-410">Checksum</span></span>

<span data-ttu-id="16f62-411">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-412">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-412">Definition</span></span>

<span data-ttu-id="16f62-413">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-414">La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-415">No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="16f62-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="16f62-416">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="16f62-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="16f62-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="16f62-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="16f62-419">australian business number</span></span>
- <span data-ttu-id="16f62-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="16f62-420">marginal tax rate</span></span>
- <span data-ttu-id="16f62-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="16f62-421">medicare levy</span></span>
- <span data-ttu-id="16f62-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="16f62-422">portfolio number</span></span>
- <span data-ttu-id="16f62-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="16f62-423">service veterans</span></span>
- <span data-ttu-id="16f62-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="16f62-424">withholding tax</span></span>
- <span data-ttu-id="16f62-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="16f62-425">individual tax return</span></span>
- <span data-ttu-id="16f62-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="16f62-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="16f62-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="16f62-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="16f62-428">00000000</span><span class="sxs-lookup"><span data-stu-id="16f62-428">00000000</span></span>
- <span data-ttu-id="16f62-429">11111111</span><span class="sxs-lookup"><span data-stu-id="16f62-429">11111111</span></span>
- <span data-ttu-id="16f62-430">22222222</span><span class="sxs-lookup"><span data-stu-id="16f62-430">22222222</span></span>
- <span data-ttu-id="16f62-431">33333333</span><span class="sxs-lookup"><span data-stu-id="16f62-431">33333333</span></span>
- <span data-ttu-id="16f62-432">44444444</span><span class="sxs-lookup"><span data-stu-id="16f62-432">44444444</span></span>
- <span data-ttu-id="16f62-433">55555555</span><span class="sxs-lookup"><span data-stu-id="16f62-433">55555555</span></span>
- <span data-ttu-id="16f62-434">66666666</span><span class="sxs-lookup"><span data-stu-id="16f62-434">66666666</span></span>
- <span data-ttu-id="16f62-435">77777777</span><span class="sxs-lookup"><span data-stu-id="16f62-435">77777777</span></span>
- <span data-ttu-id="16f62-436">88888888</span><span class="sxs-lookup"><span data-stu-id="16f62-436">88888888</span></span>
- <span data-ttu-id="16f62-437">99999999</span><span class="sxs-lookup"><span data-stu-id="16f62-437">99999999</span></span>
- <span data-ttu-id="16f62-438">000000000</span><span class="sxs-lookup"><span data-stu-id="16f62-438">000000000</span></span>
- <span data-ttu-id="16f62-439">111111111</span><span class="sxs-lookup"><span data-stu-id="16f62-439">111111111</span></span>
- <span data-ttu-id="16f62-440">222222222</span><span class="sxs-lookup"><span data-stu-id="16f62-440">222222222</span></span>
- <span data-ttu-id="16f62-441">333333333</span><span class="sxs-lookup"><span data-stu-id="16f62-441">333333333</span></span>
- <span data-ttu-id="16f62-442">444444444</span><span class="sxs-lookup"><span data-stu-id="16f62-442">444444444</span></span>
- <span data-ttu-id="16f62-443">555555555</span><span class="sxs-lookup"><span data-stu-id="16f62-443">555555555</span></span>
- <span data-ttu-id="16f62-444">666666666</span><span class="sxs-lookup"><span data-stu-id="16f62-444">666666666</span></span>
- <span data-ttu-id="16f62-445">777777777</span><span class="sxs-lookup"><span data-stu-id="16f62-445">777777777</span></span>
- <span data-ttu-id="16f62-446">888888888</span><span class="sxs-lookup"><span data-stu-id="16f62-446">888888888</span></span>
- <span data-ttu-id="16f62-447">999999999</span><span class="sxs-lookup"><span data-stu-id="16f62-447">999999999</span></span>
- <span data-ttu-id="16f62-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="16f62-448">0000000000</span></span>
- <span data-ttu-id="16f62-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="16f62-449">1111111111</span></span>
- <span data-ttu-id="16f62-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="16f62-450">2222222222</span></span>
- <span data-ttu-id="16f62-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="16f62-451">3333333333</span></span>
- <span data-ttu-id="16f62-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="16f62-452">4444444444</span></span>
- <span data-ttu-id="16f62-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="16f62-453">5555555555</span></span>
- <span data-ttu-id="16f62-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="16f62-454">6666666666</span></span>
- <span data-ttu-id="16f62-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="16f62-455">7777777777</span></span>
- <span data-ttu-id="16f62-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="16f62-456">8888888888</span></span>
- <span data-ttu-id="16f62-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="16f62-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="16f62-458">Clave de autenticación de Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="16f62-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="16f62-459">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-459">Format</span></span>

<span data-ttu-id="16f62-460">La cadena "DocumentDb" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="16f62-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-461">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-461">Pattern</span></span>

- <span data-ttu-id="16f62-462">La cadena "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="16f62-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="16f62-463">Cualquier combinación de entre 3-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-464">Un símbolo mayor que (>), un signo igual (=), una comilla (") o un apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="16f62-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="16f62-465">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="16f62-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16f62-466">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-467">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-467">Checksum</span></span>

<span data-ttu-id="16f62-468">No</span><span class="sxs-lookup"><span data-stu-id="16f62-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-469">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-469">Definition</span></span>

<span data-ttu-id="16f62-470">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-471">La expresión regular CEP_Regex_AzureDocumentDBAuthKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-472">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-473">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-475">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-476">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-476">contoso</span></span>
- <span data-ttu-id="16f62-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-477">fabrikam</span></span>
- <span data-ttu-id="16f62-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-478">northwind</span></span>
- <span data-ttu-id="16f62-479">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-479">sandbox</span></span>
- <span data-ttu-id="16f62-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-480">onebox</span></span>
- <span data-ttu-id="16f62-481">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-481">localhost</span></span>
- <span data-ttu-id="16f62-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-482">127.0.0.1</span></span>
- <span data-ttu-id="16f62-483">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-483">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-484">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-484">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="16f62-485">Cadena de conexión de base de datos IAAS de Azure y cadena de conexión SQL de Azure</span><span class="sxs-lookup"><span data-stu-id="16f62-485">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16f62-486">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-486">Format</span></span>

<span data-ttu-id="16f62-487">La cadena "Server", "Server" o "Data Source" seguida de los caracteres y las cadenas que se describen en el siguiente patrón, incluida la cadena "CloudApp. Azure. <!--no-hyperlink-->com "o" CloudApp. Azure. <!--no-hyperlink-->net "o" Database. Windows. <!--no-hyperlink-->net "y la cadena" Password "o" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="16f62-487">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.<!--no-hyperlink-->com" or "cloudapp.azure.<!--no-hyperlink-->net" or "database.windows.<!--no-hyperlink-->net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-488">Pattern</span></span>

- <span data-ttu-id="16f62-489">La cadena "servidor", "servidor" o "origen de datos"</span><span class="sxs-lookup"><span data-stu-id="16f62-489">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="16f62-490">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-490">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-491">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-491">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-492">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-492">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-493">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-493">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-494">La cadena "CloudApp. Azure. <!--no-hyperlink-->com "," CloudApp. Azure. <!--no-hyperlink-->net "o" Database. Windows. <!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="16f62-494">The string "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", or "database.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="16f62-495">Cualquier combinación de entre 1-300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-495">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-496">La cadena "Password", "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="16f62-496">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="16f62-497">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-498">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-498">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-499">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-499">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-500">Uno o más caracteres que no son un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="16f62-500">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="16f62-501">Un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="16f62-501">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-502">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-502">Checksum</span></span>

<span data-ttu-id="16f62-503">No</span><span class="sxs-lookup"><span data-stu-id="16f62-503">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-504">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-504">Definition</span></span>

<span data-ttu-id="16f62-505">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-505">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-506">La expresión regular CEP_Regex_AzureConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-506">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-507">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-507">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-508">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-508">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-509">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-509">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-510">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-510">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-511">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-511">contoso</span></span>
- <span data-ttu-id="16f62-512">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-512">fabrikam</span></span>
- <span data-ttu-id="16f62-513">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-513">northwind</span></span>
- <span data-ttu-id="16f62-514">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-514">sandbox</span></span>
- <span data-ttu-id="16f62-515">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-515">onebox</span></span>
- <span data-ttu-id="16f62-516">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-516">localhost</span></span>
- <span data-ttu-id="16f62-517">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-517">127.0.0.1</span></span>
- <span data-ttu-id="16f62-518">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-518">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-519">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-519">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="16f62-520">Cadena de conexión de Azure IoT</span><span class="sxs-lookup"><span data-stu-id="16f62-520">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16f62-521">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-521">Format</span></span>

<span data-ttu-id="16f62-522">La cadena "HostName" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "Azure-Devices. <!--no-hyperlink-->net "y" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="16f62-522">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.<!--no-hyperlink-->net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-523">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-523">Pattern</span></span>

- <span data-ttu-id="16f62-524">La cadena "HostName"</span><span class="sxs-lookup"><span data-stu-id="16f62-524">The string "HostName"</span></span>
- <span data-ttu-id="16f62-525">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-525">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-526">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-526">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-527">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-527">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-528">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-528">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-529">La cadena "Azure-Devices. <!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="16f62-529">The string "azure-devices.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="16f62-530">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-530">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-531">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="16f62-531">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="16f62-532">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-532">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-533">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-533">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-534">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-534">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-535">Cualquier combinación de 43 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="16f62-535">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16f62-536">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-536">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-537">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-537">Checksum</span></span>

<span data-ttu-id="16f62-538">No</span><span class="sxs-lookup"><span data-stu-id="16f62-538">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-539">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-539">Definition</span></span>

<span data-ttu-id="16f62-540">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-540">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-541">La expresión regular CEP_Regex_AzureIoTConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-541">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-542">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-542">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-543">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-543">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-544">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-544">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-545">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-545">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-546">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-546">contoso</span></span>
- <span data-ttu-id="16f62-547">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-547">fabrikam</span></span>
- <span data-ttu-id="16f62-548">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-548">northwind</span></span>
- <span data-ttu-id="16f62-549">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-549">sandbox</span></span>
- <span data-ttu-id="16f62-550">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-550">onebox</span></span>
- <span data-ttu-id="16f62-551">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-551">localhost</span></span>
- <span data-ttu-id="16f62-552">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-552">127.0.0.1</span></span>
- <span data-ttu-id="16f62-553">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-553">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-554">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-554">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="16f62-555">Contraseña de configuración de publicación de Azure</span><span class="sxs-lookup"><span data-stu-id="16f62-555">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="16f62-556">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-556">Format</span></span>

<span data-ttu-id="16f62-557">La cadena "userpwd =" seguida de una cadena alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="16f62-557">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-558">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-558">Pattern</span></span>

- <span data-ttu-id="16f62-559">La cadena "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="16f62-559">The string "userpwd="</span></span>
- <span data-ttu-id="16f62-560">Cualquier combinación de 60 letras minúsculas o dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-560">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="16f62-561">Un signo de Comillas (")</span><span class="sxs-lookup"><span data-stu-id="16f62-561">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-562">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-562">Checksum</span></span>

<span data-ttu-id="16f62-563">No</span><span class="sxs-lookup"><span data-stu-id="16f62-563">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-564">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-564">Definition</span></span>

<span data-ttu-id="16f62-565">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-565">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-566">La expresión regular CEP_Regex_AzurePublishSettingPasswords encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-566">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-567">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-567">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-568">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-568">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-569">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-569">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-570">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-570">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-571">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-571">contoso</span></span>
- <span data-ttu-id="16f62-572">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-572">fabrikam</span></span>
- <span data-ttu-id="16f62-573">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-573">northwind</span></span>
- <span data-ttu-id="16f62-574">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-574">sandbox</span></span>
- <span data-ttu-id="16f62-575">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-575">onebox</span></span>
- <span data-ttu-id="16f62-576">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-576">localhost</span></span>
- <span data-ttu-id="16f62-577">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-577">127.0.0.1</span></span>
- <span data-ttu-id="16f62-578">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-578">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-579">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-579">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="16f62-580">Cadena de conexión de la caché de Redis de Azure</span><span class="sxs-lookup"><span data-stu-id="16f62-580">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16f62-581">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-581">Format</span></span>

<span data-ttu-id="16f62-582">La cadena "Redis. Cache. Windows. <!--no-hyperlink-->net "seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="16f62-582">The string "redis.cache.windows.<!--no-hyperlink-->net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-583">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-583">Pattern</span></span>

- <span data-ttu-id="16f62-584">La cadena "Redis. Cache. Windows. <!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="16f62-584">The string "redis.cache.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="16f62-585">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-585">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-586">La cadena "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="16f62-586">The string "password" or "pwd"</span></span>
- <span data-ttu-id="16f62-587">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-587">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-588">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-588">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-589">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-589">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-590">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="16f62-590">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16f62-591">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-591">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-592">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-592">Checksum</span></span>

<span data-ttu-id="16f62-593">No</span><span class="sxs-lookup"><span data-stu-id="16f62-593">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-594">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-594">Definition</span></span>

<span data-ttu-id="16f62-595">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-596">La expresión regular CEP_Regex_AzureRedisCacheConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="16f62-596">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="16f62-597">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-597">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-598">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-598">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-599">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-599">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-600">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-600">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-601">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-601">contoso</span></span>
- <span data-ttu-id="16f62-602">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-602">fabrikam</span></span>
- <span data-ttu-id="16f62-603">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-603">northwind</span></span>
- <span data-ttu-id="16f62-604">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-604">sandbox</span></span>
- <span data-ttu-id="16f62-605">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-605">onebox</span></span>
- <span data-ttu-id="16f62-606">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-606">localhost</span></span>
- <span data-ttu-id="16f62-607">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-607">127.0.0.1</span></span>
- <span data-ttu-id="16f62-608">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-608">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-609">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-609">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="16f62-610">ASOCIACIONES de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="16f62-610">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="16f62-611">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-611">Format</span></span>

<span data-ttu-id="16f62-612">La cadena "SIG" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="16f62-612">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-613">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-613">Pattern</span></span>

- <span data-ttu-id="16f62-614">La cadena "SIG"</span><span class="sxs-lookup"><span data-stu-id="16f62-614">The string "sig"</span></span>
- <span data-ttu-id="16f62-615">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-615">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-616">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-616">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-617">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-617">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-618">Cualquier combinación de entre 43-53 caracteres que sean letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="16f62-618">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="16f62-619">La cadena "% 3D"</span><span class="sxs-lookup"><span data-stu-id="16f62-619">The string "%3d"</span></span>
- <span data-ttu-id="16f62-620">Cualquier carácter que no sea una letra minúscula o mayúscula, un dígito o un signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="16f62-620">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-621">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-621">Checksum</span></span>

<span data-ttu-id="16f62-622">No</span><span class="sxs-lookup"><span data-stu-id="16f62-622">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-623">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-623">Definition</span></span>

<span data-ttu-id="16f62-624">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-625">La expresión regular CEP_Regex_AzureSAS encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-625">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="16f62-626">Cadena de conexión del bus de servicio de Azure</span><span class="sxs-lookup"><span data-stu-id="16f62-626">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16f62-627">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-627">Format</span></span>

<span data-ttu-id="16f62-628">La cadena "EndPoint" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "ServiceBus. Windows. <!--no-hyperlink-->net "y" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="16f62-628">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.<!--no-hyperlink-->net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-629">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-629">Pattern</span></span>

- <span data-ttu-id="16f62-630">La cadena "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="16f62-630">The string "EndPoint"</span></span>
- <span data-ttu-id="16f62-631">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-631">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-632">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-632">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-633">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-633">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-634">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-634">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-635">La cadena "ServiceBus. Windows. <!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="16f62-635">The string "servicebus.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="16f62-636">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-636">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-637">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="16f62-637">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="16f62-638">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-638">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-639">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-639">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-640">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-640">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-641">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="16f62-641">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16f62-642">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-642">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-643">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-643">Checksum</span></span>

<span data-ttu-id="16f62-644">No</span><span class="sxs-lookup"><span data-stu-id="16f62-644">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-645">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-645">Definition</span></span>

<span data-ttu-id="16f62-646">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-646">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-647">La expresión regular CEP_Regex_AzureServiceBusConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="16f62-647">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="16f62-648">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-648">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-649">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-649">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-650">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-650">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-651">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-651">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-652">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-652">contoso</span></span>
- <span data-ttu-id="16f62-653">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-653">fabrikam</span></span>
- <span data-ttu-id="16f62-654">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-654">northwind</span></span>
- <span data-ttu-id="16f62-655">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-655">sandbox</span></span>
- <span data-ttu-id="16f62-656">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-656">onebox</span></span>
- <span data-ttu-id="16f62-657">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-657">localhost</span></span>
- <span data-ttu-id="16f62-658">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-658">127.0.0.1</span></span>
- <span data-ttu-id="16f62-659">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-659">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-660">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-660">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="16f62-661">Clave de cuenta de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="16f62-661">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="16f62-662">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-662">Format</span></span>

<span data-ttu-id="16f62-663">La cadena "DefaultEndpointsProtocol" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="16f62-663">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-664">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-664">Pattern</span></span>

- <span data-ttu-id="16f62-665">La cadena "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="16f62-665">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="16f62-666">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-666">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-667">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-667">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-668">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-668">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-669">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-669">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-670">La cadena "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="16f62-670">The string "AccountKey"</span></span>
- <span data-ttu-id="16f62-671">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-671">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-672">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-672">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-673">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-673">0-2 whitespace characters</span></span>
- <span data-ttu-id="16f62-674">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="16f62-674">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16f62-675">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-675">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-676">Checksum</span></span>

<span data-ttu-id="16f62-677">No</span><span class="sxs-lookup"><span data-stu-id="16f62-677">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-678">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-678">Definition</span></span>

<span data-ttu-id="16f62-679">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-679">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-680">La expresión regular CEP_Regex_AzureStorageAccountKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-680">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-681">La expresión regular CEP_AzureEmulatorStorageAccountFilter no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-681">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-682">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-682">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-683">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-683">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="16f62-684">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="16f62-684">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="16f62-685">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-685">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="16f62-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-687">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-687">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-688">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-688">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-689">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-689">contoso</span></span>
- <span data-ttu-id="16f62-690">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-690">fabrikam</span></span>
- <span data-ttu-id="16f62-691">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-691">northwind</span></span>
- <span data-ttu-id="16f62-692">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-692">sandbox</span></span>
- <span data-ttu-id="16f62-693">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-693">onebox</span></span>
- <span data-ttu-id="16f62-694">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-694">localhost</span></span>
- <span data-ttu-id="16f62-695">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-695">127.0.0.1</span></span>
- <span data-ttu-id="16f62-696">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-696">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-697">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-697">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="16f62-698">Clave de cuenta de almacenamiento de Azure (Genérico)</span><span class="sxs-lookup"><span data-stu-id="16f62-698">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-699">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-699">Format</span></span>

<span data-ttu-id="16f62-700">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+), precedido o seguido por los caracteres descritos en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="16f62-700">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-701">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-701">Pattern</span></span>

- <span data-ttu-id="16f62-702">0-1 del símbolo mayor que (>), apóstrofe ('), signo de igual (=), Comillas (") o almohadilla (#)</span><span class="sxs-lookup"><span data-stu-id="16f62-702">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="16f62-703">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+)</span><span class="sxs-lookup"><span data-stu-id="16f62-703">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16f62-704">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-704">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="16f62-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-705">Checksum</span></span>

<span data-ttu-id="16f62-706">No</span><span class="sxs-lookup"><span data-stu-id="16f62-706">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-707">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-707">Definition</span></span>

<span data-ttu-id="16f62-708">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-708">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-709">La expresión regular CEP_Regex_AzureStorageAccountKeyGeneric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-709">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="16f62-710">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="16f62-710">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-711">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-711">Format</span></span>

<span data-ttu-id="16f62-712">11 dígitos más delimitadores</span><span class="sxs-lookup"><span data-stu-id="16f62-712">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-713">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-713">Pattern</span></span>

<span data-ttu-id="16f62-714">11 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="16f62-714">11 digits plus delimiters:</span></span>
- <span data-ttu-id="16f62-715">Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-715">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="16f62-716">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-716">A hyphen</span></span> 
- <span data-ttu-id="16f62-717">Tres dígitos secuenciales (impares para hombres, pares para mujeres) </span><span class="sxs-lookup"><span data-stu-id="16f62-717">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="16f62-718">Un punto</span><span class="sxs-lookup"><span data-stu-id="16f62-718">A period</span></span> 
- <span data-ttu-id="16f62-719">Dos dígitos que son un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-719">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-720">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-720">Checksum</span></span>

<span data-ttu-id="16f62-721">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-721">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-722">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-722">Definition</span></span>

<span data-ttu-id="16f62-723">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-723">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-724">La función Func_belgium_national_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-724">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-725">Se encuentra una palabra clave de Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-725">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="16f62-726">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-726">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-727">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-727">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="16f62-728">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="16f62-728">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="16f62-729">Identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-729">Identity</span></span>
- <span data-ttu-id="16f62-730">Registro</span><span class="sxs-lookup"><span data-stu-id="16f62-730">Registration</span></span>
- <span data-ttu-id="16f62-731">Determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-731">Identification</span></span> 
- <span data-ttu-id="16f62-732">Id.</span><span class="sxs-lookup"><span data-stu-id="16f62-732">ID</span></span> 
- <span data-ttu-id="16f62-733">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="16f62-733">Identiteitskaart</span></span>
- <span data-ttu-id="16f62-734">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="16f62-734">Registratie nummer</span></span> 
- <span data-ttu-id="16f62-735">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="16f62-735">Identificatie nummer</span></span> 
- <span data-ttu-id="16f62-736">Identiteit</span><span class="sxs-lookup"><span data-stu-id="16f62-736">Identiteit</span></span>
- <span data-ttu-id="16f62-737">Registratie</span><span class="sxs-lookup"><span data-stu-id="16f62-737">Registratie</span></span>
- <span data-ttu-id="16f62-738">Identificatie</span><span class="sxs-lookup"><span data-stu-id="16f62-738">Identificatie</span></span> 
- <span data-ttu-id="16f62-739">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="16f62-739">Carte d’identité</span></span> 
- <span data-ttu-id="16f62-740">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="16f62-740">numéro d'immatriculation</span></span>
- <span data-ttu-id="16f62-741">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="16f62-741">numéro d'identification</span></span>
- <span data-ttu-id="16f62-742">Identité</span><span class="sxs-lookup"><span data-stu-id="16f62-742">identité</span></span> 
- <span data-ttu-id="16f62-743">indicación</span><span class="sxs-lookup"><span data-stu-id="16f62-743">inscription</span></span> 
- <span data-ttu-id="16f62-744">Identifikation</span><span class="sxs-lookup"><span data-stu-id="16f62-744">Identifikation</span></span>
- <span data-ttu-id="16f62-745">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="16f62-745">Identifizierung</span></span>
- <span data-ttu-id="16f62-746">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-746">Identifikationsnummer</span></span>
- <span data-ttu-id="16f62-747">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="16f62-747">Personalausweis</span></span>
- <span data-ttu-id="16f62-748">Registrierung</span><span class="sxs-lookup"><span data-stu-id="16f62-748">Registrierung</span></span>
- <span data-ttu-id="16f62-749">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-749">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="16f62-750">Número CPF de Brasil</span><span class="sxs-lookup"><span data-stu-id="16f62-750">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-751">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-751">Format</span></span>

<span data-ttu-id="16f62-752">11 dígitos incluido un dígito de control y que pueden tener o no formato</span><span class="sxs-lookup"><span data-stu-id="16f62-752">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-753">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-753">Pattern</span></span>

<span data-ttu-id="16f62-754">Con formato</span><span class="sxs-lookup"><span data-stu-id="16f62-754">Formatted:</span></span>
- <span data-ttu-id="16f62-755">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-755">Three digits</span></span> 
- <span data-ttu-id="16f62-756">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-756">A period</span></span> 
- <span data-ttu-id="16f62-757">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-757">Three digits</span></span> 
- <span data-ttu-id="16f62-758">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-758">A period</span></span> 
- <span data-ttu-id="16f62-759">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-759">Three digits</span></span> 
- <span data-ttu-id="16f62-760">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-760">A hyphen</span></span> 
- <span data-ttu-id="16f62-761">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="16f62-761">Two digits which are check digits</span></span>

<span data-ttu-id="16f62-762">Sin formato</span><span class="sxs-lookup"><span data-stu-id="16f62-762">Unformatted:</span></span>
- <span data-ttu-id="16f62-763">11 dígitos, donde los dos últimos dígitos son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="16f62-763">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-764">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-764">Checksum</span></span>

<span data-ttu-id="16f62-765">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-765">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-766">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-766">Definition</span></span>

<span data-ttu-id="16f62-767">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-767">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-768">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-768">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-769">Se encuentra una palabra clave de Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="16f62-769">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="16f62-770">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-770">The checksum passes.</span></span>

<span data-ttu-id="16f62-771">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-772">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-772">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-773">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-773">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-774">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-774">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="16f62-775">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="16f62-775">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="16f62-776">CPF</span><span class="sxs-lookup"><span data-stu-id="16f62-776">CPF</span></span>
- <span data-ttu-id="16f62-777">Determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-777">Identification</span></span>
- <span data-ttu-id="16f62-778">Registro</span><span class="sxs-lookup"><span data-stu-id="16f62-778">Registration</span></span>
- <span data-ttu-id="16f62-779">Generar</span><span class="sxs-lookup"><span data-stu-id="16f62-779">Revenue</span></span>
- <span data-ttu-id="16f62-780">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="16f62-780">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="16f62-781">Imposto</span><span class="sxs-lookup"><span data-stu-id="16f62-781">Imposto</span></span> 
- <span data-ttu-id="16f62-782">Identificação</span><span class="sxs-lookup"><span data-stu-id="16f62-782">Identificação</span></span> 
- <span data-ttu-id="16f62-783">Inscrição</span><span class="sxs-lookup"><span data-stu-id="16f62-783">Inscrição</span></span> 
- <span data-ttu-id="16f62-784">Receita</span><span class="sxs-lookup"><span data-stu-id="16f62-784">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="16f62-785">Número de entidad jurídica de Brasil (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="16f62-785">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-786">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-786">Format</span></span>

<span data-ttu-id="16f62-787">14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores</span><span class="sxs-lookup"><span data-stu-id="16f62-787">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-788">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-788">Pattern</span></span>
<span data-ttu-id="16f62-789">14 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="16f62-789">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="16f62-790">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-790">Two digits</span></span> 
- <span data-ttu-id="16f62-791">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-791">A period</span></span> 
- <span data-ttu-id="16f62-792">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-792">Three digits</span></span> 
- <span data-ttu-id="16f62-793">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-793">A period</span></span> 
- <span data-ttu-id="16f62-794">Tres dígitos (estos ocho primeros dígitos son el número de registro) </span><span class="sxs-lookup"><span data-stu-id="16f62-794">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="16f62-795">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="16f62-795">A forward slash</span></span> 
- <span data-ttu-id="16f62-796">Número de sucursal de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-796">Four-digit branch number</span></span> 
- <span data-ttu-id="16f62-797">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-797">A hyphen</span></span> 
- <span data-ttu-id="16f62-798">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="16f62-798">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-799">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-799">Checksum</span></span>

<span data-ttu-id="16f62-800">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-801">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-801">Definition</span></span>

<span data-ttu-id="16f62-802">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-803">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-803">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-804">Se encuentra una palabra clave de Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="16f62-804">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="16f62-805">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-805">The checksum passes.</span></span>

<span data-ttu-id="16f62-806">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-807">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-807">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-808">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-808">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-809">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-809">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="16f62-810">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="16f62-810">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="16f62-811">CNPJ</span><span class="sxs-lookup"><span data-stu-id="16f62-811">CNPJ</span></span> 
- <span data-ttu-id="16f62-812">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="16f62-812">CNPJ/MF</span></span> 
- <span data-ttu-id="16f62-813">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="16f62-813">CNPJ-MF</span></span> 
- <span data-ttu-id="16f62-814">Registro nacional de entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="16f62-814">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="16f62-815">Registro de contribuyentes</span><span class="sxs-lookup"><span data-stu-id="16f62-815">Taxpayers Registry</span></span> 
- <span data-ttu-id="16f62-816">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="16f62-816">Legal entity</span></span> 
- <span data-ttu-id="16f62-817">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="16f62-817">Legal entities</span></span> 
- <span data-ttu-id="16f62-818">Estado de registro</span><span class="sxs-lookup"><span data-stu-id="16f62-818">Registration Status</span></span> 
- <span data-ttu-id="16f62-819">Empresa</span><span class="sxs-lookup"><span data-stu-id="16f62-819">Business</span></span> 
- <span data-ttu-id="16f62-820">Company</span><span class="sxs-lookup"><span data-stu-id="16f62-820">Company</span></span>
- <span data-ttu-id="16f62-821">CNPJ</span><span class="sxs-lookup"><span data-stu-id="16f62-821">CNPJ</span></span> 
- <span data-ttu-id="16f62-822">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="16f62-822">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="16f62-823">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="16f62-823">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="16f62-824">CGC</span><span class="sxs-lookup"><span data-stu-id="16f62-824">CGC</span></span> 
- <span data-ttu-id="16f62-825">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="16f62-825">Pessoa jurídica</span></span> 
- <span data-ttu-id="16f62-826">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="16f62-826">Pessoas jurídicas</span></span> 
- <span data-ttu-id="16f62-827">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="16f62-827">Situação cadastral</span></span> 
- <span data-ttu-id="16f62-828">Inscrição</span><span class="sxs-lookup"><span data-stu-id="16f62-828">Inscrição</span></span> 
- <span data-ttu-id="16f62-829">Empresa</span><span class="sxs-lookup"><span data-stu-id="16f62-829">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="16f62-830">	Tarjeta de identificación nacional de Brasil (RG)</span><span class="sxs-lookup"><span data-stu-id="16f62-830">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-831">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-831">Format</span></span>

<span data-ttu-id="16f62-832">Registro geral (formato anterior): nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-832">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="16f62-833">Registro de Identidade (RIC) (nuevo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-833">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-834">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-834">Pattern</span></span>

<span data-ttu-id="16f62-835">Registro de Geral (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="16f62-835">Registro Geral (old format):</span></span>
- <span data-ttu-id="16f62-836">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-836">Two digits</span></span> 
- <span data-ttu-id="16f62-837">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-837">A period</span></span> 
- <span data-ttu-id="16f62-838">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-838">Three digits</span></span> 
- <span data-ttu-id="16f62-839">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-839">A period</span></span> 
- <span data-ttu-id="16f62-840">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-840">Three digits</span></span> 
- <span data-ttu-id="16f62-841">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-841">A hyphen</span></span> 
- <span data-ttu-id="16f62-842">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-842">One digit which is a check digit</span></span>

<span data-ttu-id="16f62-843">Registro de Identidade (RIC) (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="16f62-843">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="16f62-844">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-844">10 digits</span></span> 
- <span data-ttu-id="16f62-845">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-845">A hyphen</span></span> 
- <span data-ttu-id="16f62-846">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-846">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-847">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-847">Checksum</span></span>

<span data-ttu-id="16f62-848">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-848">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-849">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-849">Definition</span></span>

<span data-ttu-id="16f62-850">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-850">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-851">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-851">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-852">Se encuentra una palabra clave de Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="16f62-852">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="16f62-853">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-853">The checksum passes.</span></span>

<span data-ttu-id="16f62-854">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-854">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-855">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-855">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-856">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-857">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-857">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="16f62-858">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="16f62-858">Keyword_brazil_rg</span></span>

<span data-ttu-id="16f62-859">Cédula de Identidade identidad nacional identificador número de rregistro registro de Iidentidade registro Geral RG (esta palabra clave distingue entre mayúsculas y minúsculas) RIC (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-859">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="16f62-860">Número de cuenta bancaria de Canadá</span><span class="sxs-lookup"><span data-stu-id="16f62-860">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-861">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-861">Format</span></span>

<span data-ttu-id="16f62-862">Siete o doce dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-862">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-863">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-863">Pattern</span></span>

<span data-ttu-id="16f62-864">El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.</span><span class="sxs-lookup"><span data-stu-id="16f62-864">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="16f62-865">Un número de tránsito de cuenta bancaria de Canadá es:</span><span class="sxs-lookup"><span data-stu-id="16f62-865">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="16f62-866">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-866">Five digits</span></span> 
- <span data-ttu-id="16f62-867">Un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-867">A hyphen</span></span> 
- <span data-ttu-id="16f62-868">Tres dígitos o</span><span class="sxs-lookup"><span data-stu-id="16f62-868">Three digits OR</span></span>
- <span data-ttu-id="16f62-869">Un cero "0" </span><span class="sxs-lookup"><span data-stu-id="16f62-869">A zero "0"</span></span> 
- <span data-ttu-id="16f62-870">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-870">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-871">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-871">Checksum</span></span>

<span data-ttu-id="16f62-872">No</span><span class="sxs-lookup"><span data-stu-id="16f62-872">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-873">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-873">Definition</span></span>

<span data-ttu-id="16f62-874">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-874">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-875">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-875">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-876">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-876">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="16f62-877">La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-877">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="16f62-878">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-878">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-879">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-879">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-880">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-880">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-881">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-881">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="16f62-882">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="16f62-882">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="16f62-883">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="16f62-883">canada savings bonds</span></span>
- <span data-ttu-id="16f62-884">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="16f62-884">canada revenue agency</span></span>
- <span data-ttu-id="16f62-885">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="16f62-885">canadian financial institution</span></span>
- <span data-ttu-id="16f62-886">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="16f62-886">direct deposit form</span></span>
- <span data-ttu-id="16f62-887">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="16f62-887">canadian citizen</span></span>
- <span data-ttu-id="16f62-888">legal representative</span><span class="sxs-lookup"><span data-stu-id="16f62-888">legal representative</span></span>
- <span data-ttu-id="16f62-889">notary public</span><span class="sxs-lookup"><span data-stu-id="16f62-889">notary public</span></span>
- <span data-ttu-id="16f62-890">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="16f62-890">commissioner for oaths</span></span>
- <span data-ttu-id="16f62-891">child care benefit</span><span class="sxs-lookup"><span data-stu-id="16f62-891">child care benefit</span></span>
- <span data-ttu-id="16f62-892">universal child care</span><span class="sxs-lookup"><span data-stu-id="16f62-892">universal child care</span></span>
- <span data-ttu-id="16f62-893">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="16f62-893">canada child tax benefit</span></span>
- <span data-ttu-id="16f62-894">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="16f62-894">income tax benefit</span></span>
- <span data-ttu-id="16f62-895">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="16f62-895">harmonized sales tax</span></span>
- <span data-ttu-id="16f62-896">social insurance number</span><span class="sxs-lookup"><span data-stu-id="16f62-896">social insurance number</span></span>
- <span data-ttu-id="16f62-897">income tax refund</span><span class="sxs-lookup"><span data-stu-id="16f62-897">income tax refund</span></span>
- <span data-ttu-id="16f62-898">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="16f62-898">child tax benefit</span></span>
- <span data-ttu-id="16f62-899">territorial payments</span><span class="sxs-lookup"><span data-stu-id="16f62-899">territorial payments</span></span>
- <span data-ttu-id="16f62-900">institution number</span><span class="sxs-lookup"><span data-stu-id="16f62-900">institution number</span></span>
- <span data-ttu-id="16f62-901">deposit request</span><span class="sxs-lookup"><span data-stu-id="16f62-901">deposit request</span></span>
- <span data-ttu-id="16f62-902">banking information</span><span class="sxs-lookup"><span data-stu-id="16f62-902">banking information</span></span>
- <span data-ttu-id="16f62-903">direct deposit</span><span class="sxs-lookup"><span data-stu-id="16f62-903">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="16f62-904">Número de licencia de conductor de Canadá</span><span class="sxs-lookup"><span data-stu-id="16f62-904">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-905">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-905">Format</span></span>

<span data-ttu-id="16f62-906">Varía según la provincia</span><span class="sxs-lookup"><span data-stu-id="16f62-906">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-907">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-907">Pattern</span></span>

<span data-ttu-id="16f62-908">Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="16f62-908">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-909">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-909">Checksum</span></span>

<span data-ttu-id="16f62-910">No</span><span class="sxs-lookup"><span data-stu-id="16f62-910">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-911">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-911">Definition</span></span>

<span data-ttu-id="16f62-912">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-913">La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-913">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-914">Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="16f62-914">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="16f62-915">Se encuentra una palabra clave de Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="16f62-915">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-916">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-916">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="16f62-917">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="16f62-917">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="16f62-918">La abreviatura de la provincia, por ejemplo, AB</span><span class="sxs-lookup"><span data-stu-id="16f62-918">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="16f62-919">El nombre de la provincia, por ejemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="16f62-919">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="16f62-920">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16f62-920">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="16f62-921">LISTAS</span><span class="sxs-lookup"><span data-stu-id="16f62-921">DL</span></span>
- <span data-ttu-id="16f62-922">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="16f62-922">DLS</span></span>
- <span data-ttu-id="16f62-923">CDL</span><span class="sxs-lookup"><span data-stu-id="16f62-923">CDL</span></span>
- <span data-ttu-id="16f62-924">CDLS</span><span class="sxs-lookup"><span data-stu-id="16f62-924">CDLS</span></span>
- <span data-ttu-id="16f62-925">DriverLic</span><span class="sxs-lookup"><span data-stu-id="16f62-925">DriverLic</span></span>
- <span data-ttu-id="16f62-926">DriverLics</span><span class="sxs-lookup"><span data-stu-id="16f62-926">DriverLics</span></span>
- <span data-ttu-id="16f62-927">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-927">DriverLicense</span></span>
- <span data-ttu-id="16f62-928">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-928">DriverLicenses</span></span>
- <span data-ttu-id="16f62-929">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="16f62-929">DriverLicence</span></span>
- <span data-ttu-id="16f62-930">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="16f62-930">DriverLicences</span></span>
- <span data-ttu-id="16f62-931">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-931">Driver Lic</span></span>
- <span data-ttu-id="16f62-932">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-932">Driver Lics</span></span>
- <span data-ttu-id="16f62-933">Driver License</span><span class="sxs-lookup"><span data-stu-id="16f62-933">Driver License</span></span>
- <span data-ttu-id="16f62-934">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-934">Driver Licenses</span></span>
- <span data-ttu-id="16f62-935">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-935">Driver Licence</span></span>
- <span data-ttu-id="16f62-936">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-936">Driver Licences</span></span>
- <span data-ttu-id="16f62-937">DriversLic</span><span class="sxs-lookup"><span data-stu-id="16f62-937">DriversLic</span></span>
- <span data-ttu-id="16f62-938">DriversLics</span><span class="sxs-lookup"><span data-stu-id="16f62-938">DriversLics</span></span>
- <span data-ttu-id="16f62-939">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="16f62-939">DriversLicence</span></span>
- <span data-ttu-id="16f62-940">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="16f62-940">DriversLicences</span></span>
- <span data-ttu-id="16f62-941">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-941">DriversLicense</span></span>
- <span data-ttu-id="16f62-942">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-942">DriversLicenses</span></span>
- <span data-ttu-id="16f62-943">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-943">Drivers Lic</span></span>
- <span data-ttu-id="16f62-944">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-944">Drivers Lics</span></span>
- <span data-ttu-id="16f62-945">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16f62-945">Drivers License</span></span>
- <span data-ttu-id="16f62-946">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-946">Drivers Licenses</span></span>
- <span data-ttu-id="16f62-947">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-947">Drivers Licence</span></span>
- <span data-ttu-id="16f62-948">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-948">Drivers Licences</span></span>
- <span data-ttu-id="16f62-949">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-949">Driver'Lic</span></span>
- <span data-ttu-id="16f62-950">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-950">Driver'Lics</span></span>
- <span data-ttu-id="16f62-951">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-951">Driver'License</span></span>
- <span data-ttu-id="16f62-952">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-952">Driver'Licenses</span></span>
- <span data-ttu-id="16f62-953">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-953">Driver'Licence</span></span>
- <span data-ttu-id="16f62-954">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-954">Driver'Licences</span></span>
- <span data-ttu-id="16f62-955">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-955">Driver' Lic</span></span>
- <span data-ttu-id="16f62-956">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-956">Driver' Lics</span></span>
- <span data-ttu-id="16f62-957">Driver' License</span><span class="sxs-lookup"><span data-stu-id="16f62-957">Driver' License</span></span>
- <span data-ttu-id="16f62-958">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-958">Driver' Licenses</span></span>
- <span data-ttu-id="16f62-959">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-959">Driver' Licence</span></span>
- <span data-ttu-id="16f62-960">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-960">Driver' Licences</span></span>
- <span data-ttu-id="16f62-961">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="16f62-961">Driver'sLic</span></span>
- <span data-ttu-id="16f62-962">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="16f62-962">Driver'sLics</span></span>
- <span data-ttu-id="16f62-963">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-963">Driver'sLicense</span></span>
- <span data-ttu-id="16f62-964">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-964">Driver'sLicenses</span></span>
- <span data-ttu-id="16f62-965">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="16f62-965">Driver'sLicence</span></span>
- <span data-ttu-id="16f62-966">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="16f62-966">Driver'sLicences</span></span>
- <span data-ttu-id="16f62-967">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-967">Driver's Lic</span></span>
- <span data-ttu-id="16f62-968">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-968">Driver's Lics</span></span>
- <span data-ttu-id="16f62-969">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16f62-969">Driver's License</span></span>
- <span data-ttu-id="16f62-970">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-970">Driver's Licenses</span></span>
- <span data-ttu-id="16f62-971">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-971">Driver's Licence</span></span>
- <span data-ttu-id="16f62-972">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-972">Driver's Licences</span></span>
- <span data-ttu-id="16f62-973">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="16f62-973">Permis de Conduire</span></span>
- <span data-ttu-id="16f62-974">id</span><span class="sxs-lookup"><span data-stu-id="16f62-974">id</span></span>
- <span data-ttu-id="16f62-975">ids</span><span class="sxs-lookup"><span data-stu-id="16f62-975">ids</span></span>
- <span data-ttu-id="16f62-976">idcard number</span><span class="sxs-lookup"><span data-stu-id="16f62-976">idcard number</span></span>
- <span data-ttu-id="16f62-977">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-977">idcard numbers</span></span>
- <span data-ttu-id="16f62-978">idcard #</span><span class="sxs-lookup"><span data-stu-id="16f62-978">idcard #</span></span>
- <span data-ttu-id="16f62-979">idcard #s</span><span class="sxs-lookup"><span data-stu-id="16f62-979">idcard #s</span></span>
- <span data-ttu-id="16f62-980">idcard card</span><span class="sxs-lookup"><span data-stu-id="16f62-980">idcard card</span></span>
- <span data-ttu-id="16f62-981">idcard cards</span><span class="sxs-lookup"><span data-stu-id="16f62-981">idcard cards</span></span>
- <span data-ttu-id="16f62-982">tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-982">idcard</span></span>
- <span data-ttu-id="16f62-983">identification number</span><span class="sxs-lookup"><span data-stu-id="16f62-983">identification number</span></span>
- <span data-ttu-id="16f62-984">identification numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-984">identification numbers</span></span>
- <span data-ttu-id="16f62-985">identification #</span><span class="sxs-lookup"><span data-stu-id="16f62-985">identification #</span></span>
- <span data-ttu-id="16f62-986">identification #s</span><span class="sxs-lookup"><span data-stu-id="16f62-986">identification #s</span></span>
- <span data-ttu-id="16f62-987">identification card</span><span class="sxs-lookup"><span data-stu-id="16f62-987">identification card</span></span>
- <span data-ttu-id="16f62-988">identification cards</span><span class="sxs-lookup"><span data-stu-id="16f62-988">identification cards</span></span>
- <span data-ttu-id="16f62-989">determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-989">identification</span></span> 
- <span data-ttu-id="16f62-990">LISTAS</span><span class="sxs-lookup"><span data-stu-id="16f62-990">DL#</span></span>
- <span data-ttu-id="16f62-991">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="16f62-991">DLS#</span></span> 
- <span data-ttu-id="16f62-992">CDL</span><span class="sxs-lookup"><span data-stu-id="16f62-992">CDL#</span></span> 
- <span data-ttu-id="16f62-993">CDLS #</span><span class="sxs-lookup"><span data-stu-id="16f62-993">CDLS#</span></span> 
- <span data-ttu-id="16f62-994">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-994">DriverLic#</span></span> 
- <span data-ttu-id="16f62-995">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-995">DriverLics#</span></span> 
- <span data-ttu-id="16f62-996">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-996">DriverLicense#</span></span> 
- <span data-ttu-id="16f62-997">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-997">DriverLicenses#</span></span> 
- <span data-ttu-id="16f62-998">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="16f62-998">DriverLicence#</span></span> 
- <span data-ttu-id="16f62-999">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="16f62-999">DriverLicences#</span></span> 
- <span data-ttu-id="16f62-1000">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-1000">Driver Lic#</span></span>
- <span data-ttu-id="16f62-1001">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-1001">Driver Lics#</span></span> 
- <span data-ttu-id="16f62-1002">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16f62-1002">Driver License#</span></span> 
- <span data-ttu-id="16f62-1003">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-1003">Driver Licenses#</span></span> 
- <span data-ttu-id="16f62-1004">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16f62-1004">Driver License#</span></span> 
- <span data-ttu-id="16f62-1005">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-1005">Driver Licences#</span></span> 
- <span data-ttu-id="16f62-1006">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-1006">DriversLic#</span></span> 
- <span data-ttu-id="16f62-1007">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-1007">DriversLics#</span></span> 
- <span data-ttu-id="16f62-1008">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-1008">DriversLicense#</span></span> 
- <span data-ttu-id="16f62-1009">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-1009">DriversLicenses#</span></span> 
- <span data-ttu-id="16f62-1010">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="16f62-1010">DriversLicence#</span></span> 
- <span data-ttu-id="16f62-1011">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="16f62-1011">DriversLicences#</span></span> 
- <span data-ttu-id="16f62-1012">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-1012">Drivers Lic#</span></span> 
- <span data-ttu-id="16f62-1013">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-1013">Drivers Lics#</span></span> 
- <span data-ttu-id="16f62-1014">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="16f62-1014">Drivers License#</span></span> 
- <span data-ttu-id="16f62-1015">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-1015">Drivers Licenses#</span></span> 
- <span data-ttu-id="16f62-1016">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="16f62-1016">Drivers Licence#</span></span> 
- <span data-ttu-id="16f62-1017">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-1017">Drivers Licences#</span></span> 
- <span data-ttu-id="16f62-1018">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-1018">Driver'Lic#</span></span> 
- <span data-ttu-id="16f62-1019">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-1019">Driver'Lics#</span></span> 
- <span data-ttu-id="16f62-1020">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-1020">Driver'License#</span></span> 
- <span data-ttu-id="16f62-1021">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-1021">Driver'Licenses#</span></span> 
- <span data-ttu-id="16f62-1022">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-1022">Driver'Licence#</span></span> 
- <span data-ttu-id="16f62-1023">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-1023">Driver'Licences#</span></span> 
- <span data-ttu-id="16f62-1024">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-1024">Driver' Lic#</span></span> 
- <span data-ttu-id="16f62-1025">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-1025">Driver' Lics#</span></span> 
- <span data-ttu-id="16f62-1026">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="16f62-1026">Driver' License#</span></span> 
- <span data-ttu-id="16f62-1027">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-1027">Driver' Licenses#</span></span> 
- <span data-ttu-id="16f62-1028">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="16f62-1028">Driver' Licence#</span></span> 
- <span data-ttu-id="16f62-1029">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-1029">Driver' Licences#</span></span> 
- <span data-ttu-id="16f62-1030">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-1030">Driver'sLic#</span></span> 
- <span data-ttu-id="16f62-1031">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-1031">Driver'sLics#</span></span> 
- <span data-ttu-id="16f62-1032">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-1032">Driver'sLicense#</span></span> 
- <span data-ttu-id="16f62-1033">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-1033">Driver'sLicenses#</span></span> 
- <span data-ttu-id="16f62-1034">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="16f62-1034">Driver'sLicence#</span></span> 
- <span data-ttu-id="16f62-1035">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="16f62-1035">Driver'sLicences#</span></span> 
- <span data-ttu-id="16f62-1036">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-1036">Driver's Lic#</span></span> 
- <span data-ttu-id="16f62-1037">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-1037">Driver's Lics#</span></span> 
- <span data-ttu-id="16f62-1038">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="16f62-1038">Driver's License#</span></span> 
- <span data-ttu-id="16f62-1039">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-1039">Driver's Licenses#</span></span> 
- <span data-ttu-id="16f62-1040">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="16f62-1040">Driver's Licence#</span></span> 
- <span data-ttu-id="16f62-1041">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="16f62-1041">Driver's Licences#</span></span> 
- <span data-ttu-id="16f62-1042">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="16f62-1042">Permis de Conduire#</span></span> 
- <span data-ttu-id="16f62-1043">identificador</span><span class="sxs-lookup"><span data-stu-id="16f62-1043">id#</span></span> 
- <span data-ttu-id="16f62-1044">falta</span><span class="sxs-lookup"><span data-stu-id="16f62-1044">ids#</span></span> 
- <span data-ttu-id="16f62-1045">idcard card#</span><span class="sxs-lookup"><span data-stu-id="16f62-1045">idcard card#</span></span> 
- <span data-ttu-id="16f62-1046">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="16f62-1046">idcard cards#</span></span> 
- <span data-ttu-id="16f62-1047">tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1047">idcard#</span></span> 
- <span data-ttu-id="16f62-1048">identification card#</span><span class="sxs-lookup"><span data-stu-id="16f62-1048">identification card#</span></span> 
- <span data-ttu-id="16f62-1049">identification cards#</span><span class="sxs-lookup"><span data-stu-id="16f62-1049">identification cards#</span></span> 
- <span data-ttu-id="16f62-1050">determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-1050">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="16f62-1051">Número de servicio de salud de Canadá</span><span class="sxs-lookup"><span data-stu-id="16f62-1051">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1052">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1052">Format</span></span>

<span data-ttu-id="16f62-1053">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1053">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1054">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1054">Pattern</span></span>

<span data-ttu-id="16f62-1055">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1055">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1056">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1056">Checksum</span></span>

<span data-ttu-id="16f62-1057">No</span><span class="sxs-lookup"><span data-stu-id="16f62-1057">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1058">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1058">Definition</span></span>

<span data-ttu-id="16f62-1059">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1059">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1060">La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1060">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1061">Se encuentra una palabra clave de Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-1061">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1062">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1062">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="16f62-1063">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="16f62-1063">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="16f62-1064">personal health number</span><span class="sxs-lookup"><span data-stu-id="16f62-1064">personal health number</span></span>
- <span data-ttu-id="16f62-1065">patient information</span><span class="sxs-lookup"><span data-stu-id="16f62-1065">patient information</span></span>
- <span data-ttu-id="16f62-1066">health services</span><span class="sxs-lookup"><span data-stu-id="16f62-1066">health services</span></span>
- <span data-ttu-id="16f62-1067">speciality services</span><span class="sxs-lookup"><span data-stu-id="16f62-1067">speciality services</span></span>
- <span data-ttu-id="16f62-1068">automobile accident</span><span class="sxs-lookup"><span data-stu-id="16f62-1068">automobile accident</span></span>
- <span data-ttu-id="16f62-1069">patient hospital</span><span class="sxs-lookup"><span data-stu-id="16f62-1069">patient hospital</span></span>
- <span data-ttu-id="16f62-1070">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="16f62-1070">psychiatrist</span></span>
- <span data-ttu-id="16f62-1071">workers compensation</span><span class="sxs-lookup"><span data-stu-id="16f62-1071">workers compensation</span></span>
- <span data-ttu-id="16f62-1072">discapacidad</span><span class="sxs-lookup"><span data-stu-id="16f62-1072">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="16f62-1073">Número de pasaporte de Canadá</span><span class="sxs-lookup"><span data-stu-id="16f62-1073">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1074">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1074">Format</span></span>

<span data-ttu-id="16f62-1075">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1075">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1076">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1076">Pattern</span></span>

<span data-ttu-id="16f62-1077">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1077">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1078">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1078">Checksum</span></span>

<span data-ttu-id="16f62-1079">No</span><span class="sxs-lookup"><span data-stu-id="16f62-1079">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1080">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1080">Definition</span></span>

<span data-ttu-id="16f62-1081">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1081">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1082">La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1082">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1083">Se encuentra una palabra clave de Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="16f62-1083">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1084">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1084">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="16f62-1085">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="16f62-1085">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="16f62-1086">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="16f62-1086">canadian citizenship</span></span>
- <span data-ttu-id="16f62-1087">canadian passport</span><span class="sxs-lookup"><span data-stu-id="16f62-1087">canadian passport</span></span>
- <span data-ttu-id="16f62-1088">passport application</span><span class="sxs-lookup"><span data-stu-id="16f62-1088">passport application</span></span>
- <span data-ttu-id="16f62-1089">passport photos</span><span class="sxs-lookup"><span data-stu-id="16f62-1089">passport photos</span></span>
- <span data-ttu-id="16f62-1090">certified translator</span><span class="sxs-lookup"><span data-stu-id="16f62-1090">certified translator</span></span>
- <span data-ttu-id="16f62-1091">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="16f62-1091">canadian citizens</span></span>
- <span data-ttu-id="16f62-1092">processing times</span><span class="sxs-lookup"><span data-stu-id="16f62-1092">processing times</span></span>
- <span data-ttu-id="16f62-1093">renewal application</span><span class="sxs-lookup"><span data-stu-id="16f62-1093">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="16f62-1094">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-1094">Keyword_passport</span></span>

- <span data-ttu-id="16f62-1095">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16f62-1095">Passport Number</span></span>
- <span data-ttu-id="16f62-1096">Passport No</span><span class="sxs-lookup"><span data-stu-id="16f62-1096">Passport No</span></span>
- <span data-ttu-id="16f62-1097">Passport #</span><span class="sxs-lookup"><span data-stu-id="16f62-1097">Passport #</span></span>
- <span data-ttu-id="16f62-1098">Usuarios</span><span class="sxs-lookup"><span data-stu-id="16f62-1098">Passport#</span></span>
- <span data-ttu-id="16f62-1099">PassportID</span><span class="sxs-lookup"><span data-stu-id="16f62-1099">PassportID</span></span>
- <span data-ttu-id="16f62-1100">Passportno</span><span class="sxs-lookup"><span data-stu-id="16f62-1100">Passportno</span></span>
- <span data-ttu-id="16f62-1101">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-1101">passportnumber</span></span>
- <span data-ttu-id="16f62-1102">パスポート</span><span class="sxs-lookup"><span data-stu-id="16f62-1102">パスポート</span></span>
- <span data-ttu-id="16f62-1103">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16f62-1103">パスポート番号</span></span>
- <span data-ttu-id="16f62-1104">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16f62-1104">パスポートのNum</span></span>
- <span data-ttu-id="16f62-1105">パスポート #</span><span class="sxs-lookup"><span data-stu-id="16f62-1105">パスポート＃</span></span>
- <span data-ttu-id="16f62-1106">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16f62-1106">Numéro de passeport</span></span>
- <span data-ttu-id="16f62-1107">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16f62-1107">Passeport n °</span></span>
- <span data-ttu-id="16f62-1108">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16f62-1108">Passeport Non</span></span>
- <span data-ttu-id="16f62-1109">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-1109">Passeport #</span></span>
- <span data-ttu-id="16f62-1110">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-1110">Passeport#</span></span>
- <span data-ttu-id="16f62-1111">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16f62-1111">PasseportNon</span></span>
- <span data-ttu-id="16f62-1112">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16f62-1112">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="16f62-1113">Número de Identificación Personal de salud en Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="16f62-1113">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1114">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1114">Format</span></span>

<span data-ttu-id="16f62-1115">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1115">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1116">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1116">Pattern</span></span>

<span data-ttu-id="16f62-1117">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1117">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1118">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1118">Checksum</span></span>

<span data-ttu-id="16f62-1119">No</span><span class="sxs-lookup"><span data-stu-id="16f62-1119">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1120">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1120">Definition</span></span>

<span data-ttu-id="16f62-1121">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="16f62-1122">Se encuentran al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="16f62-1122">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1123">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1123">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="16f62-1124">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="16f62-1124">Keyword_canada_phin</span></span>

- <span data-ttu-id="16f62-1125">social insurance number</span><span class="sxs-lookup"><span data-stu-id="16f62-1125">social insurance number</span></span>
- <span data-ttu-id="16f62-1126">health information act</span><span class="sxs-lookup"><span data-stu-id="16f62-1126">health information act</span></span>
- <span data-ttu-id="16f62-1127">income tax information</span><span class="sxs-lookup"><span data-stu-id="16f62-1127">income tax information</span></span>
- <span data-ttu-id="16f62-1128">manitoba health</span><span class="sxs-lookup"><span data-stu-id="16f62-1128">manitoba health</span></span>
- <span data-ttu-id="16f62-1129">health registration</span><span class="sxs-lookup"><span data-stu-id="16f62-1129">health registration</span></span>
- <span data-ttu-id="16f62-1130">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="16f62-1130">prescription purchases</span></span>
- <span data-ttu-id="16f62-1131">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="16f62-1131">benefit eligibility</span></span>
- <span data-ttu-id="16f62-1132">personal health</span><span class="sxs-lookup"><span data-stu-id="16f62-1132">personal health</span></span>
- <span data-ttu-id="16f62-1133">power of attorney</span><span class="sxs-lookup"><span data-stu-id="16f62-1133">power of attorney</span></span>
- <span data-ttu-id="16f62-1134">registration number</span><span class="sxs-lookup"><span data-stu-id="16f62-1134">registration number</span></span>
- <span data-ttu-id="16f62-1135">personal health number</span><span class="sxs-lookup"><span data-stu-id="16f62-1135">personal health number</span></span>
- <span data-ttu-id="16f62-1136">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="16f62-1136">practitioner referral</span></span>
- <span data-ttu-id="16f62-1137">wellness professional</span><span class="sxs-lookup"><span data-stu-id="16f62-1137">wellness professional</span></span>
- <span data-ttu-id="16f62-1138">patient referral</span><span class="sxs-lookup"><span data-stu-id="16f62-1138">patient referral</span></span>
- <span data-ttu-id="16f62-1139">health and wellness</span><span class="sxs-lookup"><span data-stu-id="16f62-1139">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="16f62-1140">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="16f62-1140">Keyword_canada_provinces</span></span>

- <span data-ttu-id="16f62-1141">Nunavut</span><span class="sxs-lookup"><span data-stu-id="16f62-1141">Nunavut</span></span>
- <span data-ttu-id="16f62-1142">Quebec</span><span class="sxs-lookup"><span data-stu-id="16f62-1142">Quebec</span></span>
- <span data-ttu-id="16f62-1143">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="16f62-1143">Northwest Territories</span></span>
- <span data-ttu-id="16f62-1144">Ontario</span><span class="sxs-lookup"><span data-stu-id="16f62-1144">Ontario</span></span>
- <span data-ttu-id="16f62-1145">British Columbia</span><span class="sxs-lookup"><span data-stu-id="16f62-1145">British Columbia</span></span>
- <span data-ttu-id="16f62-1146">Alberta</span><span class="sxs-lookup"><span data-stu-id="16f62-1146">Alberta</span></span>
- <span data-ttu-id="16f62-1147">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="16f62-1147">Saskatchewan</span></span>
- <span data-ttu-id="16f62-1148">Manitoba</span><span class="sxs-lookup"><span data-stu-id="16f62-1148">Manitoba</span></span>
- <span data-ttu-id="16f62-1149">Yukon</span><span class="sxs-lookup"><span data-stu-id="16f62-1149">Yukon</span></span>
- <span data-ttu-id="16f62-1150">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="16f62-1150">Newfoundland and Labrador</span></span>
- <span data-ttu-id="16f62-1151">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="16f62-1151">New Brunswick</span></span>
- <span data-ttu-id="16f62-1152">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="16f62-1152">Nova Scotia</span></span>
- <span data-ttu-id="16f62-1153">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="16f62-1153">Prince Edward Island</span></span>
- <span data-ttu-id="16f62-1154">Canadá</span><span class="sxs-lookup"><span data-stu-id="16f62-1154">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="16f62-1155">Número de seguridad social de Canadá</span><span class="sxs-lookup"><span data-stu-id="16f62-1155">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1156">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1156">Format</span></span>

<span data-ttu-id="16f62-1157">Nueve dígitos con guiones opcionales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-1157">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1158">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1158">Pattern</span></span>

<span data-ttu-id="16f62-1159">Con formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1159">Formatted:</span></span>
- <span data-ttu-id="16f62-1160">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1160">Three digits</span></span> 
- <span data-ttu-id="16f62-1161">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="16f62-1161">A hyphen or space</span></span> 
- <span data-ttu-id="16f62-1162">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1162">Three digits</span></span> 
- <span data-ttu-id="16f62-1163">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="16f62-1163">A hyphen or space</span></span> 
- <span data-ttu-id="16f62-1164">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1164">Three digits</span></span>

<span data-ttu-id="16f62-1165">Sin formato: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1165">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1166">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1166">Checksum</span></span>

<span data-ttu-id="16f62-1167">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1167">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1168">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1168">Definition</span></span>

<span data-ttu-id="16f62-1169">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1169">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1170">La función Func_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1170">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1171">Al menos dos de cualquier combinación de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16f62-1171">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="16f62-1172">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="16f62-1172">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="16f62-1173">Se encuentra una palabra clave de Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="16f62-1173">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="16f62-1174">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-1174">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16f62-1175">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1175">The checksum passes.</span></span>

<span data-ttu-id="16f62-1176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1177">La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1177">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1178">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="16f62-1178">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="16f62-1179">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1179">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1180">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1180">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="16f62-1181">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="16f62-1181">Keyword_sin</span></span>

- <span data-ttu-id="16f62-1182">sin</span><span class="sxs-lookup"><span data-stu-id="16f62-1182">sin</span></span> 
- <span data-ttu-id="16f62-1183">social insurance</span><span class="sxs-lookup"><span data-stu-id="16f62-1183">social insurance</span></span> 
- <span data-ttu-id="16f62-1184">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="16f62-1184">numero d'assurance sociale</span></span> 
- <span data-ttu-id="16f62-1185">pecados</span><span class="sxs-lookup"><span data-stu-id="16f62-1185">sins</span></span> 
- <span data-ttu-id="16f62-1186">SSN</span><span class="sxs-lookup"><span data-stu-id="16f62-1186">ssn</span></span> 
- <span data-ttu-id="16f62-1187">SSN</span><span class="sxs-lookup"><span data-stu-id="16f62-1187">ssns</span></span> 
- <span data-ttu-id="16f62-1188">social security</span><span class="sxs-lookup"><span data-stu-id="16f62-1188">social security</span></span> 
- <span data-ttu-id="16f62-1189">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="16f62-1189">numero d'assurance social</span></span> 
- <span data-ttu-id="16f62-1190">national identification number</span><span class="sxs-lookup"><span data-stu-id="16f62-1190">national identification number</span></span> 
- <span data-ttu-id="16f62-1191">national id</span><span class="sxs-lookup"><span data-stu-id="16f62-1191">national id</span></span> 
- <span data-ttu-id="16f62-1192">PIN</span><span class="sxs-lookup"><span data-stu-id="16f62-1192">sin#</span></span> 
- <span data-ttu-id="16f62-1193">soc ins</span><span class="sxs-lookup"><span data-stu-id="16f62-1193">soc ins</span></span> 
- <span data-ttu-id="16f62-1194">social ins</span><span class="sxs-lookup"><span data-stu-id="16f62-1194">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="16f62-1195">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="16f62-1195">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="16f62-1196">driver's license</span><span class="sxs-lookup"><span data-stu-id="16f62-1196">driver's license</span></span> 
- <span data-ttu-id="16f62-1197">drivers license</span><span class="sxs-lookup"><span data-stu-id="16f62-1197">drivers license</span></span> 
- <span data-ttu-id="16f62-1198">driver's licence</span><span class="sxs-lookup"><span data-stu-id="16f62-1198">driver's licence</span></span> 
- <span data-ttu-id="16f62-1199">drivers licence</span><span class="sxs-lookup"><span data-stu-id="16f62-1199">drivers licence</span></span> 
- <span data-ttu-id="16f62-1200">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="16f62-1200">DOB</span></span> 
- <span data-ttu-id="16f62-1201">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-1201">Birthdate</span></span> 
- <span data-ttu-id="16f62-1202">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="16f62-1202">Birthday</span></span> 
- <span data-ttu-id="16f62-1203">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-1203">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="16f62-1204">	Número de tarjeta de identidad de Chile</span><span class="sxs-lookup"><span data-stu-id="16f62-1204">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1205">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1205">Format</span></span>

<span data-ttu-id="16f62-1206">7-8 dígitos más delimitadores, un dígito de control o una letra</span><span class="sxs-lookup"><span data-stu-id="16f62-1206">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1207">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1207">Pattern</span></span>

<span data-ttu-id="16f62-1208">7 u 8 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="16f62-1208">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="16f62-1209">1 o 2 dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-1209">1-2 digits</span></span> 
- <span data-ttu-id="16f62-1210">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-1210">A period</span></span> 
- <span data-ttu-id="16f62-1211">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1211">Three digits</span></span> 
- <span data-ttu-id="16f62-1212">Un punto </span><span class="sxs-lookup"><span data-stu-id="16f62-1212">A period</span></span> 
- <span data-ttu-id="16f62-1213">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1213">Three digits</span></span> 
- <span data-ttu-id="16f62-1214">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-1214">A dash</span></span> 
- <span data-ttu-id="16f62-1215">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-1215">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1216">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1216">Checksum</span></span>

<span data-ttu-id="16f62-1217">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1217">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1218">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1218">Definition</span></span>

<span data-ttu-id="16f62-1219">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1219">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1220">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1220">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1221">Se encuentra una palabra clave de Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-1221">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="16f62-1222">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1222">The checksum passes.</span></span>

<span data-ttu-id="16f62-1223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1224">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1224">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1225">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1225">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1226">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1226">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="16f62-1227">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="16f62-1227">Keyword_chile_id_card</span></span>

- <span data-ttu-id="16f62-1228">Número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="16f62-1228">National Identification Number</span></span> 
- <span data-ttu-id="16f62-1229">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-1229">Identity card</span></span> 
- <span data-ttu-id="16f62-1230">Id.</span><span class="sxs-lookup"><span data-stu-id="16f62-1230">ID</span></span> 
- <span data-ttu-id="16f62-1231">Determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-1231">Identification</span></span> 
- <span data-ttu-id="16f62-1232">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="16f62-1232">Rol Único Nacional</span></span> 
- <span data-ttu-id="16f62-1233">REALIZAR</span><span class="sxs-lookup"><span data-stu-id="16f62-1233">RUN</span></span> 
- <span data-ttu-id="16f62-1234">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="16f62-1234">Rol Único Tributario</span></span> 
- <span data-ttu-id="16f62-1235">ESTANCARSE</span><span class="sxs-lookup"><span data-stu-id="16f62-1235">RUT</span></span> 
- <span data-ttu-id="16f62-1236">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-1236">Cédula de Identidad</span></span> 
- <span data-ttu-id="16f62-1237">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="16f62-1237">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="16f62-1238">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="16f62-1238">Tarjeta de identificación</span></span> 
- <span data-ttu-id="16f62-1239">Identificación</span><span class="sxs-lookup"><span data-stu-id="16f62-1239">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="16f62-1240">	Número de tarjeta de identidad de residente de China (PRC)</span><span class="sxs-lookup"><span data-stu-id="16f62-1240">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1241">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1241">Format</span></span>

<span data-ttu-id="16f62-1242">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1242">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1243">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1243">Pattern</span></span>

<span data-ttu-id="16f62-1244">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-1244">18 digits:</span></span>
- <span data-ttu-id="16f62-1245">Seis dígitos que son un código de dirección </span><span class="sxs-lookup"><span data-stu-id="16f62-1245">Six digits which are an address code</span></span> 
- <span data-ttu-id="16f62-1246">Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-1246">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16f62-1247">Tres dígitos que son un código de pedido </span><span class="sxs-lookup"><span data-stu-id="16f62-1247">Three digits which are an order code</span></span> 
- <span data-ttu-id="16f62-1248">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-1248">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1249">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1249">Checksum</span></span>

<span data-ttu-id="16f62-1250">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1250">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1251">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1251">Definition</span></span>

<span data-ttu-id="16f62-1252">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1252">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1253">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1253">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1254">Se encuentra una palabra clave de Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="16f62-1254">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="16f62-1255">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1255">The checksum passes.</span></span>

<span data-ttu-id="16f62-1256">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1256">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1257">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1257">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1258">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1258">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1259">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1259">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="16f62-1260">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="16f62-1260">Keyword_china_resident_id</span></span>

- <span data-ttu-id="16f62-1261">Tarjeta de identidad de residente</span><span class="sxs-lookup"><span data-stu-id="16f62-1261">Resident Identity Card</span></span> 
- <span data-ttu-id="16f62-1262">China</span><span class="sxs-lookup"><span data-stu-id="16f62-1262">PRC</span></span> 
- <span data-ttu-id="16f62-1263">Tarjeta de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="16f62-1263">National Identification Card</span></span> 
- <span data-ttu-id="16f62-1264">身份证</span><span class="sxs-lookup"><span data-stu-id="16f62-1264">身份证</span></span> 
- <span data-ttu-id="16f62-1265">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="16f62-1265">居民 身份证</span></span> 
- <span data-ttu-id="16f62-1266">居民身份证</span><span class="sxs-lookup"><span data-stu-id="16f62-1266">居民身份证</span></span> 
- <span data-ttu-id="16f62-1267">鉴定</span><span class="sxs-lookup"><span data-stu-id="16f62-1267">鉴定</span></span> 
- <span data-ttu-id="16f62-1268">身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-1268">身分證</span></span> 
- <span data-ttu-id="16f62-1269">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-1269">居民 身份證</span></span>
- <span data-ttu-id="16f62-1270">鑑定</span><span class="sxs-lookup"><span data-stu-id="16f62-1270">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="16f62-1271">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1271">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1272">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1272">Format</span></span>

<span data-ttu-id="16f62-1273">16 dígitos que pueden ser formateados o sin formato (dddddddddddddddd) y deben pasar la prueba Luhn.</span><span class="sxs-lookup"><span data-stu-id="16f62-1273">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1274">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1274">Pattern</span></span>

<span data-ttu-id="16f62-1275">Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.</span><span class="sxs-lookup"><span data-stu-id="16f62-1275">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1276">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1276">Checksum</span></span>

<span data-ttu-id="16f62-1277">Sí, la suma de comprobación de Luhn</span><span class="sxs-lookup"><span data-stu-id="16f62-1277">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1278">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1278">Definition</span></span>

<span data-ttu-id="16f62-1279">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1279">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1280">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1280">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1281">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-1281">One of the following is true:</span></span>
    - <span data-ttu-id="16f62-1282">Se encuentra una palabra clave de Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="16f62-1282">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="16f62-1283">Se encuentra una palabra clave de Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="16f62-1283">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="16f62-1284">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-1284">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16f62-1285">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1285">The checksum passes.</span></span>

<span data-ttu-id="16f62-1286">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1286">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1287">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1287">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1288">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1288">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1289">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1289">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="16f62-1290">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="16f62-1290">Keyword_cc_verification</span></span>

- <span data-ttu-id="16f62-1291">card verification</span><span class="sxs-lookup"><span data-stu-id="16f62-1291">card verification</span></span>
- <span data-ttu-id="16f62-1292">card identification number</span><span class="sxs-lookup"><span data-stu-id="16f62-1292">card identification number</span></span>
- <span data-ttu-id="16f62-1293">CVN</span><span class="sxs-lookup"><span data-stu-id="16f62-1293">cvn</span></span>
- <span data-ttu-id="16f62-1294">cid</span><span class="sxs-lookup"><span data-stu-id="16f62-1294">cid</span></span>
- <span data-ttu-id="16f62-1295">CVC2</span><span class="sxs-lookup"><span data-stu-id="16f62-1295">cvc2</span></span>
- <span data-ttu-id="16f62-1296">CVV2</span><span class="sxs-lookup"><span data-stu-id="16f62-1296">cvv2</span></span>
- <span data-ttu-id="16f62-1297">pin block</span><span class="sxs-lookup"><span data-stu-id="16f62-1297">pin block</span></span>
- <span data-ttu-id="16f62-1298">security code</span><span class="sxs-lookup"><span data-stu-id="16f62-1298">security code</span></span>
- <span data-ttu-id="16f62-1299">security number</span><span class="sxs-lookup"><span data-stu-id="16f62-1299">security number</span></span>
- <span data-ttu-id="16f62-1300">security no</span><span class="sxs-lookup"><span data-stu-id="16f62-1300">security no</span></span>
- <span data-ttu-id="16f62-1301">issue number</span><span class="sxs-lookup"><span data-stu-id="16f62-1301">issue number</span></span>
- <span data-ttu-id="16f62-1302">issue no</span><span class="sxs-lookup"><span data-stu-id="16f62-1302">issue no</span></span>
- <span data-ttu-id="16f62-1303">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="16f62-1303">cryptogramme</span></span>
- <span data-ttu-id="16f62-1304">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="16f62-1304">numéro de sécurité</span></span>
- <span data-ttu-id="16f62-1305">numero de securite</span><span class="sxs-lookup"><span data-stu-id="16f62-1305">numero de securite</span></span>
- <span data-ttu-id="16f62-1306">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1306">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="16f62-1307">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1307">kreditkartenprufnummer</span></span>
- <span data-ttu-id="16f62-1308">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="16f62-1308">prüfziffer</span></span>
- <span data-ttu-id="16f62-1309">prufziffer</span><span class="sxs-lookup"><span data-stu-id="16f62-1309">prufziffer</span></span>
- <span data-ttu-id="16f62-1310">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="16f62-1310">sicherheits Kode</span></span>
- <span data-ttu-id="16f62-1311">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="16f62-1311">sicherheitscode</span></span>
- <span data-ttu-id="16f62-1312">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1312">sicherheitsnummer</span></span>
- <span data-ttu-id="16f62-1313">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="16f62-1313">verfalldatum</span></span>
- <span data-ttu-id="16f62-1314">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="16f62-1314">codice di verifica</span></span>
- <span data-ttu-id="16f62-1315">COD.</span><span class="sxs-lookup"><span data-stu-id="16f62-1315">cod.</span></span> <span data-ttu-id="16f62-1316">sicurezza</span><span class="sxs-lookup"><span data-stu-id="16f62-1316">sicurezza</span></span>
- <span data-ttu-id="16f62-1317">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="16f62-1317">cod sicurezza</span></span>
- <span data-ttu-id="16f62-1318">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="16f62-1318">n autorizzazione</span></span>
- <span data-ttu-id="16f62-1319">Código</span><span class="sxs-lookup"><span data-stu-id="16f62-1319">código</span></span>
- <span data-ttu-id="16f62-1320">codigo</span><span class="sxs-lookup"><span data-stu-id="16f62-1320">codigo</span></span>
- <span data-ttu-id="16f62-1321">COD.</span><span class="sxs-lookup"><span data-stu-id="16f62-1321">cod.</span></span> <span data-ttu-id="16f62-1322">seg</span><span class="sxs-lookup"><span data-stu-id="16f62-1322">seg</span></span>
- <span data-ttu-id="16f62-1323">cod seg</span><span class="sxs-lookup"><span data-stu-id="16f62-1323">cod seg</span></span>
- <span data-ttu-id="16f62-1324">código de segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1324">código de segurança</span></span>
- <span data-ttu-id="16f62-1325">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="16f62-1325">codigo de seguranca</span></span>
- <span data-ttu-id="16f62-1326">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1326">codigo de segurança</span></span>
- <span data-ttu-id="16f62-1327">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="16f62-1327">código de seguranca</span></span>
- <span data-ttu-id="16f62-1328">campos.</span><span class="sxs-lookup"><span data-stu-id="16f62-1328">cód.</span></span> <span data-ttu-id="16f62-1329">segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1329">segurança</span></span>
- <span data-ttu-id="16f62-1330">COD.</span><span class="sxs-lookup"><span data-stu-id="16f62-1330">cod.</span></span> <span data-ttu-id="16f62-1331">DQO SEGURANCA.</span><span class="sxs-lookup"><span data-stu-id="16f62-1331">seguranca cod.</span></span> <span data-ttu-id="16f62-1332">segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1332">segurança</span></span>
- <span data-ttu-id="16f62-1333">campos.</span><span class="sxs-lookup"><span data-stu-id="16f62-1333">cód.</span></span> <span data-ttu-id="16f62-1334">SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="16f62-1334">seguranca</span></span>
- <span data-ttu-id="16f62-1335">cód segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1335">cód segurança</span></span>
- <span data-ttu-id="16f62-1336">Bacalao SEGURANCA contra reembolso de segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1336">cod seguranca cod segurança</span></span>
- <span data-ttu-id="16f62-1337">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="16f62-1337">cód seguranca</span></span>
- <span data-ttu-id="16f62-1338">número de verificação</span><span class="sxs-lookup"><span data-stu-id="16f62-1338">número de verificação</span></span>
- <span data-ttu-id="16f62-1339">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="16f62-1339">numero de verificacao</span></span>
- <span data-ttu-id="16f62-1340">ablauf</span><span class="sxs-lookup"><span data-stu-id="16f62-1340">ablauf</span></span>
- <span data-ttu-id="16f62-1341">gültig bis</span><span class="sxs-lookup"><span data-stu-id="16f62-1341">gültig bis</span></span>
- <span data-ttu-id="16f62-1342">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16f62-1342">gültigkeitsdatum</span></span>
- <span data-ttu-id="16f62-1343">gultig bis</span><span class="sxs-lookup"><span data-stu-id="16f62-1343">gultig bis</span></span>
- <span data-ttu-id="16f62-1344">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16f62-1344">gultigkeitsdatum</span></span>
- <span data-ttu-id="16f62-1345">scadenza</span><span class="sxs-lookup"><span data-stu-id="16f62-1345">scadenza</span></span>
- <span data-ttu-id="16f62-1346">data scad</span><span class="sxs-lookup"><span data-stu-id="16f62-1346">data scad</span></span>
- <span data-ttu-id="16f62-1347">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="16f62-1347">fecha de expiracion</span></span>
- <span data-ttu-id="16f62-1348">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="16f62-1348">fecha de venc</span></span>
- <span data-ttu-id="16f62-1349">1er</span><span class="sxs-lookup"><span data-stu-id="16f62-1349">vencimiento</span></span>
- <span data-ttu-id="16f62-1350">válido hasta</span><span class="sxs-lookup"><span data-stu-id="16f62-1350">válido hasta</span></span>
- <span data-ttu-id="16f62-1351">valido hasta</span><span class="sxs-lookup"><span data-stu-id="16f62-1351">valido hasta</span></span>
- <span data-ttu-id="16f62-1352">vto</span><span class="sxs-lookup"><span data-stu-id="16f62-1352">vto</span></span>
- <span data-ttu-id="16f62-1353">data de expiração</span><span class="sxs-lookup"><span data-stu-id="16f62-1353">data de expiração</span></span>
- <span data-ttu-id="16f62-1354">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="16f62-1354">data de expiracao</span></span>
- <span data-ttu-id="16f62-1355">data em que expira</span><span class="sxs-lookup"><span data-stu-id="16f62-1355">data em que expira</span></span>
- <span data-ttu-id="16f62-1356">validade</span><span class="sxs-lookup"><span data-stu-id="16f62-1356">validade</span></span>
- <span data-ttu-id="16f62-1357">valorar</span><span class="sxs-lookup"><span data-stu-id="16f62-1357">valor</span></span>
- <span data-ttu-id="16f62-1358">vencimento</span><span class="sxs-lookup"><span data-stu-id="16f62-1358">vencimento</span></span>
- <span data-ttu-id="16f62-1359">Venc</span><span class="sxs-lookup"><span data-stu-id="16f62-1359">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="16f62-1360">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="16f62-1360">Keyword_cc_name</span></span>

- <span data-ttu-id="16f62-1361">AMEX</span><span class="sxs-lookup"><span data-stu-id="16f62-1361">amex</span></span>
- <span data-ttu-id="16f62-1362">american express</span><span class="sxs-lookup"><span data-stu-id="16f62-1362">american express</span></span>
- <span data-ttu-id="16f62-1363">americanexpress</span><span class="sxs-lookup"><span data-stu-id="16f62-1363">americanexpress</span></span>
- <span data-ttu-id="16f62-1364">Régimen</span><span class="sxs-lookup"><span data-stu-id="16f62-1364">Visa</span></span>
- <span data-ttu-id="16f62-1365">MasterCard</span><span class="sxs-lookup"><span data-stu-id="16f62-1365">mastercard</span></span>
- <span data-ttu-id="16f62-1366">master card</span><span class="sxs-lookup"><span data-stu-id="16f62-1366">master card</span></span>
- <span data-ttu-id="16f62-1367">valuación</span><span class="sxs-lookup"><span data-stu-id="16f62-1367">mc</span></span> 
- <span data-ttu-id="16f62-1368">MasterCard</span><span class="sxs-lookup"><span data-stu-id="16f62-1368">mastercards</span></span>
- <span data-ttu-id="16f62-1369">master cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1369">master cards</span></span>
- <span data-ttu-id="16f62-1370">diner's Club</span><span class="sxs-lookup"><span data-stu-id="16f62-1370">diner's Club</span></span>
- <span data-ttu-id="16f62-1371">diners club</span><span class="sxs-lookup"><span data-stu-id="16f62-1371">diners club</span></span>
- <span data-ttu-id="16f62-1372">DinersClub</span><span class="sxs-lookup"><span data-stu-id="16f62-1372">dinersclub</span></span>
- <span data-ttu-id="16f62-1373">discover card</span><span class="sxs-lookup"><span data-stu-id="16f62-1373">discover card</span></span>
- <span data-ttu-id="16f62-1374">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1374">discovercard</span></span>
- <span data-ttu-id="16f62-1375">discover cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1375">discover cards</span></span>
- <span data-ttu-id="16f62-1376">JCB</span><span class="sxs-lookup"><span data-stu-id="16f62-1376">JCB</span></span>
- <span data-ttu-id="16f62-1377">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="16f62-1377">japanese card bureau</span></span>
- <span data-ttu-id="16f62-1378">carte blanche</span><span class="sxs-lookup"><span data-stu-id="16f62-1378">carte blanche</span></span>
- <span data-ttu-id="16f62-1379">carteblanche</span><span class="sxs-lookup"><span data-stu-id="16f62-1379">carteblanche</span></span>
- <span data-ttu-id="16f62-1380">credit card</span><span class="sxs-lookup"><span data-stu-id="16f62-1380">credit card</span></span>
- <span data-ttu-id="16f62-1381">CC</span><span class="sxs-lookup"><span data-stu-id="16f62-1381">cc#</span></span>
- <span data-ttu-id="16f62-1382"># CC:</span><span class="sxs-lookup"><span data-stu-id="16f62-1382">cc#:</span></span>
- <span data-ttu-id="16f62-1383">expiration date</span><span class="sxs-lookup"><span data-stu-id="16f62-1383">expiration date</span></span>
- <span data-ttu-id="16f62-1384">exp date</span><span class="sxs-lookup"><span data-stu-id="16f62-1384">exp date</span></span>
- <span data-ttu-id="16f62-1385">expiry date</span><span class="sxs-lookup"><span data-stu-id="16f62-1385">expiry date</span></span>
- <span data-ttu-id="16f62-1386">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="16f62-1386">date d’expiration</span></span>
- <span data-ttu-id="16f62-1387">date d'exp</span><span class="sxs-lookup"><span data-stu-id="16f62-1387">date d'exp</span></span>
- <span data-ttu-id="16f62-1388">date expiration</span><span class="sxs-lookup"><span data-stu-id="16f62-1388">date expiration</span></span>
- <span data-ttu-id="16f62-1389">bank card</span><span class="sxs-lookup"><span data-stu-id="16f62-1389">bank card</span></span>
- <span data-ttu-id="16f62-1390">Bankcard</span><span class="sxs-lookup"><span data-stu-id="16f62-1390">bankcard</span></span>
- <span data-ttu-id="16f62-1391">card number</span><span class="sxs-lookup"><span data-stu-id="16f62-1391">card number</span></span>
- <span data-ttu-id="16f62-1392">card num</span><span class="sxs-lookup"><span data-stu-id="16f62-1392">card num</span></span>
- <span data-ttu-id="16f62-1393">cardNumber</span><span class="sxs-lookup"><span data-stu-id="16f62-1393">cardnumber</span></span>
- <span data-ttu-id="16f62-1394">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="16f62-1394">cardnumbers</span></span>
- <span data-ttu-id="16f62-1395">card numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-1395">card numbers</span></span>
- <span data-ttu-id="16f62-1396">crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1396">creditcard</span></span>
- <span data-ttu-id="16f62-1397">credit cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1397">credit cards</span></span>
- <span data-ttu-id="16f62-1398">creditcards</span><span class="sxs-lookup"><span data-stu-id="16f62-1398">creditcards</span></span>
- <span data-ttu-id="16f62-1399">CCN</span><span class="sxs-lookup"><span data-stu-id="16f62-1399">ccn</span></span>
- <span data-ttu-id="16f62-1400">card holder</span><span class="sxs-lookup"><span data-stu-id="16f62-1400">card holder</span></span>
- <span data-ttu-id="16f62-1401">titular</span><span class="sxs-lookup"><span data-stu-id="16f62-1401">cardholder</span></span>
- <span data-ttu-id="16f62-1402">card holders</span><span class="sxs-lookup"><span data-stu-id="16f62-1402">card holders</span></span>
- <span data-ttu-id="16f62-1403">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="16f62-1403">cardholders</span></span>
- <span data-ttu-id="16f62-1404">check card</span><span class="sxs-lookup"><span data-stu-id="16f62-1404">check card</span></span>
- <span data-ttu-id="16f62-1405">Checkcard</span><span class="sxs-lookup"><span data-stu-id="16f62-1405">checkcard</span></span>
- <span data-ttu-id="16f62-1406">check cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1406">check cards</span></span>
- <span data-ttu-id="16f62-1407">checkcards</span><span class="sxs-lookup"><span data-stu-id="16f62-1407">checkcards</span></span>
- <span data-ttu-id="16f62-1408">debit card</span><span class="sxs-lookup"><span data-stu-id="16f62-1408">debit card</span></span>
- <span data-ttu-id="16f62-1409">debitcard</span><span class="sxs-lookup"><span data-stu-id="16f62-1409">debitcard</span></span>
- <span data-ttu-id="16f62-1410">debit cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1410">debit cards</span></span>
- <span data-ttu-id="16f62-1411">DebitCards</span><span class="sxs-lookup"><span data-stu-id="16f62-1411">debitcards</span></span>
- <span data-ttu-id="16f62-1412">atm card</span><span class="sxs-lookup"><span data-stu-id="16f62-1412">atm card</span></span>
- <span data-ttu-id="16f62-1413">atmcard</span><span class="sxs-lookup"><span data-stu-id="16f62-1413">atmcard</span></span>
- <span data-ttu-id="16f62-1414">atm cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1414">atm cards</span></span>
- <span data-ttu-id="16f62-1415">atmcards</span><span class="sxs-lookup"><span data-stu-id="16f62-1415">atmcards</span></span>
- <span data-ttu-id="16f62-1416">enrutar</span><span class="sxs-lookup"><span data-stu-id="16f62-1416">enroute</span></span>
- <span data-ttu-id="16f62-1417">en route</span><span class="sxs-lookup"><span data-stu-id="16f62-1417">en route</span></span>
- <span data-ttu-id="16f62-1418">card type</span><span class="sxs-lookup"><span data-stu-id="16f62-1418">card type</span></span>
- <span data-ttu-id="16f62-1419">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="16f62-1419">carte bancaire</span></span>
- <span data-ttu-id="16f62-1420">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="16f62-1420">carte de crédit</span></span>
- <span data-ttu-id="16f62-1421">carte de credit</span><span class="sxs-lookup"><span data-stu-id="16f62-1421">carte de credit</span></span>
- <span data-ttu-id="16f62-1422">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1422">numéro de carte</span></span>
- <span data-ttu-id="16f62-1423">numero de carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1423">numero de carte</span></span>
- <span data-ttu-id="16f62-1424">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1424">nº de la carte</span></span>
- <span data-ttu-id="16f62-1425">nº de carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1425">nº de carte</span></span>
- <span data-ttu-id="16f62-1426">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="16f62-1426">kreditkarte</span></span>
- <span data-ttu-id="16f62-1427">Karte</span><span class="sxs-lookup"><span data-stu-id="16f62-1427">karte</span></span>
- <span data-ttu-id="16f62-1428">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="16f62-1428">karteninhaber</span></span>
- <span data-ttu-id="16f62-1429">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="16f62-1429">karteninhabers</span></span>
- <span data-ttu-id="16f62-1430">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="16f62-1430">kreditkarteninhaber</span></span>
- <span data-ttu-id="16f62-1431">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="16f62-1431">kreditkarteninstitut</span></span>
- <span data-ttu-id="16f62-1432">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="16f62-1432">kreditkartentyp</span></span>
- <span data-ttu-id="16f62-1433">eigentümername</span><span class="sxs-lookup"><span data-stu-id="16f62-1433">eigentümername</span></span>
- <span data-ttu-id="16f62-1434">kartennr</span><span class="sxs-lookup"><span data-stu-id="16f62-1434">kartennr</span></span> 
- <span data-ttu-id="16f62-1435">kartennummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1435">kartennummer</span></span>
- <span data-ttu-id="16f62-1436">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1436">kreditkartennummer</span></span>
- <span data-ttu-id="16f62-1437">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1437">kreditkarten-nummer</span></span>
- <span data-ttu-id="16f62-1438">carta di credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1438">carta di credito</span></span>
- <span data-ttu-id="16f62-1439">carta credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1439">carta credito</span></span>
- <span data-ttu-id="16f62-1440">cobro</span><span class="sxs-lookup"><span data-stu-id="16f62-1440">carta</span></span>
- <span data-ttu-id="16f62-1441">n carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1441">n carta</span></span>
- <span data-ttu-id="16f62-1442">Nº.</span><span class="sxs-lookup"><span data-stu-id="16f62-1442">nr.</span></span> <span data-ttu-id="16f62-1443">cobro</span><span class="sxs-lookup"><span data-stu-id="16f62-1443">carta</span></span>
- <span data-ttu-id="16f62-1444">nr carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1444">nr carta</span></span>
- <span data-ttu-id="16f62-1445">numero carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1445">numero carta</span></span>
- <span data-ttu-id="16f62-1446">numero della carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1446">numero della carta</span></span>
- <span data-ttu-id="16f62-1447">numero di carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1447">numero di carta</span></span>
- <span data-ttu-id="16f62-1448">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1448">tarjeta credito</span></span>
- <span data-ttu-id="16f62-1449">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1449">tarjeta de credito</span></span>
- <span data-ttu-id="16f62-1450">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1450">tarjeta crédito</span></span>
- <span data-ttu-id="16f62-1451">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1451">tarjeta de crédito</span></span>
- <span data-ttu-id="16f62-1452">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="16f62-1452">tarjeta de atm</span></span>
- <span data-ttu-id="16f62-1453">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="16f62-1453">tarjeta atm</span></span>
- <span data-ttu-id="16f62-1454">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1454">tarjeta debito</span></span>
- <span data-ttu-id="16f62-1455">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1455">tarjeta de debito</span></span>
- <span data-ttu-id="16f62-1456">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="16f62-1456">tarjeta débito</span></span>
- <span data-ttu-id="16f62-1457">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="16f62-1457">tarjeta de débito</span></span>
- <span data-ttu-id="16f62-1458">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1458">nº de tarjeta</span></span>
- <span data-ttu-id="16f62-1459">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1459">no.</span></span> <span data-ttu-id="16f62-1460">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1460">de tarjeta</span></span>
- <span data-ttu-id="16f62-1461">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1461">no de tarjeta</span></span>
- <span data-ttu-id="16f62-1462">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1462">numero de tarjeta</span></span>
- <span data-ttu-id="16f62-1463">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1463">número de tarjeta</span></span>
- <span data-ttu-id="16f62-1464">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="16f62-1464">tarjeta no</span></span>
- <span data-ttu-id="16f62-1465">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="16f62-1465">tarjetahabiente</span></span>
- <span data-ttu-id="16f62-1466">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1466">cartão de crédito</span></span>
- <span data-ttu-id="16f62-1467">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1467">cartão de credito</span></span>
- <span data-ttu-id="16f62-1468">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1468">cartao de crédito</span></span>
- <span data-ttu-id="16f62-1469">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1469">cartao de credito</span></span>
- <span data-ttu-id="16f62-1470">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="16f62-1470">cartão de débito</span></span>
- <span data-ttu-id="16f62-1471">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="16f62-1471">cartao de débito</span></span>
- <span data-ttu-id="16f62-1472">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1472">cartão de debito</span></span>
- <span data-ttu-id="16f62-1473">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1473">cartao de debito</span></span>
- <span data-ttu-id="16f62-1474">débito automático</span><span class="sxs-lookup"><span data-stu-id="16f62-1474">débito automático</span></span>
- <span data-ttu-id="16f62-1475">debito automatico</span><span class="sxs-lookup"><span data-stu-id="16f62-1475">debito automatico</span></span>
- <span data-ttu-id="16f62-1476">número do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1476">número do cartão</span></span>
- <span data-ttu-id="16f62-1477">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1477">numero do cartão</span></span> 
- <span data-ttu-id="16f62-1478">número do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1478">número do cartao</span></span>
- <span data-ttu-id="16f62-1479">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1479">numero do cartao</span></span>
- <span data-ttu-id="16f62-1480">número de cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1480">número de cartão</span></span>
- <span data-ttu-id="16f62-1481">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1481">numero de cartão</span></span>
- <span data-ttu-id="16f62-1482">número de cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1482">número de cartao</span></span>
- <span data-ttu-id="16f62-1483">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1483">numero de cartao</span></span>
- <span data-ttu-id="16f62-1484">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1484">nº do cartão</span></span>
- <span data-ttu-id="16f62-1485">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1485">nº do cartao</span></span>
- <span data-ttu-id="16f62-1486">Nº.</span><span class="sxs-lookup"><span data-stu-id="16f62-1486">nº.</span></span> <span data-ttu-id="16f62-1487">do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1487">do cartão</span></span>
- <span data-ttu-id="16f62-1488">no do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1488">no do cartão</span></span>
- <span data-ttu-id="16f62-1489">no do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1489">no do cartao</span></span>
- <span data-ttu-id="16f62-1490">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1490">no.</span></span> <span data-ttu-id="16f62-1491">do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1491">do cartão</span></span>
- <span data-ttu-id="16f62-1492">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1492">no.</span></span> <span data-ttu-id="16f62-1493">do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1493">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="16f62-1494">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="16f62-1494">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1495">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1495">Format</span></span>

<span data-ttu-id="16f62-1496">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1496">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1497">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1497">Pattern</span></span>

<span data-ttu-id="16f62-1498">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-1498">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1499">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1499">Checksum</span></span>

<span data-ttu-id="16f62-1500">No</span><span class="sxs-lookup"><span data-stu-id="16f62-1500">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1501">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1501">Definition</span></span>

<span data-ttu-id="16f62-1502">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1502">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1503">La función Func_croatia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1503">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1504">Se encuentra una palabra clave de Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-1504">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-1505">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1505">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="16f62-1506">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="16f62-1506">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="16f62-1507">Tarjeta de identidad croata</span><span class="sxs-lookup"><span data-stu-id="16f62-1507">Croatian identity card</span></span>
- <span data-ttu-id="16f62-1508">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="16f62-1508">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="16f62-1509">Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="16f62-1509">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1510">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1510">Format</span></span>

<span data-ttu-id="16f62-1511">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1511">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1512">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1512">Pattern</span></span>

<span data-ttu-id="16f62-1513">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-1513">11 digits:</span></span>
- <span data-ttu-id="16f62-1514">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1514">10 digits</span></span> 
- <span data-ttu-id="16f62-1515">El dígito final es un dígito de control para el intercambio internacional de datos, se agregan las letras h antes de los once dígitos.</span><span class="sxs-lookup"><span data-stu-id="16f62-1515">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1516">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1516">Checksum</span></span>

<span data-ttu-id="16f62-1517">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1518">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1518">Definition</span></span>

<span data-ttu-id="16f62-1519">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1520">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1520">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1521">Se encuentra una palabra clave de Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-1521">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="16f62-1522">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1522">The checksum passes.</span></span>

<span data-ttu-id="16f62-1523">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1523">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1524">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1524">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1525">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1525">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1526">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1526">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="16f62-1527">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="16f62-1527">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="16f62-1528">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="16f62-1528">Personal Identification Number</span></span>
- <span data-ttu-id="16f62-1529">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="16f62-1529">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="16f62-1530">OIB</span><span class="sxs-lookup"><span data-stu-id="16f62-1530">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="16f62-1531">Número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="16f62-1531">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1532">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1532">Format</span></span>

<span data-ttu-id="16f62-1533">Nueve dígitos con barra diagonal (formato antiguo) 10 dígitos con barra diagonal (nuevo formato) opcional</span><span class="sxs-lookup"><span data-stu-id="16f62-1533">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1534">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1534">Pattern</span></span>

<span data-ttu-id="16f62-1535">Nueve dígitos (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="16f62-1535">Nine digits (old format):</span></span>
- <span data-ttu-id="16f62-1536">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1536">Nine digits</span></span>

<span data-ttu-id="16f62-1537">O</span><span class="sxs-lookup"><span data-stu-id="16f62-1537">OR</span></span>

- <span data-ttu-id="16f62-1538">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-1538">Six digits that represent date of birth</span></span>
- <span data-ttu-id="16f62-1539">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="16f62-1539">A forward slash</span></span>
- <span data-ttu-id="16f62-1540">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1540">Three digits</span></span>

<span data-ttu-id="16f62-1541">10 dígitos (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="16f62-1541">10 digits (new format):</span></span>
- <span data-ttu-id="16f62-1542">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1542">10 digits</span></span>

<span data-ttu-id="16f62-1543">O</span><span class="sxs-lookup"><span data-stu-id="16f62-1543">OR</span></span>

- <span data-ttu-id="16f62-1544">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-1544">Six digits that represent date of birth</span></span>
- <span data-ttu-id="16f62-1545">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="16f62-1545">A forward slash</span></span> 
- <span data-ttu-id="16f62-1546">Cuatro dígitos donde el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-1546">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1547">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1547">Checksum</span></span>

<span data-ttu-id="16f62-1548">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1549">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1549">Definition</span></span>

<span data-ttu-id="16f62-1550">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_czech_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="16f62-1551">Se encuentra una palabra clave de Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-1551">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="16f62-1552">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1552">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="16f62-1553">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1553">Keywords</span></span>

- <span data-ttu-id="16f62-1554">número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="16f62-1554">czech personal identity number</span></span>
- <span data-ttu-id="16f62-1555">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="16f62-1555">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="16f62-1556">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="16f62-1556">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1557">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1557">Format</span></span>

<span data-ttu-id="16f62-1558">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="16f62-1558">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1559">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1559">Pattern</span></span>

<span data-ttu-id="16f62-1560">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-1560">10 digits:</span></span>
- <span data-ttu-id="16f62-1561">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-1561">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="16f62-1562">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-1562">A hyphen</span></span> 
- <span data-ttu-id="16f62-1563">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-1563">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1564">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1564">Checksum</span></span>

<span data-ttu-id="16f62-1565">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1565">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1566">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1566">Definition</span></span>

<span data-ttu-id="16f62-1567">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_denmark_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="16f62-1568">Se encuentra una palabra clave de Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="16f62-1568">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="16f62-1569">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1569">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-1570">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1570">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="16f62-1571">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="16f62-1571">Keyword_denmark_id</span></span>

- <span data-ttu-id="16f62-1572">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="16f62-1572">Personal Identification Number</span></span>
- <span data-ttu-id="16f62-1573">RCP</span><span class="sxs-lookup"><span data-stu-id="16f62-1573">CPR</span></span>
- <span data-ttu-id="16f62-1574">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="16f62-1574">Det Centrale Personregister</span></span>
- <span data-ttu-id="16f62-1575">Personnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1575">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="16f62-1576">Número de la Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="16f62-1576">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1577">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1577">Format</span></span>

<span data-ttu-id="16f62-1578">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1578">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1579">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1579">Pattern</span></span>

<span data-ttu-id="16f62-1580">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16f62-1580">Pattern must include all of the following:</span></span>
- <span data-ttu-id="16f62-1581">Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito</span><span class="sxs-lookup"><span data-stu-id="16f62-1581">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="16f62-1582">Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito.</span><span class="sxs-lookup"><span data-stu-id="16f62-1582">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="16f62-1583">Siete dígitos, el último de los cuales es el dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1583">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1584">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1584">Checksum</span></span>

<span data-ttu-id="16f62-1585">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1586">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1586">Definition</span></span>

<span data-ttu-id="16f62-1587">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1587">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1588">La función Func_dea_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1588">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1589">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1589">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-1590">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1590">Keywords</span></span>

<span data-ttu-id="16f62-1591">Ninguno</span><span class="sxs-lookup"><span data-stu-id="16f62-1591">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="16f62-1592">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="16f62-1592">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1593">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1593">Format</span></span>

<span data-ttu-id="16f62-1594">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1594">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1595">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1595">Pattern</span></span>

<span data-ttu-id="16f62-1596">Patrón muy complejo y robusto</span><span class="sxs-lookup"><span data-stu-id="16f62-1596">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1597">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1597">Checksum</span></span>

<span data-ttu-id="16f62-1598">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1598">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1599">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1599">Definition</span></span>

<span data-ttu-id="16f62-1600">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1600">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1601">La función Func_eu_debit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1601">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1602">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-1602">At least one of the following is true:</span></span>
    - <span data-ttu-id="16f62-1603">Se encuentra una palabra clave de Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-1603">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="16f62-1604">Se encuentra una palabra clave de Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="16f62-1604">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="16f62-1605">Se encuentra una palabra clave de Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="16f62-1605">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="16f62-1606">Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="16f62-1606">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="16f62-1607">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-1607">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16f62-1608">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1608">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1609">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1609">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="16f62-1610">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="16f62-1610">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="16f62-1611">account number</span><span class="sxs-lookup"><span data-stu-id="16f62-1611">account number</span></span> 
- <span data-ttu-id="16f62-1612">card number</span><span class="sxs-lookup"><span data-stu-id="16f62-1612">card number</span></span> 
- <span data-ttu-id="16f62-1613">card no.</span><span class="sxs-lookup"><span data-stu-id="16f62-1613">card no.</span></span> 
- <span data-ttu-id="16f62-1614">security number</span><span class="sxs-lookup"><span data-stu-id="16f62-1614">security number</span></span> 
- <span data-ttu-id="16f62-1615">CC</span><span class="sxs-lookup"><span data-stu-id="16f62-1615">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="16f62-1616">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="16f62-1616">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="16f62-1617">acct nbr</span><span class="sxs-lookup"><span data-stu-id="16f62-1617">acct nbr</span></span> 
- <span data-ttu-id="16f62-1618">acct num</span><span class="sxs-lookup"><span data-stu-id="16f62-1618">acct num</span></span> 
- <span data-ttu-id="16f62-1619">acct no</span><span class="sxs-lookup"><span data-stu-id="16f62-1619">acct no</span></span> 
- <span data-ttu-id="16f62-1620">american express</span><span class="sxs-lookup"><span data-stu-id="16f62-1620">american express</span></span> 
- <span data-ttu-id="16f62-1621">americanexpress</span><span class="sxs-lookup"><span data-stu-id="16f62-1621">americanexpress</span></span> 
- <span data-ttu-id="16f62-1622">americano espresso</span><span class="sxs-lookup"><span data-stu-id="16f62-1622">americano espresso</span></span> 
- <span data-ttu-id="16f62-1623">AMEX</span><span class="sxs-lookup"><span data-stu-id="16f62-1623">amex</span></span> 
- <span data-ttu-id="16f62-1624">atm card</span><span class="sxs-lookup"><span data-stu-id="16f62-1624">atm card</span></span> 
- <span data-ttu-id="16f62-1625">atm cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1625">atm cards</span></span> 
- <span data-ttu-id="16f62-1626">atm kaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1626">atm kaart</span></span> 
- <span data-ttu-id="16f62-1627">atmcard</span><span class="sxs-lookup"><span data-stu-id="16f62-1627">atmcard</span></span> 
- <span data-ttu-id="16f62-1628">atmcards</span><span class="sxs-lookup"><span data-stu-id="16f62-1628">atmcards</span></span> 
- <span data-ttu-id="16f62-1629">atmkaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1629">atmkaart</span></span> 
- <span data-ttu-id="16f62-1630">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="16f62-1630">atmkaarten</span></span> 
- <span data-ttu-id="16f62-1631">Bancontact</span><span class="sxs-lookup"><span data-stu-id="16f62-1631">bancontact</span></span> 
- <span data-ttu-id="16f62-1632">bank card</span><span class="sxs-lookup"><span data-stu-id="16f62-1632">bank card</span></span> 
- <span data-ttu-id="16f62-1633">bankkaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1633">bankkaart</span></span> 
- <span data-ttu-id="16f62-1634">card holder</span><span class="sxs-lookup"><span data-stu-id="16f62-1634">card holder</span></span> 
- <span data-ttu-id="16f62-1635">card holders</span><span class="sxs-lookup"><span data-stu-id="16f62-1635">card holders</span></span> 
- <span data-ttu-id="16f62-1636">card num</span><span class="sxs-lookup"><span data-stu-id="16f62-1636">card num</span></span> 
- <span data-ttu-id="16f62-1637">card number</span><span class="sxs-lookup"><span data-stu-id="16f62-1637">card number</span></span> 
- <span data-ttu-id="16f62-1638">card numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-1638">card numbers</span></span> 
- <span data-ttu-id="16f62-1639">card type</span><span class="sxs-lookup"><span data-stu-id="16f62-1639">card type</span></span> 
- <span data-ttu-id="16f62-1640">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="16f62-1640">cardano numerico</span></span> 
- <span data-ttu-id="16f62-1641">titular</span><span class="sxs-lookup"><span data-stu-id="16f62-1641">cardholder</span></span> 
- <span data-ttu-id="16f62-1642">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="16f62-1642">cardholders</span></span> 
- <span data-ttu-id="16f62-1643">cardNumber</span><span class="sxs-lookup"><span data-stu-id="16f62-1643">cardnumber</span></span> 
- <span data-ttu-id="16f62-1644">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="16f62-1644">cardnumbers</span></span> 
- <span data-ttu-id="16f62-1645">carta bianca</span><span class="sxs-lookup"><span data-stu-id="16f62-1645">carta bianca</span></span> 
- <span data-ttu-id="16f62-1646">carta credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1646">carta credito</span></span> 
- <span data-ttu-id="16f62-1647">carta di credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1647">carta di credito</span></span> 
- <span data-ttu-id="16f62-1648">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1648">cartao de credito</span></span> 
- <span data-ttu-id="16f62-1649">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1649">cartao de crédito</span></span> 
- <span data-ttu-id="16f62-1650">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1650">cartao de debito</span></span> 
- <span data-ttu-id="16f62-1651">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="16f62-1651">cartao de débito</span></span> 
- <span data-ttu-id="16f62-1652">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="16f62-1652">carte bancaire</span></span> 
- <span data-ttu-id="16f62-1653">carte blanche</span><span class="sxs-lookup"><span data-stu-id="16f62-1653">carte blanche</span></span> 
- <span data-ttu-id="16f62-1654">carte bleue</span><span class="sxs-lookup"><span data-stu-id="16f62-1654">carte bleue</span></span> 
- <span data-ttu-id="16f62-1655">carte de credit</span><span class="sxs-lookup"><span data-stu-id="16f62-1655">carte de credit</span></span> 
- <span data-ttu-id="16f62-1656">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="16f62-1656">carte de crédit</span></span> 
- <span data-ttu-id="16f62-1657">carte di credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1657">carte di credito</span></span> 
- <span data-ttu-id="16f62-1658">carteblanche</span><span class="sxs-lookup"><span data-stu-id="16f62-1658">carteblanche</span></span> 
- <span data-ttu-id="16f62-1659">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1659">cartão de credito</span></span> 
- <span data-ttu-id="16f62-1660">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1660">cartão de crédito</span></span> 
- <span data-ttu-id="16f62-1661">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1661">cartão de debito</span></span> 
- <span data-ttu-id="16f62-1662">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="16f62-1662">cartão de débito</span></span> 
- <span data-ttu-id="16f62-1663">cb</span><span class="sxs-lookup"><span data-stu-id="16f62-1663">cb</span></span> 
- <span data-ttu-id="16f62-1664">CCN</span><span class="sxs-lookup"><span data-stu-id="16f62-1664">ccn</span></span> 
- <span data-ttu-id="16f62-1665">check card</span><span class="sxs-lookup"><span data-stu-id="16f62-1665">check card</span></span> 
- <span data-ttu-id="16f62-1666">check cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1666">check cards</span></span> 
- <span data-ttu-id="16f62-1667">Checkcard</span><span class="sxs-lookup"><span data-stu-id="16f62-1667">checkcard</span></span>
- <span data-ttu-id="16f62-1668">checkcards</span><span class="sxs-lookup"><span data-stu-id="16f62-1668">checkcards</span></span> 
- <span data-ttu-id="16f62-1669">chequekaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1669">chequekaart</span></span> 
- <span data-ttu-id="16f62-1670">Logic</span><span class="sxs-lookup"><span data-stu-id="16f62-1670">cirrus</span></span> 
- <span data-ttu-id="16f62-1671">Cirrus-EDC-maestro</span><span class="sxs-lookup"><span data-stu-id="16f62-1671">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="16f62-1672">controlekaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1672">controlekaart</span></span> 
- <span data-ttu-id="16f62-1673">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="16f62-1673">controlekaarten</span></span> 
- <span data-ttu-id="16f62-1674">credit card</span><span class="sxs-lookup"><span data-stu-id="16f62-1674">credit card</span></span> 
- <span data-ttu-id="16f62-1675">credit cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1675">credit cards</span></span> 
- <span data-ttu-id="16f62-1676">crédito</span><span class="sxs-lookup"><span data-stu-id="16f62-1676">creditcard</span></span> 
- <span data-ttu-id="16f62-1677">creditcards</span><span class="sxs-lookup"><span data-stu-id="16f62-1677">creditcards</span></span> 
- <span data-ttu-id="16f62-1678">debetkaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1678">debetkaart</span></span> 
- <span data-ttu-id="16f62-1679">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="16f62-1679">debetkaarten</span></span> 
- <span data-ttu-id="16f62-1680">debit card</span><span class="sxs-lookup"><span data-stu-id="16f62-1680">debit card</span></span> 
- <span data-ttu-id="16f62-1681">debit cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1681">debit cards</span></span> 
- <span data-ttu-id="16f62-1682">debitcard</span><span class="sxs-lookup"><span data-stu-id="16f62-1682">debitcard</span></span> 
- <span data-ttu-id="16f62-1683">DebitCards</span><span class="sxs-lookup"><span data-stu-id="16f62-1683">debitcards</span></span> 
- <span data-ttu-id="16f62-1684">debito automatico</span><span class="sxs-lookup"><span data-stu-id="16f62-1684">debito automatico</span></span> 
- <span data-ttu-id="16f62-1685">diners club</span><span class="sxs-lookup"><span data-stu-id="16f62-1685">diners club</span></span> 
- <span data-ttu-id="16f62-1686">DinersClub</span><span class="sxs-lookup"><span data-stu-id="16f62-1686">dinersclub</span></span> 
- <span data-ttu-id="16f62-1687">advierte</span><span class="sxs-lookup"><span data-stu-id="16f62-1687">discover</span></span> 
- <span data-ttu-id="16f62-1688">discover card</span><span class="sxs-lookup"><span data-stu-id="16f62-1688">discover card</span></span> 
- <span data-ttu-id="16f62-1689">discover cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1689">discover cards</span></span> 
- <span data-ttu-id="16f62-1690">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1690">discovercard</span></span> 
- <span data-ttu-id="16f62-1691">discovercards</span><span class="sxs-lookup"><span data-stu-id="16f62-1691">discovercards</span></span> 
- <span data-ttu-id="16f62-1692">débito automático</span><span class="sxs-lookup"><span data-stu-id="16f62-1692">débito automático</span></span>
- <span data-ttu-id="16f62-1693">EDC</span><span class="sxs-lookup"><span data-stu-id="16f62-1693">edc</span></span> 
- <span data-ttu-id="16f62-1694">eigentümername</span><span class="sxs-lookup"><span data-stu-id="16f62-1694">eigentümername</span></span> 
- <span data-ttu-id="16f62-1695">european debit card</span><span class="sxs-lookup"><span data-stu-id="16f62-1695">european debit card</span></span> 
- <span data-ttu-id="16f62-1696">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1696">hoofdkaart</span></span> 
- <span data-ttu-id="16f62-1697">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="16f62-1697">hoofdkaarten</span></span> 
- <span data-ttu-id="16f62-1698">in viaggio</span><span class="sxs-lookup"><span data-stu-id="16f62-1698">in viaggio</span></span> 
- <span data-ttu-id="16f62-1699">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="16f62-1699">japanese card bureau</span></span> 
- <span data-ttu-id="16f62-1700">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="16f62-1700">japanse kaartdienst</span></span> 
- <span data-ttu-id="16f62-1701">JCB</span><span class="sxs-lookup"><span data-stu-id="16f62-1701">jcb</span></span> 
- <span data-ttu-id="16f62-1702">Kaart</span><span class="sxs-lookup"><span data-stu-id="16f62-1702">kaart</span></span> 
- <span data-ttu-id="16f62-1703">kaart num</span><span class="sxs-lookup"><span data-stu-id="16f62-1703">kaart num</span></span> 
- <span data-ttu-id="16f62-1704">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="16f62-1704">kaartaantal</span></span> 
- <span data-ttu-id="16f62-1705">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="16f62-1705">kaartaantallen</span></span> 
- <span data-ttu-id="16f62-1706">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="16f62-1706">kaarthouder</span></span> 
- <span data-ttu-id="16f62-1707">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="16f62-1707">kaarthouders</span></span> 
- <span data-ttu-id="16f62-1708">Karte</span><span class="sxs-lookup"><span data-stu-id="16f62-1708">karte</span></span>  
- <span data-ttu-id="16f62-1709">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="16f62-1709">karteninhaber</span></span> 
- <span data-ttu-id="16f62-1710">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="16f62-1710">karteninhabers</span></span>
- <span data-ttu-id="16f62-1711">kartennr</span><span class="sxs-lookup"><span data-stu-id="16f62-1711">kartennr</span></span> 
- <span data-ttu-id="16f62-1712">kartennummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1712">kartennummer</span></span> 
- <span data-ttu-id="16f62-1713">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="16f62-1713">kreditkarte</span></span> 
- <span data-ttu-id="16f62-1714">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1714">kreditkarten-nummer</span></span> 
- <span data-ttu-id="16f62-1715">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="16f62-1715">kreditkarteninhaber</span></span> 
- <span data-ttu-id="16f62-1716">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="16f62-1716">kreditkarteninstitut</span></span> 
- <span data-ttu-id="16f62-1717">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1717">kreditkartennummer</span></span> 
- <span data-ttu-id="16f62-1718">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="16f62-1718">kreditkartentyp</span></span> 
- <span data-ttu-id="16f62-1719">dispositivos</span><span class="sxs-lookup"><span data-stu-id="16f62-1719">maestro</span></span> 
- <span data-ttu-id="16f62-1720">master card</span><span class="sxs-lookup"><span data-stu-id="16f62-1720">master card</span></span> 
- <span data-ttu-id="16f62-1721">master cards</span><span class="sxs-lookup"><span data-stu-id="16f62-1721">master cards</span></span> 
- <span data-ttu-id="16f62-1722">MasterCard</span><span class="sxs-lookup"><span data-stu-id="16f62-1722">mastercard</span></span> 
- <span data-ttu-id="16f62-1723">MasterCard</span><span class="sxs-lookup"><span data-stu-id="16f62-1723">mastercards</span></span> 
- <span data-ttu-id="16f62-1724">valuación</span><span class="sxs-lookup"><span data-stu-id="16f62-1724">mc</span></span> 
- <span data-ttu-id="16f62-1725">mister cash</span><span class="sxs-lookup"><span data-stu-id="16f62-1725">mister cash</span></span> 
- <span data-ttu-id="16f62-1726">n carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1726">n carta</span></span> 
- <span data-ttu-id="16f62-1727">cobro</span><span class="sxs-lookup"><span data-stu-id="16f62-1727">carta</span></span> 
- <span data-ttu-id="16f62-1728">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1728">no de tarjeta</span></span> 
- <span data-ttu-id="16f62-1729">no do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1729">no do cartao</span></span> 
- <span data-ttu-id="16f62-1730">no do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1730">no do cartão</span></span> 
- <span data-ttu-id="16f62-1731">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1731">no.</span></span> <span data-ttu-id="16f62-1732">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1732">de tarjeta</span></span> 
- <span data-ttu-id="16f62-1733">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1733">no.</span></span> <span data-ttu-id="16f62-1734">do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1734">do cartao</span></span> 
- <span data-ttu-id="16f62-1735">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1735">no.</span></span> <span data-ttu-id="16f62-1736">do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1736">do cartão</span></span> 
- <span data-ttu-id="16f62-1737">nr carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1737">nr carta</span></span> 
- <span data-ttu-id="16f62-1738">Nº.</span><span class="sxs-lookup"><span data-stu-id="16f62-1738">nr.</span></span> <span data-ttu-id="16f62-1739">cobro</span><span class="sxs-lookup"><span data-stu-id="16f62-1739">carta</span></span> 
- <span data-ttu-id="16f62-1740">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1740">numeri di scheda</span></span> 
- <span data-ttu-id="16f62-1741">numero carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1741">numero carta</span></span> 
- <span data-ttu-id="16f62-1742">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1742">numero de cartao</span></span> 
- <span data-ttu-id="16f62-1743">numero de carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1743">numero de carte</span></span> 
- <span data-ttu-id="16f62-1744">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1744">numero de cartão</span></span> 
- <span data-ttu-id="16f62-1745">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1745">numero de tarjeta</span></span>
- <span data-ttu-id="16f62-1746">numero della carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1746">numero della carta</span></span> 
- <span data-ttu-id="16f62-1747">numero di carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1747">numero di carta</span></span> 
- <span data-ttu-id="16f62-1748">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1748">numero di scheda</span></span> 
- <span data-ttu-id="16f62-1749">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1749">numero do cartao</span></span> 
- <span data-ttu-id="16f62-1750">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1750">numero do cartão</span></span> 
- <span data-ttu-id="16f62-1751">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1751">numéro de carte</span></span> 
- <span data-ttu-id="16f62-1752">nº carta</span><span class="sxs-lookup"><span data-stu-id="16f62-1752">nº carta</span></span> 
- <span data-ttu-id="16f62-1753">nº de carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1753">nº de carte</span></span> 
- <span data-ttu-id="16f62-1754">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="16f62-1754">nº de la carte</span></span> 
- <span data-ttu-id="16f62-1755">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1755">nº de tarjeta</span></span> 
- <span data-ttu-id="16f62-1756">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1756">nº do cartao</span></span> 
- <span data-ttu-id="16f62-1757">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1757">nº do cartão</span></span> 
- <span data-ttu-id="16f62-1758">Nº.</span><span class="sxs-lookup"><span data-stu-id="16f62-1758">nº.</span></span> <span data-ttu-id="16f62-1759">do cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1759">do cartão</span></span> 
- <span data-ttu-id="16f62-1760">número de cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1760">número de cartao</span></span> 
- <span data-ttu-id="16f62-1761">número de cartão</span><span class="sxs-lookup"><span data-stu-id="16f62-1761">número de cartão</span></span> 
- <span data-ttu-id="16f62-1762">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16f62-1762">número de tarjeta</span></span> 
- <span data-ttu-id="16f62-1763">número do cartao</span><span class="sxs-lookup"><span data-stu-id="16f62-1763">número do cartao</span></span> 
- <span data-ttu-id="16f62-1764">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="16f62-1764">scheda dell'assegno</span></span> 
- <span data-ttu-id="16f62-1765">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="16f62-1765">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="16f62-1766">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="16f62-1766">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="16f62-1767">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="16f62-1767">scheda della banca</span></span> 
- <span data-ttu-id="16f62-1768">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="16f62-1768">scheda di controllo</span></span> 
- <span data-ttu-id="16f62-1769">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1769">scheda di debito</span></span> 
- <span data-ttu-id="16f62-1770">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="16f62-1770">scheda matrice</span></span> 
- <span data-ttu-id="16f62-1771">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="16f62-1771">schede dell'atmosfera</span></span> 
- <span data-ttu-id="16f62-1772">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="16f62-1772">schede di controllo</span></span> 
- <span data-ttu-id="16f62-1773">schede di debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1773">schede di debito</span></span> 
- <span data-ttu-id="16f62-1774">schede matrici</span><span class="sxs-lookup"><span data-stu-id="16f62-1774">schede matrici</span></span> 
- <span data-ttu-id="16f62-1775">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1775">scoprono la scheda</span></span> 
- <span data-ttu-id="16f62-1776">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="16f62-1776">scoprono le schede</span></span> 
- <span data-ttu-id="16f62-1777">solo</span><span class="sxs-lookup"><span data-stu-id="16f62-1777">solo</span></span> 
- <span data-ttu-id="16f62-1778">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1778">supporti di scheda</span></span> 
- <span data-ttu-id="16f62-1779">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1779">supporto di scheda</span></span> 
- <span data-ttu-id="16f62-1780">cambia</span><span class="sxs-lookup"><span data-stu-id="16f62-1780">switch</span></span> 
- <span data-ttu-id="16f62-1781">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="16f62-1781">tarjeta atm</span></span> 
- <span data-ttu-id="16f62-1782">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1782">tarjeta credito</span></span> 
- <span data-ttu-id="16f62-1783">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="16f62-1783">tarjeta de atm</span></span> 
- <span data-ttu-id="16f62-1784">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="16f62-1784">tarjeta de credito</span></span> 
- <span data-ttu-id="16f62-1785">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1785">tarjeta de debito</span></span> 
- <span data-ttu-id="16f62-1786">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="16f62-1786">tarjeta debito</span></span> 
- <span data-ttu-id="16f62-1787">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="16f62-1787">tarjeta no</span></span>
- <span data-ttu-id="16f62-1788">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="16f62-1788">tarjetahabiente</span></span> 
- <span data-ttu-id="16f62-1789">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1789">tipo della scheda</span></span> 
- <span data-ttu-id="16f62-1790">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="16f62-1790">ufficio giapponese della</span></span> 
- <span data-ttu-id="16f62-1791">Scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1791">scheda</span></span> 
- <span data-ttu-id="16f62-1792">v pay</span><span class="sxs-lookup"><span data-stu-id="16f62-1792">v pay</span></span> 
- <span data-ttu-id="16f62-1793">v-Pay</span><span class="sxs-lookup"><span data-stu-id="16f62-1793">v-pay</span></span> 
- <span data-ttu-id="16f62-1794">régimen</span><span class="sxs-lookup"><span data-stu-id="16f62-1794">visa</span></span> 
- <span data-ttu-id="16f62-1795">visa plus</span><span class="sxs-lookup"><span data-stu-id="16f62-1795">visa plus</span></span> 
- <span data-ttu-id="16f62-1796">visa electron</span><span class="sxs-lookup"><span data-stu-id="16f62-1796">visa electron</span></span> 
- <span data-ttu-id="16f62-1797">a</span><span class="sxs-lookup"><span data-stu-id="16f62-1797">visto</span></span> 
- <span data-ttu-id="16f62-1798">visum</span><span class="sxs-lookup"><span data-stu-id="16f62-1798">visum</span></span> 
- <span data-ttu-id="16f62-1799">VPay</span><span class="sxs-lookup"><span data-stu-id="16f62-1799">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="16f62-1800">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="16f62-1800">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="16f62-1801">card identification number</span><span class="sxs-lookup"><span data-stu-id="16f62-1801">card identification number</span></span>
- <span data-ttu-id="16f62-1802">card verification</span><span class="sxs-lookup"><span data-stu-id="16f62-1802">card verification</span></span> 
- <span data-ttu-id="16f62-1803">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="16f62-1803">cardi la verifica</span></span> 
- <span data-ttu-id="16f62-1804">cid</span><span class="sxs-lookup"><span data-stu-id="16f62-1804">cid</span></span> 
- <span data-ttu-id="16f62-1805">cod seg</span><span class="sxs-lookup"><span data-stu-id="16f62-1805">cod seg</span></span> 
- <span data-ttu-id="16f62-1806">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="16f62-1806">cod seguranca</span></span> 
- <span data-ttu-id="16f62-1807">cod segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1807">cod segurança</span></span> 
- <span data-ttu-id="16f62-1808">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="16f62-1808">cod sicurezza</span></span> 
- <span data-ttu-id="16f62-1809">COD.</span><span class="sxs-lookup"><span data-stu-id="16f62-1809">cod.</span></span> <span data-ttu-id="16f62-1810">seg</span><span class="sxs-lookup"><span data-stu-id="16f62-1810">seg</span></span> 
- <span data-ttu-id="16f62-1811">COD.</span><span class="sxs-lookup"><span data-stu-id="16f62-1811">cod.</span></span> <span data-ttu-id="16f62-1812">SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="16f62-1812">seguranca</span></span> 
- <span data-ttu-id="16f62-1813">COD.</span><span class="sxs-lookup"><span data-stu-id="16f62-1813">cod.</span></span> <span data-ttu-id="16f62-1814">segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1814">segurança</span></span> 
- <span data-ttu-id="16f62-1815">COD.</span><span class="sxs-lookup"><span data-stu-id="16f62-1815">cod.</span></span> <span data-ttu-id="16f62-1816">sicurezza</span><span class="sxs-lookup"><span data-stu-id="16f62-1816">sicurezza</span></span> 
- <span data-ttu-id="16f62-1817">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="16f62-1817">codice di sicurezza</span></span> 
- <span data-ttu-id="16f62-1818">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="16f62-1818">codice di verifica</span></span> 
- <span data-ttu-id="16f62-1819">codigo</span><span class="sxs-lookup"><span data-stu-id="16f62-1819">codigo</span></span> 
- <span data-ttu-id="16f62-1820">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="16f62-1820">codigo de seguranca</span></span> 
- <span data-ttu-id="16f62-1821">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1821">codigo de segurança</span></span> 
- <span data-ttu-id="16f62-1822">crittogramma</span><span class="sxs-lookup"><span data-stu-id="16f62-1822">crittogramma</span></span> 
- <span data-ttu-id="16f62-1823">criptograma</span><span class="sxs-lookup"><span data-stu-id="16f62-1823">cryptogram</span></span> 
- <span data-ttu-id="16f62-1824">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="16f62-1824">cryptogramme</span></span> 
- <span data-ttu-id="16f62-1825">CV2</span><span class="sxs-lookup"><span data-stu-id="16f62-1825">cv2</span></span> 
- <span data-ttu-id="16f62-1826">CVC</span><span class="sxs-lookup"><span data-stu-id="16f62-1826">cvc</span></span> 
- <span data-ttu-id="16f62-1827">CVC2</span><span class="sxs-lookup"><span data-stu-id="16f62-1827">cvc2</span></span> 
- <span data-ttu-id="16f62-1828">CVN</span><span class="sxs-lookup"><span data-stu-id="16f62-1828">cvn</span></span> 
- <span data-ttu-id="16f62-1829">CVV</span><span class="sxs-lookup"><span data-stu-id="16f62-1829">cvv</span></span> 
- <span data-ttu-id="16f62-1830">CVV2</span><span class="sxs-lookup"><span data-stu-id="16f62-1830">cvv2</span></span> 
- <span data-ttu-id="16f62-1831">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="16f62-1831">cód seguranca</span></span> 
- <span data-ttu-id="16f62-1832">cód segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1832">cód segurança</span></span> 
- <span data-ttu-id="16f62-1833">campos.</span><span class="sxs-lookup"><span data-stu-id="16f62-1833">cód.</span></span> <span data-ttu-id="16f62-1834">SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="16f62-1834">seguranca</span></span> 
- <span data-ttu-id="16f62-1835">campos.</span><span class="sxs-lookup"><span data-stu-id="16f62-1835">cód.</span></span> <span data-ttu-id="16f62-1836">segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1836">segurança</span></span> 
- <span data-ttu-id="16f62-1837">Código</span><span class="sxs-lookup"><span data-stu-id="16f62-1837">código</span></span> 
- <span data-ttu-id="16f62-1838">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="16f62-1838">código de seguranca</span></span> 
- <span data-ttu-id="16f62-1839">código de segurança</span><span class="sxs-lookup"><span data-stu-id="16f62-1839">código de segurança</span></span> 
- <span data-ttu-id="16f62-1840">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="16f62-1840">de kaart controle</span></span> 
- <span data-ttu-id="16f62-1841">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="16f62-1841">geeft nr uit</span></span> 
- <span data-ttu-id="16f62-1842">issue no</span><span class="sxs-lookup"><span data-stu-id="16f62-1842">issue no</span></span> 
- <span data-ttu-id="16f62-1843">issue number</span><span class="sxs-lookup"><span data-stu-id="16f62-1843">issue number</span></span> 
- <span data-ttu-id="16f62-1844">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1844">kaartidentificatienummer</span></span> 
- <span data-ttu-id="16f62-1845">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1845">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="16f62-1846">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1846">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="16f62-1847">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="16f62-1847">kwestieaantal</span></span> 
- <span data-ttu-id="16f62-1848">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1848">no.</span></span> <span data-ttu-id="16f62-1849">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="16f62-1849">dell'edizione</span></span> 
- <span data-ttu-id="16f62-1850">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-1850">no.</span></span> <span data-ttu-id="16f62-1851">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="16f62-1851">di sicurezza</span></span> 
- <span data-ttu-id="16f62-1852">numero de securite</span><span class="sxs-lookup"><span data-stu-id="16f62-1852">numero de securite</span></span> 
- <span data-ttu-id="16f62-1853">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="16f62-1853">numero de verificacao</span></span> 
- <span data-ttu-id="16f62-1854">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="16f62-1854">numero dell'edizione</span></span> 
- <span data-ttu-id="16f62-1855">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="16f62-1855">numero di identificazione della</span></span> 
- <span data-ttu-id="16f62-1856">Scheda</span><span class="sxs-lookup"><span data-stu-id="16f62-1856">scheda</span></span> 
- <span data-ttu-id="16f62-1857">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="16f62-1857">numero di sicurezza</span></span> 
- <span data-ttu-id="16f62-1858">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="16f62-1858">numero van veiligheid</span></span> 
- <span data-ttu-id="16f62-1859">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="16f62-1859">numéro de sécurité</span></span> 
- <span data-ttu-id="16f62-1860">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="16f62-1860">nº autorizzazione</span></span> 
- <span data-ttu-id="16f62-1861">número de verificação</span><span class="sxs-lookup"><span data-stu-id="16f62-1861">número de verificação</span></span> 
- <span data-ttu-id="16f62-1862">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="16f62-1862">perno il blocco</span></span> 
- <span data-ttu-id="16f62-1863">pin block</span><span class="sxs-lookup"><span data-stu-id="16f62-1863">pin block</span></span> 
- <span data-ttu-id="16f62-1864">prufziffer</span><span class="sxs-lookup"><span data-stu-id="16f62-1864">prufziffer</span></span> 
- <span data-ttu-id="16f62-1865">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="16f62-1865">prüfziffer</span></span> 
- <span data-ttu-id="16f62-1866">security code</span><span class="sxs-lookup"><span data-stu-id="16f62-1866">security code</span></span> 
- <span data-ttu-id="16f62-1867">security no</span><span class="sxs-lookup"><span data-stu-id="16f62-1867">security no</span></span> 
- <span data-ttu-id="16f62-1868">security number</span><span class="sxs-lookup"><span data-stu-id="16f62-1868">security number</span></span> 
- <span data-ttu-id="16f62-1869">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="16f62-1869">sicherheits kode</span></span> 
- <span data-ttu-id="16f62-1870">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="16f62-1870">sicherheitscode</span></span> 
- <span data-ttu-id="16f62-1871">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1871">sicherheitsnummer</span></span> 
- <span data-ttu-id="16f62-1872">speldblok</span><span class="sxs-lookup"><span data-stu-id="16f62-1872">speldblok</span></span> 
- <span data-ttu-id="16f62-1873">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="16f62-1873">veiligheid nr</span></span> 
- <span data-ttu-id="16f62-1874">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="16f62-1874">veiligheidsaantal</span></span> 
- <span data-ttu-id="16f62-1875">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="16f62-1875">veiligheidscode</span></span> 
- <span data-ttu-id="16f62-1876">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1876">veiligheidsnummer</span></span> 
- <span data-ttu-id="16f62-1877">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="16f62-1877">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="16f62-1878">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="16f62-1878">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="16f62-1879">ablauf</span><span class="sxs-lookup"><span data-stu-id="16f62-1879">ablauf</span></span> 
- <span data-ttu-id="16f62-1880">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="16f62-1880">data de expiracao</span></span> 
- <span data-ttu-id="16f62-1881">data de expiração</span><span class="sxs-lookup"><span data-stu-id="16f62-1881">data de expiração</span></span> 
- <span data-ttu-id="16f62-1882">data del exp</span><span class="sxs-lookup"><span data-stu-id="16f62-1882">data del exp</span></span> 
- <span data-ttu-id="16f62-1883">data di exp</span><span class="sxs-lookup"><span data-stu-id="16f62-1883">data di exp</span></span> 
- <span data-ttu-id="16f62-1884">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="16f62-1884">data di scadenza</span></span> 
- <span data-ttu-id="16f62-1885">data em que expira</span><span class="sxs-lookup"><span data-stu-id="16f62-1885">data em que expira</span></span> 
- <span data-ttu-id="16f62-1886">data scad</span><span class="sxs-lookup"><span data-stu-id="16f62-1886">data scad</span></span> 
- <span data-ttu-id="16f62-1887">data scadenza</span><span class="sxs-lookup"><span data-stu-id="16f62-1887">data scadenza</span></span> 
- <span data-ttu-id="16f62-1888">date de validité</span><span class="sxs-lookup"><span data-stu-id="16f62-1888">date de validité</span></span> 
- <span data-ttu-id="16f62-1889">datum afloop</span><span class="sxs-lookup"><span data-stu-id="16f62-1889">datum afloop</span></span> 
- <span data-ttu-id="16f62-1890">datum van exp</span><span class="sxs-lookup"><span data-stu-id="16f62-1890">datum van exp</span></span> 
- <span data-ttu-id="16f62-1891">de afloop</span><span class="sxs-lookup"><span data-stu-id="16f62-1891">de afloop</span></span> 
- <span data-ttu-id="16f62-1892">espira</span><span class="sxs-lookup"><span data-stu-id="16f62-1892">espira</span></span> 
- <span data-ttu-id="16f62-1893">espira</span><span class="sxs-lookup"><span data-stu-id="16f62-1893">espira</span></span> 
- <span data-ttu-id="16f62-1894">exp date</span><span class="sxs-lookup"><span data-stu-id="16f62-1894">exp date</span></span> 
- <span data-ttu-id="16f62-1895">exp datum</span><span class="sxs-lookup"><span data-stu-id="16f62-1895">exp datum</span></span> 
- <span data-ttu-id="16f62-1896">expiración</span><span class="sxs-lookup"><span data-stu-id="16f62-1896">expiration</span></span> 
- <span data-ttu-id="16f62-1897">expiran</span><span class="sxs-lookup"><span data-stu-id="16f62-1897">expire</span></span> 
- <span data-ttu-id="16f62-1898">expira</span><span class="sxs-lookup"><span data-stu-id="16f62-1898">expires</span></span> 
- <span data-ttu-id="16f62-1899">expiración</span><span class="sxs-lookup"><span data-stu-id="16f62-1899">expiry</span></span> 
- <span data-ttu-id="16f62-1900">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="16f62-1900">fecha de expiracion</span></span> 
- <span data-ttu-id="16f62-1901">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="16f62-1901">fecha de venc</span></span> 
- <span data-ttu-id="16f62-1902">gultig bis</span><span class="sxs-lookup"><span data-stu-id="16f62-1902">gultig bis</span></span> 
- <span data-ttu-id="16f62-1903">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16f62-1903">gultigkeitsdatum</span></span> 
- <span data-ttu-id="16f62-1904">gültig bis</span><span class="sxs-lookup"><span data-stu-id="16f62-1904">gültig bis</span></span> 
- <span data-ttu-id="16f62-1905">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16f62-1905">gültigkeitsdatum</span></span> 
- <span data-ttu-id="16f62-1906">la scadenza</span><span class="sxs-lookup"><span data-stu-id="16f62-1906">la scadenza</span></span> 
- <span data-ttu-id="16f62-1907">scadenza</span><span class="sxs-lookup"><span data-stu-id="16f62-1907">scadenza</span></span> 
- <span data-ttu-id="16f62-1908">valable</span><span class="sxs-lookup"><span data-stu-id="16f62-1908">valable</span></span> 
- <span data-ttu-id="16f62-1909">validade</span><span class="sxs-lookup"><span data-stu-id="16f62-1909">validade</span></span> 
- <span data-ttu-id="16f62-1910">valido hasta</span><span class="sxs-lookup"><span data-stu-id="16f62-1910">valido hasta</span></span> 
- <span data-ttu-id="16f62-1911">valorar</span><span class="sxs-lookup"><span data-stu-id="16f62-1911">valor</span></span> 
- <span data-ttu-id="16f62-1912">venc</span><span class="sxs-lookup"><span data-stu-id="16f62-1912">venc</span></span> 
- <span data-ttu-id="16f62-1913">vencimento</span><span class="sxs-lookup"><span data-stu-id="16f62-1913">vencimento</span></span> 
- <span data-ttu-id="16f62-1914">1er</span><span class="sxs-lookup"><span data-stu-id="16f62-1914">vencimiento</span></span> 
- <span data-ttu-id="16f62-1915">verloopt</span><span class="sxs-lookup"><span data-stu-id="16f62-1915">verloopt</span></span> 
- <span data-ttu-id="16f62-1916">vervaldag</span><span class="sxs-lookup"><span data-stu-id="16f62-1916">vervaldag</span></span> 
- <span data-ttu-id="16f62-1917">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="16f62-1917">vervaldatum</span></span> 
- <span data-ttu-id="16f62-1918">vto</span><span class="sxs-lookup"><span data-stu-id="16f62-1918">vto</span></span> 
- <span data-ttu-id="16f62-1919">válido hasta</span><span class="sxs-lookup"><span data-stu-id="16f62-1919">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="16f62-1920">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="16f62-1920">EU Driver's License Number</span></span>

<span data-ttu-id="16f62-1921">Para obtener más información, vea [tipo de información confidencial del número de licencia del conductor de la UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="16f62-1921">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="16f62-1922">Número de identificación nacional de la UE</span><span class="sxs-lookup"><span data-stu-id="16f62-1922">EU National Identification Number</span></span>

<span data-ttu-id="16f62-1923">Para obtener más información, consulte el [tipo de información confidencial de número de identificación nacional de la UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="16f62-1923">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="16f62-1924">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="16f62-1924">EU Passport Number</span></span>

<span data-ttu-id="16f62-1925">Para obtener más información, consulte [EU Number Sensitive Information Type](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="16f62-1925">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="16f62-1926">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="16f62-1926">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="16f62-1927">Para obtener más información, consulte el [número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="16f62-1927">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="16f62-1928">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="16f62-1928">EU Tax Identification Number</span></span>

<span data-ttu-id="16f62-1929">Para obtener más información, vea [tipo de información confidencial de número de identificación de impuestos de la UE](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="16f62-1929">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="16f62-1930">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="16f62-1930">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1931">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1931">Format</span></span>

<span data-ttu-id="16f62-1932">Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-1932">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1933">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1933">Pattern</span></span>

<span data-ttu-id="16f62-1934">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16f62-1934">Pattern must include all of the following:</span></span>
- <span data-ttu-id="16f62-1935">Seis dígitos en el formato DDMMAA que son una fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-1935">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="16f62-1936">Marcador del siglo (ya sea '-', '+' o 'a')</span><span class="sxs-lookup"><span data-stu-id="16f62-1936">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="16f62-1937">Número de identificación personal de tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1937">Three-digit personal identification number</span></span> 
- <span data-ttu-id="16f62-1938">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-1938">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1939">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1939">Checksum</span></span>

<span data-ttu-id="16f62-1940">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-1940">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1941">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1941">Definition</span></span>

<span data-ttu-id="16f62-1942">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1942">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1943">La función Func_finnish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1943">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1944">Se encuentra una palabra clave de Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="16f62-1944">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="16f62-1945">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-1945">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-1946">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1946">Keywords</span></span>

- <span data-ttu-id="16f62-1947">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="16f62-1947">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="16f62-1948">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="16f62-1948">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="16f62-1949">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="16f62-1949">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="16f62-1950">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="16f62-1950">Personbeteckning</span></span>
- <span data-ttu-id="16f62-1951">Personnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-1951">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="16f62-1952">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="16f62-1952">Finland Passport Number</span></span>

<span data-ttu-id="16f62-1953">Combinación de formato de nueve letras y dígitos de la combinación de los patrones de nueve letras y dígitos: dos letras (no distingue entre mayúsculas y minúsculas) siete dígitos de suma de comprobación no Definition una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1953">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="16f62-1954">Se encuentra una palabra clave de Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-1954">A keyword from Keyword_finland_passport_number is found.</span></span>
<span data-ttu-id="16f62-1955"><!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="16f62-1955"></span></span>
<span data-ttu-id="16f62-1956">Palabras clave Keyword_finland_passport_number Passi de Passport</span><span class="sxs-lookup"><span data-stu-id="16f62-1956">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="16f62-1957">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="16f62-1957">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1958">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1958">Format</span></span>

<span data-ttu-id="16f62-1959">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1959">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1960">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1960">Pattern</span></span>

<span data-ttu-id="16f62-1961">12 dígitos con validación para descontar patrones similares como los números de teléfono franceses</span><span class="sxs-lookup"><span data-stu-id="16f62-1961">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1962">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1962">Checksum</span></span>

<span data-ttu-id="16f62-1963">No</span><span class="sxs-lookup"><span data-stu-id="16f62-1963">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1964">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1964">Definition</span></span>

<span data-ttu-id="16f62-1965">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1965">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1966">La función Func_french_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1966">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-1967">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-1967">At least one of the following is true:</span></span>
- <span data-ttu-id="16f62-1968">Se encuentra una palabra clave de Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="16f62-1968">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="16f62-1969">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-1969">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-1970">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1970">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="16f62-1971">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16f62-1971">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="16f62-1972">drivers licence</span><span class="sxs-lookup"><span data-stu-id="16f62-1972">drivers licence</span></span>
- <span data-ttu-id="16f62-1973">drivers license</span><span class="sxs-lookup"><span data-stu-id="16f62-1973">drivers license</span></span>
- <span data-ttu-id="16f62-1974">driving licence</span><span class="sxs-lookup"><span data-stu-id="16f62-1974">driving licence</span></span>
- <span data-ttu-id="16f62-1975">driving license</span><span class="sxs-lookup"><span data-stu-id="16f62-1975">driving license</span></span>
- <span data-ttu-id="16f62-1976">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="16f62-1976">permis de conduire</span></span>
- <span data-ttu-id="16f62-1977">licence number</span><span class="sxs-lookup"><span data-stu-id="16f62-1977">licence number</span></span>
- <span data-ttu-id="16f62-1978">license number</span><span class="sxs-lookup"><span data-stu-id="16f62-1978">license number</span></span>
- <span data-ttu-id="16f62-1979">licence numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-1979">licence numbers</span></span>
- <span data-ttu-id="16f62-1980">license numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-1980">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="16f62-1981">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="16f62-1981">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1982">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1982">Format</span></span>

<span data-ttu-id="16f62-1983">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1983">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1984">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1984">Pattern</span></span>

<span data-ttu-id="16f62-1985">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1985">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-1986">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-1986">Checksum</span></span>

<span data-ttu-id="16f62-1987">No</span><span class="sxs-lookup"><span data-stu-id="16f62-1987">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-1988">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-1988">Definition</span></span>

<span data-ttu-id="16f62-1989">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-1989">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-1990">La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-1990">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-1991">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-1991">Keywords</span></span>

<span data-ttu-id="16f62-1992">Ninguno</span><span class="sxs-lookup"><span data-stu-id="16f62-1992">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="16f62-1993">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="16f62-1993">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-1994">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-1994">Format</span></span>

<span data-ttu-id="16f62-1995">Nueve dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="16f62-1995">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-1996">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-1996">Pattern</span></span>

<span data-ttu-id="16f62-1997">Nueve dígitos y letras:</span><span class="sxs-lookup"><span data-stu-id="16f62-1997">Nine digits and letters:</span></span>
- <span data-ttu-id="16f62-1998">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-1998">Two digits</span></span> 
- <span data-ttu-id="16f62-1999">Dos letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-1999">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-2000">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2000">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2001">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2001">Checksum</span></span>

<span data-ttu-id="16f62-2002">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2002">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2003">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2003">Definition</span></span>

<span data-ttu-id="16f62-2004">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2005">La función Func_fr_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2005">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2006">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="16f62-2006">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2007">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2007">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="16f62-2008">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-2008">Keyword_passport</span></span>

- <span data-ttu-id="16f62-2009">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2009">Passport Number</span></span>
- <span data-ttu-id="16f62-2010">Passport No</span><span class="sxs-lookup"><span data-stu-id="16f62-2010">Passport No</span></span>
- <span data-ttu-id="16f62-2011">Passport #</span><span class="sxs-lookup"><span data-stu-id="16f62-2011">Passport #</span></span>
- <span data-ttu-id="16f62-2012">Usuarios</span><span class="sxs-lookup"><span data-stu-id="16f62-2012">Passport#</span></span>
- <span data-ttu-id="16f62-2013">PassportID</span><span class="sxs-lookup"><span data-stu-id="16f62-2013">PassportID</span></span>
- <span data-ttu-id="16f62-2014">Passportno</span><span class="sxs-lookup"><span data-stu-id="16f62-2014">Passportno</span></span>
- <span data-ttu-id="16f62-2015">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-2015">passportnumber</span></span>
- <span data-ttu-id="16f62-2016">パスポート</span><span class="sxs-lookup"><span data-stu-id="16f62-2016">パスポート</span></span>
- <span data-ttu-id="16f62-2017">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2017">パスポート番号</span></span>
- <span data-ttu-id="16f62-2018">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16f62-2018">パスポートのNum</span></span>
- <span data-ttu-id="16f62-2019">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="16f62-2019">パスポート ＃</span></span> 
- <span data-ttu-id="16f62-2020">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16f62-2020">Numéro de passeport</span></span>
- <span data-ttu-id="16f62-2021">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16f62-2021">Passeport n °</span></span>
- <span data-ttu-id="16f62-2022">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16f62-2022">Passeport Non</span></span>
- <span data-ttu-id="16f62-2023">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-2023">Passeport #</span></span>
- <span data-ttu-id="16f62-2024">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-2024">Passeport#</span></span>
- <span data-ttu-id="16f62-2025">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16f62-2025">PasseportNon</span></span>
- <span data-ttu-id="16f62-2026">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16f62-2026">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="16f62-2027">Número de seguridad social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="16f62-2027">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2028">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2028">Format</span></span>

<span data-ttu-id="16f62-2029">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2029">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2030">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2030">Pattern</span></span>

<span data-ttu-id="16f62-2031">Debe coincidir uno de los dos patrones:</span><span class="sxs-lookup"><span data-stu-id="16f62-2031">Must match one of two patterns:</span></span>
- <span data-ttu-id="16f62-2032">13 dígitos seguidos de un espacio seguido de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2032">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="16f62-2033">o</span><span class="sxs-lookup"><span data-stu-id="16f62-2033">or</span></span>
- <span data-ttu-id="16f62-2034">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2034">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2035">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2035">Checksum</span></span>

<span data-ttu-id="16f62-2036">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2036">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2037">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2037">Definition</span></span>

<span data-ttu-id="16f62-2038">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2038">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2039">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2039">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2040">Se encuentra una palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="16f62-2040">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="16f62-2041">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2041">The checksum passes.</span></span>

<span data-ttu-id="16f62-2042">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2042">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2043">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2043">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2044">No se encuentra ninguna palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="16f62-2044">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="16f62-2045">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2045">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2046">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2046">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="16f62-2047">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="16f62-2047">Keyword_fr_insee</span></span>

- <span data-ttu-id="16f62-2048">INSEE</span><span class="sxs-lookup"><span data-stu-id="16f62-2048">insee</span></span>
- <span data-ttu-id="16f62-2049">securité sociale</span><span class="sxs-lookup"><span data-stu-id="16f62-2049">securité sociale</span></span>
- <span data-ttu-id="16f62-2050">securite sociale</span><span class="sxs-lookup"><span data-stu-id="16f62-2050">securite sociale</span></span>
- <span data-ttu-id="16f62-2051">national id</span><span class="sxs-lookup"><span data-stu-id="16f62-2051">national id</span></span>
- <span data-ttu-id="16f62-2052">national identification</span><span class="sxs-lookup"><span data-stu-id="16f62-2052">national identification</span></span>
- <span data-ttu-id="16f62-2053">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="16f62-2053">numéro d'identité</span></span>
- <span data-ttu-id="16f62-2054">no d'identité</span><span class="sxs-lookup"><span data-stu-id="16f62-2054">no d'identité</span></span>
- <span data-ttu-id="16f62-2055">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-2055">no.</span></span> <span data-ttu-id="16f62-2056">d'identité</span><span class="sxs-lookup"><span data-stu-id="16f62-2056">d'identité</span></span>
- <span data-ttu-id="16f62-2057">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="16f62-2057">numero d'identite</span></span>
- <span data-ttu-id="16f62-2058">no d'identite</span><span class="sxs-lookup"><span data-stu-id="16f62-2058">no d'identite</span></span>
- <span data-ttu-id="16f62-2059">dejan.</span><span class="sxs-lookup"><span data-stu-id="16f62-2059">no.</span></span> <span data-ttu-id="16f62-2060">d'identite</span><span class="sxs-lookup"><span data-stu-id="16f62-2060">d'identite</span></span>
- <span data-ttu-id="16f62-2061">social security number</span><span class="sxs-lookup"><span data-stu-id="16f62-2061">social security number</span></span>
- <span data-ttu-id="16f62-2062">social security code</span><span class="sxs-lookup"><span data-stu-id="16f62-2062">social security code</span></span>
- <span data-ttu-id="16f62-2063">social insurance number</span><span class="sxs-lookup"><span data-stu-id="16f62-2063">social insurance number</span></span>
- <span data-ttu-id="16f62-2064">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="16f62-2064">le numéro d'identification nationale</span></span>
- <span data-ttu-id="16f62-2065">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="16f62-2065">d'identité nationale</span></span>
- <span data-ttu-id="16f62-2066">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="16f62-2066">numéro de sécurité sociale</span></span>
- <span data-ttu-id="16f62-2067">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="16f62-2067">le code de la sécurité sociale</span></span>
- <span data-ttu-id="16f62-2068">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="16f62-2068">numéro d'assurance sociale</span></span>
- <span data-ttu-id="16f62-2069">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="16f62-2069">numéro de sécu</span></span>
- <span data-ttu-id="16f62-2070">code sécu</span><span class="sxs-lookup"><span data-stu-id="16f62-2070">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="16f62-2071">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="16f62-2071">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2072">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2072">Format</span></span>

<span data-ttu-id="16f62-2073">Combinación de 11 dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="16f62-2073">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2074">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2074">Pattern</span></span>

<span data-ttu-id="16f62-2075">11 dígitos y letras (no distingue entre mayúsculas y minúsculas):</span><span class="sxs-lookup"><span data-stu-id="16f62-2075">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="16f62-2076">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="16f62-2076">A digit or letter</span></span> 
- <span data-ttu-id="16f62-2077">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2077">Two digits</span></span> 
- <span data-ttu-id="16f62-2078">Seis dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="16f62-2078">Six digits or letters</span></span> 
- <span data-ttu-id="16f62-2079">Un dígito</span><span class="sxs-lookup"><span data-stu-id="16f62-2079">A digit</span></span> 
- <span data-ttu-id="16f62-2080">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="16f62-2080">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2081">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2081">Checksum</span></span>

<span data-ttu-id="16f62-2082">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2083">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2083">Definition</span></span>

<span data-ttu-id="16f62-2084">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2084">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2085">La función Func_german_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2085">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2086">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-2086">At least one of the following is true:</span></span>
    - <span data-ttu-id="16f62-2087">Se encuentra una palabra clave de Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2087">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="16f62-2088">Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="16f62-2088">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="16f62-2089">Se encuentra una palabra clave de Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="16f62-2089">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="16f62-2090">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2090">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2091">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2091">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="16f62-2092">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2092">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="16f62-2093">Führerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2093">Führerschein</span></span>
- <span data-ttu-id="16f62-2094">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2094">Fuhrerschein</span></span>
- <span data-ttu-id="16f62-2095">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2095">Fuehrerschein</span></span>
- <span data-ttu-id="16f62-2096">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2096">Führerscheinnummer</span></span>
- <span data-ttu-id="16f62-2097">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2097">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="16f62-2098">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2098">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="16f62-2099">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="16f62-2099">Führerschein-</span></span> 
- <span data-ttu-id="16f62-2100">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="16f62-2100">Fuhrerschein-</span></span> 
- <span data-ttu-id="16f62-2101">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="16f62-2101">Fuehrerschein-</span></span> 
- <span data-ttu-id="16f62-2102">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16f62-2102">FührerscheinnummerNr</span></span>
- <span data-ttu-id="16f62-2103">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16f62-2103">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="16f62-2104">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16f62-2104">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="16f62-2105">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2105">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="16f62-2106">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2106">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="16f62-2107">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2107">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="16f62-2108">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16f62-2108">Führerschein- Nr</span></span>
- <span data-ttu-id="16f62-2109">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16f62-2109">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="16f62-2110">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16f62-2110">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="16f62-2111">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2111">Führerschein- Klasse</span></span> 
- <span data-ttu-id="16f62-2112">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2112">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="16f62-2113">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2113">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="16f62-2114">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16f62-2114">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="16f62-2115">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16f62-2115">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="16f62-2116">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16f62-2116">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="16f62-2117">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2117">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="16f62-2118">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2118">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="16f62-2119">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2119">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="16f62-2120">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16f62-2120">Führerschein- Nr</span></span> 
- <span data-ttu-id="16f62-2121">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16f62-2121">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="16f62-2122">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16f62-2122">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="16f62-2123">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2123">Führerschein- Klasse</span></span> 
- <span data-ttu-id="16f62-2124">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2124">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="16f62-2125">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2125">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="16f62-2126">LISTAS</span><span class="sxs-lookup"><span data-stu-id="16f62-2126">DL</span></span> 
- <span data-ttu-id="16f62-2127">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="16f62-2127">DLS</span></span>
- <span data-ttu-id="16f62-2128">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-2128">Driv Lic</span></span> 
- <span data-ttu-id="16f62-2129">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="16f62-2129">Driv Licen</span></span> 
- <span data-ttu-id="16f62-2130">Driv License</span><span class="sxs-lookup"><span data-stu-id="16f62-2130">Driv License</span></span>
- <span data-ttu-id="16f62-2131">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2131">Driv Licenses</span></span> 
- <span data-ttu-id="16f62-2132">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-2132">Driv Licence</span></span> 
- <span data-ttu-id="16f62-2133">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-2133">Driv Licences</span></span> 
- <span data-ttu-id="16f62-2134">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-2134">Driv Lic</span></span> 
- <span data-ttu-id="16f62-2135">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="16f62-2135">Driver Licen</span></span> 
- <span data-ttu-id="16f62-2136">Driver License</span><span class="sxs-lookup"><span data-stu-id="16f62-2136">Driver License</span></span> 
- <span data-ttu-id="16f62-2137">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2137">Driver Licenses</span></span> 
- <span data-ttu-id="16f62-2138">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-2138">Driver Licence</span></span> 
- <span data-ttu-id="16f62-2139">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-2139">Driver Licences</span></span> 
- <span data-ttu-id="16f62-2140">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-2140">Drivers Lic</span></span> 
- <span data-ttu-id="16f62-2141">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="16f62-2141">Drivers Licen</span></span> 
- <span data-ttu-id="16f62-2142">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16f62-2142">Drivers License</span></span> 
- <span data-ttu-id="16f62-2143">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2143">Drivers Licenses</span></span> 
- <span data-ttu-id="16f62-2144">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-2144">Drivers Licence</span></span> 
- <span data-ttu-id="16f62-2145">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-2145">Drivers Licences</span></span> 
- <span data-ttu-id="16f62-2146">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-2146">Driver's Lic</span></span> 
- <span data-ttu-id="16f62-2147">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="16f62-2147">Driver's Licen</span></span> 
- <span data-ttu-id="16f62-2148">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16f62-2148">Driver's License</span></span> 
- <span data-ttu-id="16f62-2149">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2149">Driver's Licenses</span></span> 
- <span data-ttu-id="16f62-2150">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-2150">Driver's Licence</span></span> 
- <span data-ttu-id="16f62-2151">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-2151">Driver's Licences</span></span> 
- <span data-ttu-id="16f62-2152">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-2152">Driving Lic</span></span> 
- <span data-ttu-id="16f62-2153">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="16f62-2153">Driving Licen</span></span> 
- <span data-ttu-id="16f62-2154">Driving License</span><span class="sxs-lookup"><span data-stu-id="16f62-2154">Driving License</span></span> 
- <span data-ttu-id="16f62-2155">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2155">Driving Licenses</span></span> 
- <span data-ttu-id="16f62-2156">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="16f62-2156">Driving Licence</span></span> 
- <span data-ttu-id="16f62-2157">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="16f62-2157">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="16f62-2158">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="16f62-2158">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="16f62-2159">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2159">Nr-Führerschein</span></span> 
- <span data-ttu-id="16f62-2160">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2160">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="16f62-2161">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2161">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="16f62-2162">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2162">No-Führerschein</span></span> 
- <span data-ttu-id="16f62-2163">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2163">No-Fuhrerschein</span></span> 
- <span data-ttu-id="16f62-2164">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2164">No-Fuehrerschein</span></span> 
- <span data-ttu-id="16f62-2165">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2165">N-Führerschein</span></span> 
- <span data-ttu-id="16f62-2166">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2166">N-Fuhrerschein</span></span> 
- <span data-ttu-id="16f62-2167">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2167">N-Fuehrerschein</span></span>
- <span data-ttu-id="16f62-2168">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2168">Nr-Führerschein</span></span> 
- <span data-ttu-id="16f62-2169">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2169">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="16f62-2170">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2170">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="16f62-2171">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2171">No-Führerschein</span></span> 
- <span data-ttu-id="16f62-2172">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2172">No-Fuhrerschein</span></span> 
- <span data-ttu-id="16f62-2173">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2173">No-Fuehrerschein</span></span> 
- <span data-ttu-id="16f62-2174">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2174">N-Führerschein</span></span> 
- <span data-ttu-id="16f62-2175">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2175">N-Fuhrerschein</span></span> 
- <span data-ttu-id="16f62-2176">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="16f62-2176">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="16f62-2177">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16f62-2177">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="16f62-2178">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="16f62-2178">ausstellungsdatum</span></span>
- <span data-ttu-id="16f62-2179">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="16f62-2179">ausstellungsort</span></span>
- <span data-ttu-id="16f62-2180">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="16f62-2180">ausstellende behöde</span></span>
- <span data-ttu-id="16f62-2181">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="16f62-2181">ausstellende behorde</span></span>
- <span data-ttu-id="16f62-2182">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="16f62-2182">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="16f62-2183">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="16f62-2183">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2184">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2184">Format</span></span>

<span data-ttu-id="16f62-2185">10 dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="16f62-2185">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2186">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2186">Pattern</span></span>

<span data-ttu-id="16f62-2187">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16f62-2187">Pattern must include all of the following:</span></span>
- <span data-ttu-id="16f62-2188">El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="16f62-2188">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="16f62-2189">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2189">Three digits</span></span> 
- <span data-ttu-id="16f62-2190">Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="16f62-2190">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="16f62-2191">Un dígito</span><span class="sxs-lookup"><span data-stu-id="16f62-2191">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2192">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2192">Checksum</span></span>

<span data-ttu-id="16f62-2193">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2194">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2194">Definition</span></span>

<span data-ttu-id="16f62-2195">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2196">La función Func_german_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2196">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2197">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="16f62-2197">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="16f62-2198">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2198">The checksum passes.</span></span>

<span data-ttu-id="16f62-2199">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2199">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2200">La función Func_german_passport_data encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2200">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2201">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="16f62-2201">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="16f62-2202">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2202">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2203">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2203">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="16f62-2204">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-2204">Keyword_german_passport</span></span>

- <span data-ttu-id="16f62-2205">reisepass</span><span class="sxs-lookup"><span data-stu-id="16f62-2205">reisepass</span></span>
- <span data-ttu-id="16f62-2206">reisepasse</span><span class="sxs-lookup"><span data-stu-id="16f62-2206">reisepasse</span></span>
- <span data-ttu-id="16f62-2207">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2207">reisepassnummer</span></span>
- <span data-ttu-id="16f62-2208">usuarios</span><span class="sxs-lookup"><span data-stu-id="16f62-2208">passport</span></span>
- <span data-ttu-id="16f62-2209">passports</span><span class="sxs-lookup"><span data-stu-id="16f62-2209">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="16f62-2210">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="16f62-2210">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="16f62-2211">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="16f62-2211">geburtsdatum</span></span>
- <span data-ttu-id="16f62-2212">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="16f62-2212">ausstellungsdatum</span></span>
- <span data-ttu-id="16f62-2213">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="16f62-2213">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="16f62-2214">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2214">Keyword_german_passport_number</span></span>

<span data-ttu-id="16f62-2215">No-Reisepass NR-Reisepass</span><span class="sxs-lookup"><span data-stu-id="16f62-2215">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="16f62-2216">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="16f62-2216">Keyword_german_passport1</span></span>

<span data-ttu-id="16f62-2217">Reisepass-NR</span><span class="sxs-lookup"><span data-stu-id="16f62-2217">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="16f62-2218">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="16f62-2218">Keyword_german_passport2</span></span>

<span data-ttu-id="16f62-2219">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="16f62-2219">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="16f62-2220">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="16f62-2220">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2221">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2221">Format</span></span>

<span data-ttu-id="16f62-2222">Desde el 1 de noviembre de 2010: nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2222">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="16f62-2223">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2223">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2224">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2224">Pattern</span></span>

<span data-ttu-id="16f62-2225">Desde el 1 de noviembre de 2010:</span><span class="sxs-lookup"><span data-stu-id="16f62-2225">Since 1 November 2010:</span></span>
- <span data-ttu-id="16f62-2226">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-2226">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-2227">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2227">Eight digits</span></span>

<span data-ttu-id="16f62-2228">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:</span><span class="sxs-lookup"><span data-stu-id="16f62-2228">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="16f62-2229">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2229">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2230">Checksum</span></span>

<span data-ttu-id="16f62-2231">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2232">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2232">Definition</span></span>

<span data-ttu-id="16f62-2233">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2233">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2234">La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2234">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2235">Se encuentra una palabra clave de Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-2235">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2236">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="16f62-2237">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="16f62-2237">Keyword_germany_id_card</span></span>

- <span data-ttu-id="16f62-2238">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-2238">Identity Card</span></span>
- <span data-ttu-id="16f62-2239">Id.</span><span class="sxs-lookup"><span data-stu-id="16f62-2239">ID</span></span>
- <span data-ttu-id="16f62-2240">Determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-2240">Identification</span></span>
- <span data-ttu-id="16f62-2241">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="16f62-2241">Personalausweis</span></span>
- <span data-ttu-id="16f62-2242">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2242">Identifizierungsnummer</span></span>
- <span data-ttu-id="16f62-2243">Ausweis</span><span class="sxs-lookup"><span data-stu-id="16f62-2243">Ausweis</span></span>
- <span data-ttu-id="16f62-2244">Identifikation</span><span class="sxs-lookup"><span data-stu-id="16f62-2244">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="16f62-2245">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="16f62-2245">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2246">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2246">Format</span></span>

<span data-ttu-id="16f62-2247">Combinación de 7 u 8 letras y números más un guión</span><span class="sxs-lookup"><span data-stu-id="16f62-2247">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2248">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2248">Pattern</span></span>

<span data-ttu-id="16f62-2249">Siete letras y números (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="16f62-2249">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="16f62-2250">Una letra (cualquier letra del alfabeto griego) </span><span class="sxs-lookup"><span data-stu-id="16f62-2250">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="16f62-2251">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-2251">A dash</span></span> 
- <span data-ttu-id="16f62-2252">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2252">Six digits</span></span>

<span data-ttu-id="16f62-2253">Ocho letras y números (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="16f62-2253">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="16f62-2254">Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="16f62-2254">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="16f62-2255">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-2255">A dash</span></span> 
- <span data-ttu-id="16f62-2256">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2256">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2257">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2257">Checksum</span></span>

<span data-ttu-id="16f62-2258">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2258">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2259">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2259">Definition</span></span>

<span data-ttu-id="16f62-2260">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2261">La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2261">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2262">Se encuentra una palabra clave de Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-2262">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2263">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2263">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="16f62-2264">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="16f62-2264">Keyword_greece_id_card</span></span>

- <span data-ttu-id="16f62-2265">Tarjeta de identidad griega</span><span class="sxs-lookup"><span data-stu-id="16f62-2265">Greek identity Card</span></span>
- <span data-ttu-id="16f62-2266">Tautotita</span><span class="sxs-lookup"><span data-stu-id="16f62-2266">Tautotita</span></span>
- <span data-ttu-id="16f62-2267">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="16f62-2267">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="16f62-2268">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="16f62-2268">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="16f62-2269">Número de tarjeta de identidad de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="16f62-2269">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2270">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2270">Format</span></span>

<span data-ttu-id="16f62-2271">Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final</span><span class="sxs-lookup"><span data-stu-id="16f62-2271">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2272">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2272">Pattern</span></span>

<span data-ttu-id="16f62-2273">Combinación de 8 o 9 letras:</span><span class="sxs-lookup"><span data-stu-id="16f62-2273">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="16f62-2274">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-2274">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-2275">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2275">Six digits</span></span> 
- <span data-ttu-id="16f62-2276">El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="16f62-2276">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2277">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2277">Checksum</span></span>

<span data-ttu-id="16f62-2278">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2278">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2279">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2279">Definition</span></span>

<span data-ttu-id="16f62-2280">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2281">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2281">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2282">Se encuentra una palabra clave de Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-2282">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="16f62-2283">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2283">The checksum passes.</span></span>

<span data-ttu-id="16f62-2284">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2284">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2285">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2285">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2286">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2286">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2287">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2287">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="16f62-2288">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="16f62-2288">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="16f62-2289">tarjeta de identidad de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="16f62-2289">hong kong identity card</span></span>
- <span data-ttu-id="16f62-2290">HKIDC</span><span class="sxs-lookup"><span data-stu-id="16f62-2290">HKIDC</span></span>
- <span data-ttu-id="16f62-2291">id card</span><span class="sxs-lookup"><span data-stu-id="16f62-2291">id card</span></span>
- <span data-ttu-id="16f62-2292">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-2292">identity card</span></span>
- <span data-ttu-id="16f62-2293">tarjeta de identidad HK</span><span class="sxs-lookup"><span data-stu-id="16f62-2293">hk identity card</span></span>
- <span data-ttu-id="16f62-2294">ID de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="16f62-2294">hong kong id</span></span>
- <span data-ttu-id="16f62-2295">香港身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2295">香港身份證</span></span>
- <span data-ttu-id="16f62-2296">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2296">香港永久性居民身份證</span></span>
- <span data-ttu-id="16f62-2297">身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2297">身份證</span></span>
- <span data-ttu-id="16f62-2298">身份証</span><span class="sxs-lookup"><span data-stu-id="16f62-2298">身份証</span></span>
- <span data-ttu-id="16f62-2299">身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-2299">身分證</span></span>
- <span data-ttu-id="16f62-2300">身分証</span><span class="sxs-lookup"><span data-stu-id="16f62-2300">身分証</span></span>
- <span data-ttu-id="16f62-2301">香港身份証</span><span class="sxs-lookup"><span data-stu-id="16f62-2301">香港身份証</span></span>
- <span data-ttu-id="16f62-2302">香港身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-2302">香港身分證</span></span>
- <span data-ttu-id="16f62-2303">香港身分証</span><span class="sxs-lookup"><span data-stu-id="16f62-2303">香港身分証</span></span>
- <span data-ttu-id="16f62-2304">香港身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2304">香港身份證</span></span>
- <span data-ttu-id="16f62-2305">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2305">香港居民身份證</span></span>
- <span data-ttu-id="16f62-2306">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="16f62-2306">香港居民身份証</span></span>
- <span data-ttu-id="16f62-2307">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-2307">香港居民身分證</span></span>
- <span data-ttu-id="16f62-2308">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="16f62-2308">香港居民身分証</span></span>
- <span data-ttu-id="16f62-2309">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16f62-2309">香港永久性居民身份証</span></span>
- <span data-ttu-id="16f62-2310">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-2310">香港永久性居民身分證</span></span>
- <span data-ttu-id="16f62-2311">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16f62-2311">香港永久性居民身分証</span></span>
- <span data-ttu-id="16f62-2312">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2312">香港永久性居民身份證</span></span>
- <span data-ttu-id="16f62-2313">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2313">香港非永久性居民身份證</span></span>
- <span data-ttu-id="16f62-2314">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16f62-2314">香港非永久性居民身份証</span></span>
- <span data-ttu-id="16f62-2315">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-2315">香港非永久性居民身分證</span></span>
- <span data-ttu-id="16f62-2316">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16f62-2316">香港非永久性居民身分証</span></span>
- <span data-ttu-id="16f62-2317">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2317">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="16f62-2318">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16f62-2318">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="16f62-2319">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-2319">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="16f62-2320">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16f62-2320">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="16f62-2321">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-2321">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="16f62-2322">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16f62-2322">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="16f62-2323">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-2323">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="16f62-2324">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16f62-2324">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="16f62-2325">Número de cuenta permanente de India (PAN)</span><span class="sxs-lookup"><span data-stu-id="16f62-2325">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2326">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2326">Format</span></span>

<span data-ttu-id="16f62-2327">10 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2327">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2328">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2328">Pattern</span></span>

<span data-ttu-id="16f62-2329">10 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2329">10 letters or digits:</span></span>
- <span data-ttu-id="16f62-2330">Cinco letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-2330">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-2331">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2331">Four digits</span></span> 
- <span data-ttu-id="16f62-2332">Una letra que es un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="16f62-2332">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2333">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2333">Checksum</span></span>

<span data-ttu-id="16f62-2334">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2335">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2335">Definition</span></span>

<span data-ttu-id="16f62-2336">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2337">La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2337">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2338">Se encuentra una palabra clave de Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2338">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="16f62-2339">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2339">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2340">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2340">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="16f62-2341">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2341">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="16f62-2342">Número de cuenta permanente</span><span class="sxs-lookup"><span data-stu-id="16f62-2342">Permanent Account Number</span></span> 
- <span data-ttu-id="16f62-2343">MANO</span><span class="sxs-lookup"><span data-stu-id="16f62-2343">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="16f62-2344">Número de identificación único (Aadhaar) de la India</span><span class="sxs-lookup"><span data-stu-id="16f62-2344">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2345">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2345">Format</span></span>

<span data-ttu-id="16f62-2346">12 dígitos que contienen espacios o guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="16f62-2346">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2347">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2347">Pattern</span></span>

<span data-ttu-id="16f62-2348">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2348">12 digits:</span></span>
- <span data-ttu-id="16f62-2349">Cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2349">Four digits</span></span> 
- <span data-ttu-id="16f62-2350">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="16f62-2350">An optional space or dash</span></span> 
- <span data-ttu-id="16f62-2351">Cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2351">Four digits</span></span> 
- <span data-ttu-id="16f62-2352">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="16f62-2352">An optional space or dash</span></span> 
- <span data-ttu-id="16f62-2353">El dígito final que es el dígito de control</span><span class="sxs-lookup"><span data-stu-id="16f62-2353">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2354">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2354">Checksum</span></span>

<span data-ttu-id="16f62-2355">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2355">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2356">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2356">Definition</span></span>

<span data-ttu-id="16f62-2357">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2357">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="16f62-2358">Se encuentra una palabra clave de Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="16f62-2358">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="16f62-2359">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2359">The checksum passes.</span></span>
<span data-ttu-id="16f62-2360">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="16f62-2361">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2361">The checksum passes.</span></span>
<span data-ttu-id="16f62-2362"><!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="16f62-2362"></span></span>

### <a name="keywords"></a><span data-ttu-id="16f62-2363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2363">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="16f62-2364">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="16f62-2364">Keyword_india_aadhar</span></span>
- <span data-ttu-id="16f62-2365">Aadhar</span><span class="sxs-lookup"><span data-stu-id="16f62-2365">Aadhar</span></span>
- <span data-ttu-id="16f62-2366">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="16f62-2366">Aadhaar</span></span>
- <span data-ttu-id="16f62-2367">UID</span><span class="sxs-lookup"><span data-stu-id="16f62-2367">UID</span></span>
- <span data-ttu-id="16f62-2368">आधार</span><span class="sxs-lookup"><span data-stu-id="16f62-2368">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="16f62-2369">Número de tarjeta de identidad (KTP) de Indonesia</span><span class="sxs-lookup"><span data-stu-id="16f62-2369">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2370">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2370">Format</span></span>

<span data-ttu-id="16f62-2371">16 dígitos que contienen puntos opcionales</span><span class="sxs-lookup"><span data-stu-id="16f62-2371">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2372">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2372">Pattern</span></span>

<span data-ttu-id="16f62-2373">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2373">16 digits:</span></span>
- <span data-ttu-id="16f62-2374">Código de la provincia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2374">Two-digit province code</span></span> 
- <span data-ttu-id="16f62-2375">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2375">A period (optional)</span></span> 
- <span data-ttu-id="16f62-2376">Código de ciudad o regencia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2376">Two-digit regency or city code</span></span> 
- <span data-ttu-id="16f62-2377">Código de subdistrito de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2377">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="16f62-2378">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2378">A period (optional)</span></span> 
- <span data-ttu-id="16f62-2379">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-2379">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="16f62-2380">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2380">A period (optional)</span></span> 
- <span data-ttu-id="16f62-2381">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2381">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2382">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2382">Checksum</span></span>

<span data-ttu-id="16f62-2383">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2383">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2384">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2384">Definition</span></span>

<span data-ttu-id="16f62-2385">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2386">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2386">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2387">Se encuentra una palabra clave de Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-2387">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="16f62-2388">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2388">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2389">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2389">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2390">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2390">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="16f62-2391">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="16f62-2391">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="16f62-2392">KTP</span><span class="sxs-lookup"><span data-stu-id="16f62-2392">KTP</span></span>
- <span data-ttu-id="16f62-2393">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="16f62-2393">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="16f62-2394">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="16f62-2394">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="16f62-2395">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="16f62-2395">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2396">Format</span></span>

<span data-ttu-id="16f62-2397">Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)
</span><span class="sxs-lookup"><span data-stu-id="16f62-2397">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2398">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2398">Pattern</span></span>

<span data-ttu-id="16f62-2399">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16f62-2399">Pattern must include all of the following:</span></span>

- <span data-ttu-id="16f62-2400">Código de país de dos letras</span><span class="sxs-lookup"><span data-stu-id="16f62-2400">Two-letter country code</span></span>
- <span data-ttu-id="16f62-2401">Dos dígitos de control (seguidos de un espacio opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2401">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="16f62-2402">1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)</span><span class="sxs-lookup"><span data-stu-id="16f62-2402">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="16f62-2403">1-3 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2403">1-3 letters or digits</span></span>

<span data-ttu-id="16f62-p134">El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:</span><span class="sxs-lookup"><span data-stu-id="16f62-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="16f62-2406">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="16f62-2406">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2407">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2407">Checksum</span></span>

<span data-ttu-id="16f62-2408">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2408">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2409">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2409">Definition</span></span>

<span data-ttu-id="16f62-2410">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2410">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2411">La función Func_iban encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2411">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2412">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2412">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2413">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2413">Keywords</span></span>

<span data-ttu-id="16f62-2414">Ninguno</span><span class="sxs-lookup"><span data-stu-id="16f62-2414">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="16f62-2415">dirección IP</span><span class="sxs-lookup"><span data-stu-id="16f62-2415">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2416">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2416">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="16f62-2417">IPv4</span><span class="sxs-lookup"><span data-stu-id="16f62-2417">IPv4:</span></span>
<span data-ttu-id="16f62-2418">Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="16f62-2418">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="16f62-2419">Protocolo</span><span class="sxs-lookup"><span data-stu-id="16f62-2419">IPv6:</span></span>
<span data-ttu-id="16f62-2420"> Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)</span><span class="sxs-lookup"><span data-stu-id="16f62-2420">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2421">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2421">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2422">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2422">Checksum</span></span>

<span data-ttu-id="16f62-2423">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2424">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2424">Definition</span></span>

<span data-ttu-id="16f62-2425">Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2425">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2426">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2426">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2427">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="16f62-2427">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="16f62-2428">Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2428">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2429">La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2429">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2430">Se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="16f62-2430">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="16f62-2431">Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2431">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2432">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2432">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2433">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="16f62-2433">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2434">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2434">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="16f62-2435">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="16f62-2435">Keyword_ipaddress</span></span>

- <span data-ttu-id="16f62-2436">IP (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-2436">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="16f62-2437">dirección IP</span><span class="sxs-lookup"><span data-stu-id="16f62-2437">ip address</span></span> 
- <span data-ttu-id="16f62-2438">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="16f62-2438">ip addresses</span></span>
- <span data-ttu-id="16f62-2439">internet protocol</span><span class="sxs-lookup"><span data-stu-id="16f62-2439">internet protocol</span></span>
- <span data-ttu-id="16f62-2440">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="16f62-2440">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="16f62-2441">Clasificación Internacional de enfermedades (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="16f62-2441">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2442">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2442">Format</span></span>

<span data-ttu-id="16f62-2443">Dictionary</span><span class="sxs-lookup"><span data-stu-id="16f62-2443">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2444">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2444">Pattern</span></span>

<span data-ttu-id="16f62-2445">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2445">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2446">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2446">Checksum</span></span>

<span data-ttu-id="16f62-2447">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2447">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2448">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2448">Definition</span></span>

<span data-ttu-id="16f62-2449">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2449">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2450">Se encuentra una palabra clave de Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="16f62-2450">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="16f62-2451">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2451">Keywords</span></span>

<span data-ttu-id="16f62-2452">Cualquier término del Diccionario de palabras clave de Dictionary_icd_10_cm, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="16f62-2452">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="16f62-2453">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="16f62-2453">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="16f62-2454">Clasificación Internacional de enfermedades (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="16f62-2454">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2455">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2455">Format</span></span>

<span data-ttu-id="16f62-2456">Dictionary</span><span class="sxs-lookup"><span data-stu-id="16f62-2456">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2457">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2457">Pattern</span></span>

<span data-ttu-id="16f62-2458">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2458">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2459">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2459">Checksum</span></span>

<span data-ttu-id="16f62-2460">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2460">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2461">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2461">Definition</span></span>

<span data-ttu-id="16f62-2462">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2462">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2463">Se encuentra una palabra clave de Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="16f62-2463">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2464">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2464">Keywords</span></span>

<span data-ttu-id="16f62-2465">Cualquier término del Diccionario de palabras clave de Dictionary_icd_9_cm, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="16f62-2465">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="16f62-2466">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="16f62-2466">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="16f62-2467">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="16f62-2467">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2468">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2468">Format</span></span>

<span data-ttu-id="16f62-2469">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="16f62-2469">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="16f62-2470">Siete dígitos seguidos por 1 o 2 letras </span><span class="sxs-lookup"><span data-stu-id="16f62-2470">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="16f62-2471">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="16f62-2471">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="16f62-2472">Siete dígitos seguidos por dos letras</span><span class="sxs-lookup"><span data-stu-id="16f62-2472">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2473">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2473">Pattern</span></span>

<span data-ttu-id="16f62-2474">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="16f62-2474">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="16f62-2475">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2475">Seven digits</span></span> 
- <span data-ttu-id="16f62-2476">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-2476">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="16f62-2477">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="16f62-2477">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="16f62-2478">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2478">Seven digits</span></span> 
- <span data-ttu-id="16f62-2479">Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético </span><span class="sxs-lookup"><span data-stu-id="16f62-2479">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="16f62-2480">La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-2480">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2481">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2481">Checksum</span></span>

<span data-ttu-id="16f62-2482">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2482">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2483">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2483">Definition</span></span>

<span data-ttu-id="16f62-2484">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2485">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2485">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2486">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-2486">One of the following is true:</span></span>
    - <span data-ttu-id="16f62-2487">Se encuentra una palabra clave de Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="16f62-2487">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="16f62-2488">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-2488">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16f62-2489">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2489">The checksum passes.</span></span>

<span data-ttu-id="16f62-2490">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2490">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2491">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2491">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2492">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2492">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2493">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2493">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="16f62-2494">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="16f62-2494">Keyword_ireland_pps</span></span>

- <span data-ttu-id="16f62-2495">Número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="16f62-2495">Personal Public Service Number</span></span> 
- <span data-ttu-id="16f62-2496">Número de PPS</span><span class="sxs-lookup"><span data-stu-id="16f62-2496">PPS Number</span></span> 
- <span data-ttu-id="16f62-2497">Núm. PPS
</span><span class="sxs-lookup"><span data-stu-id="16f62-2497">PPS Num</span></span> 
- <span data-ttu-id="16f62-2498">N.º PPS</span><span class="sxs-lookup"><span data-stu-id="16f62-2498">PPS No.</span></span> 
- <span data-ttu-id="16f62-2499">N.ro PPS</span><span class="sxs-lookup"><span data-stu-id="16f62-2499">PPS #</span></span> 
- <span data-ttu-id="16f62-2500">PPS</span><span class="sxs-lookup"><span data-stu-id="16f62-2500">PPS#</span></span> 
- <span data-ttu-id="16f62-2501">PPSN</span><span class="sxs-lookup"><span data-stu-id="16f62-2501">PPSN</span></span> 
- <span data-ttu-id="16f62-2502">Tarjeta de servicios públicos</span><span class="sxs-lookup"><span data-stu-id="16f62-2502">Public Services Card</span></span> 
- <span data-ttu-id="16f62-2503">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="16f62-2503">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="16f62-2504">Uimh.</span><span class="sxs-lookup"><span data-stu-id="16f62-2504">Uimh.</span></span> <span data-ttu-id="16f62-2505">PSP</span><span class="sxs-lookup"><span data-stu-id="16f62-2505">PSP</span></span> 
- <span data-ttu-id="16f62-2506">PSP</span><span class="sxs-lookup"><span data-stu-id="16f62-2506">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="16f62-2507">Número de cuenta bancaria de Israel</span><span class="sxs-lookup"><span data-stu-id="16f62-2507">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2508">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2508">Format</span></span>

<span data-ttu-id="16f62-2509">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2509">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2510">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2510">Pattern</span></span>

<span data-ttu-id="16f62-2511">Con formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2511">Formatted:</span></span>
- <span data-ttu-id="16f62-2512">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2512">Two digits</span></span> 
- <span data-ttu-id="16f62-2513">Guion</span><span class="sxs-lookup"><span data-stu-id="16f62-2513">A dash</span></span> 
- <span data-ttu-id="16f62-2514">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2514">Three digits</span></span> 
- <span data-ttu-id="16f62-2515">Guion</span><span class="sxs-lookup"><span data-stu-id="16f62-2515">A dash</span></span> 
- <span data-ttu-id="16f62-2516">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2516">Eight digits</span></span>

<span data-ttu-id="16f62-2517">Sin formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2517">Unformatted:</span></span>
- <span data-ttu-id="16f62-2518">	13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2518">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2519">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2519">Checksum</span></span>

<span data-ttu-id="16f62-2520">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2520">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2521">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2521">Definition</span></span>

<span data-ttu-id="16f62-2522">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2523">La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2523">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2524">Se encuentra una palabra clave de Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2524">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2525">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2525">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="16f62-2526">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2526">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="16f62-2527">Número de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="16f62-2527">Bank Account Number</span></span> 
- <span data-ttu-id="16f62-2528">Cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="16f62-2528">Bank Account</span></span> 
- <span data-ttu-id="16f62-2529">Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2529">Account Number</span></span> 
- <span data-ttu-id="16f62-2530">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="16f62-2530">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="16f62-2531">Identificación nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="16f62-2531">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2532">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2532">Format</span></span>

<span data-ttu-id="16f62-2533">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2534">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2534">Pattern</span></span>

<span data-ttu-id="16f62-2535">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2536">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2536">Checksum</span></span>

<span data-ttu-id="16f62-2537">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2537">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2538">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2538">Definition</span></span>

<span data-ttu-id="16f62-2539">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2540">La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2540">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2541">Se encuentra una palabra clave de Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="16f62-2541">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="16f62-2542">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2542">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2543">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2543">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="16f62-2544">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="16f62-2544">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="16f62-2545">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="16f62-2545">מספר זהות</span></span> 
- <span data-ttu-id="16f62-2546">National ID Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2546">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="16f62-2547">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="16f62-2547">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2548">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2548">Format</span></span>

<span data-ttu-id="16f62-2549">Una combinación de 10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2549">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2550">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2550">Pattern</span></span>

- <span data-ttu-id="16f62-2551">Una combinación de 10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2551">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="16f62-2552">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-2552">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-2553">La letra "A" o "V" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-2553">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-2554">Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado</span><span class="sxs-lookup"><span data-stu-id="16f62-2554">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="16f62-2555">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-2555">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2556">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2556">Checksum</span></span>

<span data-ttu-id="16f62-2557">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2557">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2558">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2558">Definition</span></span>

<span data-ttu-id="16f62-2559">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2559">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2560">La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2560">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2561">Se encuentra una palabra clave de Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2561">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2562">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2562">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="16f62-2563">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2563">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="16f62-2564">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="16f62-2564">numero di patente di guida</span></span> 
- <span data-ttu-id="16f62-2565">patente di guida</span><span class="sxs-lookup"><span data-stu-id="16f62-2565">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="16f62-2566">Número de cuenta bancaria de Japón</span><span class="sxs-lookup"><span data-stu-id="16f62-2566">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2567">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2567">Format</span></span>

<span data-ttu-id="16f62-2568">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2568">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2569">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2569">Pattern</span></span>

<span data-ttu-id="16f62-2570">Número de cuenta bancaria:</span><span class="sxs-lookup"><span data-stu-id="16f62-2570">Bank account number:</span></span>
- <span data-ttu-id="16f62-2571">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2571">Seven or eight digits</span></span>
- <span data-ttu-id="16f62-2572">Código de sucursal del banco:</span><span class="sxs-lookup"><span data-stu-id="16f62-2572">Bank account branch code:</span></span>
- <span data-ttu-id="16f62-2573">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2573">Four digits</span></span> 
- <span data-ttu-id="16f62-2574">Un espacio o un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="16f62-2574">A space or dash (optional)</span></span> 
- <span data-ttu-id="16f62-2575">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2575">Three digits</span></span>

<span data-ttu-id="16f62-2576">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2576">Checksum</span></span>

<span data-ttu-id="16f62-2577">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2577">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2578">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2578">Definition</span></span>

<span data-ttu-id="16f62-2579">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2580">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2580">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2581">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="16f62-2581">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="16f62-2582">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-2582">One of the following is true:</span></span>
- <span data-ttu-id="16f62-2583">La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2583">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2584">Se encuentra una palabra clave de Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="16f62-2584">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="16f62-2585">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2586">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2586">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2587">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="16f62-2587">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2588">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2588">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="16f62-2589">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="16f62-2589">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="16f62-2590">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2590">Checking Account Number</span></span> 
- <span data-ttu-id="16f62-2591">Checking Account</span><span class="sxs-lookup"><span data-stu-id="16f62-2591">Checking Account</span></span> 
- <span data-ttu-id="16f62-2592">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-2592">Checking Account #</span></span> 
- <span data-ttu-id="16f62-2593">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2593">Checking Acct Number</span></span> 
- <span data-ttu-id="16f62-2594">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-2594">Checking Acct #</span></span> 
- <span data-ttu-id="16f62-2595">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2595">Checking Acct No.</span></span> 
- <span data-ttu-id="16f62-2596">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2596">Checking Account No.</span></span> 
- <span data-ttu-id="16f62-2597">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2597">Bank Account Number</span></span> 
- <span data-ttu-id="16f62-2598">Bank Account</span><span class="sxs-lookup"><span data-stu-id="16f62-2598">Bank Account</span></span> 
- <span data-ttu-id="16f62-2599">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-2599">Bank Account #</span></span> 
- <span data-ttu-id="16f62-2600">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2600">Bank Acct Number</span></span> 
- <span data-ttu-id="16f62-2601">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-2601">Bank Acct #</span></span> 
- <span data-ttu-id="16f62-2602">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2602">Bank Acct No.</span></span> 
- <span data-ttu-id="16f62-2603">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2603">Bank Account No.</span></span> 
- <span data-ttu-id="16f62-2604">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2604">Savings Account Number</span></span> 
- <span data-ttu-id="16f62-2605">Savings Account</span><span class="sxs-lookup"><span data-stu-id="16f62-2605">Savings Account</span></span> 
- <span data-ttu-id="16f62-2606">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-2606">Savings Account #</span></span> 
- <span data-ttu-id="16f62-2607">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2607">Savings Acct Number</span></span> 
- <span data-ttu-id="16f62-2608">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-2608">Savings Acct #</span></span> 
- <span data-ttu-id="16f62-2609">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2609">Savings Acct No.</span></span> 
- <span data-ttu-id="16f62-2610">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2610">Savings Account No.</span></span> 
- <span data-ttu-id="16f62-2611">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2611">Debit Account Number</span></span> 
- <span data-ttu-id="16f62-2612">Debit Account</span><span class="sxs-lookup"><span data-stu-id="16f62-2612">Debit Account</span></span> 
- <span data-ttu-id="16f62-2613">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-2613">Debit Account #</span></span> 
- <span data-ttu-id="16f62-2614">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2614">Debit Acct Number</span></span> 
- <span data-ttu-id="16f62-2615">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-2615">Debit Acct #</span></span> 
- <span data-ttu-id="16f62-2616">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2616">Debit Acct No.</span></span> 
- <span data-ttu-id="16f62-2617">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2617">Debit Account No.</span></span> 
- <span data-ttu-id="16f62-2618">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="16f62-2618">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="16f62-2619">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="16f62-2619">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="16f62-2620">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="16f62-2620">＃勘定の確認</span></span> 
- <span data-ttu-id="16f62-2621">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="16f62-2621">勘定番号の確認</span></span> 
- <span data-ttu-id="16f62-2622">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="16f62-2622">口座番号の確認</span></span> 
- <span data-ttu-id="16f62-2623">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2623">銀行口座番号</span></span> 
- <span data-ttu-id="16f62-2624">銀行口座</span><span class="sxs-lookup"><span data-stu-id="16f62-2624">銀行口座</span></span> 
- <span data-ttu-id="16f62-2625">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="16f62-2625">銀行口座＃</span></span> 
- <span data-ttu-id="16f62-2626">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2626">銀行の勘定番号</span></span> 
- <span data-ttu-id="16f62-2627">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="16f62-2627">銀行のacct＃</span></span> 
- <span data-ttu-id="16f62-2628">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="16f62-2628">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="16f62-2629">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2629">銀行口座番号</span></span>
- <span data-ttu-id="16f62-2630">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2630">普通預金口座番号</span></span> 
- <span data-ttu-id="16f62-2631">預金口座</span><span class="sxs-lookup"><span data-stu-id="16f62-2631">預金口座</span></span> 
- <span data-ttu-id="16f62-2632">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="16f62-2632">貯蓄口座＃</span></span> 
- <span data-ttu-id="16f62-2633">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="16f62-2633">貯蓄勘定の数</span></span> 
- <span data-ttu-id="16f62-2634">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="16f62-2634">貯蓄勘定＃</span></span> 
- <span data-ttu-id="16f62-2635">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2635">貯蓄勘定番号</span></span> 
- <span data-ttu-id="16f62-2636">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2636">普通預金口座番号</span></span> 
- <span data-ttu-id="16f62-2637">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2637">引き落とし口座番号</span></span> 
- <span data-ttu-id="16f62-2638">口座番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2638">口座番号</span></span> 
- <span data-ttu-id="16f62-2639">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="16f62-2639">口座番号＃</span></span> 
- <span data-ttu-id="16f62-2640">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2640">デビットのacct番号</span></span> 
- <span data-ttu-id="16f62-2641">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="16f62-2641">デビット勘定＃</span></span> 
- <span data-ttu-id="16f62-2642">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2642">デビットACCTの番号</span></span> 
- <span data-ttu-id="16f62-2643">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2643">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="16f62-2644">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="16f62-2644">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="16f62-2645">Otemachi</span><span class="sxs-lookup"><span data-stu-id="16f62-2645">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="16f62-2646">Número de licencia de conductor de Japón</span><span class="sxs-lookup"><span data-stu-id="16f62-2646">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2647">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2647">Format</span></span>

<span data-ttu-id="16f62-2648">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2648">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2649">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2649">Pattern</span></span>

<span data-ttu-id="16f62-2650">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2650">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2651">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2651">Checksum</span></span>

<span data-ttu-id="16f62-2652">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2652">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2653">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2653">Definition</span></span>

<span data-ttu-id="16f62-2654">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2654">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2655">La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2655">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2656">Se encuentra una palabra clave de Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2656">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2657">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2657">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="16f62-2658">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2658">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="16f62-2659">listas</span><span class="sxs-lookup"><span data-stu-id="16f62-2659">dl#</span></span> 
- <span data-ttu-id="16f62-2660">LISTAS</span><span class="sxs-lookup"><span data-stu-id="16f62-2660">DL＃</span></span> 
- <span data-ttu-id="16f62-2661">distribución</span><span class="sxs-lookup"><span data-stu-id="16f62-2661">dls#</span></span> 
- <span data-ttu-id="16f62-2662">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="16f62-2662">DLS＃</span></span> 
- <span data-ttu-id="16f62-2663">driver license</span><span class="sxs-lookup"><span data-stu-id="16f62-2663">driver license</span></span> 
- <span data-ttu-id="16f62-2664">driver licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2664">driver licenses</span></span> 
- <span data-ttu-id="16f62-2665">drivers license</span><span class="sxs-lookup"><span data-stu-id="16f62-2665">drivers license</span></span> 
- <span data-ttu-id="16f62-2666">driver's license</span><span class="sxs-lookup"><span data-stu-id="16f62-2666">driver's license</span></span> 
- <span data-ttu-id="16f62-2667">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2667">drivers licenses</span></span> 
- <span data-ttu-id="16f62-2668">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-2668">driver's licenses</span></span> 
- <span data-ttu-id="16f62-2669">driving licence</span><span class="sxs-lookup"><span data-stu-id="16f62-2669">driving licence</span></span> 
- <span data-ttu-id="16f62-2670">Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-2670">lic#</span></span> 
- <span data-ttu-id="16f62-2671">Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-2671">LIC＃</span></span> 
- <span data-ttu-id="16f62-2672">conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-2672">lics#</span></span> 
- <span data-ttu-id="16f62-2673">state id</span><span class="sxs-lookup"><span data-stu-id="16f62-2673">state id</span></span> 
- <span data-ttu-id="16f62-2674">state identification</span><span class="sxs-lookup"><span data-stu-id="16f62-2674">state identification</span></span> 
- <span data-ttu-id="16f62-2675">state identification number</span><span class="sxs-lookup"><span data-stu-id="16f62-2675">state identification number</span></span> 
- <span data-ttu-id="16f62-2676">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="16f62-2676">低所得国＃</span></span> 
- <span data-ttu-id="16f62-2677">免許証</span><span class="sxs-lookup"><span data-stu-id="16f62-2677">免許証</span></span> 
- <span data-ttu-id="16f62-2678">状態ID</span><span class="sxs-lookup"><span data-stu-id="16f62-2678">状態ID</span></span>
- <span data-ttu-id="16f62-2679">状態の識別</span><span class="sxs-lookup"><span data-stu-id="16f62-2679">状態の識別</span></span> 
- <span data-ttu-id="16f62-2680">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2680">状態の識別番号</span></span> 
- <span data-ttu-id="16f62-2681">運転免許</span><span class="sxs-lookup"><span data-stu-id="16f62-2681">運転免許</span></span> 
- <span data-ttu-id="16f62-2682">運転免許証</span><span class="sxs-lookup"><span data-stu-id="16f62-2682">運転免許証</span></span> 
- <span data-ttu-id="16f62-2683">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2683">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="16f62-2684">Número de pasaporte de Japón</span><span class="sxs-lookup"><span data-stu-id="16f62-2684">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2685">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2685">Format</span></span>

<span data-ttu-id="16f62-2686">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2686">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2687">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2687">Pattern</span></span>

<span data-ttu-id="16f62-2688">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2688">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2689">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2689">Checksum</span></span>

<span data-ttu-id="16f62-2690">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2690">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2691">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2691">Definition</span></span>

<span data-ttu-id="16f62-2692">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2692">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2693">La función Func_jp_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2693">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2694">Se encuentra una palabra clave de Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="16f62-2694">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2695">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2695">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="16f62-2696">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-2696">Keyword_jp_passport</span></span>

- <span data-ttu-id="16f62-2697">パスポート</span><span class="sxs-lookup"><span data-stu-id="16f62-2697">パスポート</span></span> 
- <span data-ttu-id="16f62-2698">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2698">パスポート番号</span></span> 
- <span data-ttu-id="16f62-2699">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16f62-2699">パスポートのNum</span></span> 
- <span data-ttu-id="16f62-2700">パスポート #</span><span class="sxs-lookup"><span data-stu-id="16f62-2700">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="16f62-2701">Número de registro de residente de Japón</span><span class="sxs-lookup"><span data-stu-id="16f62-2701">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2702">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2702">Format</span></span>

<span data-ttu-id="16f62-2703">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2703">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2704">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2704">Pattern</span></span>

<span data-ttu-id="16f62-2705">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2705">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2706">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2706">Checksum</span></span>

<span data-ttu-id="16f62-2707">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2707">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2708">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2708">Definition</span></span>

<span data-ttu-id="16f62-2709">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2709">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2710">La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2710">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2711">Se encuentra una palabra clave de Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2711">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2712">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2712">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="16f62-2713">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2713">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="16f62-2714">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2714">Resident Registration Number</span></span>
- <span data-ttu-id="16f62-2715">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2715">Resident Register Number</span></span> 
- <span data-ttu-id="16f62-2716">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2716">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="16f62-2717">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2717">Resident Registration No.</span></span> 
- <span data-ttu-id="16f62-2718">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2718">Resident Register No.</span></span> 
- <span data-ttu-id="16f62-2719">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2719">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="16f62-2720">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2720">Basic Resident Register No.</span></span> 
- <span data-ttu-id="16f62-2721">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="16f62-2721">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="16f62-2722">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2722">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="16f62-2723">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="16f62-2723">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="16f62-2724">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2724">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="16f62-2725">Número de Seguridad Social de Japón (SIN)</span><span class="sxs-lookup"><span data-stu-id="16f62-2725">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2726">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2726">Format</span></span>

<span data-ttu-id="16f62-2727">De 7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2727">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2728">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2728">Pattern</span></span>

<span data-ttu-id="16f62-2729">7-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2729">7-12 digits:</span></span>
- <span data-ttu-id="16f62-2730">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2730">Four digits</span></span> 
- <span data-ttu-id="16f62-2731">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="16f62-2731">A hyphen (optional)</span></span> 
- <span data-ttu-id="16f62-2732">Seis dígitos o</span><span class="sxs-lookup"><span data-stu-id="16f62-2732">Six digits OR</span></span>
- <span data-ttu-id="16f62-2733">De 7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2733">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2734">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2734">Checksum</span></span>

<span data-ttu-id="16f62-2735">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2736">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2736">Definition</span></span>

<span data-ttu-id="16f62-2737">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2737">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2738">La función Func_jp_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2738">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2739">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="16f62-2739">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="16f62-2740">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2740">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2741">La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2741">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2742">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="16f62-2742">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2743">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2743">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="16f62-2744">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="16f62-2744">Keyword_jp_sin</span></span>

- <span data-ttu-id="16f62-2745">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="16f62-2745">Social Insurance No.</span></span> 
- <span data-ttu-id="16f62-2746">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="16f62-2746">Social Insurance Num</span></span> 
- <span data-ttu-id="16f62-2747">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="16f62-2747">Social Insurance Number</span></span> 
- <span data-ttu-id="16f62-2748">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="16f62-2748">社会保険のテンキー</span></span> 
- <span data-ttu-id="16f62-2749">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2749">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="16f62-2750">Número de tarjeta de residencia japonés</span><span class="sxs-lookup"><span data-stu-id="16f62-2750">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2751">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2751">Format</span></span>

<span data-ttu-id="16f62-2752">12 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2752">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2753">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2753">Pattern</span></span>

<span data-ttu-id="16f62-2754">12 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2754">12 letters and digits:</span></span>
- <span data-ttu-id="16f62-2755">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-2755">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="16f62-2756">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2756">Eight digits</span></span> 
- <span data-ttu-id="16f62-2757">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-2757">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2758">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2758">Checksum</span></span>

<span data-ttu-id="16f62-2759">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2759">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2760">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2760">Definition</span></span>

<span data-ttu-id="16f62-2761">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2761">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2762">La expresión regular Regex_jp_residence_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2762">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2763">Se encuentra una palabra clave de Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2763">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2764">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2764">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="16f62-2765">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2765">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="16f62-2766">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="16f62-2766">Residence card number</span></span>
- <span data-ttu-id="16f62-2767">Nº de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="16f62-2767">Residence card no</span></span>
- <span data-ttu-id="16f62-2768">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="16f62-2768">Residence card #</span></span>
- <span data-ttu-id="16f62-2769">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="16f62-2769">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="16f62-2770">Número de la tarjeta de identificación de Malasia</span><span class="sxs-lookup"><span data-stu-id="16f62-2770">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2771">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2771">Format</span></span>

<span data-ttu-id="16f62-2772">12 dígitos que contienen guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="16f62-2772">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2773">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2773">Pattern</span></span>

<span data-ttu-id="16f62-2774">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2774">12 digits:</span></span>
- <span data-ttu-id="16f62-2775">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-2775">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16f62-2776">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2776">A dash (optional)</span></span> 
- <span data-ttu-id="16f62-2777">Código de dos letras del lugar de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-2777">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="16f62-2778">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2778">A dash (optional)</span></span> 
- <span data-ttu-id="16f62-2779">Tres dígitos aleatorios </span><span class="sxs-lookup"><span data-stu-id="16f62-2779">Three random digits</span></span> 
- <span data-ttu-id="16f62-2780">Código de género de un dígito</span><span class="sxs-lookup"><span data-stu-id="16f62-2780">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2781">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2781">Checksum</span></span>

<span data-ttu-id="16f62-2782">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2782">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2783">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2783">Definition</span></span>

<span data-ttu-id="16f62-2784">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2785">La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2785">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2786">Se encuentra una palabra clave de Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2786">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2787">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2787">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="16f62-2788">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2788">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="16f62-2789">tarjeta de aplicación digital</span><span class="sxs-lookup"><span data-stu-id="16f62-2789">digital application card</span></span>
- <span data-ttu-id="16f62-2790">i/c</span><span class="sxs-lookup"><span data-stu-id="16f62-2790">i/c</span></span>
- <span data-ttu-id="16f62-2791">i/c no</span><span class="sxs-lookup"><span data-stu-id="16f62-2791">i/c no</span></span>
- <span data-ttu-id="16f62-2792">i</span><span class="sxs-lookup"><span data-stu-id="16f62-2792">ic</span></span>
- <span data-ttu-id="16f62-2793">no IC</span><span class="sxs-lookup"><span data-stu-id="16f62-2793">ic no</span></span>
- <span data-ttu-id="16f62-2794">id card</span><span class="sxs-lookup"><span data-stu-id="16f62-2794">id card</span></span>
- <span data-ttu-id="16f62-2795">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="16f62-2795">identification Card</span></span>
- <span data-ttu-id="16f62-2796">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-2796">identity card</span></span>
- <span data-ttu-id="16f62-2797">k/p</span><span class="sxs-lookup"><span data-stu-id="16f62-2797">k/p</span></span>
- <span data-ttu-id="16f62-2798">k/p no</span><span class="sxs-lookup"><span data-stu-id="16f62-2798">k/p no</span></span>
- <span data-ttu-id="16f62-2799">Kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="16f62-2799">kad akuan diri</span></span>
- <span data-ttu-id="16f62-2800">Kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="16f62-2800">kad aplikasi digital</span></span>
- <span data-ttu-id="16f62-2801">Kad pengenalan Malasia</span><span class="sxs-lookup"><span data-stu-id="16f62-2801">kad pengenalan malaysia</span></span>
- <span data-ttu-id="16f62-2802">PK</span><span class="sxs-lookup"><span data-stu-id="16f62-2802">kp</span></span>
- <span data-ttu-id="16f62-2803">KP no</span><span class="sxs-lookup"><span data-stu-id="16f62-2803">kp no</span></span>
- <span data-ttu-id="16f62-2804">mykad</span><span class="sxs-lookup"><span data-stu-id="16f62-2804">mykad</span></span>
- <span data-ttu-id="16f62-2805">MYKAS</span><span class="sxs-lookup"><span data-stu-id="16f62-2805">mykas</span></span>
- <span data-ttu-id="16f62-2806">mykid</span><span class="sxs-lookup"><span data-stu-id="16f62-2806">mykid</span></span>
- <span data-ttu-id="16f62-2807">mypr</span><span class="sxs-lookup"><span data-stu-id="16f62-2807">mypr</span></span>
- <span data-ttu-id="16f62-2808">mytentera</span><span class="sxs-lookup"><span data-stu-id="16f62-2808">mytentera</span></span>
- <span data-ttu-id="16f62-2809">tarjeta de identidad de Malasia</span><span class="sxs-lookup"><span data-stu-id="16f62-2809">malaysia identity card</span></span>
- <span data-ttu-id="16f62-2810">tarjeta de identidad malasio</span><span class="sxs-lookup"><span data-stu-id="16f62-2810">malaysian identity card</span></span>
- <span data-ttu-id="16f62-2811">NRIC</span><span class="sxs-lookup"><span data-stu-id="16f62-2811">nric</span></span>
- <span data-ttu-id="16f62-2812">tarjeta de identificación personal</span><span class="sxs-lookup"><span data-stu-id="16f62-2812">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="16f62-2813">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="16f62-2813">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2814">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2814">Format</span></span>

<span data-ttu-id="16f62-2815">8 o 9 dígitos que contienen espacios opcionales</span><span class="sxs-lookup"><span data-stu-id="16f62-2815">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2816">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2816">Pattern</span></span>

<span data-ttu-id="16f62-2817">8 o 9 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2817">8-9 digits:</span></span>
- <span data-ttu-id="16f62-2818">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2818">Three digits</span></span> 
- <span data-ttu-id="16f62-2819">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2819">A space (optional)</span></span> 
- <span data-ttu-id="16f62-2820">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2820">Three digits</span></span> 
- <span data-ttu-id="16f62-2821">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="16f62-2821">A space (optional)</span></span> 
- <span data-ttu-id="16f62-2822">2 o 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2822">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2823">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2823">Checksum</span></span>

<span data-ttu-id="16f62-2824">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2825">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2825">Definition</span></span>

<span data-ttu-id="16f62-2826">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2826">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2827">La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2827">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2828">Se encuentra una palabra clave de Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="16f62-2828">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="16f62-2829">La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-2829">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="16f62-2830">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2830">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2831">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2831">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="16f62-2832">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="16f62-2832">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="16f62-2833">Número de servicio de ciudadanía</span><span class="sxs-lookup"><span data-stu-id="16f62-2833">Citizen service number</span></span> 
- <span data-ttu-id="16f62-2834">BSN</span><span class="sxs-lookup"><span data-stu-id="16f62-2834">BSN</span></span> 
- <span data-ttu-id="16f62-2835">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2835">Burgerservicenummer</span></span> 
- <span data-ttu-id="16f62-2836">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2836">Sofinummer</span></span> 
- <span data-ttu-id="16f62-2837">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2837">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="16f62-2838">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2838">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="16f62-2839">Número de Ministerio de salud de Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="16f62-2839">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2840">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2840">Format</span></span>

<span data-ttu-id="16f62-2841">Tres letras, un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2841">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2842">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2842">Pattern</span></span>

<span data-ttu-id="16f62-2843">Tres letras (no distingue entre mayúsculas y minúsculas), un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2843">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2844">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2844">Checksum</span></span>

<span data-ttu-id="16f62-2845">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2845">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2846">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2846">Definition</span></span>

<span data-ttu-id="16f62-2847">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2848">La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2848">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2849">Se encuentra una palabra clave de Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="16f62-2849">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="16f62-2850">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2850">The checksum passes.</span></span>

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

<span data-ttu-id="16f62-2851">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2851">Keywords</span></span>

<span data-ttu-id="16f62-2852">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="16f62-2852">Keyword_nz_terms</span></span>

- <span data-ttu-id="16f62-2853">NHI</span><span class="sxs-lookup"><span data-stu-id="16f62-2853">NHI</span></span> 
- <span data-ttu-id="16f62-2854">New Zealand</span><span class="sxs-lookup"><span data-stu-id="16f62-2854">New Zealand</span></span> 
- <span data-ttu-id="16f62-2855">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-2855">Health</span></span> 
- <span data-ttu-id="16f62-2856">régimen</span><span class="sxs-lookup"><span data-stu-id="16f62-2856">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="16f62-2857">Número de identificación de Noruega</span><span class="sxs-lookup"><span data-stu-id="16f62-2857">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2858">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2858">Format</span></span>

<span data-ttu-id="16f62-2859">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2859">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2860">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2860">Pattern</span></span>

<span data-ttu-id="16f62-2861">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2861">11 digits:</span></span>
- <span data-ttu-id="16f62-2862">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-2862">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="16f62-2863">Número individual de tres dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2863">Three-digit individual number</span></span> 
- <span data-ttu-id="16f62-2864">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="16f62-2864">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2865">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2865">Checksum</span></span>

<span data-ttu-id="16f62-2866">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2866">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2867">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2867">Definition</span></span>

<span data-ttu-id="16f62-2868">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2868">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2869">La función Func_norway_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2869">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2870">Se encuentra una palabra clave de Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2870">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="16f62-2871">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2871">The checksum passes.</span></span>
- <span data-ttu-id="16f62-2872">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2873">La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2873">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2874">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2874">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2875">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2875">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="16f62-2876">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2876">Keyword_norway_id_number</span></span>

- <span data-ttu-id="16f62-2877">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="16f62-2877">Personal identification number</span></span>
- <span data-ttu-id="16f62-2878">Número de id. noruego</span><span class="sxs-lookup"><span data-stu-id="16f62-2878">Norwegian ID Number</span></span>
- <span data-ttu-id="16f62-2879">Número de id.</span><span class="sxs-lookup"><span data-stu-id="16f62-2879">ID Number</span></span>
- <span data-ttu-id="16f62-2880">Determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-2880">Identification</span></span>
- <span data-ttu-id="16f62-2881">Personnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2881">Personnummer</span></span>
- <span data-ttu-id="16f62-2882">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="16f62-2882">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="16f62-2883">Número de id. universal unificado de Filipinas</span><span class="sxs-lookup"><span data-stu-id="16f62-2883">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2884">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2884">Format</span></span>

<span data-ttu-id="16f62-2885">12 dígitos separados por guiones</span><span class="sxs-lookup"><span data-stu-id="16f62-2885">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2886">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2886">Pattern</span></span>

<span data-ttu-id="16f62-2887">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2887">12 digits:</span></span>
- <span data-ttu-id="16f62-2888">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2888">Four digits</span></span> 
- <span data-ttu-id="16f62-2889">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-2889">A hyphen</span></span> 
- <span data-ttu-id="16f62-2890">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-2890">Seven digits</span></span> 
- <span data-ttu-id="16f62-2891">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-2891">A hyphen</span></span> 
- <span data-ttu-id="16f62-2892">Un dígito</span><span class="sxs-lookup"><span data-stu-id="16f62-2892">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2893">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2893">Checksum</span></span>

<span data-ttu-id="16f62-2894">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2894">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2895">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2895">Definition</span></span>

<span data-ttu-id="16f62-2896">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2896">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2897">La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2897">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2898">Se encuentra una palabra clave de Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="16f62-2898">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2899">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2899">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="16f62-2900">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="16f62-2900">Keyword_philippines_id</span></span>

- <span data-ttu-id="16f62-2901">Id. universal unificado
</span><span class="sxs-lookup"><span data-stu-id="16f62-2901">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="16f62-2902">UMID</span><span class="sxs-lookup"><span data-stu-id="16f62-2902">UMID</span></span> 
- <span data-ttu-id="16f62-2903">Tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-2903">Identity Card</span></span> 
- <span data-ttu-id="16f62-2904">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="16f62-2904">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="16f62-2905">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="16f62-2905">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2906">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2906">Format</span></span>

<span data-ttu-id="16f62-2907">Tres letras y seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2907">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2908">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2908">Pattern</span></span>

<span data-ttu-id="16f62-2909">Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2909">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2910">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2910">Checksum</span></span>

<span data-ttu-id="16f62-2911">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2912">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2912">Definition</span></span>

<span data-ttu-id="16f62-2913">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_polish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2913">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="16f62-2914">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2914">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="16f62-2915">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2915">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2916">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2916">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="16f62-2917">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2917">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="16f62-2918">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="16f62-2918">Dowód osobisty</span></span>
- <span data-ttu-id="16f62-2919">Numerar dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="16f62-2919">Numer dowodu osobistego</span></span>
- <span data-ttu-id="16f62-2920">Nazwa i número dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="16f62-2920">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="16f62-2921">Nazwa i NR dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="16f62-2921">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="16f62-2922">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="16f62-2922">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="16f62-2923">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="16f62-2923">Dowód Tożsamości</span></span>
- <span data-ttu-id="16f62-2924">Dow.</span><span class="sxs-lookup"><span data-stu-id="16f62-2924">dow.</span></span> <span data-ttu-id="16f62-2925">MacOS.</span><span class="sxs-lookup"><span data-stu-id="16f62-2925">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="16f62-2926">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="16f62-2926">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2927">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2927">Format</span></span>

<span data-ttu-id="16f62-2928">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2928">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2929">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2929">Pattern</span></span>

<span data-ttu-id="16f62-2930">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2930">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2931">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2931">Checksum</span></span>

<span data-ttu-id="16f62-2932">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2932">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2933">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2933">Definition</span></span>

<span data-ttu-id="16f62-2934">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2934">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2935">La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2935">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2936">Se encuentra una palabra clave de Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2936">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="16f62-2937">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2937">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2938">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2938">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="16f62-2939">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2939">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="16f62-2940">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="16f62-2940">Nr PESEL</span></span>
- <span data-ttu-id="16f62-2941">PESEL</span><span class="sxs-lookup"><span data-stu-id="16f62-2941">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="16f62-2942">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="16f62-2942">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2943">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2943">Format</span></span>

<span data-ttu-id="16f62-2944">Dos letras y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2944">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2945">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2945">Pattern</span></span>

<span data-ttu-id="16f62-2946">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2946">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2947">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2947">Checksum</span></span>

<span data-ttu-id="16f62-2948">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-2948">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2949">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2949">Definition</span></span>

<span data-ttu-id="16f62-2950">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2950">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2951">La función Func_polish_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2951">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2952">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-2952">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="16f62-2953">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-2953">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2954">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2954">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="16f62-2955">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="16f62-2955">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="16f62-2956">Números paszportu</span><span class="sxs-lookup"><span data-stu-id="16f62-2956">Numer paszportu</span></span>
- <span data-ttu-id="16f62-2957">Nº.</span><span class="sxs-lookup"><span data-stu-id="16f62-2957">Nr.</span></span> <span data-ttu-id="16f62-2958">Paszportu</span><span class="sxs-lookup"><span data-stu-id="16f62-2958">Paszportu</span></span>
- <span data-ttu-id="16f62-2959">Paszport</span><span class="sxs-lookup"><span data-stu-id="16f62-2959">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="16f62-2960">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="16f62-2960">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2961">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2961">Format</span></span>

<span data-ttu-id="16f62-2962">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2962">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2963">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2963">Pattern</span></span>

<span data-ttu-id="16f62-2964">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2964">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2965">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2965">Checksum</span></span>

<span data-ttu-id="16f62-2966">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2966">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2967">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2967">Definition</span></span>

<span data-ttu-id="16f62-2968">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2969">La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2969">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2970">Se encuentra una palabra clave de Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="16f62-2970">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-2971">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2971">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="16f62-2972">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="16f62-2972">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="16f62-2973">Tarjeta del ciudadano</span><span class="sxs-lookup"><span data-stu-id="16f62-2973">Citizen Card</span></span>
- <span data-ttu-id="16f62-2974">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="16f62-2974">National ID Card</span></span>
- <span data-ttu-id="16f62-2975">CC</span><span class="sxs-lookup"><span data-stu-id="16f62-2975">CC</span></span>
- <span data-ttu-id="16f62-2976">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="16f62-2976">Cartão de Cidadão</span></span>
- <span data-ttu-id="16f62-2977">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="16f62-2977">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="16f62-2978">Identificación nacional de Arabia Saudí</span><span class="sxs-lookup"><span data-stu-id="16f62-2978">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2979">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2979">Format</span></span>

<span data-ttu-id="16f62-2980">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2980">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2981">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2981">Pattern</span></span>

<span data-ttu-id="16f62-2982">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-2982">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-2983">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-2983">Checksum</span></span>

<span data-ttu-id="16f62-2984">No</span><span class="sxs-lookup"><span data-stu-id="16f62-2984">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-2985">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-2985">Definition</span></span>

<span data-ttu-id="16f62-2986">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-2987">La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-2987">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-2988">Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="16f62-2988">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-2989">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-2989">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="16f62-2990">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="16f62-2990">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="16f62-2991">Identification Card</span><span class="sxs-lookup"><span data-stu-id="16f62-2991">Identification Card</span></span> 
- <span data-ttu-id="16f62-2992">I card number</span><span class="sxs-lookup"><span data-stu-id="16f62-2992">I card number</span></span> 
- <span data-ttu-id="16f62-2993">ID number</span><span class="sxs-lookup"><span data-stu-id="16f62-2993">ID number</span></span> 
- <span data-ttu-id="16f62-2994">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="16f62-2994">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="16f62-2995">Número de tarjeta de identidad de registro nacional (NRIC) de Singapur</span><span class="sxs-lookup"><span data-stu-id="16f62-2995">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-2996">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-2996">Format</span></span>

<span data-ttu-id="16f62-2997">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-2997">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-2998">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-2998">Pattern</span></span>

- <span data-ttu-id="16f62-2999">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-2999">Nine letters and digits:</span></span>
- <span data-ttu-id="16f62-3000">La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-3000">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-3001">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-3001">Seven digits</span></span> 
- <span data-ttu-id="16f62-3002">Un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="16f62-3002">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3003">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3003">Checksum</span></span>

<span data-ttu-id="16f62-3004">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3004">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3005">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3005">Definition</span></span>

<span data-ttu-id="16f62-3006">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3006">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3007">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3007">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3008">Se encuentra una palabra clave de Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="16f62-3008">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="16f62-3009">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3009">The checksum passes.</span></span>

<span data-ttu-id="16f62-3010">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3010">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3011">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3011">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3012">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3012">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3013">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3013">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="16f62-3014">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="16f62-3014">Keyword_singapore_nric</span></span>

- <span data-ttu-id="16f62-3015">Tarjeta de identidad de registro nacional</span><span class="sxs-lookup"><span data-stu-id="16f62-3015">National Registration Identity Card</span></span> 
- <span data-ttu-id="16f62-3016">Número de tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-3016">Identity Card Number</span></span> 
- <span data-ttu-id="16f62-3017">NRIC</span><span class="sxs-lookup"><span data-stu-id="16f62-3017">NRIC</span></span> 
- <span data-ttu-id="16f62-3018">I</span><span class="sxs-lookup"><span data-stu-id="16f62-3018">IC</span></span> 
- <span data-ttu-id="16f62-3019">Número de identificación de extranjeros</span><span class="sxs-lookup"><span data-stu-id="16f62-3019">Foreign Identification Number</span></span> 
- <span data-ttu-id="16f62-3020">AC</span><span class="sxs-lookup"><span data-stu-id="16f62-3020">FIN</span></span> 
- <span data-ttu-id="16f62-3021">身份证</span><span class="sxs-lookup"><span data-stu-id="16f62-3021">身份证</span></span> 
- <span data-ttu-id="16f62-3022">身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-3022">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="16f62-3023">Número de identificación de Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="16f62-3023">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3024">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3024">Format</span></span>

<span data-ttu-id="16f62-3025">13 dígitos que pueden contener espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-3025">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3026">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3026">Pattern</span></span>

<span data-ttu-id="16f62-3027">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3027">13 digits:</span></span>
- <span data-ttu-id="16f62-3028">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-3028">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16f62-3029">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3029">Four digits</span></span> 
- <span data-ttu-id="16f62-3030">Un indicador de ciudadanía de un solo dígito </span><span class="sxs-lookup"><span data-stu-id="16f62-3030">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="16f62-3031">El dígito "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="16f62-3031">The digit "8" or "9"</span></span> 
- <span data-ttu-id="16f62-3032">Un dígito que es un dígito de suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3032">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3033">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3033">Checksum</span></span>

<span data-ttu-id="16f62-3034">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3034">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3035">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3035">Definition</span></span>

<span data-ttu-id="16f62-3036">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3036">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3037">La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3037">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3038">Se encuentra una palabra clave de Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-3038">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="16f62-3039">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3039">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3040">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3040">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="16f62-3041">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="16f62-3041">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="16f62-3042">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="16f62-3042">Identity card</span></span>
- <span data-ttu-id="16f62-3043">Id.</span><span class="sxs-lookup"><span data-stu-id="16f62-3043">ID</span></span>
- <span data-ttu-id="16f62-3044">Determinación</span><span class="sxs-lookup"><span data-stu-id="16f62-3044">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="16f62-3045">Número de registro de residente de Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="16f62-3045">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3046">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3046">Format</span></span>

<span data-ttu-id="16f62-3047">13 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="16f62-3047">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3048">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3048">Pattern</span></span>

<span data-ttu-id="16f62-3049">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3049">13 digits:</span></span>
- <span data-ttu-id="16f62-3050">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="16f62-3050">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16f62-3051">Un guión </span><span class="sxs-lookup"><span data-stu-id="16f62-3051">A hyphen</span></span> 
- <span data-ttu-id="16f62-3052">Un dígito determinado por el siglo y el sexo </span><span class="sxs-lookup"><span data-stu-id="16f62-3052">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="16f62-3053">Código de región de nacimiento de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="16f62-3053">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="16f62-3054">Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos </span><span class="sxs-lookup"><span data-stu-id="16f62-3054">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="16f62-3055">Un dígito de control.</span><span class="sxs-lookup"><span data-stu-id="16f62-3055">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3056">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3056">Checksum</span></span>

<span data-ttu-id="16f62-3057">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3057">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3058">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3058">Definition</span></span>

<span data-ttu-id="16f62-3059">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3059">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3060">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3060">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3061">Se encuentra una palabra clave de Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-3061">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="16f62-3062">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3062">The checksum passes.</span></span>

<span data-ttu-id="16f62-3063">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3063">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3064">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3064">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3065">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3065">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3066">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3066">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="16f62-3067">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="16f62-3067">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="16f62-3068">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="16f62-3068">National ID card</span></span> 
- <span data-ttu-id="16f62-3069">Número de registro de ciudadano</span><span class="sxs-lookup"><span data-stu-id="16f62-3069">Citizen's Registration Number</span></span> 
- <span data-ttu-id="16f62-3070">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="16f62-3070">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="16f62-3071">RRN</span><span class="sxs-lookup"><span data-stu-id="16f62-3071">RRN</span></span> 
- <span data-ttu-id="16f62-3072">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="16f62-3072">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="16f62-3073">Número de seguridad social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="16f62-3073">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3074">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3074">Format</span></span>

<span data-ttu-id="16f62-3075">11 o 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3075">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3076">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3076">Pattern</span></span>

<span data-ttu-id="16f62-3077">11-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3077">11-12 digits:</span></span>
- <span data-ttu-id="16f62-3078">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3078">Two digits</span></span> 
- <span data-ttu-id="16f62-3079">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="16f62-3079">A forward slash (optional)</span></span> 
- <span data-ttu-id="16f62-3080">7-8 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3080">7-8 digits</span></span> 
- <span data-ttu-id="16f62-3081">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="16f62-3081">A forward slash (optional)</span></span> 
- <span data-ttu-id="16f62-3082">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3082">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3083">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3083">Checksum</span></span>

<span data-ttu-id="16f62-3084">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3084">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3085">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3085">Definition</span></span>

<span data-ttu-id="16f62-3086">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3086">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3087">La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3087">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3088">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3088">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3089">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3089">Keywords</span></span>

<span data-ttu-id="16f62-3090">Ninguno</span><span class="sxs-lookup"><span data-stu-id="16f62-3090">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="16f62-3091">Cadena de conexión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="16f62-3091">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3092">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3092">Format</span></span>

<span data-ttu-id="16f62-3093">La cadena "User ID", "User ID", "UID" o "UserId" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="16f62-3093">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3094">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3094">Pattern</span></span>

- <span data-ttu-id="16f62-3095">La cadena "User ID", "User ID", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="16f62-3095">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="16f62-3096">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-3096">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16f62-3097">La cadena "Password" o "pwd" donde "pwd" no está precedida por una letra minúscula.</span><span class="sxs-lookup"><span data-stu-id="16f62-3097">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="16f62-3098">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-3098">An equal sign (=)</span></span>
- <span data-ttu-id="16f62-3099">Cualquier carácter que no sea un signo de dólar ($), un símbolo de porcentaje (%), un símbolo mayor que (>), un símbolo de arroba (@), Comillas ("), punto y coma (;), llave izquierda ([) o corchete de apertura ({)</span><span class="sxs-lookup"><span data-stu-id="16f62-3099">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="16f62-3100">Cualquier combinación de 7-128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="16f62-3100">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="16f62-3101">Un punto y coma (;) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="16f62-3101">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3102">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3102">Checksum</span></span>

<span data-ttu-id="16f62-3103">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3103">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3104">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3104">Definition</span></span>

<span data-ttu-id="16f62-3105">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3105">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3106">La expresión regular CEP_Regex_SQLServerConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3106">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3107">**No** se encuentra una palabra clave de CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="16f62-3107">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="16f62-3108">La expresión regular CEP_PasswordPlaceHolder no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3108">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3109">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3109">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3110">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="16f62-3111">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="16f62-3111">CEP_GlobalFilter</span></span>

- <span data-ttu-id="16f62-3112">Some-Password</span><span class="sxs-lookup"><span data-stu-id="16f62-3112">some-password</span></span>
- <span data-ttu-id="16f62-3113">somePassword</span><span class="sxs-lookup"><span data-stu-id="16f62-3113">somepassword</span></span>
- <span data-ttu-id="16f62-3114">secretPassword</span><span class="sxs-lookup"><span data-stu-id="16f62-3114">secretPassword</span></span>
- <span data-ttu-id="16f62-3115">AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="16f62-3115">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="16f62-3116">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="16f62-3116">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="16f62-3117">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-3117">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-3118">Password o pwd seguida de 0-2 espacios, un signo igual (=), 0-2 espacios y un asterisco (\*)--o--</span><span class="sxs-lookup"><span data-stu-id="16f62-3118">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="16f62-3119">Password o pwd seguida de:</span><span class="sxs-lookup"><span data-stu-id="16f62-3119">Password or pwd followed by:</span></span>
    - <span data-ttu-id="16f62-3120">Signo de igual (=)</span><span class="sxs-lookup"><span data-stu-id="16f62-3120">Equal sign (=)</span></span>
    - <span data-ttu-id="16f62-3121">Símbolo menor que (<)</span><span class="sxs-lookup"><span data-stu-id="16f62-3121">Less than symbol (<)</span></span>
    - <span data-ttu-id="16f62-3122">Cualquier combinación de 1-200 caracteres que estén en mayúsculas o minúsculas, dígitos, un asterisco (\*), un guión (-), un subrayado (_) o un carácter de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="16f62-3122">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="16f62-3123">Símbolo mayor que (>)</span><span class="sxs-lookup"><span data-stu-id="16f62-3123">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="16f62-3124">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16f62-3124">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16f62-3125">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="16f62-3125">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16f62-3126">contoso</span><span class="sxs-lookup"><span data-stu-id="16f62-3126">contoso</span></span>
- <span data-ttu-id="16f62-3127">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="16f62-3127">fabrikam</span></span>
- <span data-ttu-id="16f62-3128">Northwind</span><span class="sxs-lookup"><span data-stu-id="16f62-3128">northwind</span></span>
- <span data-ttu-id="16f62-3129">entorno</span><span class="sxs-lookup"><span data-stu-id="16f62-3129">sandbox</span></span>
- <span data-ttu-id="16f62-3130">OneBox</span><span class="sxs-lookup"><span data-stu-id="16f62-3130">onebox</span></span>
- <span data-ttu-id="16f62-3131">localhost</span><span class="sxs-lookup"><span data-stu-id="16f62-3131">localhost</span></span>
- <span data-ttu-id="16f62-3132">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16f62-3132">127.0.0.1</span></span>
- <span data-ttu-id="16f62-3133">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="16f62-3133">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="16f62-3134">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="16f62-3134">s-int.<!--no-hyperlink-->net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="16f62-3135">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="16f62-3135">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3136">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3136">Format</span></span>

<span data-ttu-id="16f62-3137">10 o 12 dígitos y un delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="16f62-3137">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3138">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3138">Pattern</span></span>

<span data-ttu-id="16f62-3139">10 o 12 dígitos y un delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="16f62-3139">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="16f62-3140">2-4 dígitos (opcionales)</span><span class="sxs-lookup"><span data-stu-id="16f62-3140">2-4 digits (optional)</span></span> 
- <span data-ttu-id="16f62-3141">Seis dígitos en fecha de formato AAMMDD</span><span class="sxs-lookup"><span data-stu-id="16f62-3141">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="16f62-3142">Delimitador de "-" o "+" (opcional), más</span><span class="sxs-lookup"><span data-stu-id="16f62-3142">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="16f62-3143">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3143">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3144">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3144">Checksum</span></span>

<span data-ttu-id="16f62-3145">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3145">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3146">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3146">Definition</span></span>

<span data-ttu-id="16f62-3147">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3147">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3148">La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3148">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3149">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3149">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3150">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3150">Keywords</span></span>

<span data-ttu-id="16f62-3151">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3151">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="16f62-3152">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="16f62-3152">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3153">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3153">Format</span></span>

<span data-ttu-id="16f62-3154">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3154">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3155">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3155">Pattern</span></span>

<span data-ttu-id="16f62-3156">Ocho dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-3156">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3157">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3157">Checksum</span></span>

<span data-ttu-id="16f62-3158">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3158">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3159">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3159">Definition</span></span>

<span data-ttu-id="16f62-3160">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3160">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3161">La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3161">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3162">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-3162">One of the following is true:</span></span>
    - <span data-ttu-id="16f62-3163">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="16f62-3163">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="16f62-3164">Se encuentra una palabra clave de Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="16f62-3164">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3165">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3165">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="16f62-3166">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-3166">Keyword_sweden_passport</span></span>

- <span data-ttu-id="16f62-3167">visa requirements</span><span class="sxs-lookup"><span data-stu-id="16f62-3167">visa requirements</span></span> 
- <span data-ttu-id="16f62-3168">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="16f62-3168">Alien Registration Card</span></span> 
- <span data-ttu-id="16f62-3169">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="16f62-3169">Schengen visas</span></span> 
- <span data-ttu-id="16f62-3170">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="16f62-3170">Schengen visa</span></span> 
- <span data-ttu-id="16f62-3171">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="16f62-3171">Visa Processing</span></span> 
- <span data-ttu-id="16f62-3172">Visa Type</span><span class="sxs-lookup"><span data-stu-id="16f62-3172">Visa Type</span></span> 
- <span data-ttu-id="16f62-3173">Single Entry</span><span class="sxs-lookup"><span data-stu-id="16f62-3173">Single Entry</span></span> 
- <span data-ttu-id="16f62-3174">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="16f62-3174">Multiple Entry</span></span> 
- <span data-ttu-id="16f62-3175">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="16f62-3175">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="16f62-3176">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-3176">Keyword_passport</span></span>

- <span data-ttu-id="16f62-3177">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3177">Passport Number</span></span> 
- <span data-ttu-id="16f62-3178">Passport No</span><span class="sxs-lookup"><span data-stu-id="16f62-3178">Passport No</span></span> 
- <span data-ttu-id="16f62-3179">Passport #</span><span class="sxs-lookup"><span data-stu-id="16f62-3179">Passport #</span></span> 
- <span data-ttu-id="16f62-3180">Usuarios</span><span class="sxs-lookup"><span data-stu-id="16f62-3180">Passport#</span></span> 
- <span data-ttu-id="16f62-3181">PassportID</span><span class="sxs-lookup"><span data-stu-id="16f62-3181">PassportID</span></span> 
- <span data-ttu-id="16f62-3182">Passportno</span><span class="sxs-lookup"><span data-stu-id="16f62-3182">Passportno</span></span> 
- <span data-ttu-id="16f62-3183">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-3183">passportnumber</span></span> 
- <span data-ttu-id="16f62-3184">パスポート</span><span class="sxs-lookup"><span data-stu-id="16f62-3184">パスポート</span></span> 
- <span data-ttu-id="16f62-3185">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16f62-3185">パスポート番号</span></span> 
- <span data-ttu-id="16f62-3186">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16f62-3186">パスポートのNum</span></span> 
- <span data-ttu-id="16f62-3187">パスポート #</span><span class="sxs-lookup"><span data-stu-id="16f62-3187">パスポート＃</span></span> 
- <span data-ttu-id="16f62-3188">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16f62-3188">Numéro de passeport</span></span> 
- <span data-ttu-id="16f62-3189">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16f62-3189">Passeport n °</span></span> 
- <span data-ttu-id="16f62-3190">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16f62-3190">Passeport Non</span></span> 
- <span data-ttu-id="16f62-3191">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-3191">Passeport #</span></span> 
- <span data-ttu-id="16f62-3192">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-3192">Passeport#</span></span> 
- <span data-ttu-id="16f62-3193">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16f62-3193">PasseportNon</span></span> 
- <span data-ttu-id="16f62-3194">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16f62-3194">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="16f62-3195">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="16f62-3195">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3196">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3196">Format</span></span>

<span data-ttu-id="16f62-3197">Cuatro letras seguidas de 5 a 31 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3197">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3198">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3198">Pattern</span></span>

<span data-ttu-id="16f62-3199">Cuatro letras seguidas de 5-31 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3199">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="16f62-3200">Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-3200">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-3201">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="16f62-3201">An optional space</span></span> 
- <span data-ttu-id="16f62-3202">4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))</span><span class="sxs-lookup"><span data-stu-id="16f62-3202">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="16f62-3203">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="16f62-3203">An optional space</span></span> 
- <span data-ttu-id="16f62-3204">1-3 letras o dígitos (el resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="16f62-3204">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3205">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3205">Checksum</span></span>

<span data-ttu-id="16f62-3206">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3206">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3207">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3207">Definition</span></span>

<span data-ttu-id="16f62-3208">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3208">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3209">La expresión regular Regex_swift encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3209">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3210">Se encuentra una palabra clave de Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="16f62-3210">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3211">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3211">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="16f62-3212">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="16f62-3212">Keyword_swift</span></span>

- <span data-ttu-id="16f62-3213">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="16f62-3213">international organization for standardization 9362</span></span> 
- <span data-ttu-id="16f62-3214">iso 9362</span><span class="sxs-lookup"><span data-stu-id="16f62-3214">iso 9362</span></span> 
- <span data-ttu-id="16f62-3215">iso9362</span><span class="sxs-lookup"><span data-stu-id="16f62-3215">iso9362</span></span> 
- <span data-ttu-id="16f62-3216">rápido\#</span><span class="sxs-lookup"><span data-stu-id="16f62-3216">swift\#</span></span> 
- <span data-ttu-id="16f62-3217">Swiftcode</span><span class="sxs-lookup"><span data-stu-id="16f62-3217">swiftcode</span></span> 
- <span data-ttu-id="16f62-3218">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-3218">swiftnumber</span></span> 
- <span data-ttu-id="16f62-3219">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-3219">swiftroutingnumber</span></span> 
- <span data-ttu-id="16f62-3220">swift code</span><span class="sxs-lookup"><span data-stu-id="16f62-3220">swift code</span></span> 
- <span data-ttu-id="16f62-3221">swift number #</span><span class="sxs-lookup"><span data-stu-id="16f62-3221">swift number #</span></span> 
- <span data-ttu-id="16f62-3222">swift routing number</span><span class="sxs-lookup"><span data-stu-id="16f62-3222">swift routing number</span></span> 
- <span data-ttu-id="16f62-3223">bic number</span><span class="sxs-lookup"><span data-stu-id="16f62-3223">bic number</span></span> 
- <span data-ttu-id="16f62-3224">bic code</span><span class="sxs-lookup"><span data-stu-id="16f62-3224">bic code</span></span> 
- <span data-ttu-id="16f62-3225">BIC\#</span><span class="sxs-lookup"><span data-stu-id="16f62-3225">bic \#</span></span> 
- <span data-ttu-id="16f62-3226">BIC\#</span><span class="sxs-lookup"><span data-stu-id="16f62-3226">bic\#</span></span> 
- <span data-ttu-id="16f62-3227">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="16f62-3227">bank identifier code</span></span> 
- <span data-ttu-id="16f62-3228">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="16f62-3228">標準化9362</span></span> 
- <span data-ttu-id="16f62-3229">迅速 #</span><span class="sxs-lookup"><span data-stu-id="16f62-3229">迅速＃</span></span> 
- <span data-ttu-id="16f62-3230">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="16f62-3230">SWIFTコード</span></span> 
- <span data-ttu-id="16f62-3231">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="16f62-3231">SWIFT番号</span></span> 
- <span data-ttu-id="16f62-3232">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="16f62-3232">迅速なルーティング番号</span></span> 
- <span data-ttu-id="16f62-3233">BIC番号</span><span class="sxs-lookup"><span data-stu-id="16f62-3233">BIC番号</span></span> 
- <span data-ttu-id="16f62-3234">BICコード</span><span class="sxs-lookup"><span data-stu-id="16f62-3234">BICコード</span></span> 
- <span data-ttu-id="16f62-3235">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="16f62-3235">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="16f62-3236">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="16f62-3236">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="16f62-3237">rápido\#</span><span class="sxs-lookup"><span data-stu-id="16f62-3237">rapide \#</span></span> 
- <span data-ttu-id="16f62-3238">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="16f62-3238">code SWIFT</span></span> 
- <span data-ttu-id="16f62-3239">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="16f62-3239">le numéro de swift</span></span> 
- <span data-ttu-id="16f62-3240">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="16f62-3240">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="16f62-3241">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="16f62-3241">le numéro BIC</span></span> 
- <span data-ttu-id="16f62-3242">\#BIC</span><span class="sxs-lookup"><span data-stu-id="16f62-3242">\# BIC</span></span> 
- <span data-ttu-id="16f62-3243">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="16f62-3243">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="16f62-3244">Identificación nacional de Taiwán</span><span class="sxs-lookup"><span data-stu-id="16f62-3244">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3245">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3245">Format</span></span>

<span data-ttu-id="16f62-3246">Una letra  seguida de nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3246">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3247">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3247">Pattern</span></span>

<span data-ttu-id="16f62-3248">Una letra seguida de nueve dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3248">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="16f62-3249">Una letra (en inglés, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-3249">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="16f62-3250">El dígito "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="16f62-3250">The digit "1" or "2"</span></span> 
- <span data-ttu-id="16f62-3251">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3251">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3252">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3252">Checksum</span></span>

<span data-ttu-id="16f62-3253">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3253">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3254">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3254">Definition</span></span>

<span data-ttu-id="16f62-3255">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3255">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3256">La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3256">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3257">Se encuentra una palabra clave de Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="16f62-3257">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="16f62-3258">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3258">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3259">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3259">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="16f62-3260">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="16f62-3260">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="16f62-3261">身份證字號</span><span class="sxs-lookup"><span data-stu-id="16f62-3261">身份證字號</span></span> 
- <span data-ttu-id="16f62-3262">身份證</span><span class="sxs-lookup"><span data-stu-id="16f62-3262">身份證</span></span> 
- <span data-ttu-id="16f62-3263">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="16f62-3263">身份證號碼</span></span> 
- <span data-ttu-id="16f62-3264">身份證號</span><span class="sxs-lookup"><span data-stu-id="16f62-3264">身份證號</span></span> 
- <span data-ttu-id="16f62-3265">身分證字號</span><span class="sxs-lookup"><span data-stu-id="16f62-3265">身分證字號</span></span> 
- <span data-ttu-id="16f62-3266">身分證</span><span class="sxs-lookup"><span data-stu-id="16f62-3266">身分證</span></span> 
- <span data-ttu-id="16f62-3267">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="16f62-3267">身分證號碼</span></span> 
- <span data-ttu-id="16f62-3268">身份證號</span><span class="sxs-lookup"><span data-stu-id="16f62-3268">身份證號</span></span> 
- <span data-ttu-id="16f62-3269">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="16f62-3269">身分證統一編號</span></span> 
- <span data-ttu-id="16f62-3270">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="16f62-3270">國民身分證統一編號</span></span> 
- <span data-ttu-id="16f62-3271">簽名</span><span class="sxs-lookup"><span data-stu-id="16f62-3271">簽名</span></span> 
- <span data-ttu-id="16f62-3272">蓋章</span><span class="sxs-lookup"><span data-stu-id="16f62-3272">蓋章</span></span> 
- <span data-ttu-id="16f62-3273">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="16f62-3273">簽名或蓋章</span></span> 
- <span data-ttu-id="16f62-3274">簽章</span><span class="sxs-lookup"><span data-stu-id="16f62-3274">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="16f62-3275">	Número de pasaporte de Taiwán</span><span class="sxs-lookup"><span data-stu-id="16f62-3275">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3276">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3276">Format</span></span>

- <span data-ttu-id="16f62-3277">Número de pasaporte biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3277">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="16f62-3278">Número de pasaporte no biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3278">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3279">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3279">Pattern</span></span>
<span data-ttu-id="16f62-3280">Número de pasaporte biométrico:</span><span class="sxs-lookup"><span data-stu-id="16f62-3280">Biometric passport number:</span></span>
- <span data-ttu-id="16f62-3281">El dígito "3" </span><span class="sxs-lookup"><span data-stu-id="16f62-3281">The digit "3"</span></span> 
- <span data-ttu-id="16f62-3282">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3282">Eight digits</span></span>

<span data-ttu-id="16f62-3283">Número de pasaporte no biométrico:</span><span class="sxs-lookup"><span data-stu-id="16f62-3283">Non-biometric passport number:</span></span>
- <span data-ttu-id="16f62-3284">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3284">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3285">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3285">Checksum</span></span>

<span data-ttu-id="16f62-3286">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3287">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3287">Definition</span></span>

<span data-ttu-id="16f62-3288">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3289">La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3289">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3290">Se encuentra una palabra clave de Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="16f62-3290">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3291">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3291">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="16f62-3292">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-3292">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="16f62-3293">Número de pasaporte ROC</span><span class="sxs-lookup"><span data-stu-id="16f62-3293">ROC passport number</span></span> 
- <span data-ttu-id="16f62-3294">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="16f62-3294">Passport number</span></span> 
- <span data-ttu-id="16f62-3295">Núm. pasaporte
</span><span class="sxs-lookup"><span data-stu-id="16f62-3295">Passport no</span></span> 
- <span data-ttu-id="16f62-3296">N.ro pasaporte</span><span class="sxs-lookup"><span data-stu-id="16f62-3296">Passport Num</span></span> 
- <span data-ttu-id="16f62-3297">N.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="16f62-3297">Passport #</span></span> 
- <span data-ttu-id="16f62-3298">护照</span><span class="sxs-lookup"><span data-stu-id="16f62-3298">护照</span></span> 
- <span data-ttu-id="16f62-3299">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="16f62-3299">中華民國護照</span></span> 
- <span data-ttu-id="16f62-3300">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="16f62-3300">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="16f62-3301">Número de certificado de residente (ARC/TARC) de Taiwán</span><span class="sxs-lookup"><span data-stu-id="16f62-3301">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3302">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3302">Format</span></span>

<span data-ttu-id="16f62-3303">10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3303">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3304">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3304">Pattern</span></span>

<span data-ttu-id="16f62-3305">10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3305">10 letters and digits:</span></span>
- <span data-ttu-id="16f62-3306">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="16f62-3306">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="16f62-3307">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3307">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3308">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3308">Checksum</span></span>

<span data-ttu-id="16f62-3309">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3309">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3310">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3310">Definition</span></span>

<span data-ttu-id="16f62-3311">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3311">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3312">La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3312">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3313">Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="16f62-3313">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3314">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3314">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="16f62-3315">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="16f62-3315">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="16f62-3316">Certificado de residente</span><span class="sxs-lookup"><span data-stu-id="16f62-3316">Resident Certificate</span></span> 
- <span data-ttu-id="16f62-3317">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="16f62-3317">Resident Cert</span></span> 
- <span data-ttu-id="16f62-3318">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="16f62-3318">Resident Cert.</span></span> 
- <span data-ttu-id="16f62-3319">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="16f62-3319">Identification card</span></span> 
- <span data-ttu-id="16f62-3320">Certificado de residente extranjero</span><span class="sxs-lookup"><span data-stu-id="16f62-3320">Alien Resident Certificate</span></span> 
- <span data-ttu-id="16f62-3321">ARCOS</span><span class="sxs-lookup"><span data-stu-id="16f62-3321">ARC</span></span> 
- <span data-ttu-id="16f62-3322">Certificado de residente en el área de Taiwán</span><span class="sxs-lookup"><span data-stu-id="16f62-3322">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="16f62-3323">TARC</span><span class="sxs-lookup"><span data-stu-id="16f62-3323">TARC</span></span> 
- <span data-ttu-id="16f62-3324">居留證</span><span class="sxs-lookup"><span data-stu-id="16f62-3324">居留證</span></span> 
- <span data-ttu-id="16f62-3325">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="16f62-3325">外僑居留證</span></span> 
- <span data-ttu-id="16f62-3326">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="16f62-3326">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="16f62-3327">Código de identificación de población tailandesa</span><span class="sxs-lookup"><span data-stu-id="16f62-3327">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3328">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3328">Format</span></span>

<span data-ttu-id="16f62-3329">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3329">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3330">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3330">Pattern</span></span>

<span data-ttu-id="16f62-3331">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3331">13 digits:</span></span>
- <span data-ttu-id="16f62-3332">El primer dígito no es 0 ni 9</span><span class="sxs-lookup"><span data-stu-id="16f62-3332">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="16f62-3333">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3333">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3334">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3334">Checksum</span></span>

<span data-ttu-id="16f62-3335">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3335">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3336">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3336">Definition</span></span>

<span data-ttu-id="16f62-3337">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3337">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3338">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3338">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3339">Se encuentra una palabra clave de Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="16f62-3339">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="16f62-3340">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3340">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3341">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3341">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3342">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3342">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="16f62-3343">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="16f62-3343">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="16f62-3344">Número de id.</span><span class="sxs-lookup"><span data-stu-id="16f62-3344">ID Number</span></span>
- <span data-ttu-id="16f62-3345">Número de identificación</span><span class="sxs-lookup"><span data-stu-id="16f62-3345">Identification Number</span></span>
- <span data-ttu-id="16f62-3346">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16f62-3346">บัตรประชาชน</span></span>
- <span data-ttu-id="16f62-3347">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16f62-3347">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="16f62-3348">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16f62-3348">บัตรประชาชน</span></span>
- <span data-ttu-id="16f62-3349">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16f62-3349">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="16f62-3350">Número de identificación nacional de Turco</span><span class="sxs-lookup"><span data-stu-id="16f62-3350">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3351">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3351">Format</span></span>

<span data-ttu-id="16f62-3352">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3352">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3353">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3353">Pattern</span></span>

<span data-ttu-id="16f62-3354">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3354">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3355">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3355">Checksum</span></span>

<span data-ttu-id="16f62-3356">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3356">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3357">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3357">Definition</span></span>

<span data-ttu-id="16f62-3358">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3358">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3359">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3359">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3360">Se encuentra una palabra clave de Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="16f62-3360">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="16f62-3361">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3362">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3362">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3363">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="16f62-3364">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="16f62-3364">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="16f62-3365">TC Kimlik no</span><span class="sxs-lookup"><span data-stu-id="16f62-3365">TC Kimlik No</span></span>
- <span data-ttu-id="16f62-3366">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="16f62-3366">TC Kimlik numarası</span></span>
- <span data-ttu-id="16f62-3367">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="16f62-3367">Vatandaşlık numarası</span></span>
- <span data-ttu-id="16f62-3368">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="16f62-3368">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="16f62-p141">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="16f62-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3371">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3371">Format</span></span>

<span data-ttu-id="16f62-3372">Combinación de 18 letras y dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="16f62-3372">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3373">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3373">Pattern</span></span>

<span data-ttu-id="16f62-3374">18 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3374">18 letters and digits:</span></span>
- <span data-ttu-id="16f62-3375">Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="16f62-3375">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="16f62-3376">Un dígito</span><span class="sxs-lookup"><span data-stu-id="16f62-3376">One digit</span></span> 
- <span data-ttu-id="16f62-3377">Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-3377">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="16f62-3378">Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="16f62-3378">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="16f62-3379">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3379">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3380">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3380">Checksum</span></span>

<span data-ttu-id="16f62-3381">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3382">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3382">Definition</span></span>

<span data-ttu-id="16f62-3383">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3383">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3384">La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3384">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3385">Se encuentra una palabra clave de Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="16f62-3385">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="16f62-3386">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3386">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3387">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3387">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="16f62-3388">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16f62-3388">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="16f62-3389">DVLA</span><span class="sxs-lookup"><span data-stu-id="16f62-3389">DVLA</span></span> 
- <span data-ttu-id="16f62-3390">light vans</span><span class="sxs-lookup"><span data-stu-id="16f62-3390">light vans</span></span> 
- <span data-ttu-id="16f62-3391">quadbikes</span><span class="sxs-lookup"><span data-stu-id="16f62-3391">quadbikes</span></span> 
- <span data-ttu-id="16f62-3392">motor cars</span><span class="sxs-lookup"><span data-stu-id="16f62-3392">motor cars</span></span> 
- <span data-ttu-id="16f62-3393">125cc</span><span class="sxs-lookup"><span data-stu-id="16f62-3393">125cc</span></span> 
- <span data-ttu-id="16f62-3394">sidecar</span><span class="sxs-lookup"><span data-stu-id="16f62-3394">sidecar</span></span> 
- <span data-ttu-id="16f62-3395">Tricycles</span><span class="sxs-lookup"><span data-stu-id="16f62-3395">tricycles</span></span> 
- <span data-ttu-id="16f62-3396">sidecar</span><span class="sxs-lookup"><span data-stu-id="16f62-3396">motorcycles</span></span> 
- <span data-ttu-id="16f62-3397">photocard licence</span><span class="sxs-lookup"><span data-stu-id="16f62-3397">photocard licence</span></span> 
- <span data-ttu-id="16f62-3398">learner drivers</span><span class="sxs-lookup"><span data-stu-id="16f62-3398">learner drivers</span></span> 
- <span data-ttu-id="16f62-3399">licence holder</span><span class="sxs-lookup"><span data-stu-id="16f62-3399">licence holder</span></span> 
- <span data-ttu-id="16f62-3400">licence holders</span><span class="sxs-lookup"><span data-stu-id="16f62-3400">licence holders</span></span> 
- <span data-ttu-id="16f62-3401">driving licences</span><span class="sxs-lookup"><span data-stu-id="16f62-3401">driving licences</span></span> 
- <span data-ttu-id="16f62-3402">driving licence</span><span class="sxs-lookup"><span data-stu-id="16f62-3402">driving licence</span></span> 
- <span data-ttu-id="16f62-3403">dual control car</span><span class="sxs-lookup"><span data-stu-id="16f62-3403">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="16f62-p142">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="16f62-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3406">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3406">Format</span></span>

<span data-ttu-id="16f62-3407">Dos letras seguidas por entre 1 y 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3407">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3408">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3408">Pattern</span></span>

<span data-ttu-id="16f62-3409">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números</span><span class="sxs-lookup"><span data-stu-id="16f62-3409">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3410">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3410">Checksum</span></span>

<span data-ttu-id="16f62-3411">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3411">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3412">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3412">Definition</span></span>

<span data-ttu-id="16f62-3413">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3414">La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3414">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3415">Se encuentra una palabra clave de Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="16f62-3415">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3416">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3416">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="16f62-3417">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="16f62-3417">Keyword_uk_electoral</span></span>

- <span data-ttu-id="16f62-3418">council nomination</span><span class="sxs-lookup"><span data-stu-id="16f62-3418">council nomination</span></span> 
- <span data-ttu-id="16f62-3419">nomination form</span><span class="sxs-lookup"><span data-stu-id="16f62-3419">nomination form</span></span> 
- <span data-ttu-id="16f62-3420">electoral register</span><span class="sxs-lookup"><span data-stu-id="16f62-3420">electoral register</span></span> 
- <span data-ttu-id="16f62-3421">electoral roll</span><span class="sxs-lookup"><span data-stu-id="16f62-3421">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="16f62-p143">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="16f62-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3424">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3424">Format</span></span>

<span data-ttu-id="16f62-3425">De 10 a 17 dígitos separados por espacios</span><span class="sxs-lookup"><span data-stu-id="16f62-3425">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3426">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3426">Pattern</span></span>

<span data-ttu-id="16f62-3427">10-17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16f62-3427">10-17 digits:</span></span>
- <span data-ttu-id="16f62-3428">3 o 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3428">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="16f62-3429">Un espacio</span><span class="sxs-lookup"><span data-stu-id="16f62-3429">A space</span></span> 
- <span data-ttu-id="16f62-3430">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3430">Three digits</span></span> 
- <span data-ttu-id="16f62-3431">Un espacio</span><span class="sxs-lookup"><span data-stu-id="16f62-3431">A space</span></span> 
- <span data-ttu-id="16f62-3432">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3432">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3433">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3433">Checksum</span></span>

<span data-ttu-id="16f62-3434">Sí</span><span class="sxs-lookup"><span data-stu-id="16f62-3434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3435">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3435">Definition</span></span>

<span data-ttu-id="16f62-3436">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3437">La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3437">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3438">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-3438">One of the following is true:</span></span>
    - <span data-ttu-id="16f62-3439">Se encuentra una palabra clave de Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="16f62-3439">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="16f62-3440">Se encuentra una palabra clave de Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="16f62-3440">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="16f62-3441">Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="16f62-3441">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="16f62-3442">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="16f62-3442">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3443">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="16f62-3444">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="16f62-3444">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="16f62-3445">national health service</span><span class="sxs-lookup"><span data-stu-id="16f62-3445">national health service</span></span> 
- <span data-ttu-id="16f62-3446">del NHS del</span><span class="sxs-lookup"><span data-stu-id="16f62-3446">nhs</span></span> 
- <span data-ttu-id="16f62-3447">health services authority</span><span class="sxs-lookup"><span data-stu-id="16f62-3447">health services authority</span></span> 
- <span data-ttu-id="16f62-3448">health authority</span><span class="sxs-lookup"><span data-stu-id="16f62-3448">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="16f62-3449">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="16f62-3449">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="16f62-3450">patient id</span><span class="sxs-lookup"><span data-stu-id="16f62-3450">patient id</span></span> 
- <span data-ttu-id="16f62-3451">patient identification</span><span class="sxs-lookup"><span data-stu-id="16f62-3451">patient identification</span></span> 
- <span data-ttu-id="16f62-3452">patient no</span><span class="sxs-lookup"><span data-stu-id="16f62-3452">patient no</span></span> 
- <span data-ttu-id="16f62-3453">patient number</span><span class="sxs-lookup"><span data-stu-id="16f62-3453">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="16f62-3454">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="16f62-3454">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="16f62-3455">EON</span><span class="sxs-lookup"><span data-stu-id="16f62-3455">GP</span></span> 
- <span data-ttu-id="16f62-3456">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="16f62-3456">DOB</span></span> 
- <span data-ttu-id="16f62-3457">D. O. B</span><span class="sxs-lookup"><span data-stu-id="16f62-3457">D.O.B</span></span> 
- <span data-ttu-id="16f62-3458">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-3458">Date of Birth</span></span> 
- <span data-ttu-id="16f62-3459">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-3459">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="16f62-p144">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="16f62-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3462">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3462">Format</span></span>

<span data-ttu-id="16f62-3463">7 caracteres o 9 caracteres separados por espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="16f62-3463">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3464">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3464">Pattern</span></span>

<span data-ttu-id="16f62-3465">Dos patrones posibles:</span><span class="sxs-lookup"><span data-stu-id="16f62-3465">Two possible patterns:</span></span>

- <span data-ttu-id="16f62-3466">Dos letras (los NINO válidos usan solo caracteres determinados en este prefijo, que valida este patrón; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-3466">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="16f62-3467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3467">Six digits</span></span>
- <span data-ttu-id="16f62-3468">' A ', ' B ', ' C ' o ' T ' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16f62-3468">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="16f62-3469">O</span><span class="sxs-lookup"><span data-stu-id="16f62-3469">OR</span></span>

- <span data-ttu-id="16f62-3470">Dos letras</span><span class="sxs-lookup"><span data-stu-id="16f62-3470">Two letters</span></span>
- <span data-ttu-id="16f62-3471">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-3471">A space or dash</span></span>
- <span data-ttu-id="16f62-3472">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3472">Two digits</span></span>
- <span data-ttu-id="16f62-3473">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-3473">A space or dash</span></span>
- <span data-ttu-id="16f62-3474">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3474">Two digits</span></span>
- <span data-ttu-id="16f62-3475">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-3475">A space or dash</span></span>
- <span data-ttu-id="16f62-3476">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3476">Two digits</span></span>
- <span data-ttu-id="16f62-3477">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-3477">A space or dash</span></span>
- <span data-ttu-id="16f62-3478">' A ', ' B ', ' C ' o ' T '</span><span class="sxs-lookup"><span data-stu-id="16f62-3478">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3479">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3479">Checksum</span></span>

<span data-ttu-id="16f62-3480">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3480">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3481">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3481">Definition</span></span>

<span data-ttu-id="16f62-3482">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3482">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3483">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3483">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3484">Se encuentra una palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="16f62-3484">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="16f62-3485">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3485">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3486">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3486">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3487">No se encuentra ninguna palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="16f62-3487">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3488">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3488">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="16f62-3489">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="16f62-3489">Keyword_uk_nino</span></span>

- <span data-ttu-id="16f62-3490">national insurance number</span><span class="sxs-lookup"><span data-stu-id="16f62-3490">national insurance number</span></span> 
- <span data-ttu-id="16f62-3491">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="16f62-3491">national insurance contributions</span></span> 
- <span data-ttu-id="16f62-3492">protection act</span><span class="sxs-lookup"><span data-stu-id="16f62-3492">protection act</span></span> 
- <span data-ttu-id="16f62-3493">Pensión</span><span class="sxs-lookup"><span data-stu-id="16f62-3493">insurance</span></span> 
- <span data-ttu-id="16f62-3494">social security number</span><span class="sxs-lookup"><span data-stu-id="16f62-3494">social security number</span></span> 
- <span data-ttu-id="16f62-3495">insurance application</span><span class="sxs-lookup"><span data-stu-id="16f62-3495">insurance application</span></span> 
- <span data-ttu-id="16f62-3496">medical application</span><span class="sxs-lookup"><span data-stu-id="16f62-3496">medical application</span></span> 
- <span data-ttu-id="16f62-3497">social insurance</span><span class="sxs-lookup"><span data-stu-id="16f62-3497">social insurance</span></span> 
- <span data-ttu-id="16f62-3498">medical attention</span><span class="sxs-lookup"><span data-stu-id="16f62-3498">medical attention</span></span> 
- <span data-ttu-id="16f62-3499">social security</span><span class="sxs-lookup"><span data-stu-id="16f62-3499">social security</span></span> 
- <span data-ttu-id="16f62-3500">great britain</span><span class="sxs-lookup"><span data-stu-id="16f62-3500">great britain</span></span> 
- <span data-ttu-id="16f62-3501">Pensión</span><span class="sxs-lookup"><span data-stu-id="16f62-3501">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="16f62-p145">Número de pasaporte EE. UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="16f62-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3504">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3504">Format</span></span>

<span data-ttu-id="16f62-3505">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3505">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3506">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3506">Pattern</span></span>

<span data-ttu-id="16f62-3507">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-3507">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3508">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3508">Checksum</span></span>

<span data-ttu-id="16f62-3509">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3509">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3510">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3510">Definition</span></span>

<span data-ttu-id="16f62-3511">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3511">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3512">La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3512">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3513">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="16f62-3513">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3514">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3514">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="16f62-3515">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16f62-3515">Keyword_passport</span></span>

- <span data-ttu-id="16f62-3516">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3516">Passport Number</span></span> 
- <span data-ttu-id="16f62-3517">Passport No</span><span class="sxs-lookup"><span data-stu-id="16f62-3517">Passport No</span></span> 
- <span data-ttu-id="16f62-3518">Passport #</span><span class="sxs-lookup"><span data-stu-id="16f62-3518">Passport #</span></span> 
- <span data-ttu-id="16f62-3519">Usuarios</span><span class="sxs-lookup"><span data-stu-id="16f62-3519">Passport#</span></span> 
- <span data-ttu-id="16f62-3520">PassportID</span><span class="sxs-lookup"><span data-stu-id="16f62-3520">PassportID</span></span> 
- <span data-ttu-id="16f62-3521">Passportno</span><span class="sxs-lookup"><span data-stu-id="16f62-3521">Passportno</span></span> 
- <span data-ttu-id="16f62-3522">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16f62-3522">passportnumber</span></span> 
- <span data-ttu-id="16f62-3523">パスポート</span><span class="sxs-lookup"><span data-stu-id="16f62-3523">パスポート</span></span> 
- <span data-ttu-id="16f62-3524">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16f62-3524">パスポート番号</span></span> 
- <span data-ttu-id="16f62-3525">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16f62-3525">パスポートのNum</span></span> 
- <span data-ttu-id="16f62-3526">パスポート #</span><span class="sxs-lookup"><span data-stu-id="16f62-3526">パスポート＃</span></span> 
- <span data-ttu-id="16f62-3527">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16f62-3527">Numéro de passeport</span></span> 
- <span data-ttu-id="16f62-3528">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16f62-3528">Passeport n °</span></span> 
- <span data-ttu-id="16f62-3529">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16f62-3529">Passeport Non</span></span> 
- <span data-ttu-id="16f62-3530">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-3530">Passeport #</span></span> 
- <span data-ttu-id="16f62-3531">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16f62-3531">Passeport#</span></span> 
- <span data-ttu-id="16f62-3532">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16f62-3532">PasseportNon</span></span> 
- <span data-ttu-id="16f62-3533">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16f62-3533">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="16f62-3534">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="16f62-3534">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3535">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3535">Format</span></span>

<span data-ttu-id="16f62-3536">Entre 8 y 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3536">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3537">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3537">Pattern</span></span>

<span data-ttu-id="16f62-3538">Entre 8 y 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="16f62-3538">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3539">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3539">Checksum</span></span>

<span data-ttu-id="16f62-3540">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3540">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3541">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3541">Definition</span></span>

<span data-ttu-id="16f62-3542">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3542">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3543">La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3543">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3544">Se encuentra una palabra clave de Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="16f62-3544">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16f62-3545">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3545">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="16f62-3546">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="16f62-3546">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="16f62-3547">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3547">Checking Account Number</span></span> 
- <span data-ttu-id="16f62-3548">Checking Account</span><span class="sxs-lookup"><span data-stu-id="16f62-3548">Checking Account</span></span> 
- <span data-ttu-id="16f62-3549">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-3549">Checking Account #</span></span> 
- <span data-ttu-id="16f62-3550">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3550">Checking Acct Number</span></span> 
- <span data-ttu-id="16f62-3551">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-3551">Checking Acct #</span></span> 
- <span data-ttu-id="16f62-3552">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3552">Checking Acct No.</span></span> 
- <span data-ttu-id="16f62-3553">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3553">Checking Account No.</span></span> 
- <span data-ttu-id="16f62-3554">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3554">Bank Account Number</span></span> 
- <span data-ttu-id="16f62-3555">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-3555">Bank Account #</span></span> 
- <span data-ttu-id="16f62-3556">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3556">Bank Acct Number</span></span> 
- <span data-ttu-id="16f62-3557">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-3557">Bank Acct #</span></span> 
- <span data-ttu-id="16f62-3558">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3558">Bank Acct No.</span></span> 
- <span data-ttu-id="16f62-3559">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3559">Bank Account No.</span></span> 
- <span data-ttu-id="16f62-3560">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3560">Savings Account Number</span></span> 
- <span data-ttu-id="16f62-3561">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="16f62-3561">Savings Account.</span></span> 
- <span data-ttu-id="16f62-3562">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-3562">Savings Account #</span></span> 
- <span data-ttu-id="16f62-3563">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3563">Savings Acct Number</span></span> 
- <span data-ttu-id="16f62-3564">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-3564">Savings Acct #</span></span> 
- <span data-ttu-id="16f62-3565">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3565">Savings Acct No.</span></span> 
- <span data-ttu-id="16f62-3566">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3566">Savings Account No.</span></span> 
- <span data-ttu-id="16f62-3567">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3567">Debit Account Number</span></span> 
- <span data-ttu-id="16f62-3568">Debit Account</span><span class="sxs-lookup"><span data-stu-id="16f62-3568">Debit Account</span></span> 
- <span data-ttu-id="16f62-3569">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="16f62-3569">Debit Account #</span></span> 
- <span data-ttu-id="16f62-3570">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="16f62-3570">Debit Acct Number</span></span> 
- <span data-ttu-id="16f62-3571">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="16f62-3571">Debit Acct #</span></span> 
- <span data-ttu-id="16f62-3572">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3572">Debit Acct No.</span></span> 
- <span data-ttu-id="16f62-3573">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="16f62-3573">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="16f62-3574">Número de licencia de conductor de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="16f62-3574">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3575">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3575">Format</span></span>

<span data-ttu-id="16f62-3576">Depende del estado</span><span class="sxs-lookup"><span data-stu-id="16f62-3576">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3577">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3577">Pattern</span></span>

<span data-ttu-id="16f62-3578">Depende del estado, por ejemplo, Nueva York:</span><span class="sxs-lookup"><span data-stu-id="16f62-3578">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="16f62-3579">Nueve dígitos con formato como DDD DDD DDD coincidirán.</span><span class="sxs-lookup"><span data-stu-id="16f62-3579">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="16f62-3580">Nueve dígitos como ddddddddd no coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="16f62-3580">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3581">Checksum</span></span>

<span data-ttu-id="16f62-3582">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3582">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3583">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3583">Definition</span></span>

<span data-ttu-id="16f62-3584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3585">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3585">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3586">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="16f62-3586">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="16f62-3587">Se encuentra una palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="16f62-3587">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="16f62-3588">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3588">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3589">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3589">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3590">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="16f62-3590">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="16f62-3591">Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="16f62-3591">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="16f62-3592">No se encuentra ninguna palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="16f62-3592">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3593">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3593">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="16f62-3594">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="16f62-3594">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="16f62-3595">LISTAS</span><span class="sxs-lookup"><span data-stu-id="16f62-3595">DL</span></span> 
- <span data-ttu-id="16f62-3596">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="16f62-3596">DLS</span></span> 
- <span data-ttu-id="16f62-3597">CDL</span><span class="sxs-lookup"><span data-stu-id="16f62-3597">CDL</span></span> 
- <span data-ttu-id="16f62-3598">CDLS</span><span class="sxs-lookup"><span data-stu-id="16f62-3598">CDLS</span></span> 
- <span data-ttu-id="16f62-3599">Id.</span><span class="sxs-lookup"><span data-stu-id="16f62-3599">ID</span></span> 
- <span data-ttu-id="16f62-3600">Falta</span><span class="sxs-lookup"><span data-stu-id="16f62-3600">IDs</span></span> 
- <span data-ttu-id="16f62-3601">LISTAS</span><span class="sxs-lookup"><span data-stu-id="16f62-3601">DL#</span></span> 
- <span data-ttu-id="16f62-3602">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="16f62-3602">DLS#</span></span> 
- <span data-ttu-id="16f62-3603">CDL</span><span class="sxs-lookup"><span data-stu-id="16f62-3603">CDL#</span></span> 
- <span data-ttu-id="16f62-3604">CDLS #</span><span class="sxs-lookup"><span data-stu-id="16f62-3604">CDLS#</span></span> 
- <span data-ttu-id="16f62-3605">IDENTIFICADOR</span><span class="sxs-lookup"><span data-stu-id="16f62-3605">ID#</span></span>
- <span data-ttu-id="16f62-3606">Falta</span><span class="sxs-lookup"><span data-stu-id="16f62-3606">IDs#</span></span> 
- <span data-ttu-id="16f62-3607">ID number</span><span class="sxs-lookup"><span data-stu-id="16f62-3607">ID number</span></span> 
- <span data-ttu-id="16f62-3608">ID numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-3608">ID numbers</span></span> 
- <span data-ttu-id="16f62-3609">LIC</span><span class="sxs-lookup"><span data-stu-id="16f62-3609">LIC</span></span> 
- <span data-ttu-id="16f62-3610">Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-3610">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="16f62-3611">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16f62-3611">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="16f62-3612">DriverLic</span><span class="sxs-lookup"><span data-stu-id="16f62-3612">DriverLic</span></span> 
- <span data-ttu-id="16f62-3613">DriverLics</span><span class="sxs-lookup"><span data-stu-id="16f62-3613">DriverLics</span></span> 
- <span data-ttu-id="16f62-3614">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-3614">DriverLicense</span></span> 
- <span data-ttu-id="16f62-3615">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-3615">DriverLicenses</span></span> 
- <span data-ttu-id="16f62-3616">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-3616">Driver Lic</span></span> 
- <span data-ttu-id="16f62-3617">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-3617">Driver Lics</span></span> 
- <span data-ttu-id="16f62-3618">Driver License</span><span class="sxs-lookup"><span data-stu-id="16f62-3618">Driver License</span></span> 
- <span data-ttu-id="16f62-3619">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-3619">Driver Licenses</span></span> 
- <span data-ttu-id="16f62-3620">DriversLic</span><span class="sxs-lookup"><span data-stu-id="16f62-3620">DriversLic</span></span> 
- <span data-ttu-id="16f62-3621">DriversLics</span><span class="sxs-lookup"><span data-stu-id="16f62-3621">DriversLics</span></span> 
- <span data-ttu-id="16f62-3622">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-3622">DriversLicense</span></span> 
- <span data-ttu-id="16f62-3623">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-3623">DriversLicenses</span></span> 
- <span data-ttu-id="16f62-3624">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-3624">Drivers Lic</span></span> 
- <span data-ttu-id="16f62-3625">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-3625">Drivers Lics</span></span> 
- <span data-ttu-id="16f62-3626">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16f62-3626">Drivers License</span></span> 
- <span data-ttu-id="16f62-3627">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-3627">Drivers Licenses</span></span> 
- <span data-ttu-id="16f62-3628">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-3628">Driver'Lic</span></span> 
- <span data-ttu-id="16f62-3629">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-3629">Driver'Lics</span></span> 
- <span data-ttu-id="16f62-3630">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-3630">Driver'License</span></span> 
- <span data-ttu-id="16f62-3631">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-3631">Driver'Licenses</span></span> 
- <span data-ttu-id="16f62-3632">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-3632">Driver' Lic</span></span> 
- <span data-ttu-id="16f62-3633">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-3633">Driver' Lics</span></span> 
- <span data-ttu-id="16f62-3634">Driver' License</span><span class="sxs-lookup"><span data-stu-id="16f62-3634">Driver' License</span></span> 
- <span data-ttu-id="16f62-3635">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="16f62-3635">Driver' Licenses</span></span>
- <span data-ttu-id="16f62-3636">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="16f62-3636">Driver'sLic</span></span> 
- <span data-ttu-id="16f62-3637">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="16f62-3637">Driver'sLics</span></span> 
- <span data-ttu-id="16f62-3638">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="16f62-3638">Driver'sLicense</span></span> 
- <span data-ttu-id="16f62-3639">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="16f62-3639">Driver'sLicenses</span></span> 
- <span data-ttu-id="16f62-3640">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16f62-3640">Driver's Lic</span></span> 
- <span data-ttu-id="16f62-3641">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="16f62-3641">Driver's Lics</span></span> 
- <span data-ttu-id="16f62-3642">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16f62-3642">Driver's License</span></span> 
- <span data-ttu-id="16f62-3643">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-3643">Driver's Licenses</span></span> 
- <span data-ttu-id="16f62-3644">identification number</span><span class="sxs-lookup"><span data-stu-id="16f62-3644">identification number</span></span> 
- <span data-ttu-id="16f62-3645">identification numbers</span><span class="sxs-lookup"><span data-stu-id="16f62-3645">identification numbers</span></span> 
- <span data-ttu-id="16f62-3646">identification #</span><span class="sxs-lookup"><span data-stu-id="16f62-3646">identification #</span></span> 
- <span data-ttu-id="16f62-3647">id card</span><span class="sxs-lookup"><span data-stu-id="16f62-3647">id card</span></span> 
- <span data-ttu-id="16f62-3648">id cards</span><span class="sxs-lookup"><span data-stu-id="16f62-3648">id cards</span></span> 
- <span data-ttu-id="16f62-3649">identification card</span><span class="sxs-lookup"><span data-stu-id="16f62-3649">identification card</span></span> 
- <span data-ttu-id="16f62-3650">identification cards</span><span class="sxs-lookup"><span data-stu-id="16f62-3650">identification cards</span></span> 
- <span data-ttu-id="16f62-3651">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-3651">DriverLic#</span></span> 
- <span data-ttu-id="16f62-3652">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-3652">DriverLics#</span></span> 
- <span data-ttu-id="16f62-3653">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-3653">DriverLicense#</span></span> 
- <span data-ttu-id="16f62-3654">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-3654">DriverLicenses#</span></span> 
- <span data-ttu-id="16f62-3655">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-3655">Driver Lic#</span></span> 
- <span data-ttu-id="16f62-3656">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-3656">Driver Lics#</span></span> 
- <span data-ttu-id="16f62-3657">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16f62-3657">Driver License#</span></span> 
- <span data-ttu-id="16f62-3658">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-3658">Driver Licenses#</span></span> 
- <span data-ttu-id="16f62-3659">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-3659">DriversLic#</span></span> 
- <span data-ttu-id="16f62-3660">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-3660">DriversLics#</span></span> 
- <span data-ttu-id="16f62-3661">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-3661">DriversLicense#</span></span> 
- <span data-ttu-id="16f62-3662">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-3662">DriversLicenses#</span></span> 
- <span data-ttu-id="16f62-3663">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-3663">Drivers Lic#</span></span> 
- <span data-ttu-id="16f62-3664">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-3664">Drivers Lics#</span></span> 
- <span data-ttu-id="16f62-3665">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="16f62-3665">Drivers License#</span></span> 
- <span data-ttu-id="16f62-3666">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-3666">Drivers Licenses#</span></span> 
- <span data-ttu-id="16f62-3667">N.º carné</span><span class="sxs-lookup"><span data-stu-id="16f62-3667">Driver'Lic#</span></span> 
- <span data-ttu-id="16f62-3668">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="16f62-3668">Driver'Lics#</span></span> 
- <span data-ttu-id="16f62-3669">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-3669">Driver'License#</span></span> 
- <span data-ttu-id="16f62-3670">Conducción</span><span class="sxs-lookup"><span data-stu-id="16f62-3670">Driver'Licenses#</span></span> 
- <span data-ttu-id="16f62-3671">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-3671">Driver' Lic#</span></span> 
- <span data-ttu-id="16f62-3672">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-3672">Driver' Lics#</span></span> 
- <span data-ttu-id="16f62-3673">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="16f62-3673">Driver' License#</span></span> 
- <span data-ttu-id="16f62-3674">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-3674">Driver' Licenses#</span></span> 
- <span data-ttu-id="16f62-3675">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="16f62-3675">Driver'sLic#</span></span> 
- <span data-ttu-id="16f62-3676">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="16f62-3676">Driver'sLics#</span></span> 
- <span data-ttu-id="16f62-3677">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="16f62-3677">Driver'sLicense#</span></span> 
- <span data-ttu-id="16f62-3678">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="16f62-3678">Driver'sLicenses#</span></span> 
- <span data-ttu-id="16f62-3679">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="16f62-3679">Driver's Lic#</span></span> 
- <span data-ttu-id="16f62-3680">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="16f62-3680">Driver's Lics#</span></span> 
- <span data-ttu-id="16f62-3681">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="16f62-3681">Driver's License#</span></span> 
- <span data-ttu-id="16f62-3682">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="16f62-3682">Driver's Licenses#</span></span> 
- <span data-ttu-id="16f62-3683">id card#</span><span class="sxs-lookup"><span data-stu-id="16f62-3683">id card#</span></span> 
- <span data-ttu-id="16f62-3684">id cards#</span><span class="sxs-lookup"><span data-stu-id="16f62-3684">id cards#</span></span> 
- <span data-ttu-id="16f62-3685">identification card#</span><span class="sxs-lookup"><span data-stu-id="16f62-3685">identification card#</span></span> 
- <span data-ttu-id="16f62-3686">identification cards#</span><span class="sxs-lookup"><span data-stu-id="16f62-3686">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="16f62-3687">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="16f62-3687">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="16f62-3688">Abreviatura del estado (por ejemplo, "NY")</span><span class="sxs-lookup"><span data-stu-id="16f62-3688">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="16f62-3689">Nombre del estado (por ejemplo, "New York")</span><span class="sxs-lookup"><span data-stu-id="16f62-3689">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="16f62-3690">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="16f62-3690">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3691">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3691">Format</span></span>

<span data-ttu-id="16f62-3692">Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="16f62-3692">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3693">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3693">Pattern</span></span>

<span data-ttu-id="16f62-3694">Con formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3694">Formatted:</span></span>
- <span data-ttu-id="16f62-3695">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="16f62-3695">The digit "9"</span></span> 
- <span data-ttu-id="16f62-3696">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3696">Two digits</span></span> 
- <span data-ttu-id="16f62-3697">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-3697">A space or dash</span></span> 
- <span data-ttu-id="16f62-3698">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="16f62-3698">A "7" or "8"</span></span> 
- <span data-ttu-id="16f62-3699">Un dígito</span><span class="sxs-lookup"><span data-stu-id="16f62-3699">A digit</span></span> 
- <span data-ttu-id="16f62-3700">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="16f62-3700">A space, or dash</span></span> 
- <span data-ttu-id="16f62-3701">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3701">Four digits</span></span>

<span data-ttu-id="16f62-3702">Sin formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3702">Unformatted:</span></span>
- <span data-ttu-id="16f62-3703">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="16f62-3703">The digit "9"</span></span> 
- <span data-ttu-id="16f62-3704">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3704">Two digits</span></span> 
- <span data-ttu-id="16f62-3705">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="16f62-3705">A "7" or "8"</span></span> 
- <span data-ttu-id="16f62-3706">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="16f62-3706">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3707">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3707">Checksum</span></span>

<span data-ttu-id="16f62-3708">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3708">No</span></span>

### <a name="definition"></a><span data-ttu-id="16f62-3709">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3709">Definition</span></span>

<span data-ttu-id="16f62-3710">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3710">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3711">La función Func_formatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3711">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3712">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-3712">At least one of the following is true:</span></span>
    - <span data-ttu-id="16f62-3713">Se encuentra una palabra clave de Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="16f62-3713">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="16f62-3714">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-3714">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="16f62-3715">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-3715">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="16f62-3716">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="16f62-3716">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="16f62-3717">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3717">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3718">La función Func_unformatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3718">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3719">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="16f62-3719">At least one of the following is true:</span></span>
    - <span data-ttu-id="16f62-3720">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="16f62-3720">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="16f62-3721">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-3721">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="16f62-3722">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="16f62-3722">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3723">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3723">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="16f62-3724">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="16f62-3724">Keyword_itin</span></span>

- <span data-ttu-id="16f62-3725">contribuyente</span><span class="sxs-lookup"><span data-stu-id="16f62-3725">taxpayer</span></span> 
- <span data-ttu-id="16f62-3726">tax id</span><span class="sxs-lookup"><span data-stu-id="16f62-3726">tax id</span></span> 
- <span data-ttu-id="16f62-3727">tax identification</span><span class="sxs-lookup"><span data-stu-id="16f62-3727">tax identification</span></span> 
- <span data-ttu-id="16f62-3728">élen</span><span class="sxs-lookup"><span data-stu-id="16f62-3728">itin</span></span> 
- <span data-ttu-id="16f62-3729">SSN</span><span class="sxs-lookup"><span data-stu-id="16f62-3729">ssn</span></span> 
- <span data-ttu-id="16f62-3730">/</span><span class="sxs-lookup"><span data-stu-id="16f62-3730">tin</span></span> 
- <span data-ttu-id="16f62-3731">social security</span><span class="sxs-lookup"><span data-stu-id="16f62-3731">social security</span></span> 
- <span data-ttu-id="16f62-3732">tax payer</span><span class="sxs-lookup"><span data-stu-id="16f62-3732">tax payer</span></span> 
- <span data-ttu-id="16f62-3733">ITINs</span><span class="sxs-lookup"><span data-stu-id="16f62-3733">itins</span></span> 
- <span data-ttu-id="16f62-3734">taxi</span><span class="sxs-lookup"><span data-stu-id="16f62-3734">taxid</span></span> 
- <span data-ttu-id="16f62-3735">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="16f62-3735">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="16f62-3736">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="16f62-3736">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="16f62-3737">License</span><span class="sxs-lookup"><span data-stu-id="16f62-3737">License</span></span> 
- <span data-ttu-id="16f62-3738">LISTAS</span><span class="sxs-lookup"><span data-stu-id="16f62-3738">DL</span></span> 
- <span data-ttu-id="16f62-3739">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="16f62-3739">DOB</span></span> 
- <span data-ttu-id="16f62-3740">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-3740">Birthdate</span></span> 
- <span data-ttu-id="16f62-3741">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="16f62-3741">Birthday</span></span> 
- <span data-ttu-id="16f62-3742">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16f62-3742">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="16f62-3743">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="16f62-3743">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="16f62-3744">Formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3744">Format</span></span>

<span data-ttu-id="16f62-3745">9 dígitos, que pueden ser un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="16f62-3745">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="16f62-3746">Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="16f62-3746">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="16f62-3747">Patrón</span><span class="sxs-lookup"><span data-stu-id="16f62-3747">Pattern</span></span>

<span data-ttu-id="16f62-3748">Cuatro funciones buscan SSN en cuatro patrones diferentes:</span><span class="sxs-lookup"><span data-stu-id="16f62-3748">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="16f62-3749">Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="16f62-3749">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="16f62-3750">Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="16f62-3750">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="16f62-3751">Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="16f62-3751">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="16f62-3752">Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="16f62-3752">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="16f62-3753">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16f62-3753">Checksum</span></span>

<span data-ttu-id="16f62-3754">No</span><span class="sxs-lookup"><span data-stu-id="16f62-3754">No</span></span>


### <a name="definition"></a><span data-ttu-id="16f62-3755">Definición</span><span class="sxs-lookup"><span data-stu-id="16f62-3755">Definition</span></span>

<span data-ttu-id="16f62-3756">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3757">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3757">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3758">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="16f62-3758">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="16f62-3759">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3759">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3760">La función Func_unformatted_ssn busca contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3760">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3761">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="16f62-3761">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="16f62-3762">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3762">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3763">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3763">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3764">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="16f62-3764">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="16f62-3765">La función Func_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3765">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="16f62-3766">Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16f62-3766">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16f62-3767">La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3767">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16f62-3768">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="16f62-3768">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="16f62-3769">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16f62-3769">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="16f62-3770">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16f62-3770">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="16f62-3771">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="16f62-3771">Keyword_ssn</span></span>

- <span data-ttu-id="16f62-3772">Social Security</span><span class="sxs-lookup"><span data-stu-id="16f62-3772">Social Security</span></span> 
- <span data-ttu-id="16f62-3773">Social Security#</span><span class="sxs-lookup"><span data-stu-id="16f62-3773">Social Security#</span></span> 
- <span data-ttu-id="16f62-3774">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="16f62-3774">Soc Sec</span></span> 
- <span data-ttu-id="16f62-3775">SSN</span><span class="sxs-lookup"><span data-stu-id="16f62-3775">SSN</span></span> 
- <span data-ttu-id="16f62-3776">SSN</span><span class="sxs-lookup"><span data-stu-id="16f62-3776">SSNS</span></span> 
- <span data-ttu-id="16f62-3777">SSN</span><span class="sxs-lookup"><span data-stu-id="16f62-3777">SSN#</span></span> 
- <span data-ttu-id="16f62-3778">SS</span><span class="sxs-lookup"><span data-stu-id="16f62-3778">SS#</span></span> 
- <span data-ttu-id="16f62-3779">SSID</span><span class="sxs-lookup"><span data-stu-id="16f62-3779">SSID</span></span> 
   

