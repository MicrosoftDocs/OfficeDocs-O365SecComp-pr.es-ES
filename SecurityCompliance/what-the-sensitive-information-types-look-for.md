---
title: Qué buscan los tipos de información confidencial
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 05/20/2019
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye 80 tipos de información confidencial listos para que pueda usarlos en las directivas de DLP. Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.
ms.openlocfilehash: d486510c35aaf147e6d63e28d1df36ef689e3975
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478259"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="679ba-104">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="679ba-104">What the sensitive information types look for</span></span>

<span data-ttu-id="679ba-105">La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="679ba-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="679ba-106">Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.</span><span class="sxs-lookup"><span data-stu-id="679ba-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="679ba-107">Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función.</span><span class="sxs-lookup"><span data-stu-id="679ba-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="679ba-108">Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="679ba-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="679ba-109">El nivel de confianza y la proximidad también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="679ba-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="679ba-110">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="679ba-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-111">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-111">Format</span></span>

<span data-ttu-id="679ba-112">9 dígitos, que pueden tener un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="679ba-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-113">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-113">Pattern</span></span>

<span data-ttu-id="679ba-114">Con formato</span><span class="sxs-lookup"><span data-stu-id="679ba-114">Formatted:</span></span>
- <span data-ttu-id="679ba-115">Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="679ba-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="679ba-116">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-116">A hyphen</span></span>
- <span data-ttu-id="679ba-117">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-117">Four digits</span></span>
- <span data-ttu-id="679ba-118">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-118">A hyphen</span></span>
- <span data-ttu-id="679ba-119">Un dígito</span><span class="sxs-lookup"><span data-stu-id="679ba-119">A digit</span></span>

<span data-ttu-id="679ba-120">Sin formato: 9 dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="679ba-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="679ba-121">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-121">Checksum</span></span>

<span data-ttu-id="679ba-122">No</span><span class="sxs-lookup"><span data-stu-id="679ba-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-123">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-123">Definition</span></span>

<span data-ttu-id="679ba-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-125">La función Func_aba_routing encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-126">Se encuentra una palabra clave de Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="679ba-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="679ba-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="679ba-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="679ba-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="679ba-129">ABA</span><span class="sxs-lookup"><span data-stu-id="679ba-129">aba</span></span>
- <span data-ttu-id="679ba-130">aba #</span><span class="sxs-lookup"><span data-stu-id="679ba-130">aba #</span></span>
- <span data-ttu-id="679ba-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="679ba-131">aba routing #</span></span>
- <span data-ttu-id="679ba-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="679ba-132">aba routing number</span></span>
- <span data-ttu-id="679ba-133">ABA #</span><span class="sxs-lookup"><span data-stu-id="679ba-133">aba#</span></span>
- <span data-ttu-id="679ba-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="679ba-134">abarouting#</span></span>
- <span data-ttu-id="679ba-135">aba number</span><span class="sxs-lookup"><span data-stu-id="679ba-135">aba number</span></span>
- <span data-ttu-id="679ba-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-136">abaroutingnumber</span></span>
- <span data-ttu-id="679ba-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="679ba-137">american bank association routing #</span></span>
- <span data-ttu-id="679ba-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="679ba-138">american bank association routing number</span></span>
- <span data-ttu-id="679ba-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="679ba-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="679ba-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="679ba-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="679ba-141">bank routing number</span></span>
- <span data-ttu-id="679ba-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="679ba-142">bankrouting#</span></span>
- <span data-ttu-id="679ba-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-143">bankroutingnumber</span></span>
- <span data-ttu-id="679ba-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="679ba-144">routing transit number</span></span>
- <span data-ttu-id="679ba-145">RTN</span><span class="sxs-lookup"><span data-stu-id="679ba-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="679ba-146">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="679ba-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-147">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-147">Format</span></span>

<span data-ttu-id="679ba-148">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="679ba-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-149">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-149">Pattern</span></span>

<span data-ttu-id="679ba-150">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-150">Eight digits:</span></span>
- <span data-ttu-id="679ba-151">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-151">Two digits</span></span>
- <span data-ttu-id="679ba-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-152">A period</span></span>
- <span data-ttu-id="679ba-153">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-153">Three digits</span></span>
- <span data-ttu-id="679ba-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-154">A period</span></span>
- <span data-ttu-id="679ba-155">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-156">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-156">Checksum</span></span>

<span data-ttu-id="679ba-157">No</span><span class="sxs-lookup"><span data-stu-id="679ba-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-158">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-158">Definition</span></span>

<span data-ttu-id="679ba-159">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-160">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-161">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="679ba-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="679ba-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="679ba-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="679ba-164">Número de identidad nacional de Argentina</span><span class="sxs-lookup"><span data-stu-id="679ba-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="679ba-165">Identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-165">Identity</span></span> 
- <span data-ttu-id="679ba-166">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="679ba-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="679ba-167">DNI</span><span class="sxs-lookup"><span data-stu-id="679ba-167">DNI</span></span> 
- <span data-ttu-id="679ba-168">Registro Nacional de NIC de personas</span><span class="sxs-lookup"><span data-stu-id="679ba-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="679ba-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="679ba-170">Registro nacional de las personas</span><span class="sxs-lookup"><span data-stu-id="679ba-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="679ba-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-171">Identidad</span></span> 
- <span data-ttu-id="679ba-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="679ba-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="679ba-173">Número de cuenta bancaria de Australia</span><span class="sxs-lookup"><span data-stu-id="679ba-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-174">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-174">Format</span></span>

<span data-ttu-id="679ba-175">De 6 a 10 dígitos con o sin número de sucursal bancaria de estado</span><span class="sxs-lookup"><span data-stu-id="679ba-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-176">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-176">Pattern</span></span>

<span data-ttu-id="679ba-177">El número de cuenta tiene entre 6 y 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="679ba-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="679ba-178">Número de sucursal bancaria de Australia:</span><span class="sxs-lookup"><span data-stu-id="679ba-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="679ba-179">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-179">Three digits</span></span> 
- <span data-ttu-id="679ba-180">Un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-180">A hyphen</span></span> 
- <span data-ttu-id="679ba-181">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-182">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-182">Checksum</span></span>

<span data-ttu-id="679ba-183">No</span><span class="sxs-lookup"><span data-stu-id="679ba-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-184">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-184">Definition</span></span>

<span data-ttu-id="679ba-185">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-186">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="679ba-187">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="679ba-188">La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="679ba-189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-190">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="679ba-191">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="679ba-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="679ba-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="679ba-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="679ba-194">swift bank code</span></span>
- <span data-ttu-id="679ba-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="679ba-195">correspondent bank</span></span>
- <span data-ttu-id="679ba-196">base currency</span><span class="sxs-lookup"><span data-stu-id="679ba-196">base currency</span></span>
- <span data-ttu-id="679ba-197">usa account</span><span class="sxs-lookup"><span data-stu-id="679ba-197">usa account</span></span>
- <span data-ttu-id="679ba-198">holder address</span><span class="sxs-lookup"><span data-stu-id="679ba-198">holder address</span></span>
- <span data-ttu-id="679ba-199">bank address</span><span class="sxs-lookup"><span data-stu-id="679ba-199">bank address</span></span>
- <span data-ttu-id="679ba-200">information account</span><span class="sxs-lookup"><span data-stu-id="679ba-200">information account</span></span>
- <span data-ttu-id="679ba-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="679ba-201">fund transfers</span></span>
- <span data-ttu-id="679ba-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="679ba-202">bank charges</span></span>
- <span data-ttu-id="679ba-203">bank details</span><span class="sxs-lookup"><span data-stu-id="679ba-203">bank details</span></span>
- <span data-ttu-id="679ba-204">banking information</span><span class="sxs-lookup"><span data-stu-id="679ba-204">banking information</span></span>
- <span data-ttu-id="679ba-205">full names</span><span class="sxs-lookup"><span data-stu-id="679ba-205">full names</span></span>
- <span data-ttu-id="679ba-206">OIEA</span><span class="sxs-lookup"><span data-stu-id="679ba-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="679ba-207">Número de licencia de conducción de Australia</span><span class="sxs-lookup"><span data-stu-id="679ba-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-208">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-208">Format</span></span>

<span data-ttu-id="679ba-209">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-210">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-210">Pattern</span></span>

<span data-ttu-id="679ba-211">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="679ba-212">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-213">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-213">Two digits</span></span> 
- <span data-ttu-id="679ba-214">Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="679ba-215">O</span><span class="sxs-lookup"><span data-stu-id="679ba-215">OR</span></span>

- <span data-ttu-id="679ba-216">1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-217">4-9 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-217">4-9 digits</span></span>

<span data-ttu-id="679ba-218">O</span><span class="sxs-lookup"><span data-stu-id="679ba-218">OR</span></span>

- <span data-ttu-id="679ba-219">Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-220">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-220">Checksum</span></span>

<span data-ttu-id="679ba-221">No</span><span class="sxs-lookup"><span data-stu-id="679ba-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-222">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-222">Definition</span></span>

<span data-ttu-id="679ba-223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-224">La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-225">Se encuentra una palabra clave de Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="679ba-226">No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="679ba-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="679ba-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="679ba-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="679ba-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="679ba-229">international driving permits</span></span>
- <span data-ttu-id="679ba-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="679ba-230">australian automobile association</span></span>
- <span data-ttu-id="679ba-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="679ba-231">international driving permit</span></span>
- <span data-ttu-id="679ba-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="679ba-232">DriverLicence</span></span>
- <span data-ttu-id="679ba-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="679ba-233">DriverLicences</span></span>
- <span data-ttu-id="679ba-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-234">Driver Lic</span></span>
- <span data-ttu-id="679ba-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-235">Driver Licence</span></span>
- <span data-ttu-id="679ba-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-236">Driver Licences</span></span>
- <span data-ttu-id="679ba-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="679ba-237">DriversLic</span></span>
- <span data-ttu-id="679ba-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="679ba-238">DriversLicence</span></span>
- <span data-ttu-id="679ba-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="679ba-239">DriversLicences</span></span>
- <span data-ttu-id="679ba-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-240">Drivers Lic</span></span>
- <span data-ttu-id="679ba-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-241">Drivers Lics</span></span>
- <span data-ttu-id="679ba-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-242">Drivers Licence</span></span>
- <span data-ttu-id="679ba-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-243">Drivers Licences</span></span>
- <span data-ttu-id="679ba-244">N.º carné</span><span class="sxs-lookup"><span data-stu-id="679ba-244">Driver'Lic</span></span>
- <span data-ttu-id="679ba-245">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="679ba-245">Driver'Lics</span></span>
- <span data-ttu-id="679ba-246">N.º carné</span><span class="sxs-lookup"><span data-stu-id="679ba-246">Driver'Licence</span></span>
- <span data-ttu-id="679ba-247">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="679ba-247">Driver'Licences</span></span>
- <span data-ttu-id="679ba-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-248">Driver' Lic</span></span>
- <span data-ttu-id="679ba-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-249">Driver' Lics</span></span>
- <span data-ttu-id="679ba-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-250">Driver' Licence</span></span>
- <span data-ttu-id="679ba-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-251">Driver' Licences</span></span>
- <span data-ttu-id="679ba-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="679ba-252">Driver'sLic</span></span>
- <span data-ttu-id="679ba-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="679ba-253">Driver'sLics</span></span>
- <span data-ttu-id="679ba-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="679ba-254">Driver'sLicence</span></span>
- <span data-ttu-id="679ba-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="679ba-255">Driver'sLicences</span></span>
- <span data-ttu-id="679ba-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-256">Driver's Lic</span></span>
- <span data-ttu-id="679ba-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-257">Driver's Lics</span></span>
- <span data-ttu-id="679ba-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-258">Driver's Licence</span></span>
- <span data-ttu-id="679ba-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-259">Driver's Licences</span></span>
- <span data-ttu-id="679ba-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-260">DriverLic#</span></span>
- <span data-ttu-id="679ba-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-261">DriverLics#</span></span>
- <span data-ttu-id="679ba-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="679ba-262">DriverLicence#</span></span>
- <span data-ttu-id="679ba-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="679ba-263">DriverLicences#</span></span>
- <span data-ttu-id="679ba-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-264">Driver Lic#</span></span>
- <span data-ttu-id="679ba-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-265">Driver Lics#</span></span>
- <span data-ttu-id="679ba-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="679ba-266">Driver Licence#</span></span>
- <span data-ttu-id="679ba-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-267">Driver Licences#</span></span>
- <span data-ttu-id="679ba-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-268">DriversLic#</span></span>
- <span data-ttu-id="679ba-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-269">DriversLics#</span></span>
- <span data-ttu-id="679ba-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="679ba-270">DriversLicence#</span></span>
- <span data-ttu-id="679ba-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="679ba-271">DriversLicences#</span></span>
- <span data-ttu-id="679ba-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-272">Drivers Lic#</span></span>
- <span data-ttu-id="679ba-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-273">Drivers Lics#</span></span>
- <span data-ttu-id="679ba-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="679ba-274">Drivers Licence#</span></span>
- <span data-ttu-id="679ba-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-275">Drivers Licences#</span></span>
- <span data-ttu-id="679ba-276">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="679ba-276">Driver'Lic#</span></span>
- <span data-ttu-id="679ba-277">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="679ba-277">Driver'Lics#</span></span>
- <span data-ttu-id="679ba-278">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="679ba-278">Driver'Licence#</span></span>
- <span data-ttu-id="679ba-279">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="679ba-279">Driver'Licences#</span></span>
- <span data-ttu-id="679ba-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-280">Driver' Lic#</span></span>
- <span data-ttu-id="679ba-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-281">Driver' Lics#</span></span>
- <span data-ttu-id="679ba-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="679ba-282">Driver' Licence#</span></span>
- <span data-ttu-id="679ba-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-283">Driver' Licences#</span></span>
- <span data-ttu-id="679ba-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-284">Driver'sLic#</span></span>
- <span data-ttu-id="679ba-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-285">Driver'sLics#</span></span>
- <span data-ttu-id="679ba-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="679ba-286">Driver'sLicence#</span></span>
- <span data-ttu-id="679ba-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="679ba-287">Driver'sLicences#</span></span>
- <span data-ttu-id="679ba-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-288">Driver's Lic#</span></span>
- <span data-ttu-id="679ba-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-289">Driver's Lics#</span></span>
- <span data-ttu-id="679ba-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="679ba-290">Driver's Licence#</span></span>
- <span data-ttu-id="679ba-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="679ba-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="679ba-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="679ba-293">aaaa</span><span class="sxs-lookup"><span data-stu-id="679ba-293">aaa</span></span>
- <span data-ttu-id="679ba-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-294">DriverLicense</span></span>
- <span data-ttu-id="679ba-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-295">DriverLicenses</span></span>
- <span data-ttu-id="679ba-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="679ba-296">Driver License</span></span>
- <span data-ttu-id="679ba-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-297">Driver Licenses</span></span>
- <span data-ttu-id="679ba-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-298">DriversLicense</span></span>
- <span data-ttu-id="679ba-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-299">DriversLicenses</span></span>
- <span data-ttu-id="679ba-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="679ba-300">Drivers License</span></span>
- <span data-ttu-id="679ba-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-301">Drivers Licenses</span></span>
- <span data-ttu-id="679ba-302">Conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-302">Driver'License</span></span>
- <span data-ttu-id="679ba-303">Conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-303">Driver'Licenses</span></span>
- <span data-ttu-id="679ba-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="679ba-304">Driver' License</span></span>
- <span data-ttu-id="679ba-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-305">Driver' Licenses</span></span>
- <span data-ttu-id="679ba-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-306">Driver'sLicense</span></span>
- <span data-ttu-id="679ba-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-307">Driver'sLicenses</span></span>
- <span data-ttu-id="679ba-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="679ba-308">Driver's License</span></span>
- <span data-ttu-id="679ba-309">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-309">Driver's Licenses</span></span>
- <span data-ttu-id="679ba-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-310">DriverLicense#</span></span>
- <span data-ttu-id="679ba-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-311">DriverLicenses#</span></span>
- <span data-ttu-id="679ba-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="679ba-312">Driver License#</span></span>
- <span data-ttu-id="679ba-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-313">Driver Licenses#</span></span>
- <span data-ttu-id="679ba-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-314">DriversLicense#</span></span>
- <span data-ttu-id="679ba-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-315">DriversLicenses#</span></span>
- <span data-ttu-id="679ba-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="679ba-316">Drivers License#</span></span>
- <span data-ttu-id="679ba-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-317">Drivers Licenses#</span></span>
- <span data-ttu-id="679ba-318">Conducción #</span><span class="sxs-lookup"><span data-stu-id="679ba-318">Driver'License#</span></span>
- <span data-ttu-id="679ba-319">Conducción #</span><span class="sxs-lookup"><span data-stu-id="679ba-319">Driver'Licenses#</span></span>
- <span data-ttu-id="679ba-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="679ba-320">Driver' License#</span></span>
- <span data-ttu-id="679ba-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-321">Driver' Licenses#</span></span>
- <span data-ttu-id="679ba-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-322">Driver'sLicense#</span></span>
- <span data-ttu-id="679ba-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="679ba-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="679ba-324">Driver's License#</span></span>
- <span data-ttu-id="679ba-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="679ba-326">Número de cuenta médica de Australia</span><span class="sxs-lookup"><span data-stu-id="679ba-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-327">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-327">Format</span></span>

<span data-ttu-id="679ba-328">Entre 10 y 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-329">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-329">Pattern</span></span>

<span data-ttu-id="679ba-330">Entre 10 y 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-330">10-11 digits:</span></span>
- <span data-ttu-id="679ba-331">el primer dígito está en el intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="679ba-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="679ba-332">El noveno dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="679ba-333">El décimo dígito es el dígito de emisión</span><span class="sxs-lookup"><span data-stu-id="679ba-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="679ba-334">El undécimo dígito (opcional) es el número individual</span><span class="sxs-lookup"><span data-stu-id="679ba-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-335">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-335">Checksum</span></span>

<span data-ttu-id="679ba-336">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-337">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-337">Definition</span></span>

<span data-ttu-id="679ba-338">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-339">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-340">Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="679ba-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="679ba-341">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-341">The checksum passes.</span></span>

<span data-ttu-id="679ba-342">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-343">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-344">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-344">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-345">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="679ba-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="679ba-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="679ba-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="679ba-347">bank account details</span></span>
- <span data-ttu-id="679ba-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="679ba-348">medicare payments</span></span>
- <span data-ttu-id="679ba-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="679ba-349">mortgage account</span></span>
- <span data-ttu-id="679ba-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="679ba-350">bank payments</span></span>
- <span data-ttu-id="679ba-351">information branch</span><span class="sxs-lookup"><span data-stu-id="679ba-351">information branch</span></span>
- <span data-ttu-id="679ba-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="679ba-352">credit card loan</span></span>
- <span data-ttu-id="679ba-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="679ba-353">department of human services</span></span>
- <span data-ttu-id="679ba-354">local service</span><span class="sxs-lookup"><span data-stu-id="679ba-354">local service</span></span>
- <span data-ttu-id="679ba-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="679ba-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="679ba-356">Número de pasaporte de Australia</span><span class="sxs-lookup"><span data-stu-id="679ba-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-357">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-357">Format</span></span>

<span data-ttu-id="679ba-358">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-359">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-359">Pattern</span></span>

<span data-ttu-id="679ba-360">Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-361">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-361">Checksum</span></span>

<span data-ttu-id="679ba-362">No</span><span class="sxs-lookup"><span data-stu-id="679ba-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-363">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-363">Definition</span></span>

<span data-ttu-id="679ba-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-365">La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-366">Se encuentra una palabra clave de Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-367">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="679ba-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-368">Keyword_passport</span></span>

- <span data-ttu-id="679ba-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="679ba-369">Passport Number</span></span>
- <span data-ttu-id="679ba-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="679ba-370">Passport No</span></span>
- <span data-ttu-id="679ba-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="679ba-371">Passport #</span></span>
- <span data-ttu-id="679ba-372">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="679ba-372">Passport#</span></span>
- <span data-ttu-id="679ba-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="679ba-373">PassportID</span></span>
- <span data-ttu-id="679ba-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="679ba-374">Passportno</span></span>
- <span data-ttu-id="679ba-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-375">passportnumber</span></span>
- <span data-ttu-id="679ba-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="679ba-376">パスポート</span></span>
- <span data-ttu-id="679ba-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="679ba-377">パスポート番号</span></span>
- <span data-ttu-id="679ba-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="679ba-378">パスポートのNum</span></span>
- <span data-ttu-id="679ba-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="679ba-379">パスポート ＃</span></span> 
- <span data-ttu-id="679ba-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="679ba-380">Numéro de passeport</span></span>
- <span data-ttu-id="679ba-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="679ba-381">Passeport n °</span></span>
- <span data-ttu-id="679ba-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="679ba-382">Passeport Non</span></span>
- <span data-ttu-id="679ba-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-383">Passeport #</span></span>
- <span data-ttu-id="679ba-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-384">Passeport#</span></span>
- <span data-ttu-id="679ba-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="679ba-385">PasseportNon</span></span>
- <span data-ttu-id="679ba-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="679ba-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="679ba-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="679ba-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="679ba-388">usuarios</span><span class="sxs-lookup"><span data-stu-id="679ba-388">passport</span></span>
- <span data-ttu-id="679ba-389">passport details</span><span class="sxs-lookup"><span data-stu-id="679ba-389">passport details</span></span>
- <span data-ttu-id="679ba-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="679ba-390">immigration and citizenship</span></span>
- <span data-ttu-id="679ba-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="679ba-391">commonwealth of australia</span></span>
- <span data-ttu-id="679ba-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="679ba-392">department of immigration</span></span>
- <span data-ttu-id="679ba-393">residential address</span><span class="sxs-lookup"><span data-stu-id="679ba-393">residential address</span></span>
- <span data-ttu-id="679ba-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="679ba-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="679ba-395">régimen</span><span class="sxs-lookup"><span data-stu-id="679ba-395">visa</span></span>
- <span data-ttu-id="679ba-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="679ba-396">national identity card</span></span>
- <span data-ttu-id="679ba-397">passport number</span><span class="sxs-lookup"><span data-stu-id="679ba-397">passport number</span></span>
- <span data-ttu-id="679ba-398">travel document</span><span class="sxs-lookup"><span data-stu-id="679ba-398">travel document</span></span>
- <span data-ttu-id="679ba-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="679ba-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="679ba-400">Número de archivo de impuestos de Australia</span><span class="sxs-lookup"><span data-stu-id="679ba-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-401">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-401">Format</span></span>

<span data-ttu-id="679ba-402">Entre 8 y 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-403">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-403">Pattern</span></span>

<span data-ttu-id="679ba-404">8-9 dígitos que normalmente se presentan con espacios como sigue:</span><span class="sxs-lookup"><span data-stu-id="679ba-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="679ba-405">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-405">Three digits</span></span> 
- <span data-ttu-id="679ba-406">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="679ba-406">An optional space</span></span> 
- <span data-ttu-id="679ba-407">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-407">Three digits</span></span> 
- <span data-ttu-id="679ba-408">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="679ba-408">An optional space</span></span> 
- <span data-ttu-id="679ba-409">2-3 dígitos donde el último dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-410">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-410">Checksum</span></span>

<span data-ttu-id="679ba-411">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-412">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-412">Definition</span></span>

<span data-ttu-id="679ba-413">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-414">La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-415">No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="679ba-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="679ba-416">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="679ba-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="679ba-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="679ba-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="679ba-419">australian business number</span></span>
- <span data-ttu-id="679ba-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="679ba-420">marginal tax rate</span></span>
- <span data-ttu-id="679ba-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="679ba-421">medicare levy</span></span>
- <span data-ttu-id="679ba-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="679ba-422">portfolio number</span></span>
- <span data-ttu-id="679ba-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="679ba-423">service veterans</span></span>
- <span data-ttu-id="679ba-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="679ba-424">withholding tax</span></span>
- <span data-ttu-id="679ba-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="679ba-425">individual tax return</span></span>
- <span data-ttu-id="679ba-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="679ba-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="679ba-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="679ba-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="679ba-428">00000000</span><span class="sxs-lookup"><span data-stu-id="679ba-428">00000000</span></span>
- <span data-ttu-id="679ba-429">11111111</span><span class="sxs-lookup"><span data-stu-id="679ba-429">11111111</span></span>
- <span data-ttu-id="679ba-430">22222222</span><span class="sxs-lookup"><span data-stu-id="679ba-430">22222222</span></span>
- <span data-ttu-id="679ba-431">33333333</span><span class="sxs-lookup"><span data-stu-id="679ba-431">33333333</span></span>
- <span data-ttu-id="679ba-432">44444444</span><span class="sxs-lookup"><span data-stu-id="679ba-432">44444444</span></span>
- <span data-ttu-id="679ba-433">55555555</span><span class="sxs-lookup"><span data-stu-id="679ba-433">55555555</span></span>
- <span data-ttu-id="679ba-434">66666666</span><span class="sxs-lookup"><span data-stu-id="679ba-434">66666666</span></span>
- <span data-ttu-id="679ba-435">77777777</span><span class="sxs-lookup"><span data-stu-id="679ba-435">77777777</span></span>
- <span data-ttu-id="679ba-436">88888888</span><span class="sxs-lookup"><span data-stu-id="679ba-436">88888888</span></span>
- <span data-ttu-id="679ba-437">99999999</span><span class="sxs-lookup"><span data-stu-id="679ba-437">99999999</span></span>
- <span data-ttu-id="679ba-438">000000000</span><span class="sxs-lookup"><span data-stu-id="679ba-438">000000000</span></span>
- <span data-ttu-id="679ba-439">111111111</span><span class="sxs-lookup"><span data-stu-id="679ba-439">111111111</span></span>
- <span data-ttu-id="679ba-440">222222222</span><span class="sxs-lookup"><span data-stu-id="679ba-440">222222222</span></span>
- <span data-ttu-id="679ba-441">333333333</span><span class="sxs-lookup"><span data-stu-id="679ba-441">333333333</span></span>
- <span data-ttu-id="679ba-442">444444444</span><span class="sxs-lookup"><span data-stu-id="679ba-442">444444444</span></span>
- <span data-ttu-id="679ba-443">555555555</span><span class="sxs-lookup"><span data-stu-id="679ba-443">555555555</span></span>
- <span data-ttu-id="679ba-444">666666666</span><span class="sxs-lookup"><span data-stu-id="679ba-444">666666666</span></span>
- <span data-ttu-id="679ba-445">777777777</span><span class="sxs-lookup"><span data-stu-id="679ba-445">777777777</span></span>
- <span data-ttu-id="679ba-446">888888888</span><span class="sxs-lookup"><span data-stu-id="679ba-446">888888888</span></span>
- <span data-ttu-id="679ba-447">999999999</span><span class="sxs-lookup"><span data-stu-id="679ba-447">999999999</span></span>
- <span data-ttu-id="679ba-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="679ba-448">0000000000</span></span>
- <span data-ttu-id="679ba-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="679ba-449">1111111111</span></span>
- <span data-ttu-id="679ba-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="679ba-450">2222222222</span></span>
- <span data-ttu-id="679ba-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="679ba-451">3333333333</span></span>
- <span data-ttu-id="679ba-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="679ba-452">4444444444</span></span>
- <span data-ttu-id="679ba-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="679ba-453">5555555555</span></span>
- <span data-ttu-id="679ba-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="679ba-454">6666666666</span></span>
- <span data-ttu-id="679ba-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="679ba-455">7777777777</span></span>
- <span data-ttu-id="679ba-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="679ba-456">8888888888</span></span>
- <span data-ttu-id="679ba-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="679ba-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="679ba-458">Clave de autenticación de Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="679ba-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="679ba-459">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-459">Format</span></span>

<span data-ttu-id="679ba-460">La cadena "DocumentDb" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="679ba-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-461">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-461">Pattern</span></span>

- <span data-ttu-id="679ba-462">La cadena "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="679ba-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="679ba-463">Cualquier combinación de entre 3-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-464">Un símbolo mayor que (>), un signo igual (=), una comilla (") o un apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="679ba-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="679ba-465">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="679ba-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="679ba-466">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-467">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-467">Checksum</span></span>

<span data-ttu-id="679ba-468">No</span><span class="sxs-lookup"><span data-stu-id="679ba-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-469">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-469">Definition</span></span>

<span data-ttu-id="679ba-470">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-471">La expresión regular CEP_Regex_AzureDocumentDBAuthKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-472">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-473">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-475">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-476">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-476">contoso</span></span>
- <span data-ttu-id="679ba-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-477">fabrikam</span></span>
- <span data-ttu-id="679ba-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-478">northwind</span></span>
- <span data-ttu-id="679ba-479">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-479">sandbox</span></span>
- <span data-ttu-id="679ba-480">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-480">onebox</span></span>
- <span data-ttu-id="679ba-481">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-481">localhost</span></span>
- <span data-ttu-id="679ba-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-482">127.0.0.1</span></span>
- <span data-ttu-id="679ba-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-484">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-484">com</span></span>
- <span data-ttu-id="679ba-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-486">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="679ba-487">Cadena de conexión de base de datos IAAS de Azure y cadena de conexión SQL de Azure</span><span class="sxs-lookup"><span data-stu-id="679ba-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="679ba-488">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-488">Format</span></span>

<span data-ttu-id="679ba-489">La cadena "Server", "Server" o "Data Source" seguida de los caracteres y las cadenas que se describen en el siguiente patrón, incluida la cadena "CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="679ba-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-490">com "o" CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="679ba-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-491">net "o" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="679ba-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-492">net "y la cadena" Password "o" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="679ba-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-493">Pattern</span></span>

- <span data-ttu-id="679ba-494">La cadena "servidor", "servidor" o "origen de datos"</span><span class="sxs-lookup"><span data-stu-id="679ba-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="679ba-495">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-496">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-496">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-497">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-498">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-499">La cadena "CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="679ba-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-500">com "," CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="679ba-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-501">net "o" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="679ba-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-502">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-502">net"</span></span>
- <span data-ttu-id="679ba-503">Cualquier combinación de entre 1-300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-504">La cadena "Password", "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="679ba-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="679ba-505">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-506">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-506">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-507">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-508">Uno o más caracteres que no son un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="679ba-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="679ba-509">Un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="679ba-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-510">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-510">Checksum</span></span>

<span data-ttu-id="679ba-511">No</span><span class="sxs-lookup"><span data-stu-id="679ba-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-512">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-512">Definition</span></span>

<span data-ttu-id="679ba-513">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-514">La expresión regular CEP_Regex_AzureConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-515">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-516">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-518">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-519">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-519">contoso</span></span>
- <span data-ttu-id="679ba-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-520">fabrikam</span></span>
- <span data-ttu-id="679ba-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-521">northwind</span></span>
- <span data-ttu-id="679ba-522">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-522">sandbox</span></span>
- <span data-ttu-id="679ba-523">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-523">onebox</span></span>
- <span data-ttu-id="679ba-524">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-524">localhost</span></span>
- <span data-ttu-id="679ba-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-525">127.0.0.1</span></span>
- <span data-ttu-id="679ba-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-527">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-527">com</span></span>
- <span data-ttu-id="679ba-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-529">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="679ba-530">Cadena de conexión de Azure IoT</span><span class="sxs-lookup"><span data-stu-id="679ba-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="679ba-531">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-531">Format</span></span>

<span data-ttu-id="679ba-532">La cadena "HostName" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="679ba-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-533">net "y" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="679ba-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-534">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-534">Pattern</span></span>

- <span data-ttu-id="679ba-535">La cadena "HostName"</span><span class="sxs-lookup"><span data-stu-id="679ba-535">The string "HostName"</span></span>
- <span data-ttu-id="679ba-536">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-537">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-537">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-538">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-539">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-540">La cadena "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="679ba-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-541">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-541">net"</span></span>
- <span data-ttu-id="679ba-542">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-543">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="679ba-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="679ba-544">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-545">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-545">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-546">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-547">Cualquier combinación de 43 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="679ba-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="679ba-548">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-549">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-549">Checksum</span></span>

<span data-ttu-id="679ba-550">No</span><span class="sxs-lookup"><span data-stu-id="679ba-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-551">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-551">Definition</span></span>

<span data-ttu-id="679ba-552">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-553">La expresión regular CEP_Regex_AzureIoTConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-554">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-555">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-557">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-558">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-558">contoso</span></span>
- <span data-ttu-id="679ba-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-559">fabrikam</span></span>
- <span data-ttu-id="679ba-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-560">northwind</span></span>
- <span data-ttu-id="679ba-561">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-561">sandbox</span></span>
- <span data-ttu-id="679ba-562">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-562">onebox</span></span>
- <span data-ttu-id="679ba-563">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-563">localhost</span></span>
- <span data-ttu-id="679ba-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-564">127.0.0.1</span></span>
- <span data-ttu-id="679ba-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-566">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-566">com</span></span>
- <span data-ttu-id="679ba-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-568">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="679ba-569">Contraseña de configuración de publicación de Azure</span><span class="sxs-lookup"><span data-stu-id="679ba-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="679ba-570">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-570">Format</span></span>

<span data-ttu-id="679ba-571">La cadena "userpwd =" seguida de una cadena alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="679ba-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-572">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-572">Pattern</span></span>

- <span data-ttu-id="679ba-573">La cadena "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="679ba-573">The string "userpwd="</span></span>
- <span data-ttu-id="679ba-574">Cualquier combinación de 60 letras minúsculas o dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="679ba-575">Un signo de Comillas (")</span><span class="sxs-lookup"><span data-stu-id="679ba-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-576">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-576">Checksum</span></span>

<span data-ttu-id="679ba-577">No</span><span class="sxs-lookup"><span data-stu-id="679ba-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-578">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-578">Definition</span></span>

<span data-ttu-id="679ba-579">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-580">La expresión regular CEP_Regex_AzurePublishSettingPasswords encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-581">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-582">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-584">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-585">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-585">contoso</span></span>
- <span data-ttu-id="679ba-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-586">fabrikam</span></span>
- <span data-ttu-id="679ba-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-587">northwind</span></span>
- <span data-ttu-id="679ba-588">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-588">sandbox</span></span>
- <span data-ttu-id="679ba-589">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-589">onebox</span></span>
- <span data-ttu-id="679ba-590">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-590">localhost</span></span>
- <span data-ttu-id="679ba-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-591">127.0.0.1</span></span>
- <span data-ttu-id="679ba-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-593">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-593">com</span></span>
- <span data-ttu-id="679ba-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-595">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="679ba-596">Cadena de conexión de la caché de Redis de Azure</span><span class="sxs-lookup"><span data-stu-id="679ba-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="679ba-597">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-597">Format</span></span>

<span data-ttu-id="679ba-598">La cadena "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="679ba-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-599">net "seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="679ba-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-600">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-600">Pattern</span></span>

- <span data-ttu-id="679ba-601">La cadena "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="679ba-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-602">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-602">net"</span></span>
- <span data-ttu-id="679ba-603">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-604">La cadena "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="679ba-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="679ba-605">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-606">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-606">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-607">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-608">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="679ba-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="679ba-609">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-610">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-610">Checksum</span></span>

<span data-ttu-id="679ba-611">No</span><span class="sxs-lookup"><span data-stu-id="679ba-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-612">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-612">Definition</span></span>

<span data-ttu-id="679ba-613">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-614">La expresión regular CEP_Regex_AzureRedisCacheConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="679ba-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="679ba-615">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-616">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-618">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-619">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-619">contoso</span></span>
- <span data-ttu-id="679ba-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-620">fabrikam</span></span>
- <span data-ttu-id="679ba-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-621">northwind</span></span>
- <span data-ttu-id="679ba-622">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-622">sandbox</span></span>
- <span data-ttu-id="679ba-623">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-623">onebox</span></span>
- <span data-ttu-id="679ba-624">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-624">localhost</span></span>
- <span data-ttu-id="679ba-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-625">127.0.0.1</span></span>
- <span data-ttu-id="679ba-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-627">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-627">com</span></span>
- <span data-ttu-id="679ba-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-629">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="679ba-630">ASOCIACIONES de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="679ba-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="679ba-631">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-631">Format</span></span>

<span data-ttu-id="679ba-632">La cadena "SIG" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="679ba-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-633">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-633">Pattern</span></span>

- <span data-ttu-id="679ba-634">La cadena "SIG"</span><span class="sxs-lookup"><span data-stu-id="679ba-634">The string "sig"</span></span>
- <span data-ttu-id="679ba-635">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-636">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-636">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-637">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-638">Cualquier combinación de entre 43-53 caracteres que sean letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="679ba-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="679ba-639">La cadena "% 3D"</span><span class="sxs-lookup"><span data-stu-id="679ba-639">The string "%3d"</span></span>
- <span data-ttu-id="679ba-640">Cualquier carácter que no sea una letra minúscula o mayúscula, un dígito o un signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="679ba-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-641">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-641">Checksum</span></span>

<span data-ttu-id="679ba-642">No</span><span class="sxs-lookup"><span data-stu-id="679ba-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-643">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-643">Definition</span></span>

<span data-ttu-id="679ba-644">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-645">La expresión regular CEP_Regex_AzureSAS encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="679ba-646">Cadena de conexión del bus de servicio de Azure</span><span class="sxs-lookup"><span data-stu-id="679ba-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="679ba-647">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-647">Format</span></span>

<span data-ttu-id="679ba-648">La cadena "EndPoint" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="679ba-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-649">net "y" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="679ba-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-650">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-650">Pattern</span></span>

- <span data-ttu-id="679ba-651">La cadena "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="679ba-651">The string "EndPoint"</span></span>
- <span data-ttu-id="679ba-652">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-653">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-653">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-654">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-655">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-656">La cadena "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="679ba-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-657">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-657">net"</span></span>
- <span data-ttu-id="679ba-658">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-659">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="679ba-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="679ba-660">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-661">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-661">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-662">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-663">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="679ba-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="679ba-664">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-665">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-665">Checksum</span></span>

<span data-ttu-id="679ba-666">No</span><span class="sxs-lookup"><span data-stu-id="679ba-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-667">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-667">Definition</span></span>

<span data-ttu-id="679ba-668">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-669">La expresión regular CEP_Regex_AzureServiceBusConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="679ba-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="679ba-670">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-671">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-673">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-674">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-674">contoso</span></span>
- <span data-ttu-id="679ba-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-675">fabrikam</span></span>
- <span data-ttu-id="679ba-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-676">northwind</span></span>
- <span data-ttu-id="679ba-677">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-677">sandbox</span></span>
- <span data-ttu-id="679ba-678">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-678">onebox</span></span>
- <span data-ttu-id="679ba-679">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-679">localhost</span></span>
- <span data-ttu-id="679ba-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-680">127.0.0.1</span></span>
- <span data-ttu-id="679ba-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-682">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-682">com</span></span>
- <span data-ttu-id="679ba-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-684">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="679ba-685">Clave de cuenta de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="679ba-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="679ba-686">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-686">Format</span></span>

<span data-ttu-id="679ba-687">La cadena "DefaultEndpointsProtocol" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="679ba-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-688">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-688">Pattern</span></span>

- <span data-ttu-id="679ba-689">La cadena "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="679ba-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="679ba-690">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-691">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-691">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-692">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-693">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-694">La cadena "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="679ba-694">The string "AccountKey"</span></span>
- <span data-ttu-id="679ba-695">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-696">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-696">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-697">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="679ba-698">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="679ba-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="679ba-699">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-700">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-700">Checksum</span></span>

<span data-ttu-id="679ba-701">No</span><span class="sxs-lookup"><span data-stu-id="679ba-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-702">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-702">Definition</span></span>

<span data-ttu-id="679ba-703">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-704">La expresión regular CEP_Regex_AzureStorageAccountKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-705">La expresión regular CEP_AzureEmulatorStorageAccountFilter no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-706">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-707">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="679ba-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="679ba-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="679ba-709">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="679ba-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-712">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-713">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-713">contoso</span></span>
- <span data-ttu-id="679ba-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-714">fabrikam</span></span>
- <span data-ttu-id="679ba-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-715">northwind</span></span>
- <span data-ttu-id="679ba-716">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-716">sandbox</span></span>
- <span data-ttu-id="679ba-717">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-717">onebox</span></span>
- <span data-ttu-id="679ba-718">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-718">localhost</span></span>
- <span data-ttu-id="679ba-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-719">127.0.0.1</span></span>
- <span data-ttu-id="679ba-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-721">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-721">com</span></span>
- <span data-ttu-id="679ba-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-723">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="679ba-724">Clave de cuenta de almacenamiento de Azure (Genérico)</span><span class="sxs-lookup"><span data-stu-id="679ba-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-725">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-725">Format</span></span>

<span data-ttu-id="679ba-726">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+), precedido o seguido por los caracteres descritos en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="679ba-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-727">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-727">Pattern</span></span>

- <span data-ttu-id="679ba-728">0-1 del símbolo mayor que (>), apóstrofe ('), signo de igual (=), Comillas (") o almohadilla (#)</span><span class="sxs-lookup"><span data-stu-id="679ba-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="679ba-729">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+)</span><span class="sxs-lookup"><span data-stu-id="679ba-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="679ba-730">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="679ba-731">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-731">Checksum</span></span>

<span data-ttu-id="679ba-732">No</span><span class="sxs-lookup"><span data-stu-id="679ba-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-733">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-733">Definition</span></span>

<span data-ttu-id="679ba-734">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-735">La expresión regular CEP_Regex_AzureStorageAccountKeyGeneric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="679ba-736">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="679ba-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-737">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-737">Format</span></span>

<span data-ttu-id="679ba-738">11 dígitos más delimitadores</span><span class="sxs-lookup"><span data-stu-id="679ba-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-739">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-739">Pattern</span></span>

<span data-ttu-id="679ba-740">11 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="679ba-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="679ba-741">Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="679ba-742">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-742">A hyphen</span></span> 
- <span data-ttu-id="679ba-743">Tres dígitos secuenciales (impares para hombres, pares para mujeres) </span><span class="sxs-lookup"><span data-stu-id="679ba-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="679ba-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="679ba-744">A period</span></span> 
- <span data-ttu-id="679ba-745">Dos dígitos que son un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-746">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-746">Checksum</span></span>

<span data-ttu-id="679ba-747">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-748">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-748">Definition</span></span>

<span data-ttu-id="679ba-749">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-750">La función Func_belgium_national_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-751">Se encuentra una palabra clave de Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="679ba-752">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-753">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="679ba-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="679ba-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="679ba-755">Identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-755">Identity</span></span>
- <span data-ttu-id="679ba-756">Registro</span><span class="sxs-lookup"><span data-stu-id="679ba-756">Registration</span></span>
- <span data-ttu-id="679ba-757">Determinación</span><span class="sxs-lookup"><span data-stu-id="679ba-757">Identification</span></span> 
- <span data-ttu-id="679ba-758">ID</span><span class="sxs-lookup"><span data-stu-id="679ba-758">ID</span></span> 
- <span data-ttu-id="679ba-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="679ba-759">Identiteitskaart</span></span>
- <span data-ttu-id="679ba-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="679ba-760">Registratie nummer</span></span> 
- <span data-ttu-id="679ba-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="679ba-761">Identificatie nummer</span></span> 
- <span data-ttu-id="679ba-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="679ba-762">Identiteit</span></span>
- <span data-ttu-id="679ba-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="679ba-763">Registratie</span></span>
- <span data-ttu-id="679ba-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="679ba-764">Identificatie</span></span> 
- <span data-ttu-id="679ba-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="679ba-765">Carte d’identité</span></span> 
- <span data-ttu-id="679ba-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="679ba-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="679ba-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="679ba-767">numéro d'identification</span></span>
- <span data-ttu-id="679ba-768">identité</span><span class="sxs-lookup"><span data-stu-id="679ba-768">identité</span></span> 
- <span data-ttu-id="679ba-769">indicación</span><span class="sxs-lookup"><span data-stu-id="679ba-769">inscription</span></span> 
- <span data-ttu-id="679ba-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="679ba-770">Identifikation</span></span>
- <span data-ttu-id="679ba-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="679ba-771">Identifizierung</span></span>
- <span data-ttu-id="679ba-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-772">Identifikationsnummer</span></span>
- <span data-ttu-id="679ba-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="679ba-773">Personalausweis</span></span>
- <span data-ttu-id="679ba-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="679ba-774">Registrierung</span></span>
- <span data-ttu-id="679ba-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="679ba-776">Número CPF de Brasil</span><span class="sxs-lookup"><span data-stu-id="679ba-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-777">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-777">Format</span></span>

<span data-ttu-id="679ba-778">11 dígitos incluido un dígito de control y que pueden tener o no formato</span><span class="sxs-lookup"><span data-stu-id="679ba-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-779">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-779">Pattern</span></span>

<span data-ttu-id="679ba-780">Con formato</span><span class="sxs-lookup"><span data-stu-id="679ba-780">Formatted:</span></span>
- <span data-ttu-id="679ba-781">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-781">Three digits</span></span> 
- <span data-ttu-id="679ba-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-782">A period</span></span> 
- <span data-ttu-id="679ba-783">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-783">Three digits</span></span> 
- <span data-ttu-id="679ba-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-784">A period</span></span> 
- <span data-ttu-id="679ba-785">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-785">Three digits</span></span> 
- <span data-ttu-id="679ba-786">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-786">A hyphen</span></span> 
- <span data-ttu-id="679ba-787">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="679ba-787">Two digits which are check digits</span></span>

<span data-ttu-id="679ba-788">Sin formato</span><span class="sxs-lookup"><span data-stu-id="679ba-788">Unformatted:</span></span>
- <span data-ttu-id="679ba-789">11 dígitos, donde los dos últimos dígitos son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="679ba-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-790">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-790">Checksum</span></span>

<span data-ttu-id="679ba-791">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-792">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-792">Definition</span></span>

<span data-ttu-id="679ba-793">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-794">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-795">Se encuentra una palabra clave de Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="679ba-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="679ba-796">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-796">The checksum passes.</span></span>

<span data-ttu-id="679ba-797">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-798">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-799">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-799">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-800">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="679ba-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="679ba-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="679ba-802">CPF</span><span class="sxs-lookup"><span data-stu-id="679ba-802">CPF</span></span>
- <span data-ttu-id="679ba-803">Determinación</span><span class="sxs-lookup"><span data-stu-id="679ba-803">Identification</span></span>
- <span data-ttu-id="679ba-804">Registro</span><span class="sxs-lookup"><span data-stu-id="679ba-804">Registration</span></span>
- <span data-ttu-id="679ba-805">Generar</span><span class="sxs-lookup"><span data-stu-id="679ba-805">Revenue</span></span>
- <span data-ttu-id="679ba-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="679ba-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="679ba-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="679ba-807">Imposto</span></span> 
- <span data-ttu-id="679ba-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="679ba-808">Identificação</span></span> 
- <span data-ttu-id="679ba-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="679ba-809">Inscrição</span></span> 
- <span data-ttu-id="679ba-810">Receita</span><span class="sxs-lookup"><span data-stu-id="679ba-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="679ba-811">Número de entidad jurídica de Brasil (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="679ba-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-812">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-812">Format</span></span>

<span data-ttu-id="679ba-813">14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores</span><span class="sxs-lookup"><span data-stu-id="679ba-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-814">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-814">Pattern</span></span>
<span data-ttu-id="679ba-815">14 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="679ba-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="679ba-816">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-816">Two digits</span></span> 
- <span data-ttu-id="679ba-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-817">A period</span></span> 
- <span data-ttu-id="679ba-818">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-818">Three digits</span></span> 
- <span data-ttu-id="679ba-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-819">A period</span></span> 
- <span data-ttu-id="679ba-820">Tres dígitos (estos ocho primeros dígitos son el número de registro) </span><span class="sxs-lookup"><span data-stu-id="679ba-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="679ba-821">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="679ba-821">A forward slash</span></span> 
- <span data-ttu-id="679ba-822">Número de sucursal de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-822">Four-digit branch number</span></span> 
- <span data-ttu-id="679ba-823">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-823">A hyphen</span></span> 
- <span data-ttu-id="679ba-824">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="679ba-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-825">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-825">Checksum</span></span>

<span data-ttu-id="679ba-826">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-827">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-827">Definition</span></span>

<span data-ttu-id="679ba-828">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-829">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-830">Se encuentra una palabra clave de Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="679ba-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="679ba-831">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-831">The checksum passes.</span></span>

<span data-ttu-id="679ba-832">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-833">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-834">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-834">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-835">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="679ba-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="679ba-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="679ba-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="679ba-837">CNPJ</span></span> 
- <span data-ttu-id="679ba-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="679ba-838">CNPJ/MF</span></span> 
- <span data-ttu-id="679ba-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="679ba-839">CNPJ-MF</span></span> 
- <span data-ttu-id="679ba-840">Registro nacional de entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="679ba-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="679ba-841">Registro de contribuyentes</span><span class="sxs-lookup"><span data-stu-id="679ba-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="679ba-842">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="679ba-842">Legal entity</span></span> 
- <span data-ttu-id="679ba-843">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="679ba-843">Legal entities</span></span> 
- <span data-ttu-id="679ba-844">Estado de registro</span><span class="sxs-lookup"><span data-stu-id="679ba-844">Registration Status</span></span> 
- <span data-ttu-id="679ba-845">Empresa</span><span class="sxs-lookup"><span data-stu-id="679ba-845">Business</span></span> 
- <span data-ttu-id="679ba-846">Company</span><span class="sxs-lookup"><span data-stu-id="679ba-846">Company</span></span>
- <span data-ttu-id="679ba-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="679ba-847">CNPJ</span></span> 
- <span data-ttu-id="679ba-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="679ba-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="679ba-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="679ba-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="679ba-850">CGC</span><span class="sxs-lookup"><span data-stu-id="679ba-850">CGC</span></span> 
- <span data-ttu-id="679ba-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="679ba-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="679ba-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="679ba-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="679ba-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="679ba-853">Situação cadastral</span></span> 
- <span data-ttu-id="679ba-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="679ba-854">Inscrição</span></span> 
- <span data-ttu-id="679ba-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="679ba-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="679ba-856">	Tarjeta de identificación nacional de Brasil (RG)</span><span class="sxs-lookup"><span data-stu-id="679ba-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-857">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-857">Format</span></span>

<span data-ttu-id="679ba-858">Registro geral (formato anterior): nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="679ba-859">Registro de Identidade (RIC) (nuevo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-860">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-860">Pattern</span></span>

<span data-ttu-id="679ba-861">Registro de Geral (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="679ba-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="679ba-862">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-862">Two digits</span></span> 
- <span data-ttu-id="679ba-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-863">A period</span></span> 
- <span data-ttu-id="679ba-864">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-864">Three digits</span></span> 
- <span data-ttu-id="679ba-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-865">A period</span></span> 
- <span data-ttu-id="679ba-866">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-866">Three digits</span></span> 
- <span data-ttu-id="679ba-867">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-867">A hyphen</span></span> 
- <span data-ttu-id="679ba-868">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-868">One digit which is a check digit</span></span>

<span data-ttu-id="679ba-869">Registro de Identidade (RIC) (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="679ba-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="679ba-870">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-870">10 digits</span></span> 
- <span data-ttu-id="679ba-871">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-871">A hyphen</span></span> 
- <span data-ttu-id="679ba-872">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-873">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-873">Checksum</span></span>

<span data-ttu-id="679ba-874">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-875">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-875">Definition</span></span>

<span data-ttu-id="679ba-876">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-877">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-878">Se encuentra una palabra clave de Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="679ba-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="679ba-879">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-879">The checksum passes.</span></span>

<span data-ttu-id="679ba-880">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-881">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-882">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-882">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-883">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="679ba-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="679ba-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="679ba-885">Cédula de Identidade identidad nacional identificador número de rregistro registro de Iidentidade registro Geral RG (esta palabra clave distingue entre mayúsculas y minúsculas) RIC (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="679ba-886">Número de cuenta bancaria de Canadá</span><span class="sxs-lookup"><span data-stu-id="679ba-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-887">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-887">Format</span></span>

<span data-ttu-id="679ba-888">Siete o doce dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-889">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-889">Pattern</span></span>

<span data-ttu-id="679ba-890">El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.</span><span class="sxs-lookup"><span data-stu-id="679ba-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="679ba-891">Un número de tránsito de cuenta bancaria de Canadá es:</span><span class="sxs-lookup"><span data-stu-id="679ba-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="679ba-892">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-892">Five digits</span></span> 
- <span data-ttu-id="679ba-893">Un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-893">A hyphen</span></span> 
- <span data-ttu-id="679ba-894">Tres dígitos o</span><span class="sxs-lookup"><span data-stu-id="679ba-894">Three digits OR</span></span>
- <span data-ttu-id="679ba-895">Un cero "0" </span><span class="sxs-lookup"><span data-stu-id="679ba-895">A zero "0"</span></span> 
- <span data-ttu-id="679ba-896">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-897">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-897">Checksum</span></span>

<span data-ttu-id="679ba-898">No</span><span class="sxs-lookup"><span data-stu-id="679ba-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-899">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-899">Definition</span></span>

<span data-ttu-id="679ba-900">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-901">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-902">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="679ba-903">La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="679ba-904">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-905">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-906">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-907">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="679ba-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="679ba-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="679ba-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="679ba-909">canada savings bonds</span></span>
- <span data-ttu-id="679ba-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="679ba-910">canada revenue agency</span></span>
- <span data-ttu-id="679ba-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="679ba-911">canadian financial institution</span></span>
- <span data-ttu-id="679ba-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="679ba-912">direct deposit form</span></span>
- <span data-ttu-id="679ba-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="679ba-913">canadian citizen</span></span>
- <span data-ttu-id="679ba-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="679ba-914">legal representative</span></span>
- <span data-ttu-id="679ba-915">notary public</span><span class="sxs-lookup"><span data-stu-id="679ba-915">notary public</span></span>
- <span data-ttu-id="679ba-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="679ba-916">commissioner for oaths</span></span>
- <span data-ttu-id="679ba-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="679ba-917">child care benefit</span></span>
- <span data-ttu-id="679ba-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="679ba-918">universal child care</span></span>
- <span data-ttu-id="679ba-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="679ba-919">canada child tax benefit</span></span>
- <span data-ttu-id="679ba-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="679ba-920">income tax benefit</span></span>
- <span data-ttu-id="679ba-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="679ba-921">harmonized sales tax</span></span>
- <span data-ttu-id="679ba-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="679ba-922">social insurance number</span></span>
- <span data-ttu-id="679ba-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="679ba-923">income tax refund</span></span>
- <span data-ttu-id="679ba-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="679ba-924">child tax benefit</span></span>
- <span data-ttu-id="679ba-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="679ba-925">territorial payments</span></span>
- <span data-ttu-id="679ba-926">institution number</span><span class="sxs-lookup"><span data-stu-id="679ba-926">institution number</span></span>
- <span data-ttu-id="679ba-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="679ba-927">deposit request</span></span>
- <span data-ttu-id="679ba-928">banking information</span><span class="sxs-lookup"><span data-stu-id="679ba-928">banking information</span></span>
- <span data-ttu-id="679ba-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="679ba-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="679ba-930">Número de licencia de conductor de Canadá</span><span class="sxs-lookup"><span data-stu-id="679ba-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-931">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-931">Format</span></span>

<span data-ttu-id="679ba-932">Varía según la provincia</span><span class="sxs-lookup"><span data-stu-id="679ba-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-933">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-933">Pattern</span></span>

<span data-ttu-id="679ba-934">Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="679ba-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-935">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-935">Checksum</span></span>

<span data-ttu-id="679ba-936">No</span><span class="sxs-lookup"><span data-stu-id="679ba-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-937">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-937">Definition</span></span>

<span data-ttu-id="679ba-938">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-939">La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-940">Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="679ba-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="679ba-941">Se encuentra una palabra clave de Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="679ba-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-942">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="679ba-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="679ba-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="679ba-944">La abreviatura de la provincia, por ejemplo, AB</span><span class="sxs-lookup"><span data-stu-id="679ba-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="679ba-945">El nombre de la provincia, por ejemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="679ba-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="679ba-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="679ba-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="679ba-947">LISTAS</span><span class="sxs-lookup"><span data-stu-id="679ba-947">DL</span></span>
- <span data-ttu-id="679ba-948">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="679ba-948">DLS</span></span>
- <span data-ttu-id="679ba-949">CDL</span><span class="sxs-lookup"><span data-stu-id="679ba-949">CDL</span></span>
- <span data-ttu-id="679ba-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="679ba-950">CDLS</span></span>
- <span data-ttu-id="679ba-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="679ba-951">DriverLic</span></span>
- <span data-ttu-id="679ba-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="679ba-952">DriverLics</span></span>
- <span data-ttu-id="679ba-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-953">DriverLicense</span></span>
- <span data-ttu-id="679ba-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-954">DriverLicenses</span></span>
- <span data-ttu-id="679ba-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="679ba-955">DriverLicence</span></span>
- <span data-ttu-id="679ba-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="679ba-956">DriverLicences</span></span>
- <span data-ttu-id="679ba-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-957">Driver Lic</span></span>
- <span data-ttu-id="679ba-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-958">Driver Lics</span></span>
- <span data-ttu-id="679ba-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="679ba-959">Driver License</span></span>
- <span data-ttu-id="679ba-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-960">Driver Licenses</span></span>
- <span data-ttu-id="679ba-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-961">Driver Licence</span></span>
- <span data-ttu-id="679ba-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-962">Driver Licences</span></span>
- <span data-ttu-id="679ba-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="679ba-963">DriversLic</span></span>
- <span data-ttu-id="679ba-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="679ba-964">DriversLics</span></span>
- <span data-ttu-id="679ba-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="679ba-965">DriversLicence</span></span>
- <span data-ttu-id="679ba-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="679ba-966">DriversLicences</span></span>
- <span data-ttu-id="679ba-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-967">DriversLicense</span></span>
- <span data-ttu-id="679ba-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-968">DriversLicenses</span></span>
- <span data-ttu-id="679ba-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-969">Drivers Lic</span></span>
- <span data-ttu-id="679ba-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-970">Drivers Lics</span></span>
- <span data-ttu-id="679ba-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="679ba-971">Drivers License</span></span>
- <span data-ttu-id="679ba-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-972">Drivers Licenses</span></span>
- <span data-ttu-id="679ba-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-973">Drivers Licence</span></span>
- <span data-ttu-id="679ba-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-974">Drivers Licences</span></span>
- <span data-ttu-id="679ba-975">N.º carné</span><span class="sxs-lookup"><span data-stu-id="679ba-975">Driver'Lic</span></span>
- <span data-ttu-id="679ba-976">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="679ba-976">Driver'Lics</span></span>
- <span data-ttu-id="679ba-977">Conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-977">Driver'License</span></span>
- <span data-ttu-id="679ba-978">Conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-978">Driver'Licenses</span></span>
- <span data-ttu-id="679ba-979">N.º carné</span><span class="sxs-lookup"><span data-stu-id="679ba-979">Driver'Licence</span></span>
- <span data-ttu-id="679ba-980">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="679ba-980">Driver'Licences</span></span>
- <span data-ttu-id="679ba-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-981">Driver' Lic</span></span>
- <span data-ttu-id="679ba-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-982">Driver' Lics</span></span>
- <span data-ttu-id="679ba-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="679ba-983">Driver' License</span></span>
- <span data-ttu-id="679ba-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-984">Driver' Licenses</span></span>
- <span data-ttu-id="679ba-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-985">Driver' Licence</span></span>
- <span data-ttu-id="679ba-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-986">Driver' Licences</span></span>
- <span data-ttu-id="679ba-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="679ba-987">Driver'sLic</span></span>
- <span data-ttu-id="679ba-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="679ba-988">Driver'sLics</span></span>
- <span data-ttu-id="679ba-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-989">Driver'sLicense</span></span>
- <span data-ttu-id="679ba-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-990">Driver'sLicenses</span></span>
- <span data-ttu-id="679ba-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="679ba-991">Driver'sLicence</span></span>
- <span data-ttu-id="679ba-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="679ba-992">Driver'sLicences</span></span>
- <span data-ttu-id="679ba-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-993">Driver's Lic</span></span>
- <span data-ttu-id="679ba-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-994">Driver's Lics</span></span>
- <span data-ttu-id="679ba-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="679ba-995">Driver's License</span></span>
- <span data-ttu-id="679ba-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-996">Driver's Licenses</span></span>
- <span data-ttu-id="679ba-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-997">Driver's Licence</span></span>
- <span data-ttu-id="679ba-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-998">Driver's Licences</span></span>
- <span data-ttu-id="679ba-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="679ba-999">Permis de Conduire</span></span>
- <span data-ttu-id="679ba-1000">id</span><span class="sxs-lookup"><span data-stu-id="679ba-1000">id</span></span>
- <span data-ttu-id="679ba-1001">ids</span><span class="sxs-lookup"><span data-stu-id="679ba-1001">ids</span></span>
- <span data-ttu-id="679ba-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="679ba-1002">idcard number</span></span>
- <span data-ttu-id="679ba-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-1003">idcard numbers</span></span>
- <span data-ttu-id="679ba-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="679ba-1004">idcard #</span></span>
- <span data-ttu-id="679ba-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="679ba-1005">idcard #s</span></span>
- <span data-ttu-id="679ba-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="679ba-1006">idcard card</span></span>
- <span data-ttu-id="679ba-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1007">idcard cards</span></span>
- <span data-ttu-id="679ba-1008">tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1008">idcard</span></span>
- <span data-ttu-id="679ba-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="679ba-1009">identification number</span></span>
- <span data-ttu-id="679ba-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-1010">identification numbers</span></span>
- <span data-ttu-id="679ba-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="679ba-1011">identification #</span></span>
- <span data-ttu-id="679ba-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="679ba-1012">identification #s</span></span>
- <span data-ttu-id="679ba-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="679ba-1013">identification card</span></span>
- <span data-ttu-id="679ba-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1014">identification cards</span></span>
- <span data-ttu-id="679ba-1015">determinación</span><span class="sxs-lookup"><span data-stu-id="679ba-1015">identification</span></span> 
- <span data-ttu-id="679ba-1016">LISTAS #</span><span class="sxs-lookup"><span data-stu-id="679ba-1016">DL#</span></span>
- <span data-ttu-id="679ba-1017">DISTRIBUCIÓN #</span><span class="sxs-lookup"><span data-stu-id="679ba-1017">DLS#</span></span> 
- <span data-ttu-id="679ba-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="679ba-1018">CDL#</span></span> 
- <span data-ttu-id="679ba-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="679ba-1019">CDLS#</span></span> 
- <span data-ttu-id="679ba-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-1020">DriverLic#</span></span> 
- <span data-ttu-id="679ba-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-1021">DriverLics#</span></span> 
- <span data-ttu-id="679ba-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-1022">DriverLicense#</span></span> 
- <span data-ttu-id="679ba-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="679ba-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="679ba-1024">DriverLicence#</span></span> 
- <span data-ttu-id="679ba-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="679ba-1025">DriverLicences#</span></span> 
- <span data-ttu-id="679ba-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-1026">Driver Lic#</span></span>
- <span data-ttu-id="679ba-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-1027">Driver Lics#</span></span> 
- <span data-ttu-id="679ba-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="679ba-1028">Driver License#</span></span> 
- <span data-ttu-id="679ba-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="679ba-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="679ba-1030">Driver License#</span></span> 
- <span data-ttu-id="679ba-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-1031">Driver Licences#</span></span> 
- <span data-ttu-id="679ba-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-1032">DriversLic#</span></span> 
- <span data-ttu-id="679ba-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-1033">DriversLics#</span></span> 
- <span data-ttu-id="679ba-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-1034">DriversLicense#</span></span> 
- <span data-ttu-id="679ba-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="679ba-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="679ba-1036">DriversLicence#</span></span> 
- <span data-ttu-id="679ba-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="679ba-1037">DriversLicences#</span></span> 
- <span data-ttu-id="679ba-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="679ba-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="679ba-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="679ba-1040">Drivers License#</span></span> 
- <span data-ttu-id="679ba-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="679ba-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="679ba-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="679ba-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="679ba-1044">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="679ba-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="679ba-1045">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="679ba-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="679ba-1046">Conducción #</span><span class="sxs-lookup"><span data-stu-id="679ba-1046">Driver'License#</span></span> 
- <span data-ttu-id="679ba-1047">Conducción #</span><span class="sxs-lookup"><span data-stu-id="679ba-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="679ba-1048">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="679ba-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="679ba-1049">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="679ba-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="679ba-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="679ba-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="679ba-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="679ba-1052">Driver' License#</span></span> 
- <span data-ttu-id="679ba-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="679ba-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="679ba-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="679ba-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="679ba-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="679ba-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="679ba-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="679ba-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="679ba-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="679ba-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="679ba-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="679ba-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="679ba-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="679ba-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="679ba-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="679ba-1064">Driver's License#</span></span> 
- <span data-ttu-id="679ba-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="679ba-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="679ba-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="679ba-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="679ba-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="679ba-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="679ba-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="679ba-1069">identificador #</span><span class="sxs-lookup"><span data-stu-id="679ba-1069">id#</span></span> 
- <span data-ttu-id="679ba-1070">falta #</span><span class="sxs-lookup"><span data-stu-id="679ba-1070">ids#</span></span> 
- <span data-ttu-id="679ba-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="679ba-1071">idcard card#</span></span> 
- <span data-ttu-id="679ba-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="679ba-1072">idcard cards#</span></span> 
- <span data-ttu-id="679ba-1073">tarjeta #</span><span class="sxs-lookup"><span data-stu-id="679ba-1073">idcard#</span></span> 
- <span data-ttu-id="679ba-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="679ba-1074">identification card#</span></span> 
- <span data-ttu-id="679ba-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="679ba-1075">identification cards#</span></span> 
- <span data-ttu-id="679ba-1076">determinación #</span><span class="sxs-lookup"><span data-stu-id="679ba-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="679ba-1077">Número de servicio de salud de Canadá</span><span class="sxs-lookup"><span data-stu-id="679ba-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1078">Format</span></span>

<span data-ttu-id="679ba-1079">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1080">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1080">Pattern</span></span>

<span data-ttu-id="679ba-1081">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1082">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1082">Checksum</span></span>

<span data-ttu-id="679ba-1083">No</span><span class="sxs-lookup"><span data-stu-id="679ba-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1084">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1084">Definition</span></span>

<span data-ttu-id="679ba-1085">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1086">La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1087">Se encuentra una palabra clave de Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1088">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="679ba-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="679ba-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="679ba-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="679ba-1090">personal health number</span></span>
- <span data-ttu-id="679ba-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="679ba-1091">patient information</span></span>
- <span data-ttu-id="679ba-1092">health services</span><span class="sxs-lookup"><span data-stu-id="679ba-1092">health services</span></span>
- <span data-ttu-id="679ba-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="679ba-1093">speciality services</span></span>
- <span data-ttu-id="679ba-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="679ba-1094">automobile accident</span></span>
- <span data-ttu-id="679ba-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="679ba-1095">patient hospital</span></span>
- <span data-ttu-id="679ba-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="679ba-1096">psychiatrist</span></span>
- <span data-ttu-id="679ba-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="679ba-1097">workers compensation</span></span>
- <span data-ttu-id="679ba-1098">discapacidad</span><span class="sxs-lookup"><span data-stu-id="679ba-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="679ba-1099">Número de pasaporte de Canadá</span><span class="sxs-lookup"><span data-stu-id="679ba-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1100">Format</span></span>

<span data-ttu-id="679ba-1101">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1102">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1102">Pattern</span></span>

<span data-ttu-id="679ba-1103">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1104">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1104">Checksum</span></span>

<span data-ttu-id="679ba-1105">No</span><span class="sxs-lookup"><span data-stu-id="679ba-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1106">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1106">Definition</span></span>

<span data-ttu-id="679ba-1107">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1108">La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1109">Se encuentra una palabra clave de Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="679ba-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
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

### <a name="keywords"></a><span data-ttu-id="679ba-1110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="679ba-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="679ba-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="679ba-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="679ba-1112">canadian citizenship</span></span>
- <span data-ttu-id="679ba-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="679ba-1113">canadian passport</span></span>
- <span data-ttu-id="679ba-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="679ba-1114">passport application</span></span>
- <span data-ttu-id="679ba-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="679ba-1115">passport photos</span></span>
- <span data-ttu-id="679ba-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="679ba-1116">certified translator</span></span>
- <span data-ttu-id="679ba-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="679ba-1117">canadian citizens</span></span>
- <span data-ttu-id="679ba-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="679ba-1118">processing times</span></span>
- <span data-ttu-id="679ba-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="679ba-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="679ba-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-1120">Keyword_passport</span></span>

- <span data-ttu-id="679ba-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="679ba-1121">Passport Number</span></span>
- <span data-ttu-id="679ba-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="679ba-1122">Passport No</span></span>
- <span data-ttu-id="679ba-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="679ba-1123">Passport #</span></span>
- <span data-ttu-id="679ba-1124">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="679ba-1124">Passport#</span></span>
- <span data-ttu-id="679ba-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="679ba-1125">PassportID</span></span>
- <span data-ttu-id="679ba-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="679ba-1126">Passportno</span></span>
- <span data-ttu-id="679ba-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-1127">passportnumber</span></span>
- <span data-ttu-id="679ba-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="679ba-1128">パスポート</span></span>
- <span data-ttu-id="679ba-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="679ba-1129">パスポート番号</span></span>
- <span data-ttu-id="679ba-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="679ba-1130">パスポートのNum</span></span>
- <span data-ttu-id="679ba-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="679ba-1131">パスポート＃</span></span>
- <span data-ttu-id="679ba-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="679ba-1132">Numéro de passeport</span></span>
- <span data-ttu-id="679ba-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="679ba-1133">Passeport n °</span></span>
- <span data-ttu-id="679ba-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="679ba-1134">Passeport Non</span></span>
- <span data-ttu-id="679ba-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-1135">Passeport #</span></span>
- <span data-ttu-id="679ba-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-1136">Passeport#</span></span>
- <span data-ttu-id="679ba-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="679ba-1137">PasseportNon</span></span>
- <span data-ttu-id="679ba-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="679ba-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="679ba-1139">Número de Identificación Personal de salud en Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="679ba-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1140">Format</span></span>

<span data-ttu-id="679ba-1141">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1142">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1142">Pattern</span></span>

<span data-ttu-id="679ba-1143">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1144">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1144">Checksum</span></span>

<span data-ttu-id="679ba-1145">No</span><span class="sxs-lookup"><span data-stu-id="679ba-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1146">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1146">Definition</span></span>

<span data-ttu-id="679ba-1147">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="679ba-1148">Se encuentran al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="679ba-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="679ba-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="679ba-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="679ba-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="679ba-1151">social insurance number</span></span>
- <span data-ttu-id="679ba-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="679ba-1152">health information act</span></span>
- <span data-ttu-id="679ba-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="679ba-1153">income tax information</span></span>
- <span data-ttu-id="679ba-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="679ba-1154">manitoba health</span></span>
- <span data-ttu-id="679ba-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="679ba-1155">health registration</span></span>
- <span data-ttu-id="679ba-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="679ba-1156">prescription purchases</span></span>
- <span data-ttu-id="679ba-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="679ba-1157">benefit eligibility</span></span>
- <span data-ttu-id="679ba-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="679ba-1158">personal health</span></span>
- <span data-ttu-id="679ba-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="679ba-1159">power of attorney</span></span>
- <span data-ttu-id="679ba-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="679ba-1160">registration number</span></span>
- <span data-ttu-id="679ba-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="679ba-1161">personal health number</span></span>
- <span data-ttu-id="679ba-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="679ba-1162">practitioner referral</span></span>
- <span data-ttu-id="679ba-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="679ba-1163">wellness professional</span></span>
- <span data-ttu-id="679ba-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="679ba-1164">patient referral</span></span>
- <span data-ttu-id="679ba-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="679ba-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="679ba-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="679ba-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="679ba-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="679ba-1167">Nunavut</span></span>
- <span data-ttu-id="679ba-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="679ba-1168">Quebec</span></span>
- <span data-ttu-id="679ba-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="679ba-1169">Northwest Territories</span></span>
- <span data-ttu-id="679ba-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="679ba-1170">Ontario</span></span>
- <span data-ttu-id="679ba-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="679ba-1171">British Columbia</span></span>
- <span data-ttu-id="679ba-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="679ba-1172">Alberta</span></span>
- <span data-ttu-id="679ba-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="679ba-1173">Saskatchewan</span></span>
- <span data-ttu-id="679ba-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="679ba-1174">Manitoba</span></span>
- <span data-ttu-id="679ba-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="679ba-1175">Yukon</span></span>
- <span data-ttu-id="679ba-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="679ba-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="679ba-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="679ba-1177">New Brunswick</span></span>
- <span data-ttu-id="679ba-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="679ba-1178">Nova Scotia</span></span>
- <span data-ttu-id="679ba-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="679ba-1179">Prince Edward Island</span></span>
- <span data-ttu-id="679ba-1180">Canadá</span><span class="sxs-lookup"><span data-stu-id="679ba-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="679ba-1181">Número de seguridad social de Canadá</span><span class="sxs-lookup"><span data-stu-id="679ba-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1182">Format</span></span>

<span data-ttu-id="679ba-1183">Nueve dígitos con guiones opcionales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1184">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1184">Pattern</span></span>

<span data-ttu-id="679ba-1185">Con formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1185">Formatted:</span></span>
- <span data-ttu-id="679ba-1186">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1186">Three digits</span></span> 
- <span data-ttu-id="679ba-1187">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="679ba-1187">A hyphen or space</span></span> 
- <span data-ttu-id="679ba-1188">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1188">Three digits</span></span> 
- <span data-ttu-id="679ba-1189">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="679ba-1189">A hyphen or space</span></span> 
- <span data-ttu-id="679ba-1190">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1190">Three digits</span></span>

<span data-ttu-id="679ba-1191">Sin formato: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1192">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1192">Checksum</span></span>

<span data-ttu-id="679ba-1193">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1194">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1194">Definition</span></span>

<span data-ttu-id="679ba-1195">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1196">La función Func_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1197">Al menos dos de cualquier combinación de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="679ba-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="679ba-1198">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="679ba-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="679ba-1199">Se encuentra una palabra clave de Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="679ba-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="679ba-1200">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-1201">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1201">The checksum passes.</span></span>

<span data-ttu-id="679ba-1202">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1203">La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1204">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="679ba-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="679ba-1205">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1205">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1206">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="679ba-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="679ba-1207">Keyword_sin</span></span>

- <span data-ttu-id="679ba-1208">sin</span><span class="sxs-lookup"><span data-stu-id="679ba-1208">sin</span></span> 
- <span data-ttu-id="679ba-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="679ba-1209">social insurance</span></span> 
- <span data-ttu-id="679ba-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="679ba-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="679ba-1211">pecados</span><span class="sxs-lookup"><span data-stu-id="679ba-1211">sins</span></span> 
- <span data-ttu-id="679ba-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="679ba-1212">ssn</span></span> 
- <span data-ttu-id="679ba-1213">SSN</span><span class="sxs-lookup"><span data-stu-id="679ba-1213">ssns</span></span> 
- <span data-ttu-id="679ba-1214">social security</span><span class="sxs-lookup"><span data-stu-id="679ba-1214">social security</span></span> 
- <span data-ttu-id="679ba-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="679ba-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="679ba-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="679ba-1216">national identification number</span></span> 
- <span data-ttu-id="679ba-1217">national id</span><span class="sxs-lookup"><span data-stu-id="679ba-1217">national id</span></span> 
- <span data-ttu-id="679ba-1218">PIN #</span><span class="sxs-lookup"><span data-stu-id="679ba-1218">sin#</span></span> 
- <span data-ttu-id="679ba-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="679ba-1219">soc ins</span></span> 
- <span data-ttu-id="679ba-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="679ba-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="679ba-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="679ba-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="679ba-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="679ba-1222">driver's license</span></span> 
- <span data-ttu-id="679ba-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="679ba-1223">drivers license</span></span> 
- <span data-ttu-id="679ba-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="679ba-1224">driver's licence</span></span> 
- <span data-ttu-id="679ba-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="679ba-1225">drivers licence</span></span> 
- <span data-ttu-id="679ba-1226">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="679ba-1226">DOB</span></span> 
- <span data-ttu-id="679ba-1227">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-1227">Birthdate</span></span> 
- <span data-ttu-id="679ba-1228">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="679ba-1228">Birthday</span></span> 
- <span data-ttu-id="679ba-1229">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="679ba-1230">	Número de tarjeta de identidad de Chile</span><span class="sxs-lookup"><span data-stu-id="679ba-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1231">Format</span></span>

<span data-ttu-id="679ba-1232">7-8 dígitos más delimitadores, un dígito de control o una letra</span><span class="sxs-lookup"><span data-stu-id="679ba-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1233">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1233">Pattern</span></span>

<span data-ttu-id="679ba-1234">7 u 8 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="679ba-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="679ba-1235">1 o 2 dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-1235">1-2 digits</span></span> 
- <span data-ttu-id="679ba-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-1236">A period</span></span> 
- <span data-ttu-id="679ba-1237">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1237">Three digits</span></span> 
- <span data-ttu-id="679ba-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="679ba-1238">A period</span></span> 
- <span data-ttu-id="679ba-1239">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1239">Three digits</span></span> 
- <span data-ttu-id="679ba-1240">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-1240">A dash</span></span> 
- <span data-ttu-id="679ba-1241">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1242">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1242">Checksum</span></span>

<span data-ttu-id="679ba-1243">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1244">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1244">Definition</span></span>

<span data-ttu-id="679ba-1245">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1246">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1247">Se encuentra una palabra clave de Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="679ba-1248">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1248">The checksum passes.</span></span>

<span data-ttu-id="679ba-1249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1250">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1251">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1251">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="679ba-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="679ba-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="679ba-1254">Número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="679ba-1254">National Identification Number</span></span> 
- <span data-ttu-id="679ba-1255">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-1255">Identity card</span></span> 
- <span data-ttu-id="679ba-1256">ID</span><span class="sxs-lookup"><span data-stu-id="679ba-1256">ID</span></span> 
- <span data-ttu-id="679ba-1257">Determinación</span><span class="sxs-lookup"><span data-stu-id="679ba-1257">Identification</span></span> 
- <span data-ttu-id="679ba-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="679ba-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="679ba-1259">REALIZAR</span><span class="sxs-lookup"><span data-stu-id="679ba-1259">RUN</span></span> 
- <span data-ttu-id="679ba-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="679ba-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="679ba-1261">ESTANCARSE</span><span class="sxs-lookup"><span data-stu-id="679ba-1261">RUT</span></span> 
- <span data-ttu-id="679ba-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="679ba-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="679ba-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="679ba-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="679ba-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="679ba-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="679ba-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="679ba-1266">	Número de tarjeta de identidad de residente de China (PRC)</span><span class="sxs-lookup"><span data-stu-id="679ba-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1267">Format</span></span>

<span data-ttu-id="679ba-1268">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1269">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1269">Pattern</span></span>

<span data-ttu-id="679ba-1270">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-1270">18 digits:</span></span>
- <span data-ttu-id="679ba-1271">Seis dígitos que son un código de dirección </span><span class="sxs-lookup"><span data-stu-id="679ba-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="679ba-1272">Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="679ba-1273">Tres dígitos que son un código de pedido </span><span class="sxs-lookup"><span data-stu-id="679ba-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="679ba-1274">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1275">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1275">Checksum</span></span>

<span data-ttu-id="679ba-1276">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1277">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1277">Definition</span></span>

<span data-ttu-id="679ba-1278">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1279">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1280">Se encuentra una palabra clave de Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="679ba-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="679ba-1281">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1281">The checksum passes.</span></span>

<span data-ttu-id="679ba-1282">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1283">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1284">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1284">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1285">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="679ba-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="679ba-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="679ba-1287">Tarjeta de identidad de residente</span><span class="sxs-lookup"><span data-stu-id="679ba-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="679ba-1288">China</span><span class="sxs-lookup"><span data-stu-id="679ba-1288">PRC</span></span> 
- <span data-ttu-id="679ba-1289">Tarjeta de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="679ba-1289">National Identification Card</span></span> 
- <span data-ttu-id="679ba-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="679ba-1290">身份证</span></span> 
- <span data-ttu-id="679ba-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="679ba-1291">居民 身份证</span></span> 
- <span data-ttu-id="679ba-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="679ba-1292">居民身份证</span></span> 
- <span data-ttu-id="679ba-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="679ba-1293">鉴定</span></span> 
- <span data-ttu-id="679ba-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-1294">身分證</span></span> 
- <span data-ttu-id="679ba-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-1295">居民 身份證</span></span>
- <span data-ttu-id="679ba-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="679ba-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="679ba-1297">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1298">Format</span></span>

<span data-ttu-id="679ba-1299">16 dígitos que pueden ser formateados o sin formato (dddddddddddddddd) y deben pasar la prueba Luhn.</span><span class="sxs-lookup"><span data-stu-id="679ba-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1300">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1300">Pattern</span></span>

<span data-ttu-id="679ba-1301">Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.</span><span class="sxs-lookup"><span data-stu-id="679ba-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1302">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1302">Checksum</span></span>

<span data-ttu-id="679ba-1303">Sí, la suma de comprobación de Luhn</span><span class="sxs-lookup"><span data-stu-id="679ba-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1304">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1304">Definition</span></span>

<span data-ttu-id="679ba-1305">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1306">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1307">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-1307">One of the following is true:</span></span>
    - <span data-ttu-id="679ba-1308">Se encuentra una palabra clave de Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="679ba-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="679ba-1309">Se encuentra una palabra clave de Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="679ba-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="679ba-1310">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-1311">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1311">The checksum passes.</span></span>

<span data-ttu-id="679ba-1312">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1313">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1314">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1314">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="679ba-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="679ba-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="679ba-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="679ba-1317">card verification</span></span>
- <span data-ttu-id="679ba-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="679ba-1318">card identification number</span></span>
- <span data-ttu-id="679ba-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="679ba-1319">cvn</span></span>
- <span data-ttu-id="679ba-1320">cid</span><span class="sxs-lookup"><span data-stu-id="679ba-1320">cid</span></span>
- <span data-ttu-id="679ba-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="679ba-1321">cvc2</span></span>
- <span data-ttu-id="679ba-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="679ba-1322">cvv2</span></span>
- <span data-ttu-id="679ba-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="679ba-1323">pin block</span></span>
- <span data-ttu-id="679ba-1324">security code</span><span class="sxs-lookup"><span data-stu-id="679ba-1324">security code</span></span>
- <span data-ttu-id="679ba-1325">security number</span><span class="sxs-lookup"><span data-stu-id="679ba-1325">security number</span></span>
- <span data-ttu-id="679ba-1326">security no</span><span class="sxs-lookup"><span data-stu-id="679ba-1326">security no</span></span>
- <span data-ttu-id="679ba-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="679ba-1327">issue number</span></span>
- <span data-ttu-id="679ba-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="679ba-1328">issue no</span></span>
- <span data-ttu-id="679ba-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="679ba-1329">cryptogramme</span></span>
- <span data-ttu-id="679ba-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="679ba-1330">numéro de sécurité</span></span>
- <span data-ttu-id="679ba-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="679ba-1331">numero de securite</span></span>
- <span data-ttu-id="679ba-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="679ba-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="679ba-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="679ba-1334">prüfziffer</span></span>
- <span data-ttu-id="679ba-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="679ba-1335">prufziffer</span></span>
- <span data-ttu-id="679ba-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="679ba-1336">sicherheits Kode</span></span>
- <span data-ttu-id="679ba-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="679ba-1337">sicherheitscode</span></span>
- <span data-ttu-id="679ba-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="679ba-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="679ba-1339">verfalldatum</span></span>
- <span data-ttu-id="679ba-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="679ba-1340">codice di verifica</span></span>
- <span data-ttu-id="679ba-1341">COD.</span><span class="sxs-lookup"><span data-stu-id="679ba-1341">cod.</span></span> <span data-ttu-id="679ba-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="679ba-1342">sicurezza</span></span>
- <span data-ttu-id="679ba-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="679ba-1343">cod sicurezza</span></span>
- <span data-ttu-id="679ba-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="679ba-1344">n autorizzazione</span></span>
- <span data-ttu-id="679ba-1345">Código</span><span class="sxs-lookup"><span data-stu-id="679ba-1345">código</span></span>
- <span data-ttu-id="679ba-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="679ba-1346">codigo</span></span>
- <span data-ttu-id="679ba-1347">COD.</span><span class="sxs-lookup"><span data-stu-id="679ba-1347">cod.</span></span> <span data-ttu-id="679ba-1348">seg</span><span class="sxs-lookup"><span data-stu-id="679ba-1348">seg</span></span>
- <span data-ttu-id="679ba-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="679ba-1349">cod seg</span></span>
- <span data-ttu-id="679ba-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1350">código de segurança</span></span>
- <span data-ttu-id="679ba-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1351">codigo de seguranca</span></span>
- <span data-ttu-id="679ba-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1352">codigo de segurança</span></span>
- <span data-ttu-id="679ba-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1353">código de seguranca</span></span>
- <span data-ttu-id="679ba-1354">campos.</span><span class="sxs-lookup"><span data-stu-id="679ba-1354">cód.</span></span> <span data-ttu-id="679ba-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1355">segurança</span></span>
- <span data-ttu-id="679ba-1356">COD.</span><span class="sxs-lookup"><span data-stu-id="679ba-1356">cod.</span></span> <span data-ttu-id="679ba-1357">DQO SEGURANCA.</span><span class="sxs-lookup"><span data-stu-id="679ba-1357">seguranca cod.</span></span> <span data-ttu-id="679ba-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1358">segurança</span></span>
- <span data-ttu-id="679ba-1359">campos.</span><span class="sxs-lookup"><span data-stu-id="679ba-1359">cód.</span></span> <span data-ttu-id="679ba-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1360">seguranca</span></span>
- <span data-ttu-id="679ba-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1361">cód segurança</span></span>
- <span data-ttu-id="679ba-1362">Bacalao SEGURANCA contra reembolso de segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="679ba-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1363">cód seguranca</span></span>
- <span data-ttu-id="679ba-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="679ba-1364">número de verificação</span></span>
- <span data-ttu-id="679ba-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="679ba-1365">numero de verificacao</span></span>
- <span data-ttu-id="679ba-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="679ba-1366">ablauf</span></span>
- <span data-ttu-id="679ba-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="679ba-1367">gültig bis</span></span>
- <span data-ttu-id="679ba-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="679ba-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="679ba-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="679ba-1369">gultig bis</span></span>
- <span data-ttu-id="679ba-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="679ba-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="679ba-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="679ba-1371">scadenza</span></span>
- <span data-ttu-id="679ba-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="679ba-1372">data scad</span></span>
- <span data-ttu-id="679ba-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="679ba-1373">fecha de expiracion</span></span>
- <span data-ttu-id="679ba-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="679ba-1374">fecha de venc</span></span>
- <span data-ttu-id="679ba-1375">1er</span><span class="sxs-lookup"><span data-stu-id="679ba-1375">vencimiento</span></span>
- <span data-ttu-id="679ba-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="679ba-1376">válido hasta</span></span>
- <span data-ttu-id="679ba-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="679ba-1377">valido hasta</span></span>
- <span data-ttu-id="679ba-1378">vto</span><span class="sxs-lookup"><span data-stu-id="679ba-1378">vto</span></span>
- <span data-ttu-id="679ba-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="679ba-1379">data de expiração</span></span>
- <span data-ttu-id="679ba-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="679ba-1380">data de expiracao</span></span>
- <span data-ttu-id="679ba-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="679ba-1381">data em que expira</span></span>
- <span data-ttu-id="679ba-1382">validade</span><span class="sxs-lookup"><span data-stu-id="679ba-1382">validade</span></span>
- <span data-ttu-id="679ba-1383">valorar</span><span class="sxs-lookup"><span data-stu-id="679ba-1383">valor</span></span>
- <span data-ttu-id="679ba-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="679ba-1384">vencimento</span></span>
- <span data-ttu-id="679ba-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="679ba-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="679ba-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="679ba-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="679ba-1387">AMEX</span><span class="sxs-lookup"><span data-stu-id="679ba-1387">amex</span></span>
- <span data-ttu-id="679ba-1388">american express</span><span class="sxs-lookup"><span data-stu-id="679ba-1388">american express</span></span>
- <span data-ttu-id="679ba-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="679ba-1389">americanexpress</span></span>
- <span data-ttu-id="679ba-1390">Régimen</span><span class="sxs-lookup"><span data-stu-id="679ba-1390">Visa</span></span>
- <span data-ttu-id="679ba-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="679ba-1391">mastercard</span></span>
- <span data-ttu-id="679ba-1392">master card</span><span class="sxs-lookup"><span data-stu-id="679ba-1392">master card</span></span>
- <span data-ttu-id="679ba-1393">valuación</span><span class="sxs-lookup"><span data-stu-id="679ba-1393">mc</span></span> 
- <span data-ttu-id="679ba-1394">MasterCard</span><span class="sxs-lookup"><span data-stu-id="679ba-1394">mastercards</span></span>
- <span data-ttu-id="679ba-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1395">master cards</span></span>
- <span data-ttu-id="679ba-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="679ba-1396">diner's Club</span></span>
- <span data-ttu-id="679ba-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="679ba-1397">diners club</span></span>
- <span data-ttu-id="679ba-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="679ba-1398">dinersclub</span></span>
- <span data-ttu-id="679ba-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="679ba-1399">discover card</span></span>
- <span data-ttu-id="679ba-1400">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1400">discovercard</span></span>
- <span data-ttu-id="679ba-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1401">discover cards</span></span>
- <span data-ttu-id="679ba-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="679ba-1402">JCB</span></span>
- <span data-ttu-id="679ba-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="679ba-1403">japanese card bureau</span></span>
- <span data-ttu-id="679ba-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="679ba-1404">carte blanche</span></span>
- <span data-ttu-id="679ba-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="679ba-1405">carteblanche</span></span>
- <span data-ttu-id="679ba-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="679ba-1406">credit card</span></span>
- <span data-ttu-id="679ba-1407">CC #</span><span class="sxs-lookup"><span data-stu-id="679ba-1407">cc#</span></span>
- <span data-ttu-id="679ba-1408"># CC:</span><span class="sxs-lookup"><span data-stu-id="679ba-1408">cc#:</span></span>
- <span data-ttu-id="679ba-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="679ba-1409">expiration date</span></span>
- <span data-ttu-id="679ba-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="679ba-1410">exp date</span></span>
- <span data-ttu-id="679ba-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="679ba-1411">expiry date</span></span>
- <span data-ttu-id="679ba-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="679ba-1412">date d’expiration</span></span>
- <span data-ttu-id="679ba-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="679ba-1413">date d'exp</span></span>
- <span data-ttu-id="679ba-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="679ba-1414">date expiration</span></span>
- <span data-ttu-id="679ba-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="679ba-1415">bank card</span></span>
- <span data-ttu-id="679ba-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="679ba-1416">bankcard</span></span>
- <span data-ttu-id="679ba-1417">card number</span><span class="sxs-lookup"><span data-stu-id="679ba-1417">card number</span></span>
- <span data-ttu-id="679ba-1418">card num</span><span class="sxs-lookup"><span data-stu-id="679ba-1418">card num</span></span>
- <span data-ttu-id="679ba-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-1419">cardnumber</span></span>
- <span data-ttu-id="679ba-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="679ba-1420">cardnumbers</span></span>
- <span data-ttu-id="679ba-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-1421">card numbers</span></span>
- <span data-ttu-id="679ba-1422">crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1422">creditcard</span></span>
- <span data-ttu-id="679ba-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1423">credit cards</span></span>
- <span data-ttu-id="679ba-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1424">creditcards</span></span>
- <span data-ttu-id="679ba-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="679ba-1425">ccn</span></span>
- <span data-ttu-id="679ba-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="679ba-1426">card holder</span></span>
- <span data-ttu-id="679ba-1427">titular</span><span class="sxs-lookup"><span data-stu-id="679ba-1427">cardholder</span></span>
- <span data-ttu-id="679ba-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="679ba-1428">card holders</span></span>
- <span data-ttu-id="679ba-1429">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="679ba-1429">cardholders</span></span>
- <span data-ttu-id="679ba-1430">check card</span><span class="sxs-lookup"><span data-stu-id="679ba-1430">check card</span></span>
- <span data-ttu-id="679ba-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="679ba-1431">checkcard</span></span>
- <span data-ttu-id="679ba-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1432">check cards</span></span>
- <span data-ttu-id="679ba-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1433">checkcards</span></span>
- <span data-ttu-id="679ba-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="679ba-1434">debit card</span></span>
- <span data-ttu-id="679ba-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="679ba-1435">debitcard</span></span>
- <span data-ttu-id="679ba-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1436">debit cards</span></span>
- <span data-ttu-id="679ba-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1437">debitcards</span></span>
- <span data-ttu-id="679ba-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="679ba-1438">atm card</span></span>
- <span data-ttu-id="679ba-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="679ba-1439">atmcard</span></span>
- <span data-ttu-id="679ba-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1440">atm cards</span></span>
- <span data-ttu-id="679ba-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1441">atmcards</span></span>
- <span data-ttu-id="679ba-1442">enrutar</span><span class="sxs-lookup"><span data-stu-id="679ba-1442">enroute</span></span>
- <span data-ttu-id="679ba-1443">en route</span><span class="sxs-lookup"><span data-stu-id="679ba-1443">en route</span></span>
- <span data-ttu-id="679ba-1444">card type</span><span class="sxs-lookup"><span data-stu-id="679ba-1444">card type</span></span>
- <span data-ttu-id="679ba-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="679ba-1445">carte bancaire</span></span>
- <span data-ttu-id="679ba-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="679ba-1446">carte de crédit</span></span>
- <span data-ttu-id="679ba-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="679ba-1447">carte de credit</span></span>
- <span data-ttu-id="679ba-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1448">numéro de carte</span></span>
- <span data-ttu-id="679ba-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1449">numero de carte</span></span>
- <span data-ttu-id="679ba-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1450">nº de la carte</span></span>
- <span data-ttu-id="679ba-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1451">nº de carte</span></span>
- <span data-ttu-id="679ba-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="679ba-1452">kreditkarte</span></span>
- <span data-ttu-id="679ba-1453">karte</span><span class="sxs-lookup"><span data-stu-id="679ba-1453">karte</span></span>
- <span data-ttu-id="679ba-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="679ba-1454">karteninhaber</span></span>
- <span data-ttu-id="679ba-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="679ba-1455">karteninhabers</span></span>
- <span data-ttu-id="679ba-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="679ba-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="679ba-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="679ba-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="679ba-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="679ba-1458">kreditkartentyp</span></span>
- <span data-ttu-id="679ba-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="679ba-1459">eigentümername</span></span>
- <span data-ttu-id="679ba-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="679ba-1460">kartennr</span></span> 
- <span data-ttu-id="679ba-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1461">kartennummer</span></span>
- <span data-ttu-id="679ba-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1462">kreditkartennummer</span></span>
- <span data-ttu-id="679ba-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="679ba-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1464">carta di credito</span></span>
- <span data-ttu-id="679ba-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1465">carta credito</span></span>
- <span data-ttu-id="679ba-1466">cobro</span><span class="sxs-lookup"><span data-stu-id="679ba-1466">carta</span></span>
- <span data-ttu-id="679ba-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1467">n carta</span></span>
- <span data-ttu-id="679ba-1468">Nº.</span><span class="sxs-lookup"><span data-stu-id="679ba-1468">nr.</span></span> <span data-ttu-id="679ba-1469">cobro</span><span class="sxs-lookup"><span data-stu-id="679ba-1469">carta</span></span>
- <span data-ttu-id="679ba-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1470">nr carta</span></span>
- <span data-ttu-id="679ba-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1471">numero carta</span></span>
- <span data-ttu-id="679ba-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1472">numero della carta</span></span>
- <span data-ttu-id="679ba-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1473">numero di carta</span></span>
- <span data-ttu-id="679ba-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1474">tarjeta credito</span></span>
- <span data-ttu-id="679ba-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1475">tarjeta de credito</span></span>
- <span data-ttu-id="679ba-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1476">tarjeta crédito</span></span>
- <span data-ttu-id="679ba-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="679ba-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="679ba-1478">tarjeta de atm</span></span>
- <span data-ttu-id="679ba-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="679ba-1479">tarjeta atm</span></span>
- <span data-ttu-id="679ba-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1480">tarjeta debito</span></span>
- <span data-ttu-id="679ba-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1481">tarjeta de debito</span></span>
- <span data-ttu-id="679ba-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="679ba-1482">tarjeta débito</span></span>
- <span data-ttu-id="679ba-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="679ba-1483">tarjeta de débito</span></span>
- <span data-ttu-id="679ba-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1484">nº de tarjeta</span></span>
- <span data-ttu-id="679ba-1485">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1485">no.</span></span> <span data-ttu-id="679ba-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1486">de tarjeta</span></span>
- <span data-ttu-id="679ba-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1487">no de tarjeta</span></span>
- <span data-ttu-id="679ba-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1488">numero de tarjeta</span></span>
- <span data-ttu-id="679ba-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1489">número de tarjeta</span></span>
- <span data-ttu-id="679ba-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="679ba-1490">tarjeta no</span></span>
- <span data-ttu-id="679ba-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="679ba-1491">tarjetahabiente</span></span>
- <span data-ttu-id="679ba-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1492">cartão de crédito</span></span>
- <span data-ttu-id="679ba-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1493">cartão de credito</span></span>
- <span data-ttu-id="679ba-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1494">cartao de crédito</span></span>
- <span data-ttu-id="679ba-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1495">cartao de credito</span></span>
- <span data-ttu-id="679ba-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="679ba-1496">cartão de débito</span></span>
- <span data-ttu-id="679ba-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="679ba-1497">cartao de débito</span></span>
- <span data-ttu-id="679ba-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1498">cartão de debito</span></span>
- <span data-ttu-id="679ba-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1499">cartao de debito</span></span>
- <span data-ttu-id="679ba-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="679ba-1500">débito automático</span></span>
- <span data-ttu-id="679ba-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="679ba-1501">debito automatico</span></span>
- <span data-ttu-id="679ba-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1502">número do cartão</span></span>
- <span data-ttu-id="679ba-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1503">numero do cartão</span></span> 
- <span data-ttu-id="679ba-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1504">número do cartao</span></span>
- <span data-ttu-id="679ba-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1505">numero do cartao</span></span>
- <span data-ttu-id="679ba-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1506">número de cartão</span></span>
- <span data-ttu-id="679ba-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1507">numero de cartão</span></span>
- <span data-ttu-id="679ba-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1508">número de cartao</span></span>
- <span data-ttu-id="679ba-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1509">numero de cartao</span></span>
- <span data-ttu-id="679ba-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1510">nº do cartão</span></span>
- <span data-ttu-id="679ba-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1511">nº do cartao</span></span>
- <span data-ttu-id="679ba-1512">Nº.</span><span class="sxs-lookup"><span data-stu-id="679ba-1512">nº.</span></span> <span data-ttu-id="679ba-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1513">do cartão</span></span>
- <span data-ttu-id="679ba-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1514">no do cartão</span></span>
- <span data-ttu-id="679ba-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1515">no do cartao</span></span>
- <span data-ttu-id="679ba-1516">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1516">no.</span></span> <span data-ttu-id="679ba-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1517">do cartão</span></span>
- <span data-ttu-id="679ba-1518">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1518">no.</span></span> <span data-ttu-id="679ba-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="679ba-1520">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="679ba-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1521">Format</span></span>

<span data-ttu-id="679ba-1522">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1523">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1523">Pattern</span></span>

<span data-ttu-id="679ba-1524">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1525">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1525">Checksum</span></span>

<span data-ttu-id="679ba-1526">No</span><span class="sxs-lookup"><span data-stu-id="679ba-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1527">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1527">Definition</span></span>

<span data-ttu-id="679ba-1528">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1529">La función Func_croatia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1530">Se encuentra una palabra clave de Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-1531">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="679ba-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="679ba-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="679ba-1533">Tarjeta de identidad croata</span><span class="sxs-lookup"><span data-stu-id="679ba-1533">Croatian identity card</span></span>
- <span data-ttu-id="679ba-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="679ba-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="679ba-1535">Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="679ba-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1536">Format</span></span>

<span data-ttu-id="679ba-1537">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1538">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1538">Pattern</span></span>

<span data-ttu-id="679ba-1539">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-1539">11 digits:</span></span>
- <span data-ttu-id="679ba-1540">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1540">10 digits</span></span> 
- <span data-ttu-id="679ba-1541">El dígito final es un dígito de control para el intercambio internacional de datos, se agregan las letras h antes de los once dígitos.</span><span class="sxs-lookup"><span data-stu-id="679ba-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1542">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1542">Checksum</span></span>

<span data-ttu-id="679ba-1543">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1544">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1544">Definition</span></span>

<span data-ttu-id="679ba-1545">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1546">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1547">Se encuentra una palabra clave de Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="679ba-1548">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1548">The checksum passes.</span></span>

<span data-ttu-id="679ba-1549">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1550">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1551">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1551">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1552">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="679ba-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="679ba-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="679ba-1554">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="679ba-1554">Personal Identification Number</span></span>
- <span data-ttu-id="679ba-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="679ba-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="679ba-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="679ba-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="679ba-1557">Número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="679ba-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1558">Format</span></span>

<span data-ttu-id="679ba-1559">Nueve dígitos con barra diagonal (formato antiguo) 10 dígitos con barra diagonal (nuevo formato) opcional</span><span class="sxs-lookup"><span data-stu-id="679ba-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1560">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1560">Pattern</span></span>

<span data-ttu-id="679ba-1561">Nueve dígitos (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="679ba-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="679ba-1562">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1562">Nine digits</span></span>

<span data-ttu-id="679ba-1563">O</span><span class="sxs-lookup"><span data-stu-id="679ba-1563">OR</span></span>

- <span data-ttu-id="679ba-1564">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="679ba-1565">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="679ba-1565">A forward slash</span></span>
- <span data-ttu-id="679ba-1566">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1566">Three digits</span></span>

<span data-ttu-id="679ba-1567">10 dígitos (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="679ba-1567">10 digits (new format):</span></span>
- <span data-ttu-id="679ba-1568">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1568">10 digits</span></span>

<span data-ttu-id="679ba-1569">O</span><span class="sxs-lookup"><span data-stu-id="679ba-1569">OR</span></span>

- <span data-ttu-id="679ba-1570">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="679ba-1571">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="679ba-1571">A forward slash</span></span> 
- <span data-ttu-id="679ba-1572">Cuatro dígitos donde el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1573">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1573">Checksum</span></span>

<span data-ttu-id="679ba-1574">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1575">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1575">Definition</span></span>

<span data-ttu-id="679ba-1576">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_czech_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="679ba-1577">Se encuentra una palabra clave de Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="679ba-1578">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="679ba-1579">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1579">Keywords</span></span>

- <span data-ttu-id="679ba-1580">número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="679ba-1580">czech personal identity number</span></span>
- <span data-ttu-id="679ba-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="679ba-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="679ba-1582">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="679ba-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1583">Format</span></span>

<span data-ttu-id="679ba-1584">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="679ba-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1585">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1585">Pattern</span></span>

<span data-ttu-id="679ba-1586">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-1586">10 digits:</span></span>
- <span data-ttu-id="679ba-1587">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="679ba-1588">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-1588">A hyphen</span></span> 
- <span data-ttu-id="679ba-1589">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1590">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1590">Checksum</span></span>

<span data-ttu-id="679ba-1591">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1592">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1592">Definition</span></span>

<span data-ttu-id="679ba-1593">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_denmark_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="679ba-1594">Se encuentra una palabra clave de Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="679ba-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="679ba-1595">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-1596">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="679ba-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="679ba-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="679ba-1598">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="679ba-1598">Personal Identification Number</span></span>
- <span data-ttu-id="679ba-1599">RCP</span><span class="sxs-lookup"><span data-stu-id="679ba-1599">CPR</span></span>
- <span data-ttu-id="679ba-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="679ba-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="679ba-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="679ba-1602">Número de la Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="679ba-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1603">Format</span></span>

<span data-ttu-id="679ba-1604">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1605">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1605">Pattern</span></span>

<span data-ttu-id="679ba-1606">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="679ba-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="679ba-1607">Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito</span><span class="sxs-lookup"><span data-stu-id="679ba-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="679ba-1608">Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito.</span><span class="sxs-lookup"><span data-stu-id="679ba-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="679ba-1609">Siete dígitos, el último de los cuales es el dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1610">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1610">Checksum</span></span>

<span data-ttu-id="679ba-1611">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1612">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1612">Definition</span></span>

<span data-ttu-id="679ba-1613">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1614">La función Func_dea_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1615">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-1616">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1616">Keywords</span></span>

<span data-ttu-id="679ba-1617">Ninguno</span><span class="sxs-lookup"><span data-stu-id="679ba-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="679ba-1618">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="679ba-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1619">Format</span></span>

<span data-ttu-id="679ba-1620">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1621">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1621">Pattern</span></span>

<span data-ttu-id="679ba-1622">Patrón muy complejo y robusto</span><span class="sxs-lookup"><span data-stu-id="679ba-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1623">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1623">Checksum</span></span>

<span data-ttu-id="679ba-1624">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1625">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1625">Definition</span></span>

<span data-ttu-id="679ba-1626">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1627">La función Func_eu_debit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1628">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="679ba-1629">Se encuentra una palabra clave de Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="679ba-1630">Se encuentra una palabra clave de Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="679ba-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="679ba-1631">Se encuentra una palabra clave de Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="679ba-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="679ba-1632">Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="679ba-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="679ba-1633">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-1634">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1634">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1635">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="679ba-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="679ba-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="679ba-1637">account number</span><span class="sxs-lookup"><span data-stu-id="679ba-1637">account number</span></span> 
- <span data-ttu-id="679ba-1638">card number</span><span class="sxs-lookup"><span data-stu-id="679ba-1638">card number</span></span> 
- <span data-ttu-id="679ba-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="679ba-1639">card no.</span></span> 
- <span data-ttu-id="679ba-1640">security number</span><span class="sxs-lookup"><span data-stu-id="679ba-1640">security number</span></span> 
- <span data-ttu-id="679ba-1641">CC #</span><span class="sxs-lookup"><span data-stu-id="679ba-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="679ba-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="679ba-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="679ba-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="679ba-1643">acct nbr</span></span> 
- <span data-ttu-id="679ba-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="679ba-1644">acct num</span></span> 
- <span data-ttu-id="679ba-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="679ba-1645">acct no</span></span> 
- <span data-ttu-id="679ba-1646">american express</span><span class="sxs-lookup"><span data-stu-id="679ba-1646">american express</span></span> 
- <span data-ttu-id="679ba-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="679ba-1647">americanexpress</span></span> 
- <span data-ttu-id="679ba-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="679ba-1648">americano espresso</span></span> 
- <span data-ttu-id="679ba-1649">AMEX</span><span class="sxs-lookup"><span data-stu-id="679ba-1649">amex</span></span> 
- <span data-ttu-id="679ba-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="679ba-1650">atm card</span></span> 
- <span data-ttu-id="679ba-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1651">atm cards</span></span> 
- <span data-ttu-id="679ba-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1652">atm kaart</span></span> 
- <span data-ttu-id="679ba-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="679ba-1653">atmcard</span></span> 
- <span data-ttu-id="679ba-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1654">atmcards</span></span> 
- <span data-ttu-id="679ba-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1655">atmkaart</span></span> 
- <span data-ttu-id="679ba-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="679ba-1656">atmkaarten</span></span> 
- <span data-ttu-id="679ba-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="679ba-1657">bancontact</span></span> 
- <span data-ttu-id="679ba-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="679ba-1658">bank card</span></span> 
- <span data-ttu-id="679ba-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1659">bankkaart</span></span> 
- <span data-ttu-id="679ba-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="679ba-1660">card holder</span></span> 
- <span data-ttu-id="679ba-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="679ba-1661">card holders</span></span> 
- <span data-ttu-id="679ba-1662">card num</span><span class="sxs-lookup"><span data-stu-id="679ba-1662">card num</span></span> 
- <span data-ttu-id="679ba-1663">card number</span><span class="sxs-lookup"><span data-stu-id="679ba-1663">card number</span></span> 
- <span data-ttu-id="679ba-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-1664">card numbers</span></span> 
- <span data-ttu-id="679ba-1665">card type</span><span class="sxs-lookup"><span data-stu-id="679ba-1665">card type</span></span> 
- <span data-ttu-id="679ba-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="679ba-1666">cardano numerico</span></span> 
- <span data-ttu-id="679ba-1667">titular</span><span class="sxs-lookup"><span data-stu-id="679ba-1667">cardholder</span></span> 
- <span data-ttu-id="679ba-1668">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="679ba-1668">cardholders</span></span> 
- <span data-ttu-id="679ba-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-1669">cardnumber</span></span> 
- <span data-ttu-id="679ba-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="679ba-1670">cardnumbers</span></span> 
- <span data-ttu-id="679ba-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="679ba-1671">carta bianca</span></span> 
- <span data-ttu-id="679ba-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1672">carta credito</span></span> 
- <span data-ttu-id="679ba-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1673">carta di credito</span></span> 
- <span data-ttu-id="679ba-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1674">cartao de credito</span></span> 
- <span data-ttu-id="679ba-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1675">cartao de crédito</span></span> 
- <span data-ttu-id="679ba-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1676">cartao de debito</span></span> 
- <span data-ttu-id="679ba-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="679ba-1677">cartao de débito</span></span> 
- <span data-ttu-id="679ba-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="679ba-1678">carte bancaire</span></span> 
- <span data-ttu-id="679ba-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="679ba-1679">carte blanche</span></span> 
- <span data-ttu-id="679ba-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="679ba-1680">carte bleue</span></span> 
- <span data-ttu-id="679ba-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="679ba-1681">carte de credit</span></span> 
- <span data-ttu-id="679ba-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="679ba-1682">carte de crédit</span></span> 
- <span data-ttu-id="679ba-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1683">carte di credito</span></span> 
- <span data-ttu-id="679ba-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="679ba-1684">carteblanche</span></span> 
- <span data-ttu-id="679ba-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1685">cartão de credito</span></span> 
- <span data-ttu-id="679ba-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1686">cartão de crédito</span></span> 
- <span data-ttu-id="679ba-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1687">cartão de debito</span></span> 
- <span data-ttu-id="679ba-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="679ba-1688">cartão de débito</span></span> 
- <span data-ttu-id="679ba-1689">cb</span><span class="sxs-lookup"><span data-stu-id="679ba-1689">cb</span></span> 
- <span data-ttu-id="679ba-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="679ba-1690">ccn</span></span> 
- <span data-ttu-id="679ba-1691">check card</span><span class="sxs-lookup"><span data-stu-id="679ba-1691">check card</span></span> 
- <span data-ttu-id="679ba-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1692">check cards</span></span> 
- <span data-ttu-id="679ba-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="679ba-1693">checkcard</span></span>
- <span data-ttu-id="679ba-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1694">checkcards</span></span> 
- <span data-ttu-id="679ba-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1695">chequekaart</span></span> 
- <span data-ttu-id="679ba-1696">Logic</span><span class="sxs-lookup"><span data-stu-id="679ba-1696">cirrus</span></span> 
- <span data-ttu-id="679ba-1697">Cirrus-EDC-maestro</span><span class="sxs-lookup"><span data-stu-id="679ba-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="679ba-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1698">controlekaart</span></span> 
- <span data-ttu-id="679ba-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="679ba-1699">controlekaarten</span></span> 
- <span data-ttu-id="679ba-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="679ba-1700">credit card</span></span> 
- <span data-ttu-id="679ba-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1701">credit cards</span></span> 
- <span data-ttu-id="679ba-1702">crédito</span><span class="sxs-lookup"><span data-stu-id="679ba-1702">creditcard</span></span> 
- <span data-ttu-id="679ba-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1703">creditcards</span></span> 
- <span data-ttu-id="679ba-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1704">debetkaart</span></span> 
- <span data-ttu-id="679ba-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="679ba-1705">debetkaarten</span></span> 
- <span data-ttu-id="679ba-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="679ba-1706">debit card</span></span> 
- <span data-ttu-id="679ba-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1707">debit cards</span></span> 
- <span data-ttu-id="679ba-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="679ba-1708">debitcard</span></span> 
- <span data-ttu-id="679ba-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="679ba-1709">debitcards</span></span> 
- <span data-ttu-id="679ba-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="679ba-1710">debito automatico</span></span> 
- <span data-ttu-id="679ba-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="679ba-1711">diners club</span></span> 
- <span data-ttu-id="679ba-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="679ba-1712">dinersclub</span></span> 
- <span data-ttu-id="679ba-1713">advierte</span><span class="sxs-lookup"><span data-stu-id="679ba-1713">discover</span></span> 
- <span data-ttu-id="679ba-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="679ba-1714">discover card</span></span> 
- <span data-ttu-id="679ba-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1715">discover cards</span></span> 
- <span data-ttu-id="679ba-1716">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1716">discovercard</span></span> 
- <span data-ttu-id="679ba-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="679ba-1717">discovercards</span></span> 
- <span data-ttu-id="679ba-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="679ba-1718">débito automático</span></span>
- <span data-ttu-id="679ba-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="679ba-1719">edc</span></span> 
- <span data-ttu-id="679ba-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="679ba-1720">eigentümername</span></span> 
- <span data-ttu-id="679ba-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="679ba-1721">european debit card</span></span> 
- <span data-ttu-id="679ba-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1722">hoofdkaart</span></span> 
- <span data-ttu-id="679ba-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="679ba-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="679ba-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="679ba-1724">in viaggio</span></span> 
- <span data-ttu-id="679ba-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="679ba-1725">japanese card bureau</span></span> 
- <span data-ttu-id="679ba-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="679ba-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="679ba-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="679ba-1727">jcb</span></span> 
- <span data-ttu-id="679ba-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="679ba-1728">kaart</span></span> 
- <span data-ttu-id="679ba-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="679ba-1729">kaart num</span></span> 
- <span data-ttu-id="679ba-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="679ba-1730">kaartaantal</span></span> 
- <span data-ttu-id="679ba-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="679ba-1731">kaartaantallen</span></span> 
- <span data-ttu-id="679ba-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="679ba-1732">kaarthouder</span></span> 
- <span data-ttu-id="679ba-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="679ba-1733">kaarthouders</span></span> 
- <span data-ttu-id="679ba-1734">karte</span><span class="sxs-lookup"><span data-stu-id="679ba-1734">karte</span></span>  
- <span data-ttu-id="679ba-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="679ba-1735">karteninhaber</span></span> 
- <span data-ttu-id="679ba-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="679ba-1736">karteninhabers</span></span>
- <span data-ttu-id="679ba-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="679ba-1737">kartennr</span></span> 
- <span data-ttu-id="679ba-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1738">kartennummer</span></span> 
- <span data-ttu-id="679ba-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="679ba-1739">kreditkarte</span></span> 
- <span data-ttu-id="679ba-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="679ba-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="679ba-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="679ba-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="679ba-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="679ba-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="679ba-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="679ba-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="679ba-1745">dispositivos</span><span class="sxs-lookup"><span data-stu-id="679ba-1745">maestro</span></span> 
- <span data-ttu-id="679ba-1746">master card</span><span class="sxs-lookup"><span data-stu-id="679ba-1746">master card</span></span> 
- <span data-ttu-id="679ba-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="679ba-1747">master cards</span></span> 
- <span data-ttu-id="679ba-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="679ba-1748">mastercard</span></span> 
- <span data-ttu-id="679ba-1749">MasterCard</span><span class="sxs-lookup"><span data-stu-id="679ba-1749">mastercards</span></span> 
- <span data-ttu-id="679ba-1750">valuación</span><span class="sxs-lookup"><span data-stu-id="679ba-1750">mc</span></span> 
- <span data-ttu-id="679ba-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="679ba-1751">mister cash</span></span> 
- <span data-ttu-id="679ba-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1752">n carta</span></span> 
- <span data-ttu-id="679ba-1753">cobro</span><span class="sxs-lookup"><span data-stu-id="679ba-1753">carta</span></span> 
- <span data-ttu-id="679ba-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1754">no de tarjeta</span></span> 
- <span data-ttu-id="679ba-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1755">no do cartao</span></span> 
- <span data-ttu-id="679ba-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1756">no do cartão</span></span> 
- <span data-ttu-id="679ba-1757">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1757">no.</span></span> <span data-ttu-id="679ba-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1758">de tarjeta</span></span> 
- <span data-ttu-id="679ba-1759">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1759">no.</span></span> <span data-ttu-id="679ba-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1760">do cartao</span></span> 
- <span data-ttu-id="679ba-1761">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1761">no.</span></span> <span data-ttu-id="679ba-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1762">do cartão</span></span> 
- <span data-ttu-id="679ba-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1763">nr carta</span></span> 
- <span data-ttu-id="679ba-1764">Nº.</span><span class="sxs-lookup"><span data-stu-id="679ba-1764">nr.</span></span> <span data-ttu-id="679ba-1765">cobro</span><span class="sxs-lookup"><span data-stu-id="679ba-1765">carta</span></span> 
- <span data-ttu-id="679ba-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1766">numeri di scheda</span></span> 
- <span data-ttu-id="679ba-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1767">numero carta</span></span> 
- <span data-ttu-id="679ba-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1768">numero de cartao</span></span> 
- <span data-ttu-id="679ba-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1769">numero de carte</span></span> 
- <span data-ttu-id="679ba-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1770">numero de cartão</span></span> 
- <span data-ttu-id="679ba-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1771">numero de tarjeta</span></span>
- <span data-ttu-id="679ba-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1772">numero della carta</span></span> 
- <span data-ttu-id="679ba-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1773">numero di carta</span></span> 
- <span data-ttu-id="679ba-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1774">numero di scheda</span></span> 
- <span data-ttu-id="679ba-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1775">numero do cartao</span></span> 
- <span data-ttu-id="679ba-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1776">numero do cartão</span></span> 
- <span data-ttu-id="679ba-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1777">numéro de carte</span></span> 
- <span data-ttu-id="679ba-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="679ba-1778">nº carta</span></span> 
- <span data-ttu-id="679ba-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1779">nº de carte</span></span> 
- <span data-ttu-id="679ba-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="679ba-1780">nº de la carte</span></span> 
- <span data-ttu-id="679ba-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="679ba-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1782">nº do cartao</span></span> 
- <span data-ttu-id="679ba-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1783">nº do cartão</span></span> 
- <span data-ttu-id="679ba-1784">Nº.</span><span class="sxs-lookup"><span data-stu-id="679ba-1784">nº.</span></span> <span data-ttu-id="679ba-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1785">do cartão</span></span> 
- <span data-ttu-id="679ba-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1786">número de cartao</span></span> 
- <span data-ttu-id="679ba-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="679ba-1787">número de cartão</span></span> 
- <span data-ttu-id="679ba-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="679ba-1788">número de tarjeta</span></span> 
- <span data-ttu-id="679ba-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="679ba-1789">número do cartao</span></span> 
- <span data-ttu-id="679ba-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="679ba-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="679ba-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="679ba-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="679ba-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="679ba-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="679ba-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="679ba-1793">scheda della banca</span></span> 
- <span data-ttu-id="679ba-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="679ba-1794">scheda di controllo</span></span> 
- <span data-ttu-id="679ba-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1795">scheda di debito</span></span> 
- <span data-ttu-id="679ba-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="679ba-1796">scheda matrice</span></span> 
- <span data-ttu-id="679ba-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="679ba-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="679ba-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="679ba-1798">schede di controllo</span></span> 
- <span data-ttu-id="679ba-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1799">schede di debito</span></span> 
- <span data-ttu-id="679ba-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="679ba-1800">schede matrici</span></span> 
- <span data-ttu-id="679ba-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="679ba-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="679ba-1802">scoprono le schede</span></span> 
- <span data-ttu-id="679ba-1803">solo</span><span class="sxs-lookup"><span data-stu-id="679ba-1803">solo</span></span> 
- <span data-ttu-id="679ba-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1804">supporti di scheda</span></span> 
- <span data-ttu-id="679ba-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1805">supporto di scheda</span></span> 
- <span data-ttu-id="679ba-1806">cambia</span><span class="sxs-lookup"><span data-stu-id="679ba-1806">switch</span></span> 
- <span data-ttu-id="679ba-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="679ba-1807">tarjeta atm</span></span> 
- <span data-ttu-id="679ba-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1808">tarjeta credito</span></span> 
- <span data-ttu-id="679ba-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="679ba-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="679ba-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="679ba-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="679ba-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="679ba-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="679ba-1812">tarjeta debito</span></span> 
- <span data-ttu-id="679ba-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="679ba-1813">tarjeta no</span></span>
- <span data-ttu-id="679ba-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="679ba-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="679ba-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1815">tipo della scheda</span></span> 
- <span data-ttu-id="679ba-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="679ba-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="679ba-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1817">scheda</span></span> 
- <span data-ttu-id="679ba-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="679ba-1818">v pay</span></span> 
- <span data-ttu-id="679ba-1819">v-Pay</span><span class="sxs-lookup"><span data-stu-id="679ba-1819">v-pay</span></span> 
- <span data-ttu-id="679ba-1820">régimen</span><span class="sxs-lookup"><span data-stu-id="679ba-1820">visa</span></span> 
- <span data-ttu-id="679ba-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="679ba-1821">visa plus</span></span> 
- <span data-ttu-id="679ba-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="679ba-1822">visa electron</span></span> 
- <span data-ttu-id="679ba-1823">a</span><span class="sxs-lookup"><span data-stu-id="679ba-1823">visto</span></span> 
- <span data-ttu-id="679ba-1824">visum</span><span class="sxs-lookup"><span data-stu-id="679ba-1824">visum</span></span> 
- <span data-ttu-id="679ba-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="679ba-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="679ba-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="679ba-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="679ba-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="679ba-1827">card identification number</span></span>
- <span data-ttu-id="679ba-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="679ba-1828">card verification</span></span> 
- <span data-ttu-id="679ba-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="679ba-1829">cardi la verifica</span></span> 
- <span data-ttu-id="679ba-1830">cid</span><span class="sxs-lookup"><span data-stu-id="679ba-1830">cid</span></span> 
- <span data-ttu-id="679ba-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="679ba-1831">cod seg</span></span> 
- <span data-ttu-id="679ba-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1832">cod seguranca</span></span> 
- <span data-ttu-id="679ba-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1833">cod segurança</span></span> 
- <span data-ttu-id="679ba-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="679ba-1834">cod sicurezza</span></span> 
- <span data-ttu-id="679ba-1835">COD.</span><span class="sxs-lookup"><span data-stu-id="679ba-1835">cod.</span></span> <span data-ttu-id="679ba-1836">seg</span><span class="sxs-lookup"><span data-stu-id="679ba-1836">seg</span></span> 
- <span data-ttu-id="679ba-1837">COD.</span><span class="sxs-lookup"><span data-stu-id="679ba-1837">cod.</span></span> <span data-ttu-id="679ba-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1838">seguranca</span></span> 
- <span data-ttu-id="679ba-1839">COD.</span><span class="sxs-lookup"><span data-stu-id="679ba-1839">cod.</span></span> <span data-ttu-id="679ba-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1840">segurança</span></span> 
- <span data-ttu-id="679ba-1841">COD.</span><span class="sxs-lookup"><span data-stu-id="679ba-1841">cod.</span></span> <span data-ttu-id="679ba-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="679ba-1842">sicurezza</span></span> 
- <span data-ttu-id="679ba-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="679ba-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="679ba-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="679ba-1844">codice di verifica</span></span> 
- <span data-ttu-id="679ba-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="679ba-1845">codigo</span></span> 
- <span data-ttu-id="679ba-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="679ba-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1847">codigo de segurança</span></span> 
- <span data-ttu-id="679ba-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="679ba-1848">crittogramma</span></span> 
- <span data-ttu-id="679ba-1849">criptograma</span><span class="sxs-lookup"><span data-stu-id="679ba-1849">cryptogram</span></span> 
- <span data-ttu-id="679ba-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="679ba-1850">cryptogramme</span></span> 
- <span data-ttu-id="679ba-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="679ba-1851">cv2</span></span> 
- <span data-ttu-id="679ba-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="679ba-1852">cvc</span></span> 
- <span data-ttu-id="679ba-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="679ba-1853">cvc2</span></span> 
- <span data-ttu-id="679ba-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="679ba-1854">cvn</span></span> 
- <span data-ttu-id="679ba-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="679ba-1855">cvv</span></span> 
- <span data-ttu-id="679ba-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="679ba-1856">cvv2</span></span> 
- <span data-ttu-id="679ba-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1857">cód seguranca</span></span> 
- <span data-ttu-id="679ba-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1858">cód segurança</span></span> 
- <span data-ttu-id="679ba-1859">campos.</span><span class="sxs-lookup"><span data-stu-id="679ba-1859">cód.</span></span> <span data-ttu-id="679ba-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1860">seguranca</span></span> 
- <span data-ttu-id="679ba-1861">campos.</span><span class="sxs-lookup"><span data-stu-id="679ba-1861">cód.</span></span> <span data-ttu-id="679ba-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1862">segurança</span></span> 
- <span data-ttu-id="679ba-1863">Código</span><span class="sxs-lookup"><span data-stu-id="679ba-1863">código</span></span> 
- <span data-ttu-id="679ba-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="679ba-1864">código de seguranca</span></span> 
- <span data-ttu-id="679ba-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="679ba-1865">código de segurança</span></span> 
- <span data-ttu-id="679ba-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="679ba-1866">de kaart controle</span></span> 
- <span data-ttu-id="679ba-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="679ba-1867">geeft nr uit</span></span> 
- <span data-ttu-id="679ba-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="679ba-1868">issue no</span></span> 
- <span data-ttu-id="679ba-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="679ba-1869">issue number</span></span> 
- <span data-ttu-id="679ba-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="679ba-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="679ba-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="679ba-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="679ba-1873">kwestieaantal</span></span> 
- <span data-ttu-id="679ba-1874">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1874">no.</span></span> <span data-ttu-id="679ba-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="679ba-1875">dell'edizione</span></span> 
- <span data-ttu-id="679ba-1876">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-1876">no.</span></span> <span data-ttu-id="679ba-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="679ba-1877">di sicurezza</span></span> 
- <span data-ttu-id="679ba-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="679ba-1878">numero de securite</span></span> 
- <span data-ttu-id="679ba-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="679ba-1879">numero de verificacao</span></span> 
- <span data-ttu-id="679ba-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="679ba-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="679ba-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="679ba-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="679ba-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="679ba-1882">scheda</span></span> 
- <span data-ttu-id="679ba-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="679ba-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="679ba-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="679ba-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="679ba-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="679ba-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="679ba-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="679ba-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="679ba-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="679ba-1887">número de verificação</span></span> 
- <span data-ttu-id="679ba-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="679ba-1888">perno il blocco</span></span> 
- <span data-ttu-id="679ba-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="679ba-1889">pin block</span></span> 
- <span data-ttu-id="679ba-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="679ba-1890">prufziffer</span></span> 
- <span data-ttu-id="679ba-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="679ba-1891">prüfziffer</span></span> 
- <span data-ttu-id="679ba-1892">security code</span><span class="sxs-lookup"><span data-stu-id="679ba-1892">security code</span></span> 
- <span data-ttu-id="679ba-1893">security no</span><span class="sxs-lookup"><span data-stu-id="679ba-1893">security no</span></span> 
- <span data-ttu-id="679ba-1894">security number</span><span class="sxs-lookup"><span data-stu-id="679ba-1894">security number</span></span> 
- <span data-ttu-id="679ba-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="679ba-1895">sicherheits kode</span></span> 
- <span data-ttu-id="679ba-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="679ba-1896">sicherheitscode</span></span> 
- <span data-ttu-id="679ba-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="679ba-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="679ba-1898">speldblok</span></span> 
- <span data-ttu-id="679ba-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="679ba-1899">veiligheid nr</span></span> 
- <span data-ttu-id="679ba-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="679ba-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="679ba-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="679ba-1901">veiligheidscode</span></span> 
- <span data-ttu-id="679ba-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="679ba-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="679ba-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="679ba-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="679ba-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="679ba-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="679ba-1905">ablauf</span></span> 
- <span data-ttu-id="679ba-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="679ba-1906">data de expiracao</span></span> 
- <span data-ttu-id="679ba-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="679ba-1907">data de expiração</span></span> 
- <span data-ttu-id="679ba-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="679ba-1908">data del exp</span></span> 
- <span data-ttu-id="679ba-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="679ba-1909">data di exp</span></span> 
- <span data-ttu-id="679ba-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="679ba-1910">data di scadenza</span></span> 
- <span data-ttu-id="679ba-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="679ba-1911">data em que expira</span></span> 
- <span data-ttu-id="679ba-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="679ba-1912">data scad</span></span> 
- <span data-ttu-id="679ba-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="679ba-1913">data scadenza</span></span> 
- <span data-ttu-id="679ba-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="679ba-1914">date de validité</span></span> 
- <span data-ttu-id="679ba-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="679ba-1915">datum afloop</span></span> 
- <span data-ttu-id="679ba-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="679ba-1916">datum van exp</span></span> 
- <span data-ttu-id="679ba-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="679ba-1917">de afloop</span></span> 
- <span data-ttu-id="679ba-1918">espira</span><span class="sxs-lookup"><span data-stu-id="679ba-1918">espira</span></span> 
- <span data-ttu-id="679ba-1919">espira</span><span class="sxs-lookup"><span data-stu-id="679ba-1919">espira</span></span> 
- <span data-ttu-id="679ba-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="679ba-1920">exp date</span></span> 
- <span data-ttu-id="679ba-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="679ba-1921">exp datum</span></span> 
- <span data-ttu-id="679ba-1922">expiración</span><span class="sxs-lookup"><span data-stu-id="679ba-1922">expiration</span></span> 
- <span data-ttu-id="679ba-1923">expiran</span><span class="sxs-lookup"><span data-stu-id="679ba-1923">expire</span></span> 
- <span data-ttu-id="679ba-1924">expira</span><span class="sxs-lookup"><span data-stu-id="679ba-1924">expires</span></span> 
- <span data-ttu-id="679ba-1925">expiración</span><span class="sxs-lookup"><span data-stu-id="679ba-1925">expiry</span></span> 
- <span data-ttu-id="679ba-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="679ba-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="679ba-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="679ba-1927">fecha de venc</span></span> 
- <span data-ttu-id="679ba-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="679ba-1928">gultig bis</span></span> 
- <span data-ttu-id="679ba-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="679ba-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="679ba-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="679ba-1930">gültig bis</span></span> 
- <span data-ttu-id="679ba-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="679ba-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="679ba-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="679ba-1932">la scadenza</span></span> 
- <span data-ttu-id="679ba-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="679ba-1933">scadenza</span></span> 
- <span data-ttu-id="679ba-1934">valable</span><span class="sxs-lookup"><span data-stu-id="679ba-1934">valable</span></span> 
- <span data-ttu-id="679ba-1935">validade</span><span class="sxs-lookup"><span data-stu-id="679ba-1935">validade</span></span> 
- <span data-ttu-id="679ba-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="679ba-1936">valido hasta</span></span> 
- <span data-ttu-id="679ba-1937">valorar</span><span class="sxs-lookup"><span data-stu-id="679ba-1937">valor</span></span> 
- <span data-ttu-id="679ba-1938">venc</span><span class="sxs-lookup"><span data-stu-id="679ba-1938">venc</span></span> 
- <span data-ttu-id="679ba-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="679ba-1939">vencimento</span></span> 
- <span data-ttu-id="679ba-1940">1er</span><span class="sxs-lookup"><span data-stu-id="679ba-1940">vencimiento</span></span> 
- <span data-ttu-id="679ba-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="679ba-1941">verloopt</span></span> 
- <span data-ttu-id="679ba-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="679ba-1942">vervaldag</span></span> 
- <span data-ttu-id="679ba-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="679ba-1943">vervaldatum</span></span> 
- <span data-ttu-id="679ba-1944">vto</span><span class="sxs-lookup"><span data-stu-id="679ba-1944">vto</span></span> 
- <span data-ttu-id="679ba-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="679ba-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="679ba-1946">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="679ba-1946">EU Driver's License Number</span></span>

<span data-ttu-id="679ba-1947">Para obtener más información, vea [tipo de información confidencial del número de licencia del conductor de la UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="679ba-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="679ba-1948">Número de identificación nacional de la UE</span><span class="sxs-lookup"><span data-stu-id="679ba-1948">EU National Identification Number</span></span>

<span data-ttu-id="679ba-1949">Para obtener más información, consulte el [tipo de información confidencial de número de identificación nacional de la UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="679ba-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="679ba-1950">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="679ba-1950">EU Passport Number</span></span>

<span data-ttu-id="679ba-1951">Para obtener más información, consulte [EU Number Sensitive Information Type](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="679ba-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="679ba-1952">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="679ba-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="679ba-1953">Para obtener más información, consulte el [número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="679ba-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="679ba-1954">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="679ba-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="679ba-1955">Para obtener más información, vea [tipo de información confidencial de número de identificación de impuestos de la UE](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="679ba-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="679ba-1956">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="679ba-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1957">Format</span></span>

<span data-ttu-id="679ba-1958">Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1959">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1959">Pattern</span></span>

<span data-ttu-id="679ba-1960">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="679ba-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="679ba-1961">Seis dígitos en el formato DDMMAA que son una fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="679ba-1962">Marcador del siglo (ya sea '-', '+' o 'a')</span><span class="sxs-lookup"><span data-stu-id="679ba-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="679ba-1963">Número de identificación personal de tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="679ba-1964">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1965">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1965">Checksum</span></span>

<span data-ttu-id="679ba-1966">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1967">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1967">Definition</span></span>

<span data-ttu-id="679ba-1968">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1969">La función Func_finnish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1970">Se encuentra una palabra clave de Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="679ba-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="679ba-1971">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-1972">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1972">Keywords</span></span>

- <span data-ttu-id="679ba-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="679ba-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="679ba-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="679ba-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="679ba-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="679ba-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="679ba-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="679ba-1976">Personbeteckning</span></span>
- <span data-ttu-id="679ba-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="679ba-1978">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="679ba-1978">Finland Passport Number</span></span>

<span data-ttu-id="679ba-1979">Combinación de formato de nueve letras y dígitos de la combinación de los patrones de nueve letras y dígitos: dos letras (no distingue entre mayúsculas y minúsculas) siete dígitos de suma de comprobación no Definition una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="679ba-1980">Se encuentra una palabra clave de Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="679ba-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="679ba-1981"></span></span>
<span data-ttu-id="679ba-1982">Palabras clave Keyword_finland_passport_number Passi de Passport</span><span class="sxs-lookup"><span data-stu-id="679ba-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="679ba-1983">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="679ba-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-1984">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-1984">Format</span></span>

<span data-ttu-id="679ba-1985">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-1986">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-1986">Pattern</span></span>

<span data-ttu-id="679ba-1987">12 dígitos con validación para descontar patrones similares como los números de teléfono franceses</span><span class="sxs-lookup"><span data-stu-id="679ba-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-1988">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-1988">Checksum</span></span>

<span data-ttu-id="679ba-1989">No</span><span class="sxs-lookup"><span data-stu-id="679ba-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-1990">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-1990">Definition</span></span>

<span data-ttu-id="679ba-1991">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-1992">La función Func_french_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-1993">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="679ba-1994">Se encuentra una palabra clave de Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="679ba-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="679ba-1995">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-1996">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="679ba-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="679ba-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="679ba-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="679ba-1998">drivers licence</span></span>
- <span data-ttu-id="679ba-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="679ba-1999">drivers license</span></span>
- <span data-ttu-id="679ba-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="679ba-2000">driving licence</span></span>
- <span data-ttu-id="679ba-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="679ba-2001">driving license</span></span>
- <span data-ttu-id="679ba-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="679ba-2002">permis de conduire</span></span>
- <span data-ttu-id="679ba-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="679ba-2003">licence number</span></span>
- <span data-ttu-id="679ba-2004">license number</span><span class="sxs-lookup"><span data-stu-id="679ba-2004">license number</span></span>
- <span data-ttu-id="679ba-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-2005">licence numbers</span></span>
- <span data-ttu-id="679ba-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="679ba-2007">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="679ba-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2008">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2008">Format</span></span>

<span data-ttu-id="679ba-2009">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2010">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2010">Pattern</span></span>

<span data-ttu-id="679ba-2011">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2012">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2012">Checksum</span></span>

<span data-ttu-id="679ba-2013">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2014">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2014">Definition</span></span>

<span data-ttu-id="679ba-2015">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2016">La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2017">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2017">Keywords</span></span>

<span data-ttu-id="679ba-2018">Ninguno</span><span class="sxs-lookup"><span data-stu-id="679ba-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="679ba-2019">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="679ba-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2020">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2020">Format</span></span>

<span data-ttu-id="679ba-2021">Nueve dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="679ba-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2022">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2022">Pattern</span></span>

<span data-ttu-id="679ba-2023">Nueve dígitos y letras:</span><span class="sxs-lookup"><span data-stu-id="679ba-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="679ba-2024">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2024">Two digits</span></span> 
- <span data-ttu-id="679ba-2025">Dos letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-2026">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2027">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2027">Checksum</span></span>

<span data-ttu-id="679ba-2028">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2029">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2029">Definition</span></span>

<span data-ttu-id="679ba-2030">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2031">La función Func_fr_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2032">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="679ba-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2033">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="679ba-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-2034">Keyword_passport</span></span>

- <span data-ttu-id="679ba-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2035">Passport Number</span></span>
- <span data-ttu-id="679ba-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="679ba-2036">Passport No</span></span>
- <span data-ttu-id="679ba-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="679ba-2037">Passport #</span></span>
- <span data-ttu-id="679ba-2038">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="679ba-2038">Passport#</span></span>
- <span data-ttu-id="679ba-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="679ba-2039">PassportID</span></span>
- <span data-ttu-id="679ba-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="679ba-2040">Passportno</span></span>
- <span data-ttu-id="679ba-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-2041">passportnumber</span></span>
- <span data-ttu-id="679ba-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="679ba-2042">パスポート</span></span>
- <span data-ttu-id="679ba-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2043">パスポート番号</span></span>
- <span data-ttu-id="679ba-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="679ba-2044">パスポートのNum</span></span>
- <span data-ttu-id="679ba-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2045">パスポート ＃</span></span> 
- <span data-ttu-id="679ba-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="679ba-2046">Numéro de passeport</span></span>
- <span data-ttu-id="679ba-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="679ba-2047">Passeport n °</span></span>
- <span data-ttu-id="679ba-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="679ba-2048">Passeport Non</span></span>
- <span data-ttu-id="679ba-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-2049">Passeport #</span></span>
- <span data-ttu-id="679ba-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-2050">Passeport#</span></span>
- <span data-ttu-id="679ba-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="679ba-2051">PasseportNon</span></span>
- <span data-ttu-id="679ba-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="679ba-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="679ba-2053">Número de seguridad social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="679ba-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2054">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2054">Format</span></span>

<span data-ttu-id="679ba-2055">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2056">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2056">Pattern</span></span>

<span data-ttu-id="679ba-2057">Debe coincidir uno de los dos patrones:</span><span class="sxs-lookup"><span data-stu-id="679ba-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="679ba-2058">13 dígitos seguidos de un espacio seguido de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="679ba-2059">o</span><span class="sxs-lookup"><span data-stu-id="679ba-2059">or</span></span>
- <span data-ttu-id="679ba-2060">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2061">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2061">Checksum</span></span>

<span data-ttu-id="679ba-2062">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2063">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2063">Definition</span></span>

<span data-ttu-id="679ba-2064">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2065">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2066">Se encuentra una palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="679ba-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="679ba-2067">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2067">The checksum passes.</span></span>

<span data-ttu-id="679ba-2068">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2069">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2070">No se encuentra ninguna palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="679ba-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="679ba-2071">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2071">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2072">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="679ba-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="679ba-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="679ba-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="679ba-2074">insee</span></span>
- <span data-ttu-id="679ba-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="679ba-2075">securité sociale</span></span>
- <span data-ttu-id="679ba-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="679ba-2076">securite sociale</span></span>
- <span data-ttu-id="679ba-2077">national id</span><span class="sxs-lookup"><span data-stu-id="679ba-2077">national id</span></span>
- <span data-ttu-id="679ba-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="679ba-2078">national identification</span></span>
- <span data-ttu-id="679ba-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="679ba-2079">numéro d'identité</span></span>
- <span data-ttu-id="679ba-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="679ba-2080">no d'identité</span></span>
- <span data-ttu-id="679ba-2081">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2081">no.</span></span> <span data-ttu-id="679ba-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="679ba-2082">d'identité</span></span>
- <span data-ttu-id="679ba-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="679ba-2083">numero d'identite</span></span>
- <span data-ttu-id="679ba-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="679ba-2084">no d'identite</span></span>
- <span data-ttu-id="679ba-2085">No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2085">no.</span></span> <span data-ttu-id="679ba-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="679ba-2086">d'identite</span></span>
- <span data-ttu-id="679ba-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="679ba-2087">social security number</span></span>
- <span data-ttu-id="679ba-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="679ba-2088">social security code</span></span>
- <span data-ttu-id="679ba-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="679ba-2089">social insurance number</span></span>
- <span data-ttu-id="679ba-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="679ba-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="679ba-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="679ba-2091">d'identité nationale</span></span>
- <span data-ttu-id="679ba-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="679ba-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="679ba-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="679ba-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="679ba-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="679ba-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="679ba-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="679ba-2095">numéro de sécu</span></span>
- <span data-ttu-id="679ba-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="679ba-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="679ba-2097">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="679ba-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2098">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2098">Format</span></span>

<span data-ttu-id="679ba-2099">Combinación de 11 dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="679ba-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2100">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2100">Pattern</span></span>

<span data-ttu-id="679ba-2101">11 dígitos y letras (no distingue entre mayúsculas y minúsculas):</span><span class="sxs-lookup"><span data-stu-id="679ba-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="679ba-2102">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="679ba-2102">A digit or letter</span></span> 
- <span data-ttu-id="679ba-2103">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2103">Two digits</span></span> 
- <span data-ttu-id="679ba-2104">Seis dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="679ba-2104">Six digits or letters</span></span> 
- <span data-ttu-id="679ba-2105">Un dígito</span><span class="sxs-lookup"><span data-stu-id="679ba-2105">A digit</span></span> 
- <span data-ttu-id="679ba-2106">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="679ba-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2107">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2107">Checksum</span></span>

<span data-ttu-id="679ba-2108">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2109">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2109">Definition</span></span>

<span data-ttu-id="679ba-2110">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2111">La función Func_german_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2112">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="679ba-2113">Se encuentra una palabra clave de Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="679ba-2114">Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="679ba-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="679ba-2115">Se encuentra una palabra clave de Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="679ba-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="679ba-2116">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2116">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2117">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="679ba-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="679ba-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2119">Führerschein</span></span>
- <span data-ttu-id="679ba-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2120">Fuhrerschein</span></span>
- <span data-ttu-id="679ba-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2121">Fuehrerschein</span></span>
- <span data-ttu-id="679ba-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="679ba-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="679ba-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="679ba-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="679ba-2125">Führerschein-</span></span> 
- <span data-ttu-id="679ba-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="679ba-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="679ba-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="679ba-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="679ba-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="679ba-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="679ba-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="679ba-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="679ba-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="679ba-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="679ba-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="679ba-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="679ba-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="679ba-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="679ba-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="679ba-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="679ba-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="679ba-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="679ba-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="679ba-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="679ba-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="679ba-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="679ba-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="679ba-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="679ba-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="679ba-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="679ba-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="679ba-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="679ba-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="679ba-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="679ba-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="679ba-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="679ba-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="679ba-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="679ba-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="679ba-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="679ba-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="679ba-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="679ba-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="679ba-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="679ba-2152">LISTAS</span><span class="sxs-lookup"><span data-stu-id="679ba-2152">DL</span></span> 
- <span data-ttu-id="679ba-2153">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="679ba-2153">DLS</span></span>
- <span data-ttu-id="679ba-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-2154">Driv Lic</span></span> 
- <span data-ttu-id="679ba-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="679ba-2155">Driv Licen</span></span> 
- <span data-ttu-id="679ba-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="679ba-2156">Driv License</span></span>
- <span data-ttu-id="679ba-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2157">Driv Licenses</span></span> 
- <span data-ttu-id="679ba-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-2158">Driv Licence</span></span> 
- <span data-ttu-id="679ba-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-2159">Driv Licences</span></span> 
- <span data-ttu-id="679ba-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-2160">Driv Lic</span></span> 
- <span data-ttu-id="679ba-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="679ba-2161">Driver Licen</span></span> 
- <span data-ttu-id="679ba-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="679ba-2162">Driver License</span></span> 
- <span data-ttu-id="679ba-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2163">Driver Licenses</span></span> 
- <span data-ttu-id="679ba-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-2164">Driver Licence</span></span> 
- <span data-ttu-id="679ba-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-2165">Driver Licences</span></span> 
- <span data-ttu-id="679ba-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-2166">Drivers Lic</span></span> 
- <span data-ttu-id="679ba-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="679ba-2167">Drivers Licen</span></span> 
- <span data-ttu-id="679ba-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="679ba-2168">Drivers License</span></span> 
- <span data-ttu-id="679ba-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="679ba-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-2170">Drivers Licence</span></span> 
- <span data-ttu-id="679ba-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-2171">Drivers Licences</span></span> 
- <span data-ttu-id="679ba-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-2172">Driver's Lic</span></span> 
- <span data-ttu-id="679ba-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="679ba-2173">Driver's Licen</span></span> 
- <span data-ttu-id="679ba-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="679ba-2174">Driver's License</span></span> 
- <span data-ttu-id="679ba-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="679ba-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-2176">Driver's Licence</span></span> 
- <span data-ttu-id="679ba-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-2177">Driver's Licences</span></span> 
- <span data-ttu-id="679ba-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-2178">Driving Lic</span></span> 
- <span data-ttu-id="679ba-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="679ba-2179">Driving Licen</span></span> 
- <span data-ttu-id="679ba-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="679ba-2180">Driving License</span></span> 
- <span data-ttu-id="679ba-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2181">Driving Licenses</span></span> 
- <span data-ttu-id="679ba-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="679ba-2182">Driving Licence</span></span> 
- <span data-ttu-id="679ba-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="679ba-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="679ba-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="679ba-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="679ba-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="679ba-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="679ba-2187">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="679ba-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2188">No-Führerschein</span></span> 
- <span data-ttu-id="679ba-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="679ba-2190">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="679ba-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2191">N-Führerschein</span></span> 
- <span data-ttu-id="679ba-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="679ba-2193">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="679ba-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="679ba-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="679ba-2196">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="679ba-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2197">No-Führerschein</span></span> 
- <span data-ttu-id="679ba-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="679ba-2199">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="679ba-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2200">N-Führerschein</span></span> 
- <span data-ttu-id="679ba-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="679ba-2202">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="679ba-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="679ba-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="679ba-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="679ba-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="679ba-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="679ba-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="679ba-2205">ausstellungsort</span></span>
- <span data-ttu-id="679ba-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="679ba-2206">ausstellende behöde</span></span>
- <span data-ttu-id="679ba-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="679ba-2207">ausstellende behorde</span></span>
- <span data-ttu-id="679ba-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="679ba-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="679ba-2209">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="679ba-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2210">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2210">Format</span></span>

<span data-ttu-id="679ba-2211">10 dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="679ba-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2212">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2212">Pattern</span></span>

<span data-ttu-id="679ba-2213">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="679ba-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="679ba-2214">El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="679ba-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="679ba-2215">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2215">Three digits</span></span> 
- <span data-ttu-id="679ba-2216">Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="679ba-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="679ba-2217">Un dígito</span><span class="sxs-lookup"><span data-stu-id="679ba-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2218">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2218">Checksum</span></span>

<span data-ttu-id="679ba-2219">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2220">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2220">Definition</span></span>

<span data-ttu-id="679ba-2221">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2222">La función Func_german_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2223">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="679ba-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="679ba-2224">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2224">The checksum passes.</span></span>

<span data-ttu-id="679ba-2225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2226">La función Func_german_passport_data encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2227">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="679ba-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="679ba-2228">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2228">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2229">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="679ba-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="679ba-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="679ba-2231">reisepass</span></span>
- <span data-ttu-id="679ba-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="679ba-2232">reisepasse</span></span>
- <span data-ttu-id="679ba-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2233">reisepassnummer</span></span>
- <span data-ttu-id="679ba-2234">usuarios</span><span class="sxs-lookup"><span data-stu-id="679ba-2234">passport</span></span>
- <span data-ttu-id="679ba-2235">passports</span><span class="sxs-lookup"><span data-stu-id="679ba-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="679ba-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="679ba-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="679ba-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="679ba-2237">geburtsdatum</span></span>
- <span data-ttu-id="679ba-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="679ba-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="679ba-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="679ba-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="679ba-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="679ba-2241">No-Reisepass NR-Reisepass</span><span class="sxs-lookup"><span data-stu-id="679ba-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="679ba-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="679ba-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="679ba-2243">Reisepass-NR</span><span class="sxs-lookup"><span data-stu-id="679ba-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="679ba-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="679ba-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="679ba-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="679ba-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="679ba-2246">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="679ba-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2247">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2247">Format</span></span>

<span data-ttu-id="679ba-2248">Desde el 1 de noviembre de 2010: nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="679ba-2249">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2250">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2250">Pattern</span></span>

<span data-ttu-id="679ba-2251">Desde el 1 de noviembre de 2010:</span><span class="sxs-lookup"><span data-stu-id="679ba-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="679ba-2252">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-2253">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2253">Eight digits</span></span>

<span data-ttu-id="679ba-2254">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:</span><span class="sxs-lookup"><span data-stu-id="679ba-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="679ba-2255">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2256">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2256">Checksum</span></span>

<span data-ttu-id="679ba-2257">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2258">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2258">Definition</span></span>

<span data-ttu-id="679ba-2259">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2260">La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2261">Se encuentra una palabra clave de Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2262">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="679ba-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="679ba-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="679ba-2264">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-2264">Identity Card</span></span>
- <span data-ttu-id="679ba-2265">ID</span><span class="sxs-lookup"><span data-stu-id="679ba-2265">ID</span></span>
- <span data-ttu-id="679ba-2266">Determinación</span><span class="sxs-lookup"><span data-stu-id="679ba-2266">Identification</span></span>
- <span data-ttu-id="679ba-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="679ba-2267">Personalausweis</span></span>
- <span data-ttu-id="679ba-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="679ba-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="679ba-2269">Ausweis</span></span>
- <span data-ttu-id="679ba-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="679ba-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="679ba-2271">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="679ba-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2272">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2272">Format</span></span>

<span data-ttu-id="679ba-2273">Combinación de 7 u 8 letras y números más un guión</span><span class="sxs-lookup"><span data-stu-id="679ba-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2274">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2274">Pattern</span></span>

<span data-ttu-id="679ba-2275">Siete letras y números (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="679ba-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="679ba-2276">Una letra (cualquier letra del alfabeto griego) </span><span class="sxs-lookup"><span data-stu-id="679ba-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="679ba-2277">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-2277">A dash</span></span> 
- <span data-ttu-id="679ba-2278">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2278">Six digits</span></span>

<span data-ttu-id="679ba-2279">Ocho letras y números (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="679ba-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="679ba-2280">Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="679ba-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="679ba-2281">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-2281">A dash</span></span> 
- <span data-ttu-id="679ba-2282">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2283">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2283">Checksum</span></span>

<span data-ttu-id="679ba-2284">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2285">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2285">Definition</span></span>

<span data-ttu-id="679ba-2286">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2287">La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2288">Se encuentra una palabra clave de Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2289">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="679ba-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="679ba-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="679ba-2291">Tarjeta de identidad griega</span><span class="sxs-lookup"><span data-stu-id="679ba-2291">Greek identity Card</span></span>
- <span data-ttu-id="679ba-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="679ba-2292">Tautotita</span></span>
- <span data-ttu-id="679ba-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="679ba-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="679ba-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="679ba-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="679ba-2295">Número de tarjeta de identidad de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="679ba-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2296">Format</span></span>

<span data-ttu-id="679ba-2297">Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final</span><span class="sxs-lookup"><span data-stu-id="679ba-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2298">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2298">Pattern</span></span>

<span data-ttu-id="679ba-2299">Combinación de 8 o 9 letras:</span><span class="sxs-lookup"><span data-stu-id="679ba-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="679ba-2300">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-2301">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2301">Six digits</span></span> 
- <span data-ttu-id="679ba-2302">El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="679ba-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2303">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2303">Checksum</span></span>

<span data-ttu-id="679ba-2304">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2305">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2305">Definition</span></span>

<span data-ttu-id="679ba-2306">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2307">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2308">Se encuentra una palabra clave de Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="679ba-2309">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2309">The checksum passes.</span></span>

<span data-ttu-id="679ba-2310">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2311">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2312">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2312">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2313">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="679ba-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="679ba-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="679ba-2315">tarjeta de identidad de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="679ba-2315">hong kong identity card</span></span>
- <span data-ttu-id="679ba-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="679ba-2316">HKIDC</span></span>
- <span data-ttu-id="679ba-2317">id card</span><span class="sxs-lookup"><span data-stu-id="679ba-2317">id card</span></span>
- <span data-ttu-id="679ba-2318">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-2318">identity card</span></span>
- <span data-ttu-id="679ba-2319">tarjeta de identidad HK</span><span class="sxs-lookup"><span data-stu-id="679ba-2319">hk identity card</span></span>
- <span data-ttu-id="679ba-2320">ID de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="679ba-2320">hong kong id</span></span>
- <span data-ttu-id="679ba-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2321">香港身份證</span></span>
- <span data-ttu-id="679ba-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="679ba-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2323">身份證</span></span>
- <span data-ttu-id="679ba-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="679ba-2324">身份証</span></span>
- <span data-ttu-id="679ba-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-2325">身分證</span></span>
- <span data-ttu-id="679ba-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="679ba-2326">身分証</span></span>
- <span data-ttu-id="679ba-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="679ba-2327">香港身份証</span></span>
- <span data-ttu-id="679ba-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-2328">香港身分證</span></span>
- <span data-ttu-id="679ba-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="679ba-2329">香港身分証</span></span>
- <span data-ttu-id="679ba-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2330">香港身份證</span></span>
- <span data-ttu-id="679ba-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2331">香港居民身份證</span></span>
- <span data-ttu-id="679ba-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="679ba-2332">香港居民身份証</span></span>
- <span data-ttu-id="679ba-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-2333">香港居民身分證</span></span>
- <span data-ttu-id="679ba-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="679ba-2334">香港居民身分証</span></span>
- <span data-ttu-id="679ba-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="679ba-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="679ba-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="679ba-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="679ba-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="679ba-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="679ba-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="679ba-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="679ba-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="679ba-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="679ba-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="679ba-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="679ba-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="679ba-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="679ba-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="679ba-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="679ba-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="679ba-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="679ba-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="679ba-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="679ba-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="679ba-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="679ba-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="679ba-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="679ba-2351">Número de cuenta permanente de India (PAN)</span><span class="sxs-lookup"><span data-stu-id="679ba-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2352">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2352">Format</span></span>

<span data-ttu-id="679ba-2353">10 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2354">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2354">Pattern</span></span>

<span data-ttu-id="679ba-2355">10 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2355">10 letters or digits:</span></span>
- <span data-ttu-id="679ba-2356">Cinco letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-2357">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2357">Four digits</span></span> 
- <span data-ttu-id="679ba-2358">Una letra que es un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="679ba-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2359">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2359">Checksum</span></span>

<span data-ttu-id="679ba-2360">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2361">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2361">Definition</span></span>

<span data-ttu-id="679ba-2362">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2363">La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2364">Se encuentra una palabra clave de Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="679ba-2365">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="679ba-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="679ba-2368">Número de cuenta permanente</span><span class="sxs-lookup"><span data-stu-id="679ba-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="679ba-2369">MANO</span><span class="sxs-lookup"><span data-stu-id="679ba-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="679ba-2370">Número de identificación único (Aadhaar) de la India</span><span class="sxs-lookup"><span data-stu-id="679ba-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2371">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2371">Format</span></span>

<span data-ttu-id="679ba-2372">12 dígitos que contienen espacios o guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="679ba-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2373">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2373">Pattern</span></span>

<span data-ttu-id="679ba-2374">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2374">12 digits:</span></span>
- <span data-ttu-id="679ba-2375">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2375">Four digits</span></span> 
- <span data-ttu-id="679ba-2376">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="679ba-2376">An optional space or dash</span></span> 
- <span data-ttu-id="679ba-2377">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2377">Four digits</span></span> 
- <span data-ttu-id="679ba-2378">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="679ba-2378">An optional space or dash</span></span> 
- <span data-ttu-id="679ba-2379">El dígito final que es el dígito de control</span><span class="sxs-lookup"><span data-stu-id="679ba-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2380">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2380">Checksum</span></span>

<span data-ttu-id="679ba-2381">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2382">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2382">Definition</span></span>

<span data-ttu-id="679ba-2383">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="679ba-2384">Se encuentra una palabra clave de Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="679ba-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="679ba-2385">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2385">The checksum passes.</span></span>
<span data-ttu-id="679ba-2386">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="679ba-2387">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>

### Keywords
   
#### Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## Indonesia Identity Card (KTP) Number

### Format

16 digits containing optional periods

### Pattern

16 digits:
- Two-digit province code 
- A period (optional) 
- Two-digit regency or city code 
- Two-digit subdistrict code 
- A period (optional) 
- Six digits in the format DDMMYY which are the date of birth 
- A period (optional) 
- Four digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.
- A keyword from Keyword_indonesia_id_card is found.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.

```
<!-- Indonesia Identity Card (KTP) Number -->
<span data-ttu-id="679ba-2388"><Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Regex_indonesia_id_card"/> <Match idRef="Keyword_indonesia_id_card"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_indonesia_id_card"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="679ba-2388"></span></span>
```

### Keywords
   
#### Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## International Banking Account Number (IBAN)

### Format

Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)

### Pattern

Pattern must include all of the following:

- Two-letter country code
- Two check digits (followed by an optional space) 
- 1-7 groups of four letters or digits (can be separated by spaces)
- 1-3 letters or digits

The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_iban finds content that matches the pattern.
- The checksum passes.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2389">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2389">Keywords</span></span>

<span data-ttu-id="679ba-2390">Ninguno</span><span class="sxs-lookup"><span data-stu-id="679ba-2390">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="679ba-2391">dirección IP</span><span class="sxs-lookup"><span data-stu-id="679ba-2391">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2392">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2392">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="679ba-2393">IPv4</span><span class="sxs-lookup"><span data-stu-id="679ba-2393">IPv4:</span></span>
<span data-ttu-id="679ba-2394">Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="679ba-2394">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="679ba-2395">Protocolo</span><span class="sxs-lookup"><span data-stu-id="679ba-2395">IPv6:</span></span>
<span data-ttu-id="679ba-2396"> Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)</span><span class="sxs-lookup"><span data-stu-id="679ba-2396">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2397">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2397">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2398">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2398">Checksum</span></span>

<span data-ttu-id="679ba-2399">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2399">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2400">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2400">Definition</span></span>

<span data-ttu-id="679ba-2401">Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2401">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2402">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2402">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2403">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="679ba-2403">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="679ba-2404">Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2404">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2405">La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2405">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2406">Se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="679ba-2406">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="679ba-2407">Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2407">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2408">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2408">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2409">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="679ba-2409">No keyword from Keyword_ipaddress is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2410">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2410">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="679ba-2411">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="679ba-2411">Keyword_ipaddress</span></span>

- <span data-ttu-id="679ba-2412">IP (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-2412">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="679ba-2413">dirección IP</span><span class="sxs-lookup"><span data-stu-id="679ba-2413">ip address</span></span> 
- <span data-ttu-id="679ba-2414">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="679ba-2414">ip addresses</span></span>
- <span data-ttu-id="679ba-2415">internet protocol</span><span class="sxs-lookup"><span data-stu-id="679ba-2415">internet protocol</span></span>
- <span data-ttu-id="679ba-2416">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="679ba-2416">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="679ba-2417">Clasificación Internacional de enfermedades (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="679ba-2417">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2418">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2418">Format</span></span>

<span data-ttu-id="679ba-2419">Dictionary</span><span class="sxs-lookup"><span data-stu-id="679ba-2419">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2420">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2420">Pattern</span></span>

<span data-ttu-id="679ba-2421">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2421">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2422">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2422">Checksum</span></span>

<span data-ttu-id="679ba-2423">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2424">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2424">Definition</span></span>

<span data-ttu-id="679ba-2425">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2425">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2426">Se encuentra una palabra clave de Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="679ba-2426">A keyword from Dictionary_icd_10_cm is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="679ba-2427">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2427">Keywords</span></span>

<span data-ttu-id="679ba-2428">Cualquier término del Diccionario de palabras clave de Dictionary_icd_10_cm, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="679ba-2428">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="679ba-2429">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="679ba-2429">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="679ba-2430">Clasificación Internacional de enfermedades (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="679ba-2430">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2431">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2431">Format</span></span>

<span data-ttu-id="679ba-2432">Dictionary</span><span class="sxs-lookup"><span data-stu-id="679ba-2432">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2433">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2433">Pattern</span></span>

<span data-ttu-id="679ba-2434">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2434">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2435">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2435">Checksum</span></span>

<span data-ttu-id="679ba-2436">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2436">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2437">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2437">Definition</span></span>

<span data-ttu-id="679ba-2438">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2438">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2439">Se encuentra una palabra clave de Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="679ba-2439">A keyword from Dictionary_icd_9_cm is found.</span></span>

```xml
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2440">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2440">Keywords</span></span>

<span data-ttu-id="679ba-2441">Cualquier término del Diccionario de palabras clave de Dictionary_icd_9_cm, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="679ba-2441">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="679ba-2442">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="679ba-2442">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="679ba-2443">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="679ba-2443">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2444">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2444">Format</span></span>

<span data-ttu-id="679ba-2445">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="679ba-2445">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="679ba-2446">Siete dígitos seguidos por 1 o 2 letras </span><span class="sxs-lookup"><span data-stu-id="679ba-2446">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="679ba-2447">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="679ba-2447">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="679ba-2448">Siete dígitos seguidos por dos letras</span><span class="sxs-lookup"><span data-stu-id="679ba-2448">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2449">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2449">Pattern</span></span>

<span data-ttu-id="679ba-2450">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="679ba-2450">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="679ba-2451">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-2451">Seven digits</span></span> 
- <span data-ttu-id="679ba-2452">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-2452">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="679ba-2453">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="679ba-2453">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="679ba-2454">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-2454">Seven digits</span></span> 
- <span data-ttu-id="679ba-2455">Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético </span><span class="sxs-lookup"><span data-stu-id="679ba-2455">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="679ba-2456">La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-2456">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2457">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2457">Checksum</span></span>

<span data-ttu-id="679ba-2458">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2458">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2459">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2459">Definition</span></span>

<span data-ttu-id="679ba-2460">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2461">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2461">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2462">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-2462">One of the following is true:</span></span>
    - <span data-ttu-id="679ba-2463">Se encuentra una palabra clave de Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="679ba-2463">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="679ba-2464">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-2464">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-2465">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2465">The checksum passes.</span></span>

<span data-ttu-id="679ba-2466">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2467">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2467">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2468">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2468">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2469">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2469">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="679ba-2470">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="679ba-2470">Keyword_ireland_pps</span></span>

- <span data-ttu-id="679ba-2471">Número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="679ba-2471">Personal Public Service Number</span></span> 
- <span data-ttu-id="679ba-2472">Número de PPS</span><span class="sxs-lookup"><span data-stu-id="679ba-2472">PPS Number</span></span> 
- <span data-ttu-id="679ba-2473">Núm. PPS
</span><span class="sxs-lookup"><span data-stu-id="679ba-2473">PPS Num</span></span> 
- <span data-ttu-id="679ba-2474">N.º PPS</span><span class="sxs-lookup"><span data-stu-id="679ba-2474">PPS No.</span></span> 
- <span data-ttu-id="679ba-2475">N.ro PPS</span><span class="sxs-lookup"><span data-stu-id="679ba-2475">PPS #</span></span> 
- <span data-ttu-id="679ba-2476">PPS #</span><span class="sxs-lookup"><span data-stu-id="679ba-2476">PPS#</span></span> 
- <span data-ttu-id="679ba-2477">PPSN</span><span class="sxs-lookup"><span data-stu-id="679ba-2477">PPSN</span></span> 
- <span data-ttu-id="679ba-2478">Tarjeta de servicios públicos</span><span class="sxs-lookup"><span data-stu-id="679ba-2478">Public Services Card</span></span> 
- <span data-ttu-id="679ba-2479">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="679ba-2479">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="679ba-2480">Uimh.</span><span class="sxs-lookup"><span data-stu-id="679ba-2480">Uimh.</span></span> <span data-ttu-id="679ba-2481">PSP</span><span class="sxs-lookup"><span data-stu-id="679ba-2481">PSP</span></span> 
- <span data-ttu-id="679ba-2482">PSP</span><span class="sxs-lookup"><span data-stu-id="679ba-2482">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="679ba-2483">Número de cuenta bancaria de Israel</span><span class="sxs-lookup"><span data-stu-id="679ba-2483">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2484">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2484">Format</span></span>

<span data-ttu-id="679ba-2485">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2485">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2486">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2486">Pattern</span></span>

<span data-ttu-id="679ba-2487">Con formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2487">Formatted:</span></span>
- <span data-ttu-id="679ba-2488">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2488">Two digits</span></span> 
- <span data-ttu-id="679ba-2489">Guion</span><span class="sxs-lookup"><span data-stu-id="679ba-2489">A dash</span></span> 
- <span data-ttu-id="679ba-2490">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2490">Three digits</span></span> 
- <span data-ttu-id="679ba-2491">Guion</span><span class="sxs-lookup"><span data-stu-id="679ba-2491">A dash</span></span> 
- <span data-ttu-id="679ba-2492">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2492">Eight digits</span></span>

<span data-ttu-id="679ba-2493">Sin formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2493">Unformatted:</span></span>
- <span data-ttu-id="679ba-2494">	13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2494">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2495">Checksum</span></span>

<span data-ttu-id="679ba-2496">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2496">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2497">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2497">Definition</span></span>

<span data-ttu-id="679ba-2498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2499">La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2499">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2500">Se encuentra una palabra clave de Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2500">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2501">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="679ba-2502">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2502">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="679ba-2503">Número de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="679ba-2503">Bank Account Number</span></span> 
- <span data-ttu-id="679ba-2504">Cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="679ba-2504">Bank Account</span></span> 
- <span data-ttu-id="679ba-2505">Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2505">Account Number</span></span> 
- <span data-ttu-id="679ba-2506">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="679ba-2506">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="679ba-2507">Identificación nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="679ba-2507">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2508">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2508">Format</span></span>

<span data-ttu-id="679ba-2509">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2509">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2510">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2510">Pattern</span></span>

<span data-ttu-id="679ba-2511">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2511">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2512">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2512">Checksum</span></span>

<span data-ttu-id="679ba-2513">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2514">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2514">Definition</span></span>

<span data-ttu-id="679ba-2515">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2515">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2516">La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2516">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2517">Se encuentra una palabra clave de Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="679ba-2517">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="679ba-2518">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2518">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2519">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2519">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="679ba-2520">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="679ba-2520">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="679ba-2521">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="679ba-2521">מספר זהות</span></span> 
- <span data-ttu-id="679ba-2522">National ID Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2522">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="679ba-2523">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="679ba-2523">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2524">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2524">Format</span></span>

<span data-ttu-id="679ba-2525">Una combinación de 10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2525">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2526">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2526">Pattern</span></span>

- <span data-ttu-id="679ba-2527">Una combinación de 10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2527">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="679ba-2528">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-2528">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-2529">La letra "A" o "V" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-2529">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-2530">Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado</span><span class="sxs-lookup"><span data-stu-id="679ba-2530">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="679ba-2531">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-2531">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2532">Checksum</span></span>

<span data-ttu-id="679ba-2533">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2533">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2534">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2534">Definition</span></span>

<span data-ttu-id="679ba-2535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2536">La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2536">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2537">Se encuentra una palabra clave de Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2537">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2538">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="679ba-2539">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2539">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="679ba-2540">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="679ba-2540">numero di patente di guida</span></span> 
- <span data-ttu-id="679ba-2541">patente di guida</span><span class="sxs-lookup"><span data-stu-id="679ba-2541">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="679ba-2542">Número de cuenta bancaria de Japón</span><span class="sxs-lookup"><span data-stu-id="679ba-2542">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2543">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2543">Format</span></span>

<span data-ttu-id="679ba-2544">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2544">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2545">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2545">Pattern</span></span>

<span data-ttu-id="679ba-2546">Número de cuenta bancaria:</span><span class="sxs-lookup"><span data-stu-id="679ba-2546">Bank account number:</span></span>
- <span data-ttu-id="679ba-2547">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2547">Seven or eight digits</span></span>
- <span data-ttu-id="679ba-2548">Código de sucursal del banco:</span><span class="sxs-lookup"><span data-stu-id="679ba-2548">Bank account branch code:</span></span>
- <span data-ttu-id="679ba-2549">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2549">Four digits</span></span> 
- <span data-ttu-id="679ba-2550">Un espacio o un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="679ba-2550">A space or dash (optional)</span></span> 
- <span data-ttu-id="679ba-2551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2551">Three digits</span></span>

<span data-ttu-id="679ba-2552">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2552">Checksum</span></span>

<span data-ttu-id="679ba-2553">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2553">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2554">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2554">Definition</span></span>

<span data-ttu-id="679ba-2555">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2555">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2556">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2556">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2557">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="679ba-2557">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="679ba-2558">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-2558">One of the following is true:</span></span>
- <span data-ttu-id="679ba-2559">La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2559">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2560">Se encuentra una palabra clave de Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="679ba-2560">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="679ba-2561">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2561">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2562">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2562">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2563">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="679ba-2563">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2564">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2564">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="679ba-2565">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="679ba-2565">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="679ba-2566">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2566">Checking Account Number</span></span> 
- <span data-ttu-id="679ba-2567">Checking Account</span><span class="sxs-lookup"><span data-stu-id="679ba-2567">Checking Account</span></span> 
- <span data-ttu-id="679ba-2568">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-2568">Checking Account #</span></span> 
- <span data-ttu-id="679ba-2569">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2569">Checking Acct Number</span></span> 
- <span data-ttu-id="679ba-2570">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-2570">Checking Acct #</span></span> 
- <span data-ttu-id="679ba-2571">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2571">Checking Acct No.</span></span> 
- <span data-ttu-id="679ba-2572">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2572">Checking Account No.</span></span> 
- <span data-ttu-id="679ba-2573">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2573">Bank Account Number</span></span> 
- <span data-ttu-id="679ba-2574">Bank Account</span><span class="sxs-lookup"><span data-stu-id="679ba-2574">Bank Account</span></span> 
- <span data-ttu-id="679ba-2575">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-2575">Bank Account #</span></span> 
- <span data-ttu-id="679ba-2576">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2576">Bank Acct Number</span></span> 
- <span data-ttu-id="679ba-2577">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-2577">Bank Acct #</span></span> 
- <span data-ttu-id="679ba-2578">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2578">Bank Acct No.</span></span> 
- <span data-ttu-id="679ba-2579">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2579">Bank Account No.</span></span> 
- <span data-ttu-id="679ba-2580">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2580">Savings Account Number</span></span> 
- <span data-ttu-id="679ba-2581">Savings Account</span><span class="sxs-lookup"><span data-stu-id="679ba-2581">Savings Account</span></span> 
- <span data-ttu-id="679ba-2582">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-2582">Savings Account #</span></span> 
- <span data-ttu-id="679ba-2583">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2583">Savings Acct Number</span></span> 
- <span data-ttu-id="679ba-2584">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-2584">Savings Acct #</span></span> 
- <span data-ttu-id="679ba-2585">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2585">Savings Acct No.</span></span> 
- <span data-ttu-id="679ba-2586">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2586">Savings Account No.</span></span> 
- <span data-ttu-id="679ba-2587">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2587">Debit Account Number</span></span> 
- <span data-ttu-id="679ba-2588">Debit Account</span><span class="sxs-lookup"><span data-stu-id="679ba-2588">Debit Account</span></span> 
- <span data-ttu-id="679ba-2589">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-2589">Debit Account #</span></span> 
- <span data-ttu-id="679ba-2590">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2590">Debit Acct Number</span></span> 
- <span data-ttu-id="679ba-2591">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-2591">Debit Acct #</span></span> 
- <span data-ttu-id="679ba-2592">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2592">Debit Acct No.</span></span> 
- <span data-ttu-id="679ba-2593">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2593">Debit Account No.</span></span> 
- <span data-ttu-id="679ba-2594">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="679ba-2594">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="679ba-2595">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="679ba-2595">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="679ba-2596">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="679ba-2596">＃勘定の確認</span></span> 
- <span data-ttu-id="679ba-2597">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="679ba-2597">勘定番号の確認</span></span> 
- <span data-ttu-id="679ba-2598">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="679ba-2598">口座番号の確認</span></span> 
- <span data-ttu-id="679ba-2599">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2599">銀行口座番号</span></span> 
- <span data-ttu-id="679ba-2600">銀行口座</span><span class="sxs-lookup"><span data-stu-id="679ba-2600">銀行口座</span></span> 
- <span data-ttu-id="679ba-2601">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2601">銀行口座＃</span></span> 
- <span data-ttu-id="679ba-2602">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2602">銀行の勘定番号</span></span> 
- <span data-ttu-id="679ba-2603">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2603">銀行のacct＃</span></span> 
- <span data-ttu-id="679ba-2604">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="679ba-2604">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="679ba-2605">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2605">銀行口座番号</span></span>
- <span data-ttu-id="679ba-2606">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2606">普通預金口座番号</span></span> 
- <span data-ttu-id="679ba-2607">預金口座</span><span class="sxs-lookup"><span data-stu-id="679ba-2607">預金口座</span></span> 
- <span data-ttu-id="679ba-2608">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2608">貯蓄口座＃</span></span> 
- <span data-ttu-id="679ba-2609">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="679ba-2609">貯蓄勘定の数</span></span> 
- <span data-ttu-id="679ba-2610">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2610">貯蓄勘定＃</span></span> 
- <span data-ttu-id="679ba-2611">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2611">貯蓄勘定番号</span></span> 
- <span data-ttu-id="679ba-2612">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2612">普通預金口座番号</span></span> 
- <span data-ttu-id="679ba-2613">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2613">引き落とし口座番号</span></span> 
- <span data-ttu-id="679ba-2614">口座番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2614">口座番号</span></span> 
- <span data-ttu-id="679ba-2615">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2615">口座番号＃</span></span> 
- <span data-ttu-id="679ba-2616">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2616">デビットのacct番号</span></span> 
- <span data-ttu-id="679ba-2617">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2617">デビット勘定＃</span></span> 
- <span data-ttu-id="679ba-2618">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2618">デビットACCTの番号</span></span> 
- <span data-ttu-id="679ba-2619">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2619">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="679ba-2620">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="679ba-2620">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="679ba-2621">Otemachi</span><span class="sxs-lookup"><span data-stu-id="679ba-2621">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="679ba-2622">Número de licencia de conductor de Japón</span><span class="sxs-lookup"><span data-stu-id="679ba-2622">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2623">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2623">Format</span></span>

<span data-ttu-id="679ba-2624">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2624">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2625">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2625">Pattern</span></span>

<span data-ttu-id="679ba-2626">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2626">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2627">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2627">Checksum</span></span>

<span data-ttu-id="679ba-2628">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2628">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2629">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2629">Definition</span></span>

<span data-ttu-id="679ba-2630">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2631">La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2631">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2632">Se encuentra una palabra clave de Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2632">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2633">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2633">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="679ba-2634">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2634">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="679ba-2635">listas #</span><span class="sxs-lookup"><span data-stu-id="679ba-2635">dl#</span></span> 
- <span data-ttu-id="679ba-2636">LISTAS</span><span class="sxs-lookup"><span data-stu-id="679ba-2636">DL＃</span></span> 
- <span data-ttu-id="679ba-2637">distribución #</span><span class="sxs-lookup"><span data-stu-id="679ba-2637">dls#</span></span> 
- <span data-ttu-id="679ba-2638">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="679ba-2638">DLS＃</span></span> 
- <span data-ttu-id="679ba-2639">driver license</span><span class="sxs-lookup"><span data-stu-id="679ba-2639">driver license</span></span> 
- <span data-ttu-id="679ba-2640">driver licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2640">driver licenses</span></span> 
- <span data-ttu-id="679ba-2641">drivers license</span><span class="sxs-lookup"><span data-stu-id="679ba-2641">drivers license</span></span> 
- <span data-ttu-id="679ba-2642">driver's license</span><span class="sxs-lookup"><span data-stu-id="679ba-2642">driver's license</span></span> 
- <span data-ttu-id="679ba-2643">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2643">drivers licenses</span></span> 
- <span data-ttu-id="679ba-2644">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-2644">driver's licenses</span></span> 
- <span data-ttu-id="679ba-2645">driving licence</span><span class="sxs-lookup"><span data-stu-id="679ba-2645">driving licence</span></span> 
- <span data-ttu-id="679ba-2646">Lic #</span><span class="sxs-lookup"><span data-stu-id="679ba-2646">lic#</span></span> 
- <span data-ttu-id="679ba-2647">Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-2647">LIC＃</span></span> 
- <span data-ttu-id="679ba-2648">conducción #</span><span class="sxs-lookup"><span data-stu-id="679ba-2648">lics#</span></span> 
- <span data-ttu-id="679ba-2649">state id</span><span class="sxs-lookup"><span data-stu-id="679ba-2649">state id</span></span> 
- <span data-ttu-id="679ba-2650">state identification</span><span class="sxs-lookup"><span data-stu-id="679ba-2650">state identification</span></span> 
- <span data-ttu-id="679ba-2651">state identification number</span><span class="sxs-lookup"><span data-stu-id="679ba-2651">state identification number</span></span> 
- <span data-ttu-id="679ba-2652">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2652">低所得国＃</span></span> 
- <span data-ttu-id="679ba-2653">免許証</span><span class="sxs-lookup"><span data-stu-id="679ba-2653">免許証</span></span> 
- <span data-ttu-id="679ba-2654">状態ID</span><span class="sxs-lookup"><span data-stu-id="679ba-2654">状態ID</span></span>
- <span data-ttu-id="679ba-2655">状態の識別</span><span class="sxs-lookup"><span data-stu-id="679ba-2655">状態の識別</span></span> 
- <span data-ttu-id="679ba-2656">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2656">状態の識別番号</span></span> 
- <span data-ttu-id="679ba-2657">運転免許</span><span class="sxs-lookup"><span data-stu-id="679ba-2657">運転免許</span></span> 
- <span data-ttu-id="679ba-2658">運転免許証</span><span class="sxs-lookup"><span data-stu-id="679ba-2658">運転免許証</span></span> 
- <span data-ttu-id="679ba-2659">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2659">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="679ba-2660">Número de pasaporte de Japón</span><span class="sxs-lookup"><span data-stu-id="679ba-2660">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2661">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2661">Format</span></span>

<span data-ttu-id="679ba-2662">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2662">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2663">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2663">Pattern</span></span>

<span data-ttu-id="679ba-2664">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2664">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2665">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2665">Checksum</span></span>

<span data-ttu-id="679ba-2666">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2666">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2667">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2667">Definition</span></span>

<span data-ttu-id="679ba-2668">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2668">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2669">La función Func_jp_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2669">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2670">Se encuentra una palabra clave de Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="679ba-2670">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2671">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2671">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="679ba-2672">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-2672">Keyword_jp_passport</span></span>

- <span data-ttu-id="679ba-2673">パスポート</span><span class="sxs-lookup"><span data-stu-id="679ba-2673">パスポート</span></span> 
- <span data-ttu-id="679ba-2674">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2674">パスポート番号</span></span> 
- <span data-ttu-id="679ba-2675">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="679ba-2675">パスポートのNum</span></span> 
- <span data-ttu-id="679ba-2676">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="679ba-2676">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="679ba-2677">Número de registro de residente de Japón</span><span class="sxs-lookup"><span data-stu-id="679ba-2677">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2678">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2678">Format</span></span>

<span data-ttu-id="679ba-2679">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2679">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2680">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2680">Pattern</span></span>

<span data-ttu-id="679ba-2681">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2681">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2682">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2682">Checksum</span></span>

<span data-ttu-id="679ba-2683">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2683">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2684">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2684">Definition</span></span>

<span data-ttu-id="679ba-2685">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2685">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2686">La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2686">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2687">Se encuentra una palabra clave de Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2687">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2688">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2688">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="679ba-2689">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2689">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="679ba-2690">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2690">Resident Registration Number</span></span>
- <span data-ttu-id="679ba-2691">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2691">Resident Register Number</span></span> 
- <span data-ttu-id="679ba-2692">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2692">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="679ba-2693">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2693">Resident Registration No.</span></span> 
- <span data-ttu-id="679ba-2694">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2694">Resident Register No.</span></span> 
- <span data-ttu-id="679ba-2695">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2695">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="679ba-2696">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2696">Basic Resident Register No.</span></span> 
- <span data-ttu-id="679ba-2697">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="679ba-2697">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="679ba-2698">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2698">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="679ba-2699">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="679ba-2699">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="679ba-2700">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2700">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="679ba-2701">Número de Seguridad Social de Japón (SIN)</span><span class="sxs-lookup"><span data-stu-id="679ba-2701">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2702">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2702">Format</span></span>

<span data-ttu-id="679ba-2703">De 7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2703">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2704">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2704">Pattern</span></span>

<span data-ttu-id="679ba-2705">7-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2705">7-12 digits:</span></span>
- <span data-ttu-id="679ba-2706">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2706">Four digits</span></span> 
- <span data-ttu-id="679ba-2707">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="679ba-2707">A hyphen (optional)</span></span> 
- <span data-ttu-id="679ba-2708">Seis dígitos o</span><span class="sxs-lookup"><span data-stu-id="679ba-2708">Six digits OR</span></span>
- <span data-ttu-id="679ba-2709">De 7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2709">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2710">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2710">Checksum</span></span>

<span data-ttu-id="679ba-2711">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2711">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2712">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2712">Definition</span></span>

<span data-ttu-id="679ba-2713">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2713">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2714">La función Func_jp_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2714">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2715">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="679ba-2715">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="679ba-2716">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2716">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2717">La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2717">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2718">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="679ba-2718">A keyword from Keyword_jp_sin is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2719">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2719">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="679ba-2720">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="679ba-2720">Keyword_jp_sin</span></span>

- <span data-ttu-id="679ba-2721">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="679ba-2721">Social Insurance No.</span></span> 
- <span data-ttu-id="679ba-2722">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="679ba-2722">Social Insurance Num</span></span> 
- <span data-ttu-id="679ba-2723">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="679ba-2723">Social Insurance Number</span></span> 
- <span data-ttu-id="679ba-2724">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="679ba-2724">社会保険のテンキー</span></span> 
- <span data-ttu-id="679ba-2725">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2725">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="679ba-2726">Número de tarjeta de residencia japonés</span><span class="sxs-lookup"><span data-stu-id="679ba-2726">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2727">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2727">Format</span></span>

<span data-ttu-id="679ba-2728">12 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2728">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2729">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2729">Pattern</span></span>

<span data-ttu-id="679ba-2730">12 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2730">12 letters and digits:</span></span>
- <span data-ttu-id="679ba-2731">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-2731">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="679ba-2732">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2732">Eight digits</span></span> 
- <span data-ttu-id="679ba-2733">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-2733">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2734">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2734">Checksum</span></span>

<span data-ttu-id="679ba-2735">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2736">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2736">Definition</span></span>

<span data-ttu-id="679ba-2737">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2738">La expresión regular Regex_jp_residence_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2738">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2739">Se encuentra una palabra clave de Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2739">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2740">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2740">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="679ba-2741">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2741">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="679ba-2742">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="679ba-2742">Residence card number</span></span>
- <span data-ttu-id="679ba-2743">Nº de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="679ba-2743">Residence card no</span></span>
- <span data-ttu-id="679ba-2744">Tarjeta de residencia #</span><span class="sxs-lookup"><span data-stu-id="679ba-2744">Residence card #</span></span>
- <span data-ttu-id="679ba-2745">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="679ba-2745">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="679ba-2746">Número de la tarjeta de identificación de Malasia</span><span class="sxs-lookup"><span data-stu-id="679ba-2746">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2747">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2747">Format</span></span>

<span data-ttu-id="679ba-2748">12 dígitos que contienen guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="679ba-2748">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2749">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2749">Pattern</span></span>

<span data-ttu-id="679ba-2750">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2750">12 digits:</span></span>
- <span data-ttu-id="679ba-2751">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-2751">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="679ba-2752">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="679ba-2752">A dash (optional)</span></span> 
- <span data-ttu-id="679ba-2753">Código de dos letras del lugar de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-2753">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="679ba-2754">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="679ba-2754">A dash (optional)</span></span> 
- <span data-ttu-id="679ba-2755">Tres dígitos aleatorios </span><span class="sxs-lookup"><span data-stu-id="679ba-2755">Three random digits</span></span> 
- <span data-ttu-id="679ba-2756">Código de género de un dígito</span><span class="sxs-lookup"><span data-stu-id="679ba-2756">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2757">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2757">Checksum</span></span>

<span data-ttu-id="679ba-2758">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2758">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2759">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2759">Definition</span></span>

<span data-ttu-id="679ba-2760">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2760">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2761">La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2761">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2762">Se encuentra una palabra clave de Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2762">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2763">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2763">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="679ba-2764">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2764">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="679ba-2765">tarjeta de aplicación digital</span><span class="sxs-lookup"><span data-stu-id="679ba-2765">digital application card</span></span>
- <span data-ttu-id="679ba-2766">i/c</span><span class="sxs-lookup"><span data-stu-id="679ba-2766">i/c</span></span>
- <span data-ttu-id="679ba-2767">i/c no</span><span class="sxs-lookup"><span data-stu-id="679ba-2767">i/c no</span></span>
- <span data-ttu-id="679ba-2768">i</span><span class="sxs-lookup"><span data-stu-id="679ba-2768">ic</span></span>
- <span data-ttu-id="679ba-2769">no IC</span><span class="sxs-lookup"><span data-stu-id="679ba-2769">ic no</span></span>
- <span data-ttu-id="679ba-2770">id card</span><span class="sxs-lookup"><span data-stu-id="679ba-2770">id card</span></span>
- <span data-ttu-id="679ba-2771">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="679ba-2771">identification Card</span></span>
- <span data-ttu-id="679ba-2772">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-2772">identity card</span></span>
- <span data-ttu-id="679ba-2773">k/p</span><span class="sxs-lookup"><span data-stu-id="679ba-2773">k/p</span></span>
- <span data-ttu-id="679ba-2774">k/p no</span><span class="sxs-lookup"><span data-stu-id="679ba-2774">k/p no</span></span>
- <span data-ttu-id="679ba-2775">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="679ba-2775">kad akuan diri</span></span>
- <span data-ttu-id="679ba-2776">Kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="679ba-2776">kad aplikasi digital</span></span>
- <span data-ttu-id="679ba-2777">Kad pengenalan Malasia</span><span class="sxs-lookup"><span data-stu-id="679ba-2777">kad pengenalan malaysia</span></span>
- <span data-ttu-id="679ba-2778">PK</span><span class="sxs-lookup"><span data-stu-id="679ba-2778">kp</span></span>
- <span data-ttu-id="679ba-2779">KP no</span><span class="sxs-lookup"><span data-stu-id="679ba-2779">kp no</span></span>
- <span data-ttu-id="679ba-2780">mykad</span><span class="sxs-lookup"><span data-stu-id="679ba-2780">mykad</span></span>
- <span data-ttu-id="679ba-2781">mykas</span><span class="sxs-lookup"><span data-stu-id="679ba-2781">mykas</span></span>
- <span data-ttu-id="679ba-2782">mykid</span><span class="sxs-lookup"><span data-stu-id="679ba-2782">mykid</span></span>
- <span data-ttu-id="679ba-2783">mypr</span><span class="sxs-lookup"><span data-stu-id="679ba-2783">mypr</span></span>
- <span data-ttu-id="679ba-2784">mytentera</span><span class="sxs-lookup"><span data-stu-id="679ba-2784">mytentera</span></span>
- <span data-ttu-id="679ba-2785">tarjeta de identidad de Malasia</span><span class="sxs-lookup"><span data-stu-id="679ba-2785">malaysia identity card</span></span>
- <span data-ttu-id="679ba-2786">tarjeta de identidad malasio</span><span class="sxs-lookup"><span data-stu-id="679ba-2786">malaysian identity card</span></span>
- <span data-ttu-id="679ba-2787">nric</span><span class="sxs-lookup"><span data-stu-id="679ba-2787">nric</span></span>
- <span data-ttu-id="679ba-2788">tarjeta de identificación personal</span><span class="sxs-lookup"><span data-stu-id="679ba-2788">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="679ba-2789">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="679ba-2789">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2790">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2790">Format</span></span>

<span data-ttu-id="679ba-2791">8 o 9 dígitos que contienen espacios opcionales</span><span class="sxs-lookup"><span data-stu-id="679ba-2791">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2792">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2792">Pattern</span></span>

<span data-ttu-id="679ba-2793">8 o 9 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2793">8-9 digits:</span></span>
- <span data-ttu-id="679ba-2794">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2794">Three digits</span></span> 
- <span data-ttu-id="679ba-2795">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="679ba-2795">A space (optional)</span></span> 
- <span data-ttu-id="679ba-2796">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2796">Three digits</span></span> 
- <span data-ttu-id="679ba-2797">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="679ba-2797">A space (optional)</span></span> 
- <span data-ttu-id="679ba-2798">2 o 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2798">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2799">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2799">Checksum</span></span>

<span data-ttu-id="679ba-2800">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2801">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2801">Definition</span></span>

<span data-ttu-id="679ba-2802">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2803">La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2803">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2804">Se encuentra una palabra clave de Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="679ba-2804">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="679ba-2805">La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-2805">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-2806">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2806">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2807">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2807">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="679ba-2808">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="679ba-2808">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="679ba-2809">Número de servicio de ciudadanía</span><span class="sxs-lookup"><span data-stu-id="679ba-2809">Citizen service number</span></span> 
- <span data-ttu-id="679ba-2810">BSN</span><span class="sxs-lookup"><span data-stu-id="679ba-2810">BSN</span></span> 
- <span data-ttu-id="679ba-2811">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2811">Burgerservicenummer</span></span> 
- <span data-ttu-id="679ba-2812">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2812">Sofinummer</span></span> 
- <span data-ttu-id="679ba-2813">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2813">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="679ba-2814">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2814">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="679ba-2815">Número de Ministerio de salud de Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="679ba-2815">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2816">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2816">Format</span></span>

<span data-ttu-id="679ba-2817">Tres letras, un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2817">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2818">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2818">Pattern</span></span>

<span data-ttu-id="679ba-2819">Tres letras (no distingue entre mayúsculas y minúsculas), un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2819">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2820">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2820">Checksum</span></span>

<span data-ttu-id="679ba-2821">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2821">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2822">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2822">Definition</span></span>

<span data-ttu-id="679ba-2823">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2823">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2824">La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2824">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2825">Se encuentra una palabra clave de Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="679ba-2825">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="679ba-2826">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2826">The checksum passes.</span></span>

```xml
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

<span data-ttu-id="679ba-2827">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2827">Keywords</span></span>

<span data-ttu-id="679ba-2828">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="679ba-2828">Keyword_nz_terms</span></span>

- <span data-ttu-id="679ba-2829">NHI</span><span class="sxs-lookup"><span data-stu-id="679ba-2829">NHI</span></span> 
- <span data-ttu-id="679ba-2830">New Zealand</span><span class="sxs-lookup"><span data-stu-id="679ba-2830">New Zealand</span></span> 
- <span data-ttu-id="679ba-2831">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-2831">Health</span></span> 
- <span data-ttu-id="679ba-2832">régimen</span><span class="sxs-lookup"><span data-stu-id="679ba-2832">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="679ba-2833">Número de identificación de Noruega</span><span class="sxs-lookup"><span data-stu-id="679ba-2833">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2834">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2834">Format</span></span>

<span data-ttu-id="679ba-2835">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2835">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2836">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2836">Pattern</span></span>

<span data-ttu-id="679ba-2837">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2837">11 digits:</span></span>
- <span data-ttu-id="679ba-2838">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-2838">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="679ba-2839">Número individual de tres dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-2839">Three-digit individual number</span></span> 
- <span data-ttu-id="679ba-2840">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="679ba-2840">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2841">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2841">Checksum</span></span>

<span data-ttu-id="679ba-2842">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2842">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2843">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2843">Definition</span></span>

<span data-ttu-id="679ba-2844">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2844">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2845">La función Func_norway_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2845">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2846">Se encuentra una palabra clave de Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2846">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="679ba-2847">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2847">The checksum passes.</span></span>
- <span data-ttu-id="679ba-2848">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2848">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2849">La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2849">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2850">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2850">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2851">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2851">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="679ba-2852">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2852">Keyword_norway_id_number</span></span>

- <span data-ttu-id="679ba-2853">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="679ba-2853">Personal identification number</span></span>
- <span data-ttu-id="679ba-2854">Número de id. noruego</span><span class="sxs-lookup"><span data-stu-id="679ba-2854">Norwegian ID Number</span></span>
- <span data-ttu-id="679ba-2855">Número de id.</span><span class="sxs-lookup"><span data-stu-id="679ba-2855">ID Number</span></span>
- <span data-ttu-id="679ba-2856">Determinación</span><span class="sxs-lookup"><span data-stu-id="679ba-2856">Identification</span></span>
- <span data-ttu-id="679ba-2857">Personnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2857">Personnummer</span></span>
- <span data-ttu-id="679ba-2858">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="679ba-2858">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="679ba-2859">Número de id. universal unificado de Filipinas</span><span class="sxs-lookup"><span data-stu-id="679ba-2859">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2860">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2860">Format</span></span>

<span data-ttu-id="679ba-2861">12 dígitos separados por guiones</span><span class="sxs-lookup"><span data-stu-id="679ba-2861">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2862">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2862">Pattern</span></span>

<span data-ttu-id="679ba-2863">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2863">12 digits:</span></span>
- <span data-ttu-id="679ba-2864">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2864">Four digits</span></span> 
- <span data-ttu-id="679ba-2865">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-2865">A hyphen</span></span> 
- <span data-ttu-id="679ba-2866">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-2866">Seven digits</span></span> 
- <span data-ttu-id="679ba-2867">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-2867">A hyphen</span></span> 
- <span data-ttu-id="679ba-2868">Un dígito</span><span class="sxs-lookup"><span data-stu-id="679ba-2868">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2869">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2869">Checksum</span></span>

<span data-ttu-id="679ba-2870">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2870">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2871">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2871">Definition</span></span>

<span data-ttu-id="679ba-2872">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2873">La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2873">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2874">Se encuentra una palabra clave de Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="679ba-2874">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2875">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2875">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="679ba-2876">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="679ba-2876">Keyword_philippines_id</span></span>

- <span data-ttu-id="679ba-2877">Id. universal unificado
</span><span class="sxs-lookup"><span data-stu-id="679ba-2877">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="679ba-2878">UMID</span><span class="sxs-lookup"><span data-stu-id="679ba-2878">UMID</span></span> 
- <span data-ttu-id="679ba-2879">Tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-2879">Identity Card</span></span> 
- <span data-ttu-id="679ba-2880">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="679ba-2880">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="679ba-2881">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="679ba-2881">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2882">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2882">Format</span></span>

<span data-ttu-id="679ba-2883">Tres letras y seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2883">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2884">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2884">Pattern</span></span>

<span data-ttu-id="679ba-2885">Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2885">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2886">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2886">Checksum</span></span>

<span data-ttu-id="679ba-2887">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2887">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2888">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2888">Definition</span></span>

<span data-ttu-id="679ba-2889">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_polish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2889">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="679ba-2890">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2890">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="679ba-2891">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2891">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2892">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2892">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="679ba-2893">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2893">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="679ba-2894">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="679ba-2894">Dowód osobisty</span></span>
- <span data-ttu-id="679ba-2895">Numerar dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="679ba-2895">Numer dowodu osobistego</span></span>
- <span data-ttu-id="679ba-2896">Nazwa i número dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="679ba-2896">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="679ba-2897">Nazwa i NR dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="679ba-2897">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="679ba-2898">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="679ba-2898">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="679ba-2899">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="679ba-2899">Dowód Tożsamości</span></span>
- <span data-ttu-id="679ba-2900">Dow.</span><span class="sxs-lookup"><span data-stu-id="679ba-2900">dow.</span></span> <span data-ttu-id="679ba-2901">MacOS.</span><span class="sxs-lookup"><span data-stu-id="679ba-2901">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="679ba-2902">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="679ba-2902">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2903">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2903">Format</span></span>

<span data-ttu-id="679ba-2904">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2905">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2905">Pattern</span></span>

<span data-ttu-id="679ba-2906">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2906">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2907">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2907">Checksum</span></span>

<span data-ttu-id="679ba-2908">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2908">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2909">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2909">Definition</span></span>

<span data-ttu-id="679ba-2910">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2910">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2911">La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2911">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2912">Se encuentra una palabra clave de Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2912">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="679ba-2913">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2913">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2914">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2914">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="679ba-2915">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2915">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="679ba-2916">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="679ba-2916">Nr PESEL</span></span>
- <span data-ttu-id="679ba-2917">PESEL</span><span class="sxs-lookup"><span data-stu-id="679ba-2917">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="679ba-2918">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="679ba-2918">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2919">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2919">Format</span></span>

<span data-ttu-id="679ba-2920">Dos letras y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2920">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2921">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2921">Pattern</span></span>

<span data-ttu-id="679ba-2922">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2922">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2923">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2923">Checksum</span></span>

<span data-ttu-id="679ba-2924">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2924">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2925">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2925">Definition</span></span>

<span data-ttu-id="679ba-2926">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2926">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2927">La función Func_polish_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2927">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2928">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-2928">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="679ba-2929">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2929">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2930">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2930">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="679ba-2931">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="679ba-2931">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="679ba-2932">Números paszportu</span><span class="sxs-lookup"><span data-stu-id="679ba-2932">Numer paszportu</span></span>
- <span data-ttu-id="679ba-2933">Nº.</span><span class="sxs-lookup"><span data-stu-id="679ba-2933">Nr.</span></span> <span data-ttu-id="679ba-2934">Paszportu</span><span class="sxs-lookup"><span data-stu-id="679ba-2934">Paszportu</span></span>
- <span data-ttu-id="679ba-2935">Paszport</span><span class="sxs-lookup"><span data-stu-id="679ba-2935">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="679ba-2936">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="679ba-2936">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2937">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2937">Format</span></span>

<span data-ttu-id="679ba-2938">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2938">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2939">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2939">Pattern</span></span>

<span data-ttu-id="679ba-2940">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2940">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2941">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2941">Checksum</span></span>

<span data-ttu-id="679ba-2942">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2942">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2943">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2943">Definition</span></span>

<span data-ttu-id="679ba-2944">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2944">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2945">La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2945">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2946">Se encuentra una palabra clave de Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="679ba-2946">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-2947">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2947">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="679ba-2948">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="679ba-2948">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="679ba-2949">Tarjeta del ciudadano</span><span class="sxs-lookup"><span data-stu-id="679ba-2949">Citizen Card</span></span>
- <span data-ttu-id="679ba-2950">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="679ba-2950">National ID Card</span></span>
- <span data-ttu-id="679ba-2951">CC</span><span class="sxs-lookup"><span data-stu-id="679ba-2951">CC</span></span>
- <span data-ttu-id="679ba-2952">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="679ba-2952">Cartão de Cidadão</span></span>
- <span data-ttu-id="679ba-2953">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="679ba-2953">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="679ba-2954">Identificación nacional de Arabia Saudí</span><span class="sxs-lookup"><span data-stu-id="679ba-2954">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2955">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2955">Format</span></span>

<span data-ttu-id="679ba-2956">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2956">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2957">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2957">Pattern</span></span>

<span data-ttu-id="679ba-2958">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-2958">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2959">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2959">Checksum</span></span>

<span data-ttu-id="679ba-2960">No</span><span class="sxs-lookup"><span data-stu-id="679ba-2960">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2961">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2961">Definition</span></span>

<span data-ttu-id="679ba-2962">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2962">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2963">La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2963">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2964">Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="679ba-2964">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2965">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2965">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="679ba-2966">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="679ba-2966">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="679ba-2967">Identification Card</span><span class="sxs-lookup"><span data-stu-id="679ba-2967">Identification Card</span></span> 
- <span data-ttu-id="679ba-2968">I card number</span><span class="sxs-lookup"><span data-stu-id="679ba-2968">I card number</span></span> 
- <span data-ttu-id="679ba-2969">ID number</span><span class="sxs-lookup"><span data-stu-id="679ba-2969">ID number</span></span> 
- <span data-ttu-id="679ba-2970">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="679ba-2970">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="679ba-2971">Número de tarjeta de identidad de registro nacional (NRIC) de Singapur</span><span class="sxs-lookup"><span data-stu-id="679ba-2971">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-2972">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-2972">Format</span></span>

<span data-ttu-id="679ba-2973">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-2973">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-2974">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-2974">Pattern</span></span>

- <span data-ttu-id="679ba-2975">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-2975">Nine letters and digits:</span></span>
- <span data-ttu-id="679ba-2976">La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-2976">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-2977">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-2977">Seven digits</span></span> 
- <span data-ttu-id="679ba-2978">Un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="679ba-2978">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-2979">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-2979">Checksum</span></span>

<span data-ttu-id="679ba-2980">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-2980">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-2981">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-2981">Definition</span></span>

<span data-ttu-id="679ba-2982">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2982">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2983">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2983">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2984">Se encuentra una palabra clave de Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="679ba-2984">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="679ba-2985">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2985">The checksum passes.</span></span>

<span data-ttu-id="679ba-2986">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-2987">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-2987">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-2988">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-2988">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-2989">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-2989">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="679ba-2990">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="679ba-2990">Keyword_singapore_nric</span></span>

- <span data-ttu-id="679ba-2991">Tarjeta de identidad de registro nacional</span><span class="sxs-lookup"><span data-stu-id="679ba-2991">National Registration Identity Card</span></span> 
- <span data-ttu-id="679ba-2992">Número de tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-2992">Identity Card Number</span></span> 
- <span data-ttu-id="679ba-2993">NRIC</span><span class="sxs-lookup"><span data-stu-id="679ba-2993">NRIC</span></span> 
- <span data-ttu-id="679ba-2994">I</span><span class="sxs-lookup"><span data-stu-id="679ba-2994">IC</span></span> 
- <span data-ttu-id="679ba-2995">Número de identificación de extranjeros</span><span class="sxs-lookup"><span data-stu-id="679ba-2995">Foreign Identification Number</span></span> 
- <span data-ttu-id="679ba-2996">AC</span><span class="sxs-lookup"><span data-stu-id="679ba-2996">FIN</span></span> 
- <span data-ttu-id="679ba-2997">身份证</span><span class="sxs-lookup"><span data-stu-id="679ba-2997">身份证</span></span> 
- <span data-ttu-id="679ba-2998">身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-2998">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="679ba-2999">Número de identificación de Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="679ba-2999">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3000">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3000">Format</span></span>

<span data-ttu-id="679ba-3001">13 dígitos que pueden contener espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-3001">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3002">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3002">Pattern</span></span>

<span data-ttu-id="679ba-3003">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3003">13 digits:</span></span>
- <span data-ttu-id="679ba-3004">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-3004">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="679ba-3005">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3005">Four digits</span></span> 
- <span data-ttu-id="679ba-3006">Un indicador de ciudadanía de un solo dígito </span><span class="sxs-lookup"><span data-stu-id="679ba-3006">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="679ba-3007">El dígito "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="679ba-3007">The digit "8" or "9"</span></span> 
- <span data-ttu-id="679ba-3008">Un dígito que es un dígito de suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3008">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3009">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3009">Checksum</span></span>

<span data-ttu-id="679ba-3010">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3010">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3011">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3011">Definition</span></span>

<span data-ttu-id="679ba-3012">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3012">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3013">La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3013">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3014">Se encuentra una palabra clave de Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-3014">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="679ba-3015">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3015">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3016">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3016">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="679ba-3017">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="679ba-3017">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="679ba-3018">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="679ba-3018">Identity card</span></span>
- <span data-ttu-id="679ba-3019">ID</span><span class="sxs-lookup"><span data-stu-id="679ba-3019">ID</span></span>
- <span data-ttu-id="679ba-3020">Determinación</span><span class="sxs-lookup"><span data-stu-id="679ba-3020">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="679ba-3021">Número de registro de residente de Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="679ba-3021">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3022">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3022">Format</span></span>

<span data-ttu-id="679ba-3023">13 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="679ba-3023">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3024">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3024">Pattern</span></span>

<span data-ttu-id="679ba-3025">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3025">13 digits:</span></span>
- <span data-ttu-id="679ba-3026">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="679ba-3026">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="679ba-3027">Un guión </span><span class="sxs-lookup"><span data-stu-id="679ba-3027">A hyphen</span></span> 
- <span data-ttu-id="679ba-3028">Un dígito determinado por el siglo y el sexo </span><span class="sxs-lookup"><span data-stu-id="679ba-3028">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="679ba-3029">Código de región de nacimiento de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="679ba-3029">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="679ba-3030">Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos </span><span class="sxs-lookup"><span data-stu-id="679ba-3030">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="679ba-3031">Un dígito de control.</span><span class="sxs-lookup"><span data-stu-id="679ba-3031">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3032">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3032">Checksum</span></span>

<span data-ttu-id="679ba-3033">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3033">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3034">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3034">Definition</span></span>

<span data-ttu-id="679ba-3035">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3035">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3036">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3036">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3037">Se encuentra una palabra clave de Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-3037">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="679ba-3038">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3038">The checksum passes.</span></span>

<span data-ttu-id="679ba-3039">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3039">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3040">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3040">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3041">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3041">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3042">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3042">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="679ba-3043">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="679ba-3043">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="679ba-3044">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="679ba-3044">National ID card</span></span> 
- <span data-ttu-id="679ba-3045">Número de registro de ciudadano</span><span class="sxs-lookup"><span data-stu-id="679ba-3045">Citizen's Registration Number</span></span> 
- <span data-ttu-id="679ba-3046">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="679ba-3046">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="679ba-3047">RRN</span><span class="sxs-lookup"><span data-stu-id="679ba-3047">RRN</span></span> 
- <span data-ttu-id="679ba-3048">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="679ba-3048">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="679ba-3049">Número de seguridad social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="679ba-3049">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3050">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3050">Format</span></span>

<span data-ttu-id="679ba-3051">11 o 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3051">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3052">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3052">Pattern</span></span>

<span data-ttu-id="679ba-3053">11-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3053">11-12 digits:</span></span>
- <span data-ttu-id="679ba-3054">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3054">Two digits</span></span> 
- <span data-ttu-id="679ba-3055">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="679ba-3055">A forward slash (optional)</span></span> 
- <span data-ttu-id="679ba-3056">7-8 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3056">7-8 digits</span></span> 
- <span data-ttu-id="679ba-3057">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="679ba-3057">A forward slash (optional)</span></span> 
- <span data-ttu-id="679ba-3058">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3058">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3059">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3059">Checksum</span></span>

<span data-ttu-id="679ba-3060">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3061">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3061">Definition</span></span>

<span data-ttu-id="679ba-3062">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3063">La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3063">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3064">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3064">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3065">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3065">Keywords</span></span>

<span data-ttu-id="679ba-3066">Ninguno</span><span class="sxs-lookup"><span data-stu-id="679ba-3066">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="679ba-3067">Cadena de conexión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="679ba-3067">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3068">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3068">Format</span></span>

<span data-ttu-id="679ba-3069">La cadena "User ID", "User ID", "UID" o "UserId" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="679ba-3069">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3070">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3070">Pattern</span></span>

- <span data-ttu-id="679ba-3071">La cadena "User ID", "User ID", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="679ba-3071">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="679ba-3072">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-3072">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="679ba-3073">La cadena "Password" o "pwd" donde "pwd" no está precedida por una letra minúscula.</span><span class="sxs-lookup"><span data-stu-id="679ba-3073">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="679ba-3074">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-3074">An equal sign (=)</span></span>
- <span data-ttu-id="679ba-3075">Cualquier carácter que no sea un signo de dólar ($), un símbolo de porcentaje (%), un símbolo mayor que (>), un símbolo de arroba (@), Comillas ("), punto y coma (;), llave izquierda ([) o corchete de apertura ({)</span><span class="sxs-lookup"><span data-stu-id="679ba-3075">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="679ba-3076">Cualquier combinación de 7-128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="679ba-3076">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="679ba-3077">Un punto y coma (;) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="679ba-3077">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3078">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3078">Checksum</span></span>

<span data-ttu-id="679ba-3079">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3079">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3080">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3080">Definition</span></span>

<span data-ttu-id="679ba-3081">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3082">La expresión regular CEP_Regex_SQLServerConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3082">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3083">**No** se encuentra una palabra clave de CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="679ba-3083">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="679ba-3084">La expresión regular CEP_PasswordPlaceHolder no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3084">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3085">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3085">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
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

### <a name="keywords"></a><span data-ttu-id="679ba-3086">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3086">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="679ba-3087">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="679ba-3087">CEP_GlobalFilter</span></span>

- <span data-ttu-id="679ba-3088">Some-Password</span><span class="sxs-lookup"><span data-stu-id="679ba-3088">some-password</span></span>
- <span data-ttu-id="679ba-3089">somepassword</span><span class="sxs-lookup"><span data-stu-id="679ba-3089">somepassword</span></span>
- <span data-ttu-id="679ba-3090">secretPassword</span><span class="sxs-lookup"><span data-stu-id="679ba-3090">secretPassword</span></span>
- <span data-ttu-id="679ba-3091">AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="679ba-3091">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="679ba-3092">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="679ba-3092">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="679ba-3093">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-3093">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-3094">Password o pwd seguida de 0-2 espacios, un signo igual (=), 0-2 espacios y un asterisco (\*)--o--</span><span class="sxs-lookup"><span data-stu-id="679ba-3094">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="679ba-3095">Password o pwd seguida de:</span><span class="sxs-lookup"><span data-stu-id="679ba-3095">Password or pwd followed by:</span></span>
    - <span data-ttu-id="679ba-3096">Signo de igual (=)</span><span class="sxs-lookup"><span data-stu-id="679ba-3096">Equal sign (=)</span></span>
    - <span data-ttu-id="679ba-3097">Símbolo menor que (<)</span><span class="sxs-lookup"><span data-stu-id="679ba-3097">Less than symbol (<)</span></span>
    - <span data-ttu-id="679ba-3098">Cualquier combinación de 1-200 caracteres que estén en mayúsculas o minúsculas, dígitos, un asterisco (\*), un guión (-), un subrayado (_) o un carácter de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="679ba-3098">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="679ba-3099">Símbolo mayor que (>)</span><span class="sxs-lookup"><span data-stu-id="679ba-3099">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="679ba-3100">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="679ba-3100">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="679ba-3101">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="679ba-3101">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="679ba-3102">contoso</span><span class="sxs-lookup"><span data-stu-id="679ba-3102">contoso</span></span>
- <span data-ttu-id="679ba-3103">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="679ba-3103">fabrikam</span></span>
- <span data-ttu-id="679ba-3104">Northwind</span><span class="sxs-lookup"><span data-stu-id="679ba-3104">northwind</span></span>
- <span data-ttu-id="679ba-3105">entorno</span><span class="sxs-lookup"><span data-stu-id="679ba-3105">sandbox</span></span>
- <span data-ttu-id="679ba-3106">onebox</span><span class="sxs-lookup"><span data-stu-id="679ba-3106">onebox</span></span>
- <span data-ttu-id="679ba-3107">localhost</span><span class="sxs-lookup"><span data-stu-id="679ba-3107">localhost</span></span>
- <span data-ttu-id="679ba-3108">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="679ba-3108">127.0.0.1</span></span>
- <span data-ttu-id="679ba-3109">testacs.</span><span class="sxs-lookup"><span data-stu-id="679ba-3109">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-3110">Puerto</span><span class="sxs-lookup"><span data-stu-id="679ba-3110">com</span></span>
- <span data-ttu-id="679ba-3111">s-int.</span><span class="sxs-lookup"><span data-stu-id="679ba-3111">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="679ba-3112">ADO.net</span><span class="sxs-lookup"><span data-stu-id="679ba-3112">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="679ba-3113">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="679ba-3113">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3114">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3114">Format</span></span>

<span data-ttu-id="679ba-3115">10 o 12 dígitos y un delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="679ba-3115">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3116">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3116">Pattern</span></span>

<span data-ttu-id="679ba-3117">10 o 12 dígitos y un delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="679ba-3117">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="679ba-3118">2-4 dígitos (opcionales)</span><span class="sxs-lookup"><span data-stu-id="679ba-3118">2-4 digits (optional)</span></span> 
- <span data-ttu-id="679ba-3119">Seis dígitos en fecha de formato AAMMDD</span><span class="sxs-lookup"><span data-stu-id="679ba-3119">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="679ba-3120">Delimitador de "-" o "+" (opcional), más</span><span class="sxs-lookup"><span data-stu-id="679ba-3120">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="679ba-3121">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3121">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3122">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3122">Checksum</span></span>

<span data-ttu-id="679ba-3123">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3123">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3124">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3124">Definition</span></span>

<span data-ttu-id="679ba-3125">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3125">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3126">La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3126">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3127">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3127">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3128">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3128">Keywords</span></span>

<span data-ttu-id="679ba-3129">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3129">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="679ba-3130">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="679ba-3130">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3131">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3131">Format</span></span>

<span data-ttu-id="679ba-3132">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3132">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3133">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3133">Pattern</span></span>

<span data-ttu-id="679ba-3134">Ocho dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-3134">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3135">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3135">Checksum</span></span>

<span data-ttu-id="679ba-3136">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3136">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3137">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3137">Definition</span></span>

<span data-ttu-id="679ba-3138">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3139">La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3139">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3140">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-3140">One of the following is true:</span></span>
    - <span data-ttu-id="679ba-3141">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="679ba-3141">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="679ba-3142">Se encuentra una palabra clave de Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="679ba-3142">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3143">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3143">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="679ba-3144">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-3144">Keyword_sweden_passport</span></span>

- <span data-ttu-id="679ba-3145">visa requirements</span><span class="sxs-lookup"><span data-stu-id="679ba-3145">visa requirements</span></span> 
- <span data-ttu-id="679ba-3146">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="679ba-3146">Alien Registration Card</span></span> 
- <span data-ttu-id="679ba-3147">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="679ba-3147">Schengen visas</span></span> 
- <span data-ttu-id="679ba-3148">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="679ba-3148">Schengen visa</span></span> 
- <span data-ttu-id="679ba-3149">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="679ba-3149">Visa Processing</span></span> 
- <span data-ttu-id="679ba-3150">Visa Type</span><span class="sxs-lookup"><span data-stu-id="679ba-3150">Visa Type</span></span> 
- <span data-ttu-id="679ba-3151">Single Entry</span><span class="sxs-lookup"><span data-stu-id="679ba-3151">Single Entry</span></span> 
- <span data-ttu-id="679ba-3152">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="679ba-3152">Multiple Entry</span></span> 
- <span data-ttu-id="679ba-3153">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="679ba-3153">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="679ba-3154">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-3154">Keyword_passport</span></span>

- <span data-ttu-id="679ba-3155">Passport Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3155">Passport Number</span></span> 
- <span data-ttu-id="679ba-3156">Passport No</span><span class="sxs-lookup"><span data-stu-id="679ba-3156">Passport No</span></span> 
- <span data-ttu-id="679ba-3157">Passport #</span><span class="sxs-lookup"><span data-stu-id="679ba-3157">Passport #</span></span> 
- <span data-ttu-id="679ba-3158">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="679ba-3158">Passport#</span></span> 
- <span data-ttu-id="679ba-3159">PassportID</span><span class="sxs-lookup"><span data-stu-id="679ba-3159">PassportID</span></span> 
- <span data-ttu-id="679ba-3160">Passportno</span><span class="sxs-lookup"><span data-stu-id="679ba-3160">Passportno</span></span> 
- <span data-ttu-id="679ba-3161">passportnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-3161">passportnumber</span></span> 
- <span data-ttu-id="679ba-3162">パスポート</span><span class="sxs-lookup"><span data-stu-id="679ba-3162">パスポート</span></span> 
- <span data-ttu-id="679ba-3163">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="679ba-3163">パスポート番号</span></span> 
- <span data-ttu-id="679ba-3164">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="679ba-3164">パスポートのNum</span></span> 
- <span data-ttu-id="679ba-3165">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="679ba-3165">パスポート＃</span></span> 
- <span data-ttu-id="679ba-3166">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="679ba-3166">Numéro de passeport</span></span> 
- <span data-ttu-id="679ba-3167">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="679ba-3167">Passeport n °</span></span> 
- <span data-ttu-id="679ba-3168">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="679ba-3168">Passeport Non</span></span> 
- <span data-ttu-id="679ba-3169">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-3169">Passeport #</span></span> 
- <span data-ttu-id="679ba-3170">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-3170">Passeport#</span></span> 
- <span data-ttu-id="679ba-3171">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="679ba-3171">PasseportNon</span></span> 
- <span data-ttu-id="679ba-3172">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="679ba-3172">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="679ba-3173">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="679ba-3173">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3174">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3174">Format</span></span>

<span data-ttu-id="679ba-3175">Cuatro letras seguidas de 5 a 31 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3175">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3176">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3176">Pattern</span></span>

<span data-ttu-id="679ba-3177">Cuatro letras seguidas de 5-31 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3177">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="679ba-3178">Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-3178">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-3179">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="679ba-3179">An optional space</span></span> 
- <span data-ttu-id="679ba-3180">4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))</span><span class="sxs-lookup"><span data-stu-id="679ba-3180">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="679ba-3181">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="679ba-3181">An optional space</span></span> 
- <span data-ttu-id="679ba-3182">1-3 letras o dígitos (el resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="679ba-3182">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3183">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3183">Checksum</span></span>

<span data-ttu-id="679ba-3184">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3185">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3185">Definition</span></span>

<span data-ttu-id="679ba-3186">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3186">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3187">La expresión regular Regex_swift encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3187">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3188">Se encuentra una palabra clave de Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="679ba-3188">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3189">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3189">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="679ba-3190">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="679ba-3190">Keyword_swift</span></span>

- <span data-ttu-id="679ba-3191">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="679ba-3191">international organization for standardization 9362</span></span> 
- <span data-ttu-id="679ba-3192">iso 9362</span><span class="sxs-lookup"><span data-stu-id="679ba-3192">iso 9362</span></span> 
- <span data-ttu-id="679ba-3193">iso9362</span><span class="sxs-lookup"><span data-stu-id="679ba-3193">iso9362</span></span> 
- <span data-ttu-id="679ba-3194">rápido\#</span><span class="sxs-lookup"><span data-stu-id="679ba-3194">swift\#</span></span> 
- <span data-ttu-id="679ba-3195">swiftcode</span><span class="sxs-lookup"><span data-stu-id="679ba-3195">swiftcode</span></span> 
- <span data-ttu-id="679ba-3196">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-3196">swiftnumber</span></span> 
- <span data-ttu-id="679ba-3197">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-3197">swiftroutingnumber</span></span> 
- <span data-ttu-id="679ba-3198">swift code</span><span class="sxs-lookup"><span data-stu-id="679ba-3198">swift code</span></span> 
- <span data-ttu-id="679ba-3199">swift number #</span><span class="sxs-lookup"><span data-stu-id="679ba-3199">swift number #</span></span> 
- <span data-ttu-id="679ba-3200">swift routing number</span><span class="sxs-lookup"><span data-stu-id="679ba-3200">swift routing number</span></span> 
- <span data-ttu-id="679ba-3201">bic number</span><span class="sxs-lookup"><span data-stu-id="679ba-3201">bic number</span></span> 
- <span data-ttu-id="679ba-3202">bic code</span><span class="sxs-lookup"><span data-stu-id="679ba-3202">bic code</span></span> 
- <span data-ttu-id="679ba-3203">BIC\#</span><span class="sxs-lookup"><span data-stu-id="679ba-3203">bic \#</span></span> 
- <span data-ttu-id="679ba-3204">BIC\#</span><span class="sxs-lookup"><span data-stu-id="679ba-3204">bic\#</span></span> 
- <span data-ttu-id="679ba-3205">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="679ba-3205">bank identifier code</span></span> 
- <span data-ttu-id="679ba-3206">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="679ba-3206">標準化9362</span></span> 
- <span data-ttu-id="679ba-3207">迅速＃</span><span class="sxs-lookup"><span data-stu-id="679ba-3207">迅速＃</span></span> 
- <span data-ttu-id="679ba-3208">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="679ba-3208">SWIFTコード</span></span> 
- <span data-ttu-id="679ba-3209">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="679ba-3209">SWIFT番号</span></span> 
- <span data-ttu-id="679ba-3210">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="679ba-3210">迅速なルーティング番号</span></span> 
- <span data-ttu-id="679ba-3211">BIC番号</span><span class="sxs-lookup"><span data-stu-id="679ba-3211">BIC番号</span></span> 
- <span data-ttu-id="679ba-3212">BICコード</span><span class="sxs-lookup"><span data-stu-id="679ba-3212">BICコード</span></span> 
- <span data-ttu-id="679ba-3213">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="679ba-3213">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="679ba-3214">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="679ba-3214">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="679ba-3215">rápido\#</span><span class="sxs-lookup"><span data-stu-id="679ba-3215">rapide \#</span></span> 
- <span data-ttu-id="679ba-3216">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="679ba-3216">code SWIFT</span></span> 
- <span data-ttu-id="679ba-3217">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="679ba-3217">le numéro de swift</span></span> 
- <span data-ttu-id="679ba-3218">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="679ba-3218">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="679ba-3219">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="679ba-3219">le numéro BIC</span></span> 
- <span data-ttu-id="679ba-3220">\#BIC</span><span class="sxs-lookup"><span data-stu-id="679ba-3220">\# BIC</span></span> 
- <span data-ttu-id="679ba-3221">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="679ba-3221">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="679ba-3222">Identificación nacional de Taiwán</span><span class="sxs-lookup"><span data-stu-id="679ba-3222">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3223">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3223">Format</span></span>

<span data-ttu-id="679ba-3224">Una letra  seguida de nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3224">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3225">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3225">Pattern</span></span>

<span data-ttu-id="679ba-3226">Una letra seguida de nueve dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3226">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="679ba-3227">Una letra (en inglés, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-3227">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="679ba-3228">El dígito "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="679ba-3228">The digit "1" or "2"</span></span> 
- <span data-ttu-id="679ba-3229">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3229">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3230">Checksum</span></span>

<span data-ttu-id="679ba-3231">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3231">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3232">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3232">Definition</span></span>

<span data-ttu-id="679ba-3233">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3233">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3234">La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3234">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3235">Se encuentra una palabra clave de Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="679ba-3235">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="679ba-3236">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3236">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3237">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3237">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="679ba-3238">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="679ba-3238">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="679ba-3239">身份證字號</span><span class="sxs-lookup"><span data-stu-id="679ba-3239">身份證字號</span></span> 
- <span data-ttu-id="679ba-3240">身份證</span><span class="sxs-lookup"><span data-stu-id="679ba-3240">身份證</span></span> 
- <span data-ttu-id="679ba-3241">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="679ba-3241">身份證號碼</span></span> 
- <span data-ttu-id="679ba-3242">身份證號</span><span class="sxs-lookup"><span data-stu-id="679ba-3242">身份證號</span></span> 
- <span data-ttu-id="679ba-3243">身分證字號</span><span class="sxs-lookup"><span data-stu-id="679ba-3243">身分證字號</span></span> 
- <span data-ttu-id="679ba-3244">身分證</span><span class="sxs-lookup"><span data-stu-id="679ba-3244">身分證</span></span> 
- <span data-ttu-id="679ba-3245">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="679ba-3245">身分證號碼</span></span> 
- <span data-ttu-id="679ba-3246">身份證號</span><span class="sxs-lookup"><span data-stu-id="679ba-3246">身份證號</span></span> 
- <span data-ttu-id="679ba-3247">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="679ba-3247">身分證統一編號</span></span> 
- <span data-ttu-id="679ba-3248">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="679ba-3248">國民身分證統一編號</span></span> 
- <span data-ttu-id="679ba-3249">簽名</span><span class="sxs-lookup"><span data-stu-id="679ba-3249">簽名</span></span> 
- <span data-ttu-id="679ba-3250">蓋章</span><span class="sxs-lookup"><span data-stu-id="679ba-3250">蓋章</span></span> 
- <span data-ttu-id="679ba-3251">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="679ba-3251">簽名或蓋章</span></span> 
- <span data-ttu-id="679ba-3252">簽章</span><span class="sxs-lookup"><span data-stu-id="679ba-3252">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="679ba-3253">	Número de pasaporte de Taiwán</span><span class="sxs-lookup"><span data-stu-id="679ba-3253">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3254">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3254">Format</span></span>

- <span data-ttu-id="679ba-3255">Número de pasaporte biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3255">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="679ba-3256">Número de pasaporte no biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3256">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3257">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3257">Pattern</span></span>
<span data-ttu-id="679ba-3258">Número de pasaporte biométrico:</span><span class="sxs-lookup"><span data-stu-id="679ba-3258">Biometric passport number:</span></span>
- <span data-ttu-id="679ba-3259">El dígito "3" </span><span class="sxs-lookup"><span data-stu-id="679ba-3259">The digit "3"</span></span> 
- <span data-ttu-id="679ba-3260">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3260">Eight digits</span></span>

<span data-ttu-id="679ba-3261">Número de pasaporte no biométrico:</span><span class="sxs-lookup"><span data-stu-id="679ba-3261">Non-biometric passport number:</span></span>
- <span data-ttu-id="679ba-3262">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3262">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3263">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3263">Checksum</span></span>

<span data-ttu-id="679ba-3264">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3264">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3265">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3265">Definition</span></span>

<span data-ttu-id="679ba-3266">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3266">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3267">La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3267">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3268">Se encuentra una palabra clave de Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="679ba-3268">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3269">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3269">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="679ba-3270">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-3270">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="679ba-3271">Número de pasaporte ROC</span><span class="sxs-lookup"><span data-stu-id="679ba-3271">ROC passport number</span></span> 
- <span data-ttu-id="679ba-3272">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="679ba-3272">Passport number</span></span> 
- <span data-ttu-id="679ba-3273">Núm. pasaporte
</span><span class="sxs-lookup"><span data-stu-id="679ba-3273">Passport no</span></span> 
- <span data-ttu-id="679ba-3274">N.ro pasaporte</span><span class="sxs-lookup"><span data-stu-id="679ba-3274">Passport Num</span></span> 
- <span data-ttu-id="679ba-3275">N.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="679ba-3275">Passport #</span></span> 
- <span data-ttu-id="679ba-3276">护照</span><span class="sxs-lookup"><span data-stu-id="679ba-3276">护照</span></span> 
- <span data-ttu-id="679ba-3277">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="679ba-3277">中華民國護照</span></span> 
- <span data-ttu-id="679ba-3278">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="679ba-3278">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="679ba-3279">Número de certificado de residente (ARC/TARC) de Taiwán</span><span class="sxs-lookup"><span data-stu-id="679ba-3279">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3280">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3280">Format</span></span>

<span data-ttu-id="679ba-3281">10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3281">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3282">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3282">Pattern</span></span>

<span data-ttu-id="679ba-3283">10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3283">10 letters and digits:</span></span>
- <span data-ttu-id="679ba-3284">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="679ba-3284">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="679ba-3285">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3285">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3286">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3286">Checksum</span></span>

<span data-ttu-id="679ba-3287">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3287">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3288">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3288">Definition</span></span>

<span data-ttu-id="679ba-3289">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3289">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3290">La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3290">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3291">Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="679ba-3291">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3292">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3292">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="679ba-3293">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="679ba-3293">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="679ba-3294">Certificado de residente</span><span class="sxs-lookup"><span data-stu-id="679ba-3294">Resident Certificate</span></span> 
- <span data-ttu-id="679ba-3295">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="679ba-3295">Resident Cert</span></span> 
- <span data-ttu-id="679ba-3296">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="679ba-3296">Resident Cert.</span></span> 
- <span data-ttu-id="679ba-3297">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="679ba-3297">Identification card</span></span> 
- <span data-ttu-id="679ba-3298">Certificado de residente extranjero</span><span class="sxs-lookup"><span data-stu-id="679ba-3298">Alien Resident Certificate</span></span> 
- <span data-ttu-id="679ba-3299">ARCOS</span><span class="sxs-lookup"><span data-stu-id="679ba-3299">ARC</span></span> 
- <span data-ttu-id="679ba-3300">Certificado de residente en el área de Taiwán</span><span class="sxs-lookup"><span data-stu-id="679ba-3300">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="679ba-3301">TARC</span><span class="sxs-lookup"><span data-stu-id="679ba-3301">TARC</span></span> 
- <span data-ttu-id="679ba-3302">居留證</span><span class="sxs-lookup"><span data-stu-id="679ba-3302">居留證</span></span> 
- <span data-ttu-id="679ba-3303">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="679ba-3303">外僑居留證</span></span> 
- <span data-ttu-id="679ba-3304">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="679ba-3304">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="679ba-3305">Código de identificación de población tailandesa</span><span class="sxs-lookup"><span data-stu-id="679ba-3305">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3306">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3306">Format</span></span>

<span data-ttu-id="679ba-3307">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3307">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3308">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3308">Pattern</span></span>

<span data-ttu-id="679ba-3309">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3309">13 digits:</span></span>
- <span data-ttu-id="679ba-3310">El primer dígito no es 0 ni 9</span><span class="sxs-lookup"><span data-stu-id="679ba-3310">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="679ba-3311">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3311">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3312">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3312">Checksum</span></span>

<span data-ttu-id="679ba-3313">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3314">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3314">Definition</span></span>

<span data-ttu-id="679ba-3315">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3315">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3316">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3316">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3317">Se encuentra una palabra clave de Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="679ba-3317">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="679ba-3318">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3319">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3319">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3320">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3320">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="679ba-3321">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="679ba-3321">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="679ba-3322">Número de id.</span><span class="sxs-lookup"><span data-stu-id="679ba-3322">ID Number</span></span>
- <span data-ttu-id="679ba-3323">Número de identificación</span><span class="sxs-lookup"><span data-stu-id="679ba-3323">Identification Number</span></span>
- <span data-ttu-id="679ba-3324">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="679ba-3324">บัตรประชาชน</span></span>
- <span data-ttu-id="679ba-3325">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="679ba-3325">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="679ba-3326">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="679ba-3326">บัตรประชาชน</span></span>
- <span data-ttu-id="679ba-3327">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="679ba-3327">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="679ba-3328">Número de identificación nacional de Turco</span><span class="sxs-lookup"><span data-stu-id="679ba-3328">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3329">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3329">Format</span></span>

<span data-ttu-id="679ba-3330">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3330">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3331">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3331">Pattern</span></span>

<span data-ttu-id="679ba-3332">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3332">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3333">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3333">Checksum</span></span>

<span data-ttu-id="679ba-3334">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3335">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3335">Definition</span></span>

<span data-ttu-id="679ba-3336">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3337">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3337">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3338">Se encuentra una palabra clave de Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="679ba-3338">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="679ba-3339">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3340">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3340">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3341">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3341">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="679ba-3342">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="679ba-3342">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="679ba-3343">TC Kimlik no</span><span class="sxs-lookup"><span data-stu-id="679ba-3343">TC Kimlik No</span></span>
- <span data-ttu-id="679ba-3344">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="679ba-3344">TC Kimlik numarası</span></span>
- <span data-ttu-id="679ba-3345">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="679ba-3345">Vatandaşlık numarası</span></span>
- <span data-ttu-id="679ba-3346">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="679ba-3346">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="679ba-p141">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="679ba-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3349">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3349">Format</span></span>

<span data-ttu-id="679ba-3350">Combinación de 18 letras y dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="679ba-3350">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3351">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3351">Pattern</span></span>

<span data-ttu-id="679ba-3352">18 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3352">18 letters and digits:</span></span>
- <span data-ttu-id="679ba-3353">Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="679ba-3353">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="679ba-3354">Un dígito</span><span class="sxs-lookup"><span data-stu-id="679ba-3354">One digit</span></span> 
- <span data-ttu-id="679ba-3355">Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-3355">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="679ba-3356">Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="679ba-3356">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="679ba-3357">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3357">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3358">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3358">Checksum</span></span>

<span data-ttu-id="679ba-3359">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3359">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3360">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3360">Definition</span></span>

<span data-ttu-id="679ba-3361">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3362">La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3362">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3363">Se encuentra una palabra clave de Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="679ba-3363">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="679ba-3364">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3364">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3365">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3365">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="679ba-3366">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="679ba-3366">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="679ba-3367">DVLA</span><span class="sxs-lookup"><span data-stu-id="679ba-3367">DVLA</span></span> 
- <span data-ttu-id="679ba-3368">light vans</span><span class="sxs-lookup"><span data-stu-id="679ba-3368">light vans</span></span> 
- <span data-ttu-id="679ba-3369">quadbikes</span><span class="sxs-lookup"><span data-stu-id="679ba-3369">quadbikes</span></span> 
- <span data-ttu-id="679ba-3370">motor cars</span><span class="sxs-lookup"><span data-stu-id="679ba-3370">motor cars</span></span> 
- <span data-ttu-id="679ba-3371">125cc</span><span class="sxs-lookup"><span data-stu-id="679ba-3371">125cc</span></span> 
- <span data-ttu-id="679ba-3372">sidecar</span><span class="sxs-lookup"><span data-stu-id="679ba-3372">sidecar</span></span> 
- <span data-ttu-id="679ba-3373">Tricycles</span><span class="sxs-lookup"><span data-stu-id="679ba-3373">tricycles</span></span> 
- <span data-ttu-id="679ba-3374">sidecar</span><span class="sxs-lookup"><span data-stu-id="679ba-3374">motorcycles</span></span> 
- <span data-ttu-id="679ba-3375">photocard licence</span><span class="sxs-lookup"><span data-stu-id="679ba-3375">photocard licence</span></span> 
- <span data-ttu-id="679ba-3376">learner drivers</span><span class="sxs-lookup"><span data-stu-id="679ba-3376">learner drivers</span></span> 
- <span data-ttu-id="679ba-3377">licence holder</span><span class="sxs-lookup"><span data-stu-id="679ba-3377">licence holder</span></span> 
- <span data-ttu-id="679ba-3378">licence holders</span><span class="sxs-lookup"><span data-stu-id="679ba-3378">licence holders</span></span> 
- <span data-ttu-id="679ba-3379">driving licences</span><span class="sxs-lookup"><span data-stu-id="679ba-3379">driving licences</span></span> 
- <span data-ttu-id="679ba-3380">driving licence</span><span class="sxs-lookup"><span data-stu-id="679ba-3380">driving licence</span></span> 
- <span data-ttu-id="679ba-3381">dual control car</span><span class="sxs-lookup"><span data-stu-id="679ba-3381">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="679ba-p142">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="679ba-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3384">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3384">Format</span></span>

<span data-ttu-id="679ba-3385">Dos letras seguidas por entre 1 y 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3385">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3386">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3386">Pattern</span></span>

<span data-ttu-id="679ba-3387">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números</span><span class="sxs-lookup"><span data-stu-id="679ba-3387">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3388">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3388">Checksum</span></span>

<span data-ttu-id="679ba-3389">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3389">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3390">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3390">Definition</span></span>

<span data-ttu-id="679ba-3391">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3391">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3392">La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3392">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3393">Se encuentra una palabra clave de Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="679ba-3393">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3394">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3394">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="679ba-3395">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="679ba-3395">Keyword_uk_electoral</span></span>

- <span data-ttu-id="679ba-3396">council nomination</span><span class="sxs-lookup"><span data-stu-id="679ba-3396">council nomination</span></span> 
- <span data-ttu-id="679ba-3397">nomination form</span><span class="sxs-lookup"><span data-stu-id="679ba-3397">nomination form</span></span> 
- <span data-ttu-id="679ba-3398">electoral register</span><span class="sxs-lookup"><span data-stu-id="679ba-3398">electoral register</span></span> 
- <span data-ttu-id="679ba-3399">electoral roll</span><span class="sxs-lookup"><span data-stu-id="679ba-3399">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="679ba-p143">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="679ba-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3402">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3402">Format</span></span>

<span data-ttu-id="679ba-3403">De 10 a 17 dígitos separados por espacios</span><span class="sxs-lookup"><span data-stu-id="679ba-3403">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3404">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3404">Pattern</span></span>

<span data-ttu-id="679ba-3405">10-17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="679ba-3405">10-17 digits:</span></span>
- <span data-ttu-id="679ba-3406">3 o 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3406">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="679ba-3407">Un espacio</span><span class="sxs-lookup"><span data-stu-id="679ba-3407">A space</span></span> 
- <span data-ttu-id="679ba-3408">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3408">Three digits</span></span> 
- <span data-ttu-id="679ba-3409">Un espacio</span><span class="sxs-lookup"><span data-stu-id="679ba-3409">A space</span></span> 
- <span data-ttu-id="679ba-3410">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3410">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3411">Checksum</span></span>

<span data-ttu-id="679ba-3412">Sí</span><span class="sxs-lookup"><span data-stu-id="679ba-3412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3413">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3413">Definition</span></span>

<span data-ttu-id="679ba-3414">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3415">La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3415">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3416">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-3416">One of the following is true:</span></span>
    - <span data-ttu-id="679ba-3417">Se encuentra una palabra clave de Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="679ba-3417">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="679ba-3418">Se encuentra una palabra clave de Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="679ba-3418">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="679ba-3419">Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="679ba-3419">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="679ba-3420">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="679ba-3420">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3421">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3421">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="679ba-3422">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="679ba-3422">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="679ba-3423">national health service</span><span class="sxs-lookup"><span data-stu-id="679ba-3423">national health service</span></span> 
- <span data-ttu-id="679ba-3424">del NHS del</span><span class="sxs-lookup"><span data-stu-id="679ba-3424">nhs</span></span> 
- <span data-ttu-id="679ba-3425">health services authority</span><span class="sxs-lookup"><span data-stu-id="679ba-3425">health services authority</span></span> 
- <span data-ttu-id="679ba-3426">health authority</span><span class="sxs-lookup"><span data-stu-id="679ba-3426">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="679ba-3427">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="679ba-3427">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="679ba-3428">patient id</span><span class="sxs-lookup"><span data-stu-id="679ba-3428">patient id</span></span> 
- <span data-ttu-id="679ba-3429">patient identification</span><span class="sxs-lookup"><span data-stu-id="679ba-3429">patient identification</span></span> 
- <span data-ttu-id="679ba-3430">patient no</span><span class="sxs-lookup"><span data-stu-id="679ba-3430">patient no</span></span> 
- <span data-ttu-id="679ba-3431">patient number</span><span class="sxs-lookup"><span data-stu-id="679ba-3431">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="679ba-3432">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="679ba-3432">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="679ba-3433">EON</span><span class="sxs-lookup"><span data-stu-id="679ba-3433">GP</span></span> 
- <span data-ttu-id="679ba-3434">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="679ba-3434">DOB</span></span> 
- <span data-ttu-id="679ba-3435">D. O. B</span><span class="sxs-lookup"><span data-stu-id="679ba-3435">D.O.B</span></span> 
- <span data-ttu-id="679ba-3436">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-3436">Date of Birth</span></span> 
- <span data-ttu-id="679ba-3437">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-3437">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="679ba-p144">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="679ba-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3440">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3440">Format</span></span>

<span data-ttu-id="679ba-3441">7 caracteres o 9 caracteres separados por espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="679ba-3441">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3442">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3442">Pattern</span></span>

<span data-ttu-id="679ba-3443">Dos patrones posibles:</span><span class="sxs-lookup"><span data-stu-id="679ba-3443">Two possible patterns:</span></span>

- <span data-ttu-id="679ba-3444">Dos letras (los NINO válidos usan solo caracteres determinados en este prefijo, que valida este patrón; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-3444">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="679ba-3445">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3445">Six digits</span></span>
- <span data-ttu-id="679ba-3446">' A ', ' B ', ' C ' o ' t ' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="679ba-3446">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="679ba-3447">O</span><span class="sxs-lookup"><span data-stu-id="679ba-3447">OR</span></span>

- <span data-ttu-id="679ba-3448">Dos letras</span><span class="sxs-lookup"><span data-stu-id="679ba-3448">Two letters</span></span>
- <span data-ttu-id="679ba-3449">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-3449">A space or dash</span></span>
- <span data-ttu-id="679ba-3450">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3450">Two digits</span></span>
- <span data-ttu-id="679ba-3451">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-3451">A space or dash</span></span>
- <span data-ttu-id="679ba-3452">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3452">Two digits</span></span>
- <span data-ttu-id="679ba-3453">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-3453">A space or dash</span></span>
- <span data-ttu-id="679ba-3454">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3454">Two digits</span></span>
- <span data-ttu-id="679ba-3455">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-3455">A space or dash</span></span>
- <span data-ttu-id="679ba-3456">' A ', ' B ', ' C ' o ' t '</span><span class="sxs-lookup"><span data-stu-id="679ba-3456">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3457">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3457">Checksum</span></span>

<span data-ttu-id="679ba-3458">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3459">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3459">Definition</span></span>

<span data-ttu-id="679ba-3460">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3461">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3461">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3462">Se encuentra una palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="679ba-3462">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="679ba-3463">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3464">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3464">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3465">No se encuentra ninguna palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="679ba-3465">No keyword from Keyword_uk_nino is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3466">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3466">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="679ba-3467">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="679ba-3467">Keyword_uk_nino</span></span>

- <span data-ttu-id="679ba-3468">national insurance number</span><span class="sxs-lookup"><span data-stu-id="679ba-3468">national insurance number</span></span> 
- <span data-ttu-id="679ba-3469">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="679ba-3469">national insurance contributions</span></span> 
- <span data-ttu-id="679ba-3470">protection act</span><span class="sxs-lookup"><span data-stu-id="679ba-3470">protection act</span></span> 
- <span data-ttu-id="679ba-3471">Pensión</span><span class="sxs-lookup"><span data-stu-id="679ba-3471">insurance</span></span> 
- <span data-ttu-id="679ba-3472">social security number</span><span class="sxs-lookup"><span data-stu-id="679ba-3472">social security number</span></span> 
- <span data-ttu-id="679ba-3473">insurance application</span><span class="sxs-lookup"><span data-stu-id="679ba-3473">insurance application</span></span> 
- <span data-ttu-id="679ba-3474">medical application</span><span class="sxs-lookup"><span data-stu-id="679ba-3474">medical application</span></span> 
- <span data-ttu-id="679ba-3475">social insurance</span><span class="sxs-lookup"><span data-stu-id="679ba-3475">social insurance</span></span> 
- <span data-ttu-id="679ba-3476">medical attention</span><span class="sxs-lookup"><span data-stu-id="679ba-3476">medical attention</span></span> 
- <span data-ttu-id="679ba-3477">social security</span><span class="sxs-lookup"><span data-stu-id="679ba-3477">social security</span></span> 
- <span data-ttu-id="679ba-3478">great britain</span><span class="sxs-lookup"><span data-stu-id="679ba-3478">great britain</span></span> 
- <span data-ttu-id="679ba-3479">Pensión</span><span class="sxs-lookup"><span data-stu-id="679ba-3479">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="679ba-p145">Número de pasaporte EE. UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="679ba-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3482">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3482">Format</span></span>

<span data-ttu-id="679ba-3483">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3483">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3484">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3484">Pattern</span></span>

<span data-ttu-id="679ba-3485">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-3485">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3486">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3486">Checksum</span></span>

<span data-ttu-id="679ba-3487">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3487">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3488">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3488">Definition</span></span>

<span data-ttu-id="679ba-3489">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3489">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3490">La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3490">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3491">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="679ba-3491">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3492">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3492">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="679ba-3493">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="679ba-3493">Keyword_passport</span></span>

- <span data-ttu-id="679ba-3494">Passport Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3494">Passport Number</span></span> 
- <span data-ttu-id="679ba-3495">Passport No</span><span class="sxs-lookup"><span data-stu-id="679ba-3495">Passport No</span></span> 
- <span data-ttu-id="679ba-3496">Passport #</span><span class="sxs-lookup"><span data-stu-id="679ba-3496">Passport #</span></span> 
- <span data-ttu-id="679ba-3497">Usuarios #</span><span class="sxs-lookup"><span data-stu-id="679ba-3497">Passport#</span></span> 
- <span data-ttu-id="679ba-3498">PassportID</span><span class="sxs-lookup"><span data-stu-id="679ba-3498">PassportID</span></span> 
- <span data-ttu-id="679ba-3499">Passportno</span><span class="sxs-lookup"><span data-stu-id="679ba-3499">Passportno</span></span> 
- <span data-ttu-id="679ba-3500">passportnumber</span><span class="sxs-lookup"><span data-stu-id="679ba-3500">passportnumber</span></span> 
- <span data-ttu-id="679ba-3501">パスポート</span><span class="sxs-lookup"><span data-stu-id="679ba-3501">パスポート</span></span> 
- <span data-ttu-id="679ba-3502">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="679ba-3502">パスポート番号</span></span> 
- <span data-ttu-id="679ba-3503">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="679ba-3503">パスポートのNum</span></span> 
- <span data-ttu-id="679ba-3504">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="679ba-3504">パスポート＃</span></span> 
- <span data-ttu-id="679ba-3505">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="679ba-3505">Numéro de passeport</span></span> 
- <span data-ttu-id="679ba-3506">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="679ba-3506">Passeport n °</span></span> 
- <span data-ttu-id="679ba-3507">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="679ba-3507">Passeport Non</span></span> 
- <span data-ttu-id="679ba-3508">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-3508">Passeport #</span></span> 
- <span data-ttu-id="679ba-3509">Passeport #</span><span class="sxs-lookup"><span data-stu-id="679ba-3509">Passeport#</span></span> 
- <span data-ttu-id="679ba-3510">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="679ba-3510">PasseportNon</span></span> 
- <span data-ttu-id="679ba-3511">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="679ba-3511">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="679ba-3512">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="679ba-3512">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3513">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3513">Format</span></span>

<span data-ttu-id="679ba-3514">Entre 8 y 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3514">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3515">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3515">Pattern</span></span>

<span data-ttu-id="679ba-3516">Entre 8 y 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="679ba-3516">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3517">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3517">Checksum</span></span>

<span data-ttu-id="679ba-3518">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3518">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3519">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3519">Definition</span></span>

<span data-ttu-id="679ba-3520">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3521">La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3521">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3522">Se encuentra una palabra clave de Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="679ba-3522">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3523">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3523">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="679ba-3524">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="679ba-3524">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="679ba-3525">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3525">Checking Account Number</span></span> 
- <span data-ttu-id="679ba-3526">Checking Account</span><span class="sxs-lookup"><span data-stu-id="679ba-3526">Checking Account</span></span> 
- <span data-ttu-id="679ba-3527">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-3527">Checking Account #</span></span> 
- <span data-ttu-id="679ba-3528">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3528">Checking Acct Number</span></span> 
- <span data-ttu-id="679ba-3529">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-3529">Checking Acct #</span></span> 
- <span data-ttu-id="679ba-3530">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3530">Checking Acct No.</span></span> 
- <span data-ttu-id="679ba-3531">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3531">Checking Account No.</span></span> 
- <span data-ttu-id="679ba-3532">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3532">Bank Account Number</span></span> 
- <span data-ttu-id="679ba-3533">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-3533">Bank Account #</span></span> 
- <span data-ttu-id="679ba-3534">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3534">Bank Acct Number</span></span> 
- <span data-ttu-id="679ba-3535">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-3535">Bank Acct #</span></span> 
- <span data-ttu-id="679ba-3536">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3536">Bank Acct No.</span></span> 
- <span data-ttu-id="679ba-3537">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3537">Bank Account No.</span></span> 
- <span data-ttu-id="679ba-3538">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3538">Savings Account Number</span></span> 
- <span data-ttu-id="679ba-3539">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="679ba-3539">Savings Account.</span></span> 
- <span data-ttu-id="679ba-3540">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-3540">Savings Account #</span></span> 
- <span data-ttu-id="679ba-3541">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3541">Savings Acct Number</span></span> 
- <span data-ttu-id="679ba-3542">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-3542">Savings Acct #</span></span> 
- <span data-ttu-id="679ba-3543">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3543">Savings Acct No.</span></span> 
- <span data-ttu-id="679ba-3544">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3544">Savings Account No.</span></span> 
- <span data-ttu-id="679ba-3545">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3545">Debit Account Number</span></span> 
- <span data-ttu-id="679ba-3546">Debit Account</span><span class="sxs-lookup"><span data-stu-id="679ba-3546">Debit Account</span></span> 
- <span data-ttu-id="679ba-3547">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="679ba-3547">Debit Account #</span></span> 
- <span data-ttu-id="679ba-3548">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="679ba-3548">Debit Acct Number</span></span> 
- <span data-ttu-id="679ba-3549">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="679ba-3549">Debit Acct #</span></span> 
- <span data-ttu-id="679ba-3550">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3550">Debit Acct No.</span></span> 
- <span data-ttu-id="679ba-3551">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="679ba-3551">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="679ba-3552">Número de licencia de conductor de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="679ba-3552">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3553">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3553">Format</span></span>

<span data-ttu-id="679ba-3554">Depende del estado</span><span class="sxs-lookup"><span data-stu-id="679ba-3554">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3555">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3555">Pattern</span></span>

<span data-ttu-id="679ba-3556">Depende del estado, por ejemplo, Nueva York:</span><span class="sxs-lookup"><span data-stu-id="679ba-3556">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="679ba-3557">Nueve dígitos con formato como DDD DDD DDD coincidirán.</span><span class="sxs-lookup"><span data-stu-id="679ba-3557">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="679ba-3558">Nueve dígitos como ddddddddd no coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="679ba-3558">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3559">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3559">Checksum</span></span>

<span data-ttu-id="679ba-3560">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3560">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3561">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3561">Definition</span></span>

<span data-ttu-id="679ba-3562">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3562">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3563">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3563">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3564">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="679ba-3564">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="679ba-3565">Se encuentra una palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="679ba-3565">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="679ba-3566">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3566">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3567">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3567">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3568">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="679ba-3568">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="679ba-3569">Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="679ba-3569">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="679ba-3570">No se encuentra ninguna palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="679ba-3570">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3571">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3571">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="679ba-3572">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="679ba-3572">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="679ba-3573">LISTAS</span><span class="sxs-lookup"><span data-stu-id="679ba-3573">DL</span></span> 
- <span data-ttu-id="679ba-3574">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="679ba-3574">DLS</span></span> 
- <span data-ttu-id="679ba-3575">CDL</span><span class="sxs-lookup"><span data-stu-id="679ba-3575">CDL</span></span> 
- <span data-ttu-id="679ba-3576">CDLS</span><span class="sxs-lookup"><span data-stu-id="679ba-3576">CDLS</span></span> 
- <span data-ttu-id="679ba-3577">ID</span><span class="sxs-lookup"><span data-stu-id="679ba-3577">ID</span></span> 
- <span data-ttu-id="679ba-3578">Falta</span><span class="sxs-lookup"><span data-stu-id="679ba-3578">IDs</span></span> 
- <span data-ttu-id="679ba-3579">LISTAS #</span><span class="sxs-lookup"><span data-stu-id="679ba-3579">DL#</span></span> 
- <span data-ttu-id="679ba-3580">DISTRIBUCIÓN #</span><span class="sxs-lookup"><span data-stu-id="679ba-3580">DLS#</span></span> 
- <span data-ttu-id="679ba-3581">CDL #</span><span class="sxs-lookup"><span data-stu-id="679ba-3581">CDL#</span></span> 
- <span data-ttu-id="679ba-3582">CDLS #</span><span class="sxs-lookup"><span data-stu-id="679ba-3582">CDLS#</span></span> 
- <span data-ttu-id="679ba-3583">IDENTIFICADOR #</span><span class="sxs-lookup"><span data-stu-id="679ba-3583">ID#</span></span>
- <span data-ttu-id="679ba-3584">Falta #</span><span class="sxs-lookup"><span data-stu-id="679ba-3584">IDs#</span></span> 
- <span data-ttu-id="679ba-3585">ID number</span><span class="sxs-lookup"><span data-stu-id="679ba-3585">ID number</span></span> 
- <span data-ttu-id="679ba-3586">ID numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-3586">ID numbers</span></span> 
- <span data-ttu-id="679ba-3587">LIC</span><span class="sxs-lookup"><span data-stu-id="679ba-3587">LIC</span></span> 
- <span data-ttu-id="679ba-3588">LIC #</span><span class="sxs-lookup"><span data-stu-id="679ba-3588">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="679ba-3589">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="679ba-3589">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="679ba-3590">DriverLic</span><span class="sxs-lookup"><span data-stu-id="679ba-3590">DriverLic</span></span> 
- <span data-ttu-id="679ba-3591">DriverLics</span><span class="sxs-lookup"><span data-stu-id="679ba-3591">DriverLics</span></span> 
- <span data-ttu-id="679ba-3592">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-3592">DriverLicense</span></span> 
- <span data-ttu-id="679ba-3593">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-3593">DriverLicenses</span></span> 
- <span data-ttu-id="679ba-3594">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-3594">Driver Lic</span></span> 
- <span data-ttu-id="679ba-3595">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-3595">Driver Lics</span></span> 
- <span data-ttu-id="679ba-3596">Driver License</span><span class="sxs-lookup"><span data-stu-id="679ba-3596">Driver License</span></span> 
- <span data-ttu-id="679ba-3597">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-3597">Driver Licenses</span></span> 
- <span data-ttu-id="679ba-3598">DriversLic</span><span class="sxs-lookup"><span data-stu-id="679ba-3598">DriversLic</span></span> 
- <span data-ttu-id="679ba-3599">DriversLics</span><span class="sxs-lookup"><span data-stu-id="679ba-3599">DriversLics</span></span> 
- <span data-ttu-id="679ba-3600">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-3600">DriversLicense</span></span> 
- <span data-ttu-id="679ba-3601">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-3601">DriversLicenses</span></span> 
- <span data-ttu-id="679ba-3602">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-3602">Drivers Lic</span></span> 
- <span data-ttu-id="679ba-3603">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-3603">Drivers Lics</span></span> 
- <span data-ttu-id="679ba-3604">Drivers License</span><span class="sxs-lookup"><span data-stu-id="679ba-3604">Drivers License</span></span> 
- <span data-ttu-id="679ba-3605">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-3605">Drivers Licenses</span></span> 
- <span data-ttu-id="679ba-3606">N.º carné</span><span class="sxs-lookup"><span data-stu-id="679ba-3606">Driver'Lic</span></span> 
- <span data-ttu-id="679ba-3607">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="679ba-3607">Driver'Lics</span></span> 
- <span data-ttu-id="679ba-3608">Conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-3608">Driver'License</span></span> 
- <span data-ttu-id="679ba-3609">Conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-3609">Driver'Licenses</span></span> 
- <span data-ttu-id="679ba-3610">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-3610">Driver' Lic</span></span> 
- <span data-ttu-id="679ba-3611">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-3611">Driver' Lics</span></span> 
- <span data-ttu-id="679ba-3612">Driver' License</span><span class="sxs-lookup"><span data-stu-id="679ba-3612">Driver' License</span></span> 
- <span data-ttu-id="679ba-3613">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="679ba-3613">Driver' Licenses</span></span>
- <span data-ttu-id="679ba-3614">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="679ba-3614">Driver'sLic</span></span> 
- <span data-ttu-id="679ba-3615">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="679ba-3615">Driver'sLics</span></span> 
- <span data-ttu-id="679ba-3616">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="679ba-3616">Driver'sLicense</span></span> 
- <span data-ttu-id="679ba-3617">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="679ba-3617">Driver'sLicenses</span></span> 
- <span data-ttu-id="679ba-3618">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="679ba-3618">Driver's Lic</span></span> 
- <span data-ttu-id="679ba-3619">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="679ba-3619">Driver's Lics</span></span> 
- <span data-ttu-id="679ba-3620">Driver's License</span><span class="sxs-lookup"><span data-stu-id="679ba-3620">Driver's License</span></span> 
- <span data-ttu-id="679ba-3621">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="679ba-3621">Driver's Licenses</span></span> 
- <span data-ttu-id="679ba-3622">identification number</span><span class="sxs-lookup"><span data-stu-id="679ba-3622">identification number</span></span> 
- <span data-ttu-id="679ba-3623">identification numbers</span><span class="sxs-lookup"><span data-stu-id="679ba-3623">identification numbers</span></span> 
- <span data-ttu-id="679ba-3624">identification #</span><span class="sxs-lookup"><span data-stu-id="679ba-3624">identification #</span></span> 
- <span data-ttu-id="679ba-3625">id card</span><span class="sxs-lookup"><span data-stu-id="679ba-3625">id card</span></span> 
- <span data-ttu-id="679ba-3626">id cards</span><span class="sxs-lookup"><span data-stu-id="679ba-3626">id cards</span></span> 
- <span data-ttu-id="679ba-3627">identification card</span><span class="sxs-lookup"><span data-stu-id="679ba-3627">identification card</span></span> 
- <span data-ttu-id="679ba-3628">identification cards</span><span class="sxs-lookup"><span data-stu-id="679ba-3628">identification cards</span></span> 
- <span data-ttu-id="679ba-3629">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-3629">DriverLic#</span></span> 
- <span data-ttu-id="679ba-3630">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-3630">DriverLics#</span></span> 
- <span data-ttu-id="679ba-3631">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-3631">DriverLicense#</span></span> 
- <span data-ttu-id="679ba-3632">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-3632">DriverLicenses#</span></span> 
- <span data-ttu-id="679ba-3633">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-3633">Driver Lic#</span></span> 
- <span data-ttu-id="679ba-3634">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-3634">Driver Lics#</span></span> 
- <span data-ttu-id="679ba-3635">Driver License#</span><span class="sxs-lookup"><span data-stu-id="679ba-3635">Driver License#</span></span> 
- <span data-ttu-id="679ba-3636">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-3636">Driver Licenses#</span></span> 
- <span data-ttu-id="679ba-3637">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-3637">DriversLic#</span></span> 
- <span data-ttu-id="679ba-3638">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-3638">DriversLics#</span></span> 
- <span data-ttu-id="679ba-3639">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-3639">DriversLicense#</span></span> 
- <span data-ttu-id="679ba-3640">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-3640">DriversLicenses#</span></span> 
- <span data-ttu-id="679ba-3641">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-3641">Drivers Lic#</span></span> 
- <span data-ttu-id="679ba-3642">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-3642">Drivers Lics#</span></span> 
- <span data-ttu-id="679ba-3643">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="679ba-3643">Drivers License#</span></span> 
- <span data-ttu-id="679ba-3644">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-3644">Drivers Licenses#</span></span> 
- <span data-ttu-id="679ba-3645">N.º carné #</span><span class="sxs-lookup"><span data-stu-id="679ba-3645">Driver'Lic#</span></span> 
- <span data-ttu-id="679ba-3646">N.º carnés #</span><span class="sxs-lookup"><span data-stu-id="679ba-3646">Driver'Lics#</span></span> 
- <span data-ttu-id="679ba-3647">Conducción #</span><span class="sxs-lookup"><span data-stu-id="679ba-3647">Driver'License#</span></span> 
- <span data-ttu-id="679ba-3648">Conducción #</span><span class="sxs-lookup"><span data-stu-id="679ba-3648">Driver'Licenses#</span></span> 
- <span data-ttu-id="679ba-3649">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-3649">Driver' Lic#</span></span> 
- <span data-ttu-id="679ba-3650">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-3650">Driver' Lics#</span></span> 
- <span data-ttu-id="679ba-3651">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="679ba-3651">Driver' License#</span></span> 
- <span data-ttu-id="679ba-3652">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-3652">Driver' Licenses#</span></span> 
- <span data-ttu-id="679ba-3653">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="679ba-3653">Driver'sLic#</span></span> 
- <span data-ttu-id="679ba-3654">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="679ba-3654">Driver'sLics#</span></span> 
- <span data-ttu-id="679ba-3655">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="679ba-3655">Driver'sLicense#</span></span> 
- <span data-ttu-id="679ba-3656">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="679ba-3656">Driver'sLicenses#</span></span> 
- <span data-ttu-id="679ba-3657">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="679ba-3657">Driver's Lic#</span></span> 
- <span data-ttu-id="679ba-3658">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="679ba-3658">Driver's Lics#</span></span> 
- <span data-ttu-id="679ba-3659">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="679ba-3659">Driver's License#</span></span> 
- <span data-ttu-id="679ba-3660">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="679ba-3660">Driver's Licenses#</span></span> 
- <span data-ttu-id="679ba-3661">id card#</span><span class="sxs-lookup"><span data-stu-id="679ba-3661">id card#</span></span> 
- <span data-ttu-id="679ba-3662">id cards#</span><span class="sxs-lookup"><span data-stu-id="679ba-3662">id cards#</span></span> 
- <span data-ttu-id="679ba-3663">identification card#</span><span class="sxs-lookup"><span data-stu-id="679ba-3663">identification card#</span></span> 
- <span data-ttu-id="679ba-3664">identification cards#</span><span class="sxs-lookup"><span data-stu-id="679ba-3664">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="679ba-3665">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="679ba-3665">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="679ba-3666">Abreviatura del estado (por ejemplo, "NY")</span><span class="sxs-lookup"><span data-stu-id="679ba-3666">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="679ba-3667">Nombre del estado (por ejemplo, "New York")</span><span class="sxs-lookup"><span data-stu-id="679ba-3667">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="679ba-3668">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="679ba-3668">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3669">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3669">Format</span></span>

<span data-ttu-id="679ba-3670">Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="679ba-3670">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3671">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3671">Pattern</span></span>

<span data-ttu-id="679ba-3672">Con formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3672">Formatted:</span></span>
- <span data-ttu-id="679ba-3673">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="679ba-3673">The digit "9"</span></span> 
- <span data-ttu-id="679ba-3674">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3674">Two digits</span></span> 
- <span data-ttu-id="679ba-3675">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-3675">A space or dash</span></span> 
- <span data-ttu-id="679ba-3676">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="679ba-3676">A "7" or "8"</span></span> 
- <span data-ttu-id="679ba-3677">Un dígito</span><span class="sxs-lookup"><span data-stu-id="679ba-3677">A digit</span></span> 
- <span data-ttu-id="679ba-3678">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="679ba-3678">A space, or dash</span></span> 
- <span data-ttu-id="679ba-3679">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3679">Four digits</span></span>

<span data-ttu-id="679ba-3680">Sin formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3680">Unformatted:</span></span>
- <span data-ttu-id="679ba-3681">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="679ba-3681">The digit "9"</span></span> 
- <span data-ttu-id="679ba-3682">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3682">Two digits</span></span> 
- <span data-ttu-id="679ba-3683">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="679ba-3683">A "7" or "8"</span></span> 
- <span data-ttu-id="679ba-3684">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="679ba-3684">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3685">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3685">Checksum</span></span>

<span data-ttu-id="679ba-3686">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3686">No</span></span>

### <a name="definition"></a><span data-ttu-id="679ba-3687">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3687">Definition</span></span>

<span data-ttu-id="679ba-3688">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3689">La función Func_formatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3689">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3690">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-3690">At least one of the following is true:</span></span>
    - <span data-ttu-id="679ba-3691">Se encuentra una palabra clave de Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="679ba-3691">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="679ba-3692">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3692">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="679ba-3693">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3693">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="679ba-3694">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="679ba-3694">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="679ba-3695">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3695">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3696">La función Func_unformatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3696">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3697">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="679ba-3697">At least one of the following is true:</span></span>
    - <span data-ttu-id="679ba-3698">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="679ba-3698">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="679ba-3699">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3699">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="679ba-3700">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3700">The function Func_us_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="679ba-3701">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3701">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="679ba-3702">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="679ba-3702">Keyword_itin</span></span>

- <span data-ttu-id="679ba-3703">contribuyente</span><span class="sxs-lookup"><span data-stu-id="679ba-3703">taxpayer</span></span> 
- <span data-ttu-id="679ba-3704">tax id</span><span class="sxs-lookup"><span data-stu-id="679ba-3704">tax id</span></span> 
- <span data-ttu-id="679ba-3705">tax identification</span><span class="sxs-lookup"><span data-stu-id="679ba-3705">tax identification</span></span> 
- <span data-ttu-id="679ba-3706">élen</span><span class="sxs-lookup"><span data-stu-id="679ba-3706">itin</span></span> 
- <span data-ttu-id="679ba-3707">SSN</span><span class="sxs-lookup"><span data-stu-id="679ba-3707">ssn</span></span> 
- <span data-ttu-id="679ba-3708">/</span><span class="sxs-lookup"><span data-stu-id="679ba-3708">tin</span></span> 
- <span data-ttu-id="679ba-3709">social security</span><span class="sxs-lookup"><span data-stu-id="679ba-3709">social security</span></span> 
- <span data-ttu-id="679ba-3710">tax payer</span><span class="sxs-lookup"><span data-stu-id="679ba-3710">tax payer</span></span> 
- <span data-ttu-id="679ba-3711">itins</span><span class="sxs-lookup"><span data-stu-id="679ba-3711">itins</span></span> 
- <span data-ttu-id="679ba-3712">taxi</span><span class="sxs-lookup"><span data-stu-id="679ba-3712">taxid</span></span> 
- <span data-ttu-id="679ba-3713">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="679ba-3713">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="679ba-3714">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="679ba-3714">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="679ba-3715">Licencia</span><span class="sxs-lookup"><span data-stu-id="679ba-3715">License</span></span> 
- <span data-ttu-id="679ba-3716">LISTAS</span><span class="sxs-lookup"><span data-stu-id="679ba-3716">DL</span></span> 
- <span data-ttu-id="679ba-3717">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="679ba-3717">DOB</span></span> 
- <span data-ttu-id="679ba-3718">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-3718">Birthdate</span></span> 
- <span data-ttu-id="679ba-3719">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="679ba-3719">Birthday</span></span> 
- <span data-ttu-id="679ba-3720">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="679ba-3720">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="679ba-3721">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="679ba-3721">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="679ba-3722">Formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3722">Format</span></span>

<span data-ttu-id="679ba-3723">9 dígitos, que pueden ser un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="679ba-3723">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="679ba-3724">Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="679ba-3724">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="679ba-3725">Patrón</span><span class="sxs-lookup"><span data-stu-id="679ba-3725">Pattern</span></span>

<span data-ttu-id="679ba-3726">Cuatro funciones buscan SSN en cuatro patrones diferentes:</span><span class="sxs-lookup"><span data-stu-id="679ba-3726">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="679ba-3727">Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="679ba-3727">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="679ba-3728">Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="679ba-3728">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="679ba-3729">Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="679ba-3729">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="679ba-3730">Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="679ba-3730">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="679ba-3731">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="679ba-3731">Checksum</span></span>

<span data-ttu-id="679ba-3732">No</span><span class="sxs-lookup"><span data-stu-id="679ba-3732">No</span></span>


### <a name="definition"></a><span data-ttu-id="679ba-3733">Definición</span><span class="sxs-lookup"><span data-stu-id="679ba-3733">Definition</span></span>

<span data-ttu-id="679ba-3734">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3735">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3735">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3736">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="679ba-3736">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="679ba-3737">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3737">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-3738">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3738">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="679ba-3739">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3739">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3740">La función Func_unformatted_ssn busca contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3740">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3741">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="679ba-3741">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="679ba-3742">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3742">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-3743">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3743">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="679ba-3744">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3744">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3745">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3745">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3746">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="679ba-3746">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="679ba-3747">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3747">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-3748">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3748">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="679ba-3749">Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3749">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3750">La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3750">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3751">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="679ba-3751">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="679ba-3752">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3752">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="679ba-3753">La función Func_us_address encuentra una dirección en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="679ba-3753">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="679ba-3754">Una directiva DLP está 40% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="679ba-3754">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="679ba-3755">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3755">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3756">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3756">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3757">La función Func_randomized_unformatted_ssn no encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3757">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3758">No se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="679ba-3758">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="679ba-3759">O bien</span><span class="sxs-lookup"><span data-stu-id="679ba-3759">Or</span></span>

- <span data-ttu-id="679ba-3760">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3760">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3761">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3761">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3762">La función Func_randomized_unformatted_ssn no encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="679ba-3762">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="679ba-3763">No se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="679ba-3763">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="679ba-3764">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="679ba-3764">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="679ba-3765">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="679ba-3765">Keyword_ssn</span></span>

- <span data-ttu-id="679ba-3766">Social Security</span><span class="sxs-lookup"><span data-stu-id="679ba-3766">Social Security</span></span> 
- <span data-ttu-id="679ba-3767">Social Security#</span><span class="sxs-lookup"><span data-stu-id="679ba-3767">Social Security#</span></span> 
- <span data-ttu-id="679ba-3768">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="679ba-3768">Soc Sec</span></span> 
- <span data-ttu-id="679ba-3769">SSN</span><span class="sxs-lookup"><span data-stu-id="679ba-3769">SSN</span></span> 
- <span data-ttu-id="679ba-3770">SSN</span><span class="sxs-lookup"><span data-stu-id="679ba-3770">SSNS</span></span> 
- <span data-ttu-id="679ba-3771">SSN #</span><span class="sxs-lookup"><span data-stu-id="679ba-3771">SSN#</span></span> 
- <span data-ttu-id="679ba-3772">SS #</span><span class="sxs-lookup"><span data-stu-id="679ba-3772">SS#</span></span> 
- <span data-ttu-id="679ba-3773">SSID</span><span class="sxs-lookup"><span data-stu-id="679ba-3773">SSID</span></span> 
   

