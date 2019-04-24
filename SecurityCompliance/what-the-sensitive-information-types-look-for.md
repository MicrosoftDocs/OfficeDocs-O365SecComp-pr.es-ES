---
title: Qué buscan los tipos de información confidencial
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: d161435c75149183289cfbfd6abe79d55e371e31
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266876"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="4c713-104">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4c713-104">What the sensitive information types look for</span></span>

<span data-ttu-id="4c713-105">La prevención de pérdida de datos (DLP) en el &amp; centro de seguridad y cumplimiento de Office 365 incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="4c713-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="4c713-106">Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.</span><span class="sxs-lookup"><span data-stu-id="4c713-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="4c713-107">Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función.</span><span class="sxs-lookup"><span data-stu-id="4c713-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="4c713-108">Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="4c713-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="4c713-109">El nivel de confianza y la proximidad también se usan en el proceso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="4c713-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="4c713-110">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="4c713-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-111">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-111">Format</span></span>

<span data-ttu-id="4c713-112">9 dígitos, que pueden tener un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="4c713-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-113">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-113">Pattern</span></span>

<span data-ttu-id="4c713-114">Con formato</span><span class="sxs-lookup"><span data-stu-id="4c713-114">Formatted:</span></span>
- <span data-ttu-id="4c713-115">Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="4c713-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="4c713-116">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-116">A hyphen</span></span>
- <span data-ttu-id="4c713-117">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-117">Four digits</span></span>
- <span data-ttu-id="4c713-118">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-118">A hyphen</span></span>
- <span data-ttu-id="4c713-119">Un dígito</span><span class="sxs-lookup"><span data-stu-id="4c713-119">A digit</span></span>

<span data-ttu-id="4c713-120">Sin formato: 9 dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8</span><span class="sxs-lookup"><span data-stu-id="4c713-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="4c713-121">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-121">Checksum</span></span>

<span data-ttu-id="4c713-122">No</span><span class="sxs-lookup"><span data-stu-id="4c713-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-123">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-123">Definition</span></span>

<span data-ttu-id="4c713-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-125">La función Func_aba_routing encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-126">Se encuentra una palabra clave de Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="4c713-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="4c713-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="4c713-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="4c713-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="4c713-129">ABA</span><span class="sxs-lookup"><span data-stu-id="4c713-129">aba</span></span>
- <span data-ttu-id="4c713-130">aba #</span><span class="sxs-lookup"><span data-stu-id="4c713-130">aba #</span></span>
- <span data-ttu-id="4c713-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="4c713-131">aba routing #</span></span>
- <span data-ttu-id="4c713-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="4c713-132">aba routing number</span></span>
- <span data-ttu-id="4c713-133">ABA</span><span class="sxs-lookup"><span data-stu-id="4c713-133">aba#</span></span>
- <span data-ttu-id="4c713-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="4c713-134">abarouting#</span></span>
- <span data-ttu-id="4c713-135">aba number</span><span class="sxs-lookup"><span data-stu-id="4c713-135">aba number</span></span>
- <span data-ttu-id="4c713-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-136">abaroutingnumber</span></span>
- <span data-ttu-id="4c713-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="4c713-137">american bank association routing #</span></span>
- <span data-ttu-id="4c713-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="4c713-138">american bank association routing number</span></span>
- <span data-ttu-id="4c713-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="4c713-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="4c713-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="4c713-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="4c713-141">bank routing number</span></span>
- <span data-ttu-id="4c713-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="4c713-142">bankrouting#</span></span>
- <span data-ttu-id="4c713-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-143">bankroutingnumber</span></span>
- <span data-ttu-id="4c713-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="4c713-144">routing transit number</span></span>
- <span data-ttu-id="4c713-145">RTN</span><span class="sxs-lookup"><span data-stu-id="4c713-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="4c713-146">Número de identidad nacional (DNI) de Argentina</span><span class="sxs-lookup"><span data-stu-id="4c713-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-147">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-147">Format</span></span>

<span data-ttu-id="4c713-148">Ocho dígitos separados por puntos</span><span class="sxs-lookup"><span data-stu-id="4c713-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-149">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-149">Pattern</span></span>

<span data-ttu-id="4c713-150">Ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-150">Eight digits:</span></span>
- <span data-ttu-id="4c713-151">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-151">Two digits</span></span>
- <span data-ttu-id="4c713-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-152">A period</span></span>
- <span data-ttu-id="4c713-153">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-153">Three digits</span></span>
- <span data-ttu-id="4c713-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-154">A period</span></span>
- <span data-ttu-id="4c713-155">Tres dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-156">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-156">Checksum</span></span>

<span data-ttu-id="4c713-157">No</span><span class="sxs-lookup"><span data-stu-id="4c713-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-158">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-158">Definition</span></span>

<span data-ttu-id="4c713-159">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-160">La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-161">Se encuentra una palabra clave de Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="4c713-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-162">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="4c713-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="4c713-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="4c713-164">Número de identidad nacional de Argentina</span><span class="sxs-lookup"><span data-stu-id="4c713-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="4c713-165">Identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-165">Identity</span></span> 
- <span data-ttu-id="4c713-166">Tarjeta de identidad nacional de identificación</span><span class="sxs-lookup"><span data-stu-id="4c713-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="4c713-167">DNI</span><span class="sxs-lookup"><span data-stu-id="4c713-167">DNI</span></span> 
- <span data-ttu-id="4c713-168">Registro Nacional de NIC de personas</span><span class="sxs-lookup"><span data-stu-id="4c713-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="4c713-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="4c713-170">Registro nacional de las personas</span><span class="sxs-lookup"><span data-stu-id="4c713-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="4c713-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-171">Identidad</span></span> 
- <span data-ttu-id="4c713-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="4c713-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="4c713-173">Número de cuenta bancaria de Australia</span><span class="sxs-lookup"><span data-stu-id="4c713-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-174">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-174">Format</span></span>

<span data-ttu-id="4c713-175">De 6 a 10 dígitos con o sin número de sucursal bancaria de estado</span><span class="sxs-lookup"><span data-stu-id="4c713-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-176">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-176">Pattern</span></span>

<span data-ttu-id="4c713-177">El número de cuenta tiene entre 6 y 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="4c713-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="4c713-178">Número de sucursal bancaria de Australia:</span><span class="sxs-lookup"><span data-stu-id="4c713-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="4c713-179">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-179">Three digits</span></span> 
- <span data-ttu-id="4c713-180">Un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-180">A hyphen</span></span> 
- <span data-ttu-id="4c713-181">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-182">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-182">Checksum</span></span>

<span data-ttu-id="4c713-183">No</span><span class="sxs-lookup"><span data-stu-id="4c713-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-184">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-184">Definition</span></span>

<span data-ttu-id="4c713-185">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-186">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="4c713-187">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="4c713-188">La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="4c713-189">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-190">La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="4c713-191">Se encuentra una palabra clave de Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-192">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="4c713-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="4c713-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="4c713-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="4c713-194">swift bank code</span></span>
- <span data-ttu-id="4c713-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="4c713-195">correspondent bank</span></span>
- <span data-ttu-id="4c713-196">base currency</span><span class="sxs-lookup"><span data-stu-id="4c713-196">base currency</span></span>
- <span data-ttu-id="4c713-197">usa account</span><span class="sxs-lookup"><span data-stu-id="4c713-197">usa account</span></span>
- <span data-ttu-id="4c713-198">holder address</span><span class="sxs-lookup"><span data-stu-id="4c713-198">holder address</span></span>
- <span data-ttu-id="4c713-199">bank address</span><span class="sxs-lookup"><span data-stu-id="4c713-199">bank address</span></span>
- <span data-ttu-id="4c713-200">information account</span><span class="sxs-lookup"><span data-stu-id="4c713-200">information account</span></span>
- <span data-ttu-id="4c713-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="4c713-201">fund transfers</span></span>
- <span data-ttu-id="4c713-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="4c713-202">bank charges</span></span>
- <span data-ttu-id="4c713-203">bank details</span><span class="sxs-lookup"><span data-stu-id="4c713-203">bank details</span></span>
- <span data-ttu-id="4c713-204">banking information</span><span class="sxs-lookup"><span data-stu-id="4c713-204">banking information</span></span>
- <span data-ttu-id="4c713-205">full names</span><span class="sxs-lookup"><span data-stu-id="4c713-205">full names</span></span>
- <span data-ttu-id="4c713-206">OIEA</span><span class="sxs-lookup"><span data-stu-id="4c713-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="4c713-207">Número de licencia de conducción de Australia</span><span class="sxs-lookup"><span data-stu-id="4c713-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-208">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-208">Format</span></span>

<span data-ttu-id="4c713-209">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-210">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-210">Pattern</span></span>

<span data-ttu-id="4c713-211">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="4c713-212">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-213">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-213">Two digits</span></span> 
- <span data-ttu-id="4c713-214">Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="4c713-215">O</span><span class="sxs-lookup"><span data-stu-id="4c713-215">OR</span></span>

- <span data-ttu-id="4c713-216">1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-217">4-9 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-217">4-9 digits</span></span>

<span data-ttu-id="4c713-218">O</span><span class="sxs-lookup"><span data-stu-id="4c713-218">OR</span></span>

- <span data-ttu-id="4c713-219">Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-220">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-220">Checksum</span></span>

<span data-ttu-id="4c713-221">No</span><span class="sxs-lookup"><span data-stu-id="4c713-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-222">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-222">Definition</span></span>

<span data-ttu-id="4c713-223">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-224">La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-225">Se encuentra una palabra clave de Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="4c713-226">No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="4c713-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="4c713-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4c713-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="4c713-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="4c713-229">international driving permits</span></span>
- <span data-ttu-id="4c713-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="4c713-230">australian automobile association</span></span>
- <span data-ttu-id="4c713-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="4c713-231">international driving permit</span></span>
- <span data-ttu-id="4c713-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="4c713-232">DriverLicence</span></span>
- <span data-ttu-id="4c713-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="4c713-233">DriverLicences</span></span>
- <span data-ttu-id="4c713-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-234">Driver Lic</span></span>
- <span data-ttu-id="4c713-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-235">Driver Licence</span></span>
- <span data-ttu-id="4c713-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-236">Driver Licences</span></span>
- <span data-ttu-id="4c713-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="4c713-237">DriversLic</span></span>
- <span data-ttu-id="4c713-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="4c713-238">DriversLicence</span></span>
- <span data-ttu-id="4c713-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="4c713-239">DriversLicences</span></span>
- <span data-ttu-id="4c713-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-240">Drivers Lic</span></span>
- <span data-ttu-id="4c713-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-241">Drivers Lics</span></span>
- <span data-ttu-id="4c713-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-242">Drivers Licence</span></span>
- <span data-ttu-id="4c713-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-243">Drivers Licences</span></span>
- <span data-ttu-id="4c713-244">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-244">Driver'Lic</span></span>
- <span data-ttu-id="4c713-245">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-245">Driver'Lics</span></span>
- <span data-ttu-id="4c713-246">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-246">Driver'Licence</span></span>
- <span data-ttu-id="4c713-247">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-247">Driver'Licences</span></span>
- <span data-ttu-id="4c713-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-248">Driver' Lic</span></span>
- <span data-ttu-id="4c713-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-249">Driver' Lics</span></span>
- <span data-ttu-id="4c713-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-250">Driver' Licence</span></span>
- <span data-ttu-id="4c713-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-251">Driver' Licences</span></span>
- <span data-ttu-id="4c713-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="4c713-252">Driver'sLic</span></span>
- <span data-ttu-id="4c713-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="4c713-253">Driver'sLics</span></span>
- <span data-ttu-id="4c713-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="4c713-254">Driver'sLicence</span></span>
- <span data-ttu-id="4c713-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="4c713-255">Driver'sLicences</span></span>
- <span data-ttu-id="4c713-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-256">Driver's Lic</span></span>
- <span data-ttu-id="4c713-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-257">Driver's Lics</span></span>
- <span data-ttu-id="4c713-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-258">Driver's Licence</span></span>
- <span data-ttu-id="4c713-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-259">Driver's Licences</span></span>
- <span data-ttu-id="4c713-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-260">DriverLic#</span></span>
- <span data-ttu-id="4c713-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-261">DriverLics#</span></span>
- <span data-ttu-id="4c713-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="4c713-262">DriverLicence#</span></span>
- <span data-ttu-id="4c713-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="4c713-263">DriverLicences#</span></span>
- <span data-ttu-id="4c713-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-264">Driver Lic#</span></span>
- <span data-ttu-id="4c713-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-265">Driver Lics#</span></span>
- <span data-ttu-id="4c713-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="4c713-266">Driver Licence#</span></span>
- <span data-ttu-id="4c713-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-267">Driver Licences#</span></span>
- <span data-ttu-id="4c713-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-268">DriversLic#</span></span>
- <span data-ttu-id="4c713-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-269">DriversLics#</span></span>
- <span data-ttu-id="4c713-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="4c713-270">DriversLicence#</span></span>
- <span data-ttu-id="4c713-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="4c713-271">DriversLicences#</span></span>
- <span data-ttu-id="4c713-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-272">Drivers Lic#</span></span>
- <span data-ttu-id="4c713-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-273">Drivers Lics#</span></span>
- <span data-ttu-id="4c713-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="4c713-274">Drivers Licence#</span></span>
- <span data-ttu-id="4c713-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-275">Drivers Licences#</span></span>
- <span data-ttu-id="4c713-276">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-276">Driver'Lic#</span></span>
- <span data-ttu-id="4c713-277">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-277">Driver'Lics#</span></span>
- <span data-ttu-id="4c713-278">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-278">Driver'Licence#</span></span>
- <span data-ttu-id="4c713-279">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-279">Driver'Licences#</span></span>
- <span data-ttu-id="4c713-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-280">Driver' Lic#</span></span>
- <span data-ttu-id="4c713-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-281">Driver' Lics#</span></span>
- <span data-ttu-id="4c713-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="4c713-282">Driver' Licence#</span></span>
- <span data-ttu-id="4c713-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-283">Driver' Licences#</span></span>
- <span data-ttu-id="4c713-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-284">Driver'sLic#</span></span>
- <span data-ttu-id="4c713-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-285">Driver'sLics#</span></span>
- <span data-ttu-id="4c713-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="4c713-286">Driver'sLicence#</span></span>
- <span data-ttu-id="4c713-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="4c713-287">Driver'sLicences#</span></span>
- <span data-ttu-id="4c713-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-288">Driver's Lic#</span></span>
- <span data-ttu-id="4c713-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-289">Driver's Lics#</span></span>
- <span data-ttu-id="4c713-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="4c713-290">Driver's Licence#</span></span>
- <span data-ttu-id="4c713-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="4c713-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="4c713-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="4c713-293">aaaa</span><span class="sxs-lookup"><span data-stu-id="4c713-293">aaa</span></span>
- <span data-ttu-id="4c713-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-294">DriverLicense</span></span>
- <span data-ttu-id="4c713-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-295">DriverLicenses</span></span>
- <span data-ttu-id="4c713-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="4c713-296">Driver License</span></span>
- <span data-ttu-id="4c713-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-297">Driver Licenses</span></span>
- <span data-ttu-id="4c713-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-298">DriversLicense</span></span>
- <span data-ttu-id="4c713-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-299">DriversLicenses</span></span>
- <span data-ttu-id="4c713-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4c713-300">Drivers License</span></span>
- <span data-ttu-id="4c713-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-301">Drivers Licenses</span></span>
- <span data-ttu-id="4c713-302">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-302">Driver'License</span></span>
- <span data-ttu-id="4c713-303">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-303">Driver'Licenses</span></span>
- <span data-ttu-id="4c713-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="4c713-304">Driver' License</span></span>
- <span data-ttu-id="4c713-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-305">Driver' Licenses</span></span>
- <span data-ttu-id="4c713-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-306">Driver'sLicense</span></span>
- <span data-ttu-id="4c713-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-307">Driver'sLicenses</span></span>
- <span data-ttu-id="4c713-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4c713-308">Driver's License</span></span>
- <span data-ttu-id="4c713-309">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-309">Driver's Licenses</span></span>
- <span data-ttu-id="4c713-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-310">DriverLicense#</span></span>
- <span data-ttu-id="4c713-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-311">DriverLicenses#</span></span>
- <span data-ttu-id="4c713-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4c713-312">Driver License#</span></span>
- <span data-ttu-id="4c713-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-313">Driver Licenses#</span></span>
- <span data-ttu-id="4c713-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-314">DriversLicense#</span></span>
- <span data-ttu-id="4c713-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-315">DriversLicenses#</span></span>
- <span data-ttu-id="4c713-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="4c713-316">Drivers License#</span></span>
- <span data-ttu-id="4c713-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-317">Drivers Licenses#</span></span>
- <span data-ttu-id="4c713-318">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-318">Driver'License#</span></span>
- <span data-ttu-id="4c713-319">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-319">Driver'Licenses#</span></span>
- <span data-ttu-id="4c713-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="4c713-320">Driver' License#</span></span>
- <span data-ttu-id="4c713-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-321">Driver' Licenses#</span></span>
- <span data-ttu-id="4c713-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-322">Driver'sLicense#</span></span>
- <span data-ttu-id="4c713-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="4c713-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="4c713-324">Driver's License#</span></span>
- <span data-ttu-id="4c713-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="4c713-326">Número de cuenta médica de Australia</span><span class="sxs-lookup"><span data-stu-id="4c713-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-327">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-327">Format</span></span>

<span data-ttu-id="4c713-328">Entre 10 y 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-329">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-329">Pattern</span></span>

<span data-ttu-id="4c713-330">Entre 10 y 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-330">10-11 digits:</span></span>
- <span data-ttu-id="4c713-331">el primer dígito está en el intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="4c713-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="4c713-332">El noveno dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="4c713-333">El décimo dígito es el dígito de emisión</span><span class="sxs-lookup"><span data-stu-id="4c713-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="4c713-334">El undécimo dígito (opcional) es el número individual</span><span class="sxs-lookup"><span data-stu-id="4c713-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-335">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-335">Checksum</span></span>

<span data-ttu-id="4c713-336">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-337">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-337">Definition</span></span>

<span data-ttu-id="4c713-338">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-339">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-340">Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="4c713-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="4c713-341">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-341">The checksum passes.</span></span>

<span data-ttu-id="4c713-342">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-343">La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-344">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-345">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="4c713-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="4c713-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="4c713-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="4c713-347">bank account details</span></span>
- <span data-ttu-id="4c713-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="4c713-348">medicare payments</span></span>
- <span data-ttu-id="4c713-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="4c713-349">mortgage account</span></span>
- <span data-ttu-id="4c713-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="4c713-350">bank payments</span></span>
- <span data-ttu-id="4c713-351">information branch</span><span class="sxs-lookup"><span data-stu-id="4c713-351">information branch</span></span>
- <span data-ttu-id="4c713-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="4c713-352">credit card loan</span></span>
- <span data-ttu-id="4c713-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="4c713-353">department of human services</span></span>
- <span data-ttu-id="4c713-354">local service</span><span class="sxs-lookup"><span data-stu-id="4c713-354">local service</span></span>
- <span data-ttu-id="4c713-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="4c713-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="4c713-356">Número de pasaporte de Australia</span><span class="sxs-lookup"><span data-stu-id="4c713-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-357">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-357">Format</span></span>

<span data-ttu-id="4c713-358">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-359">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-359">Pattern</span></span>

<span data-ttu-id="4c713-360">Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-361">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-361">Checksum</span></span>

<span data-ttu-id="4c713-362">No</span><span class="sxs-lookup"><span data-stu-id="4c713-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-363">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-363">Definition</span></span>

<span data-ttu-id="4c713-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-365">La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-366">Se encuentra una palabra clave de Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-367">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="4c713-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-368">Keyword_passport</span></span>

- <span data-ttu-id="4c713-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4c713-369">Passport Number</span></span>
- <span data-ttu-id="4c713-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="4c713-370">Passport No</span></span>
- <span data-ttu-id="4c713-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="4c713-371">Passport #</span></span>
- <span data-ttu-id="4c713-372">Usuarios</span><span class="sxs-lookup"><span data-stu-id="4c713-372">Passport#</span></span>
- <span data-ttu-id="4c713-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="4c713-373">PassportID</span></span>
- <span data-ttu-id="4c713-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="4c713-374">Passportno</span></span>
- <span data-ttu-id="4c713-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-375">passportnumber</span></span>
- <span data-ttu-id="4c713-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="4c713-376">パスポート</span></span>
- <span data-ttu-id="4c713-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4c713-377">パスポート番号</span></span>
- <span data-ttu-id="4c713-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4c713-378">パスポートのNum</span></span>
- <span data-ttu-id="4c713-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="4c713-379">パスポート ＃</span></span> 
- <span data-ttu-id="4c713-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4c713-380">Numéro de passeport</span></span>
- <span data-ttu-id="4c713-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4c713-381">Passeport n °</span></span>
- <span data-ttu-id="4c713-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4c713-382">Passeport Non</span></span>
- <span data-ttu-id="4c713-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-383">Passeport #</span></span>
- <span data-ttu-id="4c713-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-384">Passeport#</span></span>
- <span data-ttu-id="4c713-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4c713-385">PasseportNon</span></span>
- <span data-ttu-id="4c713-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4c713-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="4c713-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="4c713-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="4c713-388">usuarios</span><span class="sxs-lookup"><span data-stu-id="4c713-388">passport</span></span>
- <span data-ttu-id="4c713-389">passport details</span><span class="sxs-lookup"><span data-stu-id="4c713-389">passport details</span></span>
- <span data-ttu-id="4c713-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="4c713-390">immigration and citizenship</span></span>
- <span data-ttu-id="4c713-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="4c713-391">commonwealth of australia</span></span>
- <span data-ttu-id="4c713-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="4c713-392">department of immigration</span></span>
- <span data-ttu-id="4c713-393">residential address</span><span class="sxs-lookup"><span data-stu-id="4c713-393">residential address</span></span>
- <span data-ttu-id="4c713-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="4c713-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="4c713-395">régimen</span><span class="sxs-lookup"><span data-stu-id="4c713-395">visa</span></span>
- <span data-ttu-id="4c713-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="4c713-396">national identity card</span></span>
- <span data-ttu-id="4c713-397">passport number</span><span class="sxs-lookup"><span data-stu-id="4c713-397">passport number</span></span>
- <span data-ttu-id="4c713-398">travel document</span><span class="sxs-lookup"><span data-stu-id="4c713-398">travel document</span></span>
- <span data-ttu-id="4c713-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="4c713-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="4c713-400">Número de archivo de impuestos de Australia</span><span class="sxs-lookup"><span data-stu-id="4c713-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-401">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-401">Format</span></span>

<span data-ttu-id="4c713-402">Entre 8 y 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-403">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-403">Pattern</span></span>

<span data-ttu-id="4c713-404">8-9 dígitos que normalmente se presentan con espacios como sigue:</span><span class="sxs-lookup"><span data-stu-id="4c713-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="4c713-405">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-405">Three digits</span></span> 
- <span data-ttu-id="4c713-406">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="4c713-406">An optional space</span></span> 
- <span data-ttu-id="4c713-407">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-407">Three digits</span></span> 
- <span data-ttu-id="4c713-408">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="4c713-408">An optional space</span></span> 
- <span data-ttu-id="4c713-409">2-3 dígitos donde el último dígito es un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-410">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-410">Checksum</span></span>

<span data-ttu-id="4c713-411">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-412">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-412">Definition</span></span>

<span data-ttu-id="4c713-413">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-414">La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-415">No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="4c713-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="4c713-416">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="4c713-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="4c713-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="4c713-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="4c713-419">australian business number</span></span>
- <span data-ttu-id="4c713-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="4c713-420">marginal tax rate</span></span>
- <span data-ttu-id="4c713-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="4c713-421">medicare levy</span></span>
- <span data-ttu-id="4c713-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="4c713-422">portfolio number</span></span>
- <span data-ttu-id="4c713-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="4c713-423">service veterans</span></span>
- <span data-ttu-id="4c713-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="4c713-424">withholding tax</span></span>
- <span data-ttu-id="4c713-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="4c713-425">individual tax return</span></span>
- <span data-ttu-id="4c713-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="4c713-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="4c713-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="4c713-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="4c713-428">00000000</span><span class="sxs-lookup"><span data-stu-id="4c713-428">00000000</span></span>
- <span data-ttu-id="4c713-429">11111111</span><span class="sxs-lookup"><span data-stu-id="4c713-429">11111111</span></span>
- <span data-ttu-id="4c713-430">22222222</span><span class="sxs-lookup"><span data-stu-id="4c713-430">22222222</span></span>
- <span data-ttu-id="4c713-431">33333333</span><span class="sxs-lookup"><span data-stu-id="4c713-431">33333333</span></span>
- <span data-ttu-id="4c713-432">44444444</span><span class="sxs-lookup"><span data-stu-id="4c713-432">44444444</span></span>
- <span data-ttu-id="4c713-433">55555555</span><span class="sxs-lookup"><span data-stu-id="4c713-433">55555555</span></span>
- <span data-ttu-id="4c713-434">66666666</span><span class="sxs-lookup"><span data-stu-id="4c713-434">66666666</span></span>
- <span data-ttu-id="4c713-435">77777777</span><span class="sxs-lookup"><span data-stu-id="4c713-435">77777777</span></span>
- <span data-ttu-id="4c713-436">88888888</span><span class="sxs-lookup"><span data-stu-id="4c713-436">88888888</span></span>
- <span data-ttu-id="4c713-437">99999999</span><span class="sxs-lookup"><span data-stu-id="4c713-437">99999999</span></span>
- <span data-ttu-id="4c713-438">000000000</span><span class="sxs-lookup"><span data-stu-id="4c713-438">000000000</span></span>
- <span data-ttu-id="4c713-439">111111111</span><span class="sxs-lookup"><span data-stu-id="4c713-439">111111111</span></span>
- <span data-ttu-id="4c713-440">222222222</span><span class="sxs-lookup"><span data-stu-id="4c713-440">222222222</span></span>
- <span data-ttu-id="4c713-441">333333333</span><span class="sxs-lookup"><span data-stu-id="4c713-441">333333333</span></span>
- <span data-ttu-id="4c713-442">444444444</span><span class="sxs-lookup"><span data-stu-id="4c713-442">444444444</span></span>
- <span data-ttu-id="4c713-443">555555555</span><span class="sxs-lookup"><span data-stu-id="4c713-443">555555555</span></span>
- <span data-ttu-id="4c713-444">666666666</span><span class="sxs-lookup"><span data-stu-id="4c713-444">666666666</span></span>
- <span data-ttu-id="4c713-445">777777777</span><span class="sxs-lookup"><span data-stu-id="4c713-445">777777777</span></span>
- <span data-ttu-id="4c713-446">888888888</span><span class="sxs-lookup"><span data-stu-id="4c713-446">888888888</span></span>
- <span data-ttu-id="4c713-447">999999999</span><span class="sxs-lookup"><span data-stu-id="4c713-447">999999999</span></span>
- <span data-ttu-id="4c713-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="4c713-448">0000000000</span></span>
- <span data-ttu-id="4c713-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="4c713-449">1111111111</span></span>
- <span data-ttu-id="4c713-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="4c713-450">2222222222</span></span>
- <span data-ttu-id="4c713-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="4c713-451">3333333333</span></span>
- <span data-ttu-id="4c713-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="4c713-452">4444444444</span></span>
- <span data-ttu-id="4c713-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="4c713-453">5555555555</span></span>
- <span data-ttu-id="4c713-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="4c713-454">6666666666</span></span>
- <span data-ttu-id="4c713-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="4c713-455">7777777777</span></span>
- <span data-ttu-id="4c713-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="4c713-456">8888888888</span></span>
- <span data-ttu-id="4c713-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="4c713-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="4c713-458">Clave de autenticación de Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="4c713-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="4c713-459">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-459">Format</span></span>

<span data-ttu-id="4c713-460">La cadena "DocumentDb" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c713-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-461">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-461">Pattern</span></span>

- <span data-ttu-id="4c713-462">La cadena "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="4c713-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="4c713-463">Cualquier combinación de entre 3-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-464">Un símbolo mayor que (>), un signo igual (=), una comilla (") o un apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="4c713-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="4c713-465">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="4c713-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4c713-466">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-467">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-467">Checksum</span></span>

<span data-ttu-id="4c713-468">No</span><span class="sxs-lookup"><span data-stu-id="4c713-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-469">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-469">Definition</span></span>

<span data-ttu-id="4c713-470">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-471">La expresión regular CEP_Regex_AzureDocumentDBAuthKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-472">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-473">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-475">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-476">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-476">contoso</span></span>
- <span data-ttu-id="4c713-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-477">fabrikam</span></span>
- <span data-ttu-id="4c713-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-478">northwind</span></span>
- <span data-ttu-id="4c713-479">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-479">sandbox</span></span>
- <span data-ttu-id="4c713-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-480">onebox</span></span>
- <span data-ttu-id="4c713-481">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-481">localhost</span></span>
- <span data-ttu-id="4c713-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-482">127.0.0.1</span></span>
- <span data-ttu-id="4c713-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-484">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-484">com</span></span>
- <span data-ttu-id="4c713-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-486">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="4c713-487">Cadena de conexión de base de datos IAAS de Azure y cadena de conexión SQL de Azure</span><span class="sxs-lookup"><span data-stu-id="4c713-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4c713-488">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-488">Format</span></span>

<span data-ttu-id="4c713-489">La cadena "Server", "Server" o "Data Source" seguida de los caracteres y las cadenas que se describen en el siguiente patrón, incluida la cadena "CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4c713-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-490">com "o" CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4c713-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-491">net "o" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="4c713-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-492">net "y la cadena" Password "o" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="4c713-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-493">Pattern</span></span>

- <span data-ttu-id="4c713-494">La cadena "servidor", "servidor" o "origen de datos"</span><span class="sxs-lookup"><span data-stu-id="4c713-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="4c713-495">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-496">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-496">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-497">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-498">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-499">La cadena "CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4c713-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-500">com "," CloudApp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4c713-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-501">net "o" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="4c713-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-502">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-502">net"</span></span>
- <span data-ttu-id="4c713-503">Cualquier combinación de entre 1-300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-504">La cadena "Password", "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="4c713-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="4c713-505">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-506">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-506">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-507">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-508">Uno o más caracteres que no son un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="4c713-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="4c713-509">Un punto y coma (;), Comillas (") o apóstrofe (')</span><span class="sxs-lookup"><span data-stu-id="4c713-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-510">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-510">Checksum</span></span>

<span data-ttu-id="4c713-511">No</span><span class="sxs-lookup"><span data-stu-id="4c713-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-512">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-512">Definition</span></span>

<span data-ttu-id="4c713-513">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-514">La expresión regular CEP_Regex_AzureConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-515">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-516">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-516">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-518">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-519">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-519">contoso</span></span>
- <span data-ttu-id="4c713-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-520">fabrikam</span></span>
- <span data-ttu-id="4c713-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-521">northwind</span></span>
- <span data-ttu-id="4c713-522">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-522">sandbox</span></span>
- <span data-ttu-id="4c713-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-523">onebox</span></span>
- <span data-ttu-id="4c713-524">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-524">localhost</span></span>
- <span data-ttu-id="4c713-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-525">127.0.0.1</span></span>
- <span data-ttu-id="4c713-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-527">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-527">com</span></span>
- <span data-ttu-id="4c713-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-529">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="4c713-530">Cadena de conexión de Azure IoT</span><span class="sxs-lookup"><span data-stu-id="4c713-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4c713-531">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-531">Format</span></span>

<span data-ttu-id="4c713-532">La cadena "HostName" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="4c713-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-533">net "y" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="4c713-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-534">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-534">Pattern</span></span>

- <span data-ttu-id="4c713-535">La cadena "HostName"</span><span class="sxs-lookup"><span data-stu-id="4c713-535">The string "HostName"</span></span>
- <span data-ttu-id="4c713-536">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-537">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-537">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-538">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-539">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-540">La cadena "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="4c713-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-541">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-541">net"</span></span>
- <span data-ttu-id="4c713-542">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-543">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="4c713-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="4c713-544">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-545">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-545">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-546">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-547">Cualquier combinación de 43 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="4c713-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4c713-548">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-549">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-549">Checksum</span></span>

<span data-ttu-id="4c713-550">No</span><span class="sxs-lookup"><span data-stu-id="4c713-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-551">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-551">Definition</span></span>

<span data-ttu-id="4c713-552">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-553">La expresión regular CEP_Regex_AzureIoTConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-554">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-555">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-555">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-557">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-558">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-558">contoso</span></span>
- <span data-ttu-id="4c713-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-559">fabrikam</span></span>
- <span data-ttu-id="4c713-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-560">northwind</span></span>
- <span data-ttu-id="4c713-561">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-561">sandbox</span></span>
- <span data-ttu-id="4c713-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-562">onebox</span></span>
- <span data-ttu-id="4c713-563">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-563">localhost</span></span>
- <span data-ttu-id="4c713-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-564">127.0.0.1</span></span>
- <span data-ttu-id="4c713-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-566">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-566">com</span></span>
- <span data-ttu-id="4c713-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-568">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="4c713-569">Contraseña de configuración de publicación de Azure</span><span class="sxs-lookup"><span data-stu-id="4c713-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="4c713-570">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-570">Format</span></span>

<span data-ttu-id="4c713-571">La cadena "userpwd =" seguida de una cadena alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="4c713-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-572">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-572">Pattern</span></span>

- <span data-ttu-id="4c713-573">La cadena "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="4c713-573">The string "userpwd="</span></span>
- <span data-ttu-id="4c713-574">Cualquier combinación de 60 letras minúsculas o dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="4c713-575">Un signo de Comillas (")</span><span class="sxs-lookup"><span data-stu-id="4c713-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-576">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-576">Checksum</span></span>

<span data-ttu-id="4c713-577">No</span><span class="sxs-lookup"><span data-stu-id="4c713-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-578">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-578">Definition</span></span>

<span data-ttu-id="4c713-579">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-580">La expresión regular CEP_Regex_AzurePublishSettingPasswords encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-581">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="4c713-582">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-582">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-584">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-585">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-585">contoso</span></span>
- <span data-ttu-id="4c713-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-586">fabrikam</span></span>
- <span data-ttu-id="4c713-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-587">northwind</span></span>
- <span data-ttu-id="4c713-588">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-588">sandbox</span></span>
- <span data-ttu-id="4c713-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-589">onebox</span></span>
- <span data-ttu-id="4c713-590">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-590">localhost</span></span>
- <span data-ttu-id="4c713-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-591">127.0.0.1</span></span>
- <span data-ttu-id="4c713-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-593">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-593">com</span></span>
- <span data-ttu-id="4c713-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-595">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="4c713-596">Cadena de conexión de la caché de Redis de Azure</span><span class="sxs-lookup"><span data-stu-id="4c713-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4c713-597">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-597">Format</span></span>

<span data-ttu-id="4c713-598">La cadena "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="4c713-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-599">net "seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena" Password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="4c713-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-600">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-600">Pattern</span></span>

- <span data-ttu-id="4c713-601">La cadena "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="4c713-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-602">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-602">net"</span></span>
- <span data-ttu-id="4c713-603">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-604">La cadena "Password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="4c713-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="4c713-605">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-606">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-606">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-607">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-608">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="4c713-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4c713-609">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-610">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-610">Checksum</span></span>

<span data-ttu-id="4c713-611">No</span><span class="sxs-lookup"><span data-stu-id="4c713-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-612">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-612">Definition</span></span>

<span data-ttu-id="4c713-613">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-614">La expresión regular CEP_Regex_AzureRedisCacheConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="4c713-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="4c713-615">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-616">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-616">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-618">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-619">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-619">contoso</span></span>
- <span data-ttu-id="4c713-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-620">fabrikam</span></span>
- <span data-ttu-id="4c713-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-621">northwind</span></span>
- <span data-ttu-id="4c713-622">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-622">sandbox</span></span>
- <span data-ttu-id="4c713-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-623">onebox</span></span>
- <span data-ttu-id="4c713-624">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-624">localhost</span></span>
- <span data-ttu-id="4c713-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-625">127.0.0.1</span></span>
- <span data-ttu-id="4c713-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-627">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-627">com</span></span>
- <span data-ttu-id="4c713-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-629">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="4c713-630">ASOCIACIONES de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="4c713-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="4c713-631">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-631">Format</span></span>

<span data-ttu-id="4c713-632">La cadena "SIG" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c713-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-633">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-633">Pattern</span></span>

- <span data-ttu-id="4c713-634">La cadena "SIG"</span><span class="sxs-lookup"><span data-stu-id="4c713-634">The string "sig"</span></span>
- <span data-ttu-id="4c713-635">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-636">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-636">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-637">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-638">Cualquier combinación de entre 43-53 caracteres que sean letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="4c713-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="4c713-639">La cadena "% 3D"</span><span class="sxs-lookup"><span data-stu-id="4c713-639">The string "%3d"</span></span>
- <span data-ttu-id="4c713-640">Cualquier carácter que no sea una letra minúscula o mayúscula, un dígito o un signo de porcentaje (%)</span><span class="sxs-lookup"><span data-stu-id="4c713-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-641">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-641">Checksum</span></span>

<span data-ttu-id="4c713-642">No</span><span class="sxs-lookup"><span data-stu-id="4c713-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-643">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-643">Definition</span></span>

<span data-ttu-id="4c713-644">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-645">La expresión regular CEP_Regex_AzureSAS encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="4c713-646">Cadena de conexión del bus de servicio de Azure</span><span class="sxs-lookup"><span data-stu-id="4c713-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4c713-647">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-647">Format</span></span>

<span data-ttu-id="4c713-648">La cadena "EndPoint" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="4c713-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-649">net "y" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="4c713-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-650">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-650">Pattern</span></span>

- <span data-ttu-id="4c713-651">La cadena "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="4c713-651">The string "EndPoint"</span></span>
- <span data-ttu-id="4c713-652">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-653">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-653">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-654">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-655">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-656">La cadena "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="4c713-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-657">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-657">net"</span></span>
- <span data-ttu-id="4c713-658">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-659">La cadena "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="4c713-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="4c713-660">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-661">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-661">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-662">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-663">Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="4c713-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4c713-664">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-665">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-665">Checksum</span></span>

<span data-ttu-id="4c713-666">No</span><span class="sxs-lookup"><span data-stu-id="4c713-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-667">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-667">Definition</span></span>

<span data-ttu-id="4c713-668">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-669">La expresión regular CEP_Regex_AzureServiceBusConnectionString encuentra contenido que coincide con el patrón..</span><span class="sxs-lookup"><span data-stu-id="4c713-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="4c713-670">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-671">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-671">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-673">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-674">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-674">contoso</span></span>
- <span data-ttu-id="4c713-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-675">fabrikam</span></span>
- <span data-ttu-id="4c713-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-676">northwind</span></span>
- <span data-ttu-id="4c713-677">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-677">sandbox</span></span>
- <span data-ttu-id="4c713-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-678">onebox</span></span>
- <span data-ttu-id="4c713-679">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-679">localhost</span></span>
- <span data-ttu-id="4c713-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-680">127.0.0.1</span></span>
- <span data-ttu-id="4c713-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-682">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-682">com</span></span>
- <span data-ttu-id="4c713-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-684">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="4c713-685">Clave de cuenta de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="4c713-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="4c713-686">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-686">Format</span></span>

<span data-ttu-id="4c713-687">La cadena "DefaultEndpointsProtocol" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="4c713-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-688">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-688">Pattern</span></span>

- <span data-ttu-id="4c713-689">La cadena "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="4c713-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="4c713-690">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-691">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-691">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-692">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-693">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-694">La cadena "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="4c713-694">The string "AccountKey"</span></span>
- <span data-ttu-id="4c713-695">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-696">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-696">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-697">0-2 caracteres de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="4c713-698">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)</span><span class="sxs-lookup"><span data-stu-id="4c713-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4c713-699">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-700">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-700">Checksum</span></span>

<span data-ttu-id="4c713-701">No</span><span class="sxs-lookup"><span data-stu-id="4c713-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-702">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-702">Definition</span></span>

<span data-ttu-id="4c713-703">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-704">La expresión regular CEP_Regex_AzureStorageAccountKey encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-705">La expresión regular CEP_AzureEmulatorStorageAccountFilter no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-706">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-707">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-707">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="4c713-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="4c713-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="4c713-709">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="4c713-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-712">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-713">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-713">contoso</span></span>
- <span data-ttu-id="4c713-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-714">fabrikam</span></span>
- <span data-ttu-id="4c713-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-715">northwind</span></span>
- <span data-ttu-id="4c713-716">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-716">sandbox</span></span>
- <span data-ttu-id="4c713-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-717">onebox</span></span>
- <span data-ttu-id="4c713-718">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-718">localhost</span></span>
- <span data-ttu-id="4c713-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-719">127.0.0.1</span></span>
- <span data-ttu-id="4c713-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-721">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-721">com</span></span>
- <span data-ttu-id="4c713-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-723">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="4c713-724">Clave de cuenta de almacenamiento de Azure (Genérico)</span><span class="sxs-lookup"><span data-stu-id="4c713-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-725">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-725">Format</span></span>

<span data-ttu-id="4c713-726">Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+), precedido o seguido por los caracteres descritos en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c713-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-727">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-727">Pattern</span></span>

- <span data-ttu-id="4c713-728">0-1 del símbolo mayor que (>), apóstrofe ('), signo de igual (=), Comillas (") o almohadilla (#)</span><span class="sxs-lookup"><span data-stu-id="4c713-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="4c713-729">Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+)</span><span class="sxs-lookup"><span data-stu-id="4c713-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4c713-730">Dos signos de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="4c713-731">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-731">Checksum</span></span>

<span data-ttu-id="4c713-732">No</span><span class="sxs-lookup"><span data-stu-id="4c713-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-733">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-733">Definition</span></span>

<span data-ttu-id="4c713-734">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-735">La expresión regular CEP_Regex_AzureStorageAccountKeyGeneric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="4c713-736">Número nacional de Bélgica</span><span class="sxs-lookup"><span data-stu-id="4c713-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-737">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-737">Format</span></span>

<span data-ttu-id="4c713-738">11 dígitos más delimitadores</span><span class="sxs-lookup"><span data-stu-id="4c713-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-739">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-739">Pattern</span></span>

<span data-ttu-id="4c713-740">11 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="4c713-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="4c713-741">Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="4c713-742">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-742">A hyphen</span></span> 
- <span data-ttu-id="4c713-743">Tres dígitos secuenciales (impares para hombres, pares para mujeres) </span><span class="sxs-lookup"><span data-stu-id="4c713-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="4c713-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="4c713-744">A period</span></span> 
- <span data-ttu-id="4c713-745">Dos dígitos que son un dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-746">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-746">Checksum</span></span>

<span data-ttu-id="4c713-747">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-748">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-748">Definition</span></span>

<span data-ttu-id="4c713-749">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-750">La función Func_belgium_national_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-751">Se encuentra una palabra clave de Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="4c713-752">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-752">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-753">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-753">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="4c713-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="4c713-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="4c713-755">Identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-755">Identity</span></span>
- <span data-ttu-id="4c713-756">Registro</span><span class="sxs-lookup"><span data-stu-id="4c713-756">Registration</span></span>
- <span data-ttu-id="4c713-757">Determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-757">Identification</span></span> 
- <span data-ttu-id="4c713-758">ID</span><span class="sxs-lookup"><span data-stu-id="4c713-758">ID</span></span> 
- <span data-ttu-id="4c713-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="4c713-759">Identiteitskaart</span></span>
- <span data-ttu-id="4c713-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="4c713-760">Registratie nummer</span></span> 
- <span data-ttu-id="4c713-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="4c713-761">Identificatie nummer</span></span> 
- <span data-ttu-id="4c713-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="4c713-762">Identiteit</span></span>
- <span data-ttu-id="4c713-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="4c713-763">Registratie</span></span>
- <span data-ttu-id="4c713-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="4c713-764">Identificatie</span></span> 
- <span data-ttu-id="4c713-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="4c713-765">Carte d’identité</span></span> 
- <span data-ttu-id="4c713-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="4c713-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="4c713-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="4c713-767">numéro d'identification</span></span>
- <span data-ttu-id="4c713-768">Identité</span><span class="sxs-lookup"><span data-stu-id="4c713-768">identité</span></span> 
- <span data-ttu-id="4c713-769">indicación</span><span class="sxs-lookup"><span data-stu-id="4c713-769">inscription</span></span> 
- <span data-ttu-id="4c713-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="4c713-770">Identifikation</span></span>
- <span data-ttu-id="4c713-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="4c713-771">Identifizierung</span></span>
- <span data-ttu-id="4c713-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-772">Identifikationsnummer</span></span>
- <span data-ttu-id="4c713-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="4c713-773">Personalausweis</span></span>
- <span data-ttu-id="4c713-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="4c713-774">Registrierung</span></span>
- <span data-ttu-id="4c713-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="4c713-776">Número CPF de Brasil</span><span class="sxs-lookup"><span data-stu-id="4c713-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-777">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-777">Format</span></span>

<span data-ttu-id="4c713-778">11 dígitos incluido un dígito de control y que pueden tener o no formato</span><span class="sxs-lookup"><span data-stu-id="4c713-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-779">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-779">Pattern</span></span>

<span data-ttu-id="4c713-780">Con formato</span><span class="sxs-lookup"><span data-stu-id="4c713-780">Formatted:</span></span>
- <span data-ttu-id="4c713-781">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-781">Three digits</span></span> 
- <span data-ttu-id="4c713-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-782">A period</span></span> 
- <span data-ttu-id="4c713-783">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-783">Three digits</span></span> 
- <span data-ttu-id="4c713-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-784">A period</span></span> 
- <span data-ttu-id="4c713-785">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-785">Three digits</span></span> 
- <span data-ttu-id="4c713-786">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-786">A hyphen</span></span> 
- <span data-ttu-id="4c713-787">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="4c713-787">Two digits which are check digits</span></span>

<span data-ttu-id="4c713-788">Sin formato</span><span class="sxs-lookup"><span data-stu-id="4c713-788">Unformatted:</span></span>
- <span data-ttu-id="4c713-789">11 dígitos, donde los dos últimos dígitos son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="4c713-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-790">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-790">Checksum</span></span>

<span data-ttu-id="4c713-791">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-792">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-792">Definition</span></span>

<span data-ttu-id="4c713-793">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-794">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-795">Se encuentra una palabra clave de Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="4c713-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="4c713-796">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-796">The checksum passes.</span></span>

<span data-ttu-id="4c713-797">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-798">La función Func_brazil_cpf encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-799">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-800">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-800">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="4c713-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="4c713-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="4c713-802">CPF</span><span class="sxs-lookup"><span data-stu-id="4c713-802">CPF</span></span>
- <span data-ttu-id="4c713-803">Determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-803">Identification</span></span>
- <span data-ttu-id="4c713-804">Registro</span><span class="sxs-lookup"><span data-stu-id="4c713-804">Registration</span></span>
- <span data-ttu-id="4c713-805">Generar</span><span class="sxs-lookup"><span data-stu-id="4c713-805">Revenue</span></span>
- <span data-ttu-id="4c713-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="4c713-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="4c713-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="4c713-807">Imposto</span></span> 
- <span data-ttu-id="4c713-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="4c713-808">Identificação</span></span> 
- <span data-ttu-id="4c713-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="4c713-809">Inscrição</span></span> 
- <span data-ttu-id="4c713-810">Receita</span><span class="sxs-lookup"><span data-stu-id="4c713-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="4c713-811">Número de entidad jurídica de Brasil (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="4c713-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-812">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-812">Format</span></span>

<span data-ttu-id="4c713-813">14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores</span><span class="sxs-lookup"><span data-stu-id="4c713-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-814">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-814">Pattern</span></span>
<span data-ttu-id="4c713-815">14 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="4c713-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="4c713-816">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-816">Two digits</span></span> 
- <span data-ttu-id="4c713-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-817">A period</span></span> 
- <span data-ttu-id="4c713-818">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-818">Three digits</span></span> 
- <span data-ttu-id="4c713-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-819">A period</span></span> 
- <span data-ttu-id="4c713-820">Tres dígitos (estos ocho primeros dígitos son el número de registro) </span><span class="sxs-lookup"><span data-stu-id="4c713-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="4c713-821">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="4c713-821">A forward slash</span></span> 
- <span data-ttu-id="4c713-822">Número de sucursal de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-822">Four-digit branch number</span></span> 
- <span data-ttu-id="4c713-823">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-823">A hyphen</span></span> 
- <span data-ttu-id="4c713-824">Dos dígitos que son dígitos de control</span><span class="sxs-lookup"><span data-stu-id="4c713-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-825">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-825">Checksum</span></span>

<span data-ttu-id="4c713-826">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-827">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-827">Definition</span></span>

<span data-ttu-id="4c713-828">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-829">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-830">Se encuentra una palabra clave de Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="4c713-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="4c713-831">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-831">The checksum passes.</span></span>

<span data-ttu-id="4c713-832">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-833">La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-834">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-835">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-835">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="4c713-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="4c713-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="4c713-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="4c713-837">CNPJ</span></span> 
- <span data-ttu-id="4c713-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="4c713-838">CNPJ/MF</span></span> 
- <span data-ttu-id="4c713-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="4c713-839">CNPJ-MF</span></span> 
- <span data-ttu-id="4c713-840">Registro nacional de entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="4c713-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="4c713-841">Registro de contribuyentes</span><span class="sxs-lookup"><span data-stu-id="4c713-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="4c713-842">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="4c713-842">Legal entity</span></span> 
- <span data-ttu-id="4c713-843">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="4c713-843">Legal entities</span></span> 
- <span data-ttu-id="4c713-844">Estado de registro</span><span class="sxs-lookup"><span data-stu-id="4c713-844">Registration Status</span></span> 
- <span data-ttu-id="4c713-845">Empresa</span><span class="sxs-lookup"><span data-stu-id="4c713-845">Business</span></span> 
- <span data-ttu-id="4c713-846">Empresa</span><span class="sxs-lookup"><span data-stu-id="4c713-846">Company</span></span>
- <span data-ttu-id="4c713-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="4c713-847">CNPJ</span></span> 
- <span data-ttu-id="4c713-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="4c713-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="4c713-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="4c713-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="4c713-850">CGC</span><span class="sxs-lookup"><span data-stu-id="4c713-850">CGC</span></span> 
- <span data-ttu-id="4c713-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="4c713-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="4c713-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="4c713-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="4c713-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="4c713-853">Situação cadastral</span></span> 
- <span data-ttu-id="4c713-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="4c713-854">Inscrição</span></span> 
- <span data-ttu-id="4c713-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="4c713-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="4c713-856">	Tarjeta de identificación nacional de Brasil (RG)</span><span class="sxs-lookup"><span data-stu-id="4c713-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-857">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-857">Format</span></span>

<span data-ttu-id="4c713-858">Registro geral (formato anterior): nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="4c713-859">Registro de Identidade (RIC) (nuevo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-860">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-860">Pattern</span></span>

<span data-ttu-id="4c713-861">Registro de Geral (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="4c713-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="4c713-862">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-862">Two digits</span></span> 
- <span data-ttu-id="4c713-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-863">A period</span></span> 
- <span data-ttu-id="4c713-864">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-864">Three digits</span></span> 
- <span data-ttu-id="4c713-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-865">A period</span></span> 
- <span data-ttu-id="4c713-866">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-866">Three digits</span></span> 
- <span data-ttu-id="4c713-867">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-867">A hyphen</span></span> 
- <span data-ttu-id="4c713-868">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-868">One digit which is a check digit</span></span>

<span data-ttu-id="4c713-869">Registro de Identidade (RIC) (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="4c713-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="4c713-870">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-870">10 digits</span></span> 
- <span data-ttu-id="4c713-871">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-871">A hyphen</span></span> 
- <span data-ttu-id="4c713-872">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-873">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-873">Checksum</span></span>

<span data-ttu-id="4c713-874">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-875">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-875">Definition</span></span>

<span data-ttu-id="4c713-876">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-877">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-878">Se encuentra una palabra clave de Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="4c713-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="4c713-879">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-879">The checksum passes.</span></span>

<span data-ttu-id="4c713-880">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-881">La función Func_brazil_rg encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-882">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-883">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-883">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="4c713-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="4c713-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="4c713-885">Cédula de Identidade identidad nacional identificador número de rregistro registro de Iidentidade registro Geral RG (esta palabra clave distingue entre mayúsculas y minúsculas) RIC (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="4c713-886">Número de cuenta bancaria de Canadá</span><span class="sxs-lookup"><span data-stu-id="4c713-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-887">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-887">Format</span></span>

<span data-ttu-id="4c713-888">Siete o doce dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-889">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-889">Pattern</span></span>

<span data-ttu-id="4c713-890">El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.</span><span class="sxs-lookup"><span data-stu-id="4c713-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="4c713-891">Un número de tránsito de cuenta bancaria de Canadá es:</span><span class="sxs-lookup"><span data-stu-id="4c713-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="4c713-892">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-892">Five digits</span></span> 
- <span data-ttu-id="4c713-893">Un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-893">A hyphen</span></span> 
- <span data-ttu-id="4c713-894">Tres dígitos o</span><span class="sxs-lookup"><span data-stu-id="4c713-894">Three digits OR</span></span>
- <span data-ttu-id="4c713-895">Un cero "0" </span><span class="sxs-lookup"><span data-stu-id="4c713-895">A zero "0"</span></span> 
- <span data-ttu-id="4c713-896">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-897">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-897">Checksum</span></span>

<span data-ttu-id="4c713-898">No</span><span class="sxs-lookup"><span data-stu-id="4c713-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-899">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-899">Definition</span></span>

<span data-ttu-id="4c713-900">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-901">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-902">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="4c713-903">La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="4c713-904">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-905">La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-906">Se encuentra una palabra clave de Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-907">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-907">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="4c713-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="4c713-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="4c713-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="4c713-909">canada savings bonds</span></span>
- <span data-ttu-id="4c713-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="4c713-910">canada revenue agency</span></span>
- <span data-ttu-id="4c713-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="4c713-911">canadian financial institution</span></span>
- <span data-ttu-id="4c713-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="4c713-912">direct deposit form</span></span>
- <span data-ttu-id="4c713-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="4c713-913">canadian citizen</span></span>
- <span data-ttu-id="4c713-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="4c713-914">legal representative</span></span>
- <span data-ttu-id="4c713-915">notary public</span><span class="sxs-lookup"><span data-stu-id="4c713-915">notary public</span></span>
- <span data-ttu-id="4c713-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="4c713-916">commissioner for oaths</span></span>
- <span data-ttu-id="4c713-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="4c713-917">child care benefit</span></span>
- <span data-ttu-id="4c713-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="4c713-918">universal child care</span></span>
- <span data-ttu-id="4c713-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="4c713-919">canada child tax benefit</span></span>
- <span data-ttu-id="4c713-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="4c713-920">income tax benefit</span></span>
- <span data-ttu-id="4c713-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="4c713-921">harmonized sales tax</span></span>
- <span data-ttu-id="4c713-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="4c713-922">social insurance number</span></span>
- <span data-ttu-id="4c713-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="4c713-923">income tax refund</span></span>
- <span data-ttu-id="4c713-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="4c713-924">child tax benefit</span></span>
- <span data-ttu-id="4c713-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="4c713-925">territorial payments</span></span>
- <span data-ttu-id="4c713-926">institution number</span><span class="sxs-lookup"><span data-stu-id="4c713-926">institution number</span></span>
- <span data-ttu-id="4c713-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="4c713-927">deposit request</span></span>
- <span data-ttu-id="4c713-928">banking information</span><span class="sxs-lookup"><span data-stu-id="4c713-928">banking information</span></span>
- <span data-ttu-id="4c713-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="4c713-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="4c713-930">Número de licencia de conductor de Canadá</span><span class="sxs-lookup"><span data-stu-id="4c713-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-931">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-931">Format</span></span>

<span data-ttu-id="4c713-932">Varía según la provincia</span><span class="sxs-lookup"><span data-stu-id="4c713-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-933">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-933">Pattern</span></span>

<span data-ttu-id="4c713-934">Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="4c713-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-935">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-935">Checksum</span></span>

<span data-ttu-id="4c713-936">No</span><span class="sxs-lookup"><span data-stu-id="4c713-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-937">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-937">Definition</span></span>

<span data-ttu-id="4c713-938">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-939">La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-940">Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="4c713-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="4c713-941">Se encuentra una palabra clave de Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="4c713-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-942">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-942">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="4c713-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="4c713-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="4c713-944">La abreviatura de la provincia, por ejemplo, AB</span><span class="sxs-lookup"><span data-stu-id="4c713-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="4c713-945">El nombre de la provincia, por ejemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="4c713-945">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="4c713-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4c713-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="4c713-947">LISTAS</span><span class="sxs-lookup"><span data-stu-id="4c713-947">DL</span></span>
- <span data-ttu-id="4c713-948">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c713-948">DLS</span></span>
- <span data-ttu-id="4c713-949">CDL</span><span class="sxs-lookup"><span data-stu-id="4c713-949">CDL</span></span>
- <span data-ttu-id="4c713-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="4c713-950">CDLS</span></span>
- <span data-ttu-id="4c713-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="4c713-951">DriverLic</span></span>
- <span data-ttu-id="4c713-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="4c713-952">DriverLics</span></span>
- <span data-ttu-id="4c713-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-953">DriverLicense</span></span>
- <span data-ttu-id="4c713-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-954">DriverLicenses</span></span>
- <span data-ttu-id="4c713-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="4c713-955">DriverLicence</span></span>
- <span data-ttu-id="4c713-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="4c713-956">DriverLicences</span></span>
- <span data-ttu-id="4c713-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-957">Driver Lic</span></span>
- <span data-ttu-id="4c713-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-958">Driver Lics</span></span>
- <span data-ttu-id="4c713-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="4c713-959">Driver License</span></span>
- <span data-ttu-id="4c713-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-960">Driver Licenses</span></span>
- <span data-ttu-id="4c713-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-961">Driver Licence</span></span>
- <span data-ttu-id="4c713-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-962">Driver Licences</span></span>
- <span data-ttu-id="4c713-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="4c713-963">DriversLic</span></span>
- <span data-ttu-id="4c713-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="4c713-964">DriversLics</span></span>
- <span data-ttu-id="4c713-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="4c713-965">DriversLicence</span></span>
- <span data-ttu-id="4c713-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="4c713-966">DriversLicences</span></span>
- <span data-ttu-id="4c713-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-967">DriversLicense</span></span>
- <span data-ttu-id="4c713-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-968">DriversLicenses</span></span>
- <span data-ttu-id="4c713-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-969">Drivers Lic</span></span>
- <span data-ttu-id="4c713-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-970">Drivers Lics</span></span>
- <span data-ttu-id="4c713-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4c713-971">Drivers License</span></span>
- <span data-ttu-id="4c713-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-972">Drivers Licenses</span></span>
- <span data-ttu-id="4c713-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-973">Drivers Licence</span></span>
- <span data-ttu-id="4c713-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-974">Drivers Licences</span></span>
- <span data-ttu-id="4c713-975">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-975">Driver'Lic</span></span>
- <span data-ttu-id="4c713-976">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-976">Driver'Lics</span></span>
- <span data-ttu-id="4c713-977">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-977">Driver'License</span></span>
- <span data-ttu-id="4c713-978">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-978">Driver'Licenses</span></span>
- <span data-ttu-id="4c713-979">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-979">Driver'Licence</span></span>
- <span data-ttu-id="4c713-980">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-980">Driver'Licences</span></span>
- <span data-ttu-id="4c713-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-981">Driver' Lic</span></span>
- <span data-ttu-id="4c713-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-982">Driver' Lics</span></span>
- <span data-ttu-id="4c713-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="4c713-983">Driver' License</span></span>
- <span data-ttu-id="4c713-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-984">Driver' Licenses</span></span>
- <span data-ttu-id="4c713-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-985">Driver' Licence</span></span>
- <span data-ttu-id="4c713-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-986">Driver' Licences</span></span>
- <span data-ttu-id="4c713-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="4c713-987">Driver'sLic</span></span>
- <span data-ttu-id="4c713-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="4c713-988">Driver'sLics</span></span>
- <span data-ttu-id="4c713-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-989">Driver'sLicense</span></span>
- <span data-ttu-id="4c713-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-990">Driver'sLicenses</span></span>
- <span data-ttu-id="4c713-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="4c713-991">Driver'sLicence</span></span>
- <span data-ttu-id="4c713-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="4c713-992">Driver'sLicences</span></span>
- <span data-ttu-id="4c713-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-993">Driver's Lic</span></span>
- <span data-ttu-id="4c713-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-994">Driver's Lics</span></span>
- <span data-ttu-id="4c713-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4c713-995">Driver's License</span></span>
- <span data-ttu-id="4c713-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-996">Driver's Licenses</span></span>
- <span data-ttu-id="4c713-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-997">Driver's Licence</span></span>
- <span data-ttu-id="4c713-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-998">Driver's Licences</span></span>
- <span data-ttu-id="4c713-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="4c713-999">Permis de Conduire</span></span>
- <span data-ttu-id="4c713-1000">id</span><span class="sxs-lookup"><span data-stu-id="4c713-1000">id</span></span>
- <span data-ttu-id="4c713-1001">ids</span><span class="sxs-lookup"><span data-stu-id="4c713-1001">ids</span></span>
- <span data-ttu-id="4c713-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="4c713-1002">idcard number</span></span>
- <span data-ttu-id="4c713-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-1003">idcard numbers</span></span>
- <span data-ttu-id="4c713-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="4c713-1004">idcard #</span></span>
- <span data-ttu-id="4c713-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="4c713-1005">idcard #s</span></span>
- <span data-ttu-id="4c713-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="4c713-1006">idcard card</span></span>
- <span data-ttu-id="4c713-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1007">idcard cards</span></span>
- <span data-ttu-id="4c713-1008">tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1008">idcard</span></span>
- <span data-ttu-id="4c713-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="4c713-1009">identification number</span></span>
- <span data-ttu-id="4c713-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-1010">identification numbers</span></span>
- <span data-ttu-id="4c713-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="4c713-1011">identification #</span></span>
- <span data-ttu-id="4c713-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="4c713-1012">identification #s</span></span>
- <span data-ttu-id="4c713-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="4c713-1013">identification card</span></span>
- <span data-ttu-id="4c713-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1014">identification cards</span></span>
- <span data-ttu-id="4c713-1015">determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-1015">identification</span></span> 
- <span data-ttu-id="4c713-1016">LISTAS</span><span class="sxs-lookup"><span data-stu-id="4c713-1016">DL#</span></span>
- <span data-ttu-id="4c713-1017">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c713-1017">DLS#</span></span> 
- <span data-ttu-id="4c713-1018">CDL</span><span class="sxs-lookup"><span data-stu-id="4c713-1018">CDL#</span></span> 
- <span data-ttu-id="4c713-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="4c713-1019">CDLS#</span></span> 
- <span data-ttu-id="4c713-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-1020">DriverLic#</span></span> 
- <span data-ttu-id="4c713-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-1021">DriverLics#</span></span> 
- <span data-ttu-id="4c713-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-1022">DriverLicense#</span></span> 
- <span data-ttu-id="4c713-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="4c713-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="4c713-1024">DriverLicence#</span></span> 
- <span data-ttu-id="4c713-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="4c713-1025">DriverLicences#</span></span> 
- <span data-ttu-id="4c713-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-1026">Driver Lic#</span></span>
- <span data-ttu-id="4c713-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-1027">Driver Lics#</span></span> 
- <span data-ttu-id="4c713-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4c713-1028">Driver License#</span></span> 
- <span data-ttu-id="4c713-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="4c713-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4c713-1030">Driver License#</span></span> 
- <span data-ttu-id="4c713-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-1031">Driver Licences#</span></span> 
- <span data-ttu-id="4c713-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-1032">DriversLic#</span></span> 
- <span data-ttu-id="4c713-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-1033">DriversLics#</span></span> 
- <span data-ttu-id="4c713-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-1034">DriversLicense#</span></span> 
- <span data-ttu-id="4c713-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="4c713-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="4c713-1036">DriversLicence#</span></span> 
- <span data-ttu-id="4c713-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="4c713-1037">DriversLicences#</span></span> 
- <span data-ttu-id="4c713-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="4c713-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="4c713-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="4c713-1040">Drivers License#</span></span> 
- <span data-ttu-id="4c713-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="4c713-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="4c713-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="4c713-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="4c713-1044">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="4c713-1045">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="4c713-1046">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-1046">Driver'License#</span></span> 
- <span data-ttu-id="4c713-1047">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="4c713-1048">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="4c713-1049">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="4c713-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="4c713-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="4c713-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="4c713-1052">Driver' License#</span></span> 
- <span data-ttu-id="4c713-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="4c713-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="4c713-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="4c713-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="4c713-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="4c713-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="4c713-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="4c713-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="4c713-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="4c713-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="4c713-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="4c713-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="4c713-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="4c713-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="4c713-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="4c713-1064">Driver's License#</span></span> 
- <span data-ttu-id="4c713-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="4c713-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="4c713-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="4c713-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="4c713-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="4c713-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="4c713-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="4c713-1069">identificador</span><span class="sxs-lookup"><span data-stu-id="4c713-1069">id#</span></span> 
- <span data-ttu-id="4c713-1070">falta</span><span class="sxs-lookup"><span data-stu-id="4c713-1070">ids#</span></span> 
- <span data-ttu-id="4c713-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="4c713-1071">idcard card#</span></span> 
- <span data-ttu-id="4c713-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="4c713-1072">idcard cards#</span></span> 
- <span data-ttu-id="4c713-1073">tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1073">idcard#</span></span> 
- <span data-ttu-id="4c713-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="4c713-1074">identification card#</span></span> 
- <span data-ttu-id="4c713-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="4c713-1075">identification cards#</span></span> 
- <span data-ttu-id="4c713-1076">determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="4c713-1077">Número de servicio de salud de Canadá</span><span class="sxs-lookup"><span data-stu-id="4c713-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1078">Format</span></span>

<span data-ttu-id="4c713-1079">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1080">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1080">Pattern</span></span>

<span data-ttu-id="4c713-1081">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1082">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1082">Checksum</span></span>

<span data-ttu-id="4c713-1083">No</span><span class="sxs-lookup"><span data-stu-id="4c713-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1084">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1084">Definition</span></span>

<span data-ttu-id="4c713-1085">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1086">La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1087">Se encuentra una palabra clave de Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1088">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1088">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="4c713-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="4c713-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="4c713-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="4c713-1090">personal health number</span></span>
- <span data-ttu-id="4c713-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="4c713-1091">patient information</span></span>
- <span data-ttu-id="4c713-1092">health services</span><span class="sxs-lookup"><span data-stu-id="4c713-1092">health services</span></span>
- <span data-ttu-id="4c713-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="4c713-1093">speciality services</span></span>
- <span data-ttu-id="4c713-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="4c713-1094">automobile accident</span></span>
- <span data-ttu-id="4c713-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="4c713-1095">patient hospital</span></span>
- <span data-ttu-id="4c713-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="4c713-1096">psychiatrist</span></span>
- <span data-ttu-id="4c713-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="4c713-1097">workers compensation</span></span>
- <span data-ttu-id="4c713-1098">discapacidad</span><span class="sxs-lookup"><span data-stu-id="4c713-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="4c713-1099">Número de pasaporte de Canadá</span><span class="sxs-lookup"><span data-stu-id="4c713-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1100">Format</span></span>

<span data-ttu-id="4c713-1101">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1102">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1102">Pattern</span></span>

<span data-ttu-id="4c713-1103">Dos letras mayúsculas seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1104">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1104">Checksum</span></span>

<span data-ttu-id="4c713-1105">No</span><span class="sxs-lookup"><span data-stu-id="4c713-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1106">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1106">Definition</span></span>

<span data-ttu-id="4c713-1107">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1108">La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1109">Se encuentra una palabra clave de Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="4c713-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1110">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="4c713-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="4c713-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="4c713-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="4c713-1112">canadian citizenship</span></span>
- <span data-ttu-id="4c713-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="4c713-1113">canadian passport</span></span>
- <span data-ttu-id="4c713-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="4c713-1114">passport application</span></span>
- <span data-ttu-id="4c713-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="4c713-1115">passport photos</span></span>
- <span data-ttu-id="4c713-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="4c713-1116">certified translator</span></span>
- <span data-ttu-id="4c713-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="4c713-1117">canadian citizens</span></span>
- <span data-ttu-id="4c713-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="4c713-1118">processing times</span></span>
- <span data-ttu-id="4c713-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="4c713-1119">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="4c713-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-1120">Keyword_passport</span></span>

- <span data-ttu-id="4c713-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4c713-1121">Passport Number</span></span>
- <span data-ttu-id="4c713-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="4c713-1122">Passport No</span></span>
- <span data-ttu-id="4c713-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="4c713-1123">Passport #</span></span>
- <span data-ttu-id="4c713-1124">Usuarios</span><span class="sxs-lookup"><span data-stu-id="4c713-1124">Passport#</span></span>
- <span data-ttu-id="4c713-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="4c713-1125">PassportID</span></span>
- <span data-ttu-id="4c713-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="4c713-1126">Passportno</span></span>
- <span data-ttu-id="4c713-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-1127">passportnumber</span></span>
- <span data-ttu-id="4c713-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="4c713-1128">パスポート</span></span>
- <span data-ttu-id="4c713-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4c713-1129">パスポート番号</span></span>
- <span data-ttu-id="4c713-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4c713-1130">パスポートのNum</span></span>
- <span data-ttu-id="4c713-1131">パスポート #</span><span class="sxs-lookup"><span data-stu-id="4c713-1131">パスポート＃</span></span>
- <span data-ttu-id="4c713-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4c713-1132">Numéro de passeport</span></span>
- <span data-ttu-id="4c713-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4c713-1133">Passeport n °</span></span>
- <span data-ttu-id="4c713-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4c713-1134">Passeport Non</span></span>
- <span data-ttu-id="4c713-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-1135">Passeport #</span></span>
- <span data-ttu-id="4c713-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-1136">Passeport#</span></span>
- <span data-ttu-id="4c713-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4c713-1137">PasseportNon</span></span>
- <span data-ttu-id="4c713-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4c713-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="4c713-1139">Número de Identificación Personal de salud en Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="4c713-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1140">Format</span></span>

<span data-ttu-id="4c713-1141">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1142">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1142">Pattern</span></span>

<span data-ttu-id="4c713-1143">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1144">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1144">Checksum</span></span>

<span data-ttu-id="4c713-1145">No</span><span class="sxs-lookup"><span data-stu-id="4c713-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1146">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1146">Definition</span></span>

<span data-ttu-id="4c713-1147">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="4c713-1148">Se encuentran al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="4c713-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1149">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="4c713-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="4c713-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="4c713-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="4c713-1151">social insurance number</span></span>
- <span data-ttu-id="4c713-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="4c713-1152">health information act</span></span>
- <span data-ttu-id="4c713-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="4c713-1153">income tax information</span></span>
- <span data-ttu-id="4c713-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="4c713-1154">manitoba health</span></span>
- <span data-ttu-id="4c713-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="4c713-1155">health registration</span></span>
- <span data-ttu-id="4c713-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="4c713-1156">prescription purchases</span></span>
- <span data-ttu-id="4c713-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="4c713-1157">benefit eligibility</span></span>
- <span data-ttu-id="4c713-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="4c713-1158">personal health</span></span>
- <span data-ttu-id="4c713-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="4c713-1159">power of attorney</span></span>
- <span data-ttu-id="4c713-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="4c713-1160">registration number</span></span>
- <span data-ttu-id="4c713-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="4c713-1161">personal health number</span></span>
- <span data-ttu-id="4c713-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="4c713-1162">practitioner referral</span></span>
- <span data-ttu-id="4c713-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="4c713-1163">wellness professional</span></span>
- <span data-ttu-id="4c713-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="4c713-1164">patient referral</span></span>
- <span data-ttu-id="4c713-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="4c713-1165">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="4c713-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="4c713-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="4c713-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="4c713-1167">Nunavut</span></span>
- <span data-ttu-id="4c713-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="4c713-1168">Quebec</span></span>
- <span data-ttu-id="4c713-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="4c713-1169">Northwest Territories</span></span>
- <span data-ttu-id="4c713-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="4c713-1170">Ontario</span></span>
- <span data-ttu-id="4c713-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="4c713-1171">British Columbia</span></span>
- <span data-ttu-id="4c713-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="4c713-1172">Alberta</span></span>
- <span data-ttu-id="4c713-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="4c713-1173">Saskatchewan</span></span>
- <span data-ttu-id="4c713-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="4c713-1174">Manitoba</span></span>
- <span data-ttu-id="4c713-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="4c713-1175">Yukon</span></span>
- <span data-ttu-id="4c713-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="4c713-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="4c713-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="4c713-1177">New Brunswick</span></span>
- <span data-ttu-id="4c713-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="4c713-1178">Nova Scotia</span></span>
- <span data-ttu-id="4c713-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="4c713-1179">Prince Edward Island</span></span>
- <span data-ttu-id="4c713-1180">Canada</span><span class="sxs-lookup"><span data-stu-id="4c713-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="4c713-1181">Número de seguridad social de Canadá</span><span class="sxs-lookup"><span data-stu-id="4c713-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1182">Format</span></span>

<span data-ttu-id="4c713-1183">Nueve dígitos con guiones opcionales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1184">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1184">Pattern</span></span>

<span data-ttu-id="4c713-1185">Con formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1185">Formatted:</span></span>
- <span data-ttu-id="4c713-1186">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1186">Three digits</span></span> 
- <span data-ttu-id="4c713-1187">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="4c713-1187">A hyphen or space</span></span> 
- <span data-ttu-id="4c713-1188">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1188">Three digits</span></span> 
- <span data-ttu-id="4c713-1189">Un guion o un espacio</span><span class="sxs-lookup"><span data-stu-id="4c713-1189">A hyphen or space</span></span> 
- <span data-ttu-id="4c713-1190">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1190">Three digits</span></span>

<span data-ttu-id="4c713-1191">Sin formato: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1192">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1192">Checksum</span></span>

<span data-ttu-id="4c713-1193">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1194">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1194">Definition</span></span>

<span data-ttu-id="4c713-1195">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1196">La función Func_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1197">Al menos dos de cualquier combinación de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c713-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="4c713-1198">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="4c713-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="4c713-1199">Se encuentra una palabra clave de Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="4c713-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="4c713-1200">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4c713-1201">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1201">The checksum passes.</span></span>

<span data-ttu-id="4c713-1202">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1203">La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1204">Se encuentra una palabra clave de Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="4c713-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="4c713-1205">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1206">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1206">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="4c713-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="4c713-1207">Keyword_sin</span></span>

- <span data-ttu-id="4c713-1208">sin</span><span class="sxs-lookup"><span data-stu-id="4c713-1208">sin</span></span> 
- <span data-ttu-id="4c713-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="4c713-1209">social insurance</span></span> 
- <span data-ttu-id="4c713-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="4c713-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="4c713-1211">pecados</span><span class="sxs-lookup"><span data-stu-id="4c713-1211">sins</span></span> 
- <span data-ttu-id="4c713-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="4c713-1212">ssn</span></span> 
- <span data-ttu-id="4c713-1213">SSN</span><span class="sxs-lookup"><span data-stu-id="4c713-1213">ssns</span></span> 
- <span data-ttu-id="4c713-1214">social security</span><span class="sxs-lookup"><span data-stu-id="4c713-1214">social security</span></span> 
- <span data-ttu-id="4c713-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="4c713-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="4c713-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="4c713-1216">national identification number</span></span> 
- <span data-ttu-id="4c713-1217">national id</span><span class="sxs-lookup"><span data-stu-id="4c713-1217">national id</span></span> 
- <span data-ttu-id="4c713-1218">PIN</span><span class="sxs-lookup"><span data-stu-id="4c713-1218">sin#</span></span> 
- <span data-ttu-id="4c713-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="4c713-1219">soc ins</span></span> 
- <span data-ttu-id="4c713-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="4c713-1220">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="4c713-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="4c713-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="4c713-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="4c713-1222">driver's license</span></span> 
- <span data-ttu-id="4c713-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="4c713-1223">drivers license</span></span> 
- <span data-ttu-id="4c713-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="4c713-1224">driver's licence</span></span> 
- <span data-ttu-id="4c713-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="4c713-1225">drivers licence</span></span> 
- <span data-ttu-id="4c713-1226">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="4c713-1226">DOB</span></span> 
- <span data-ttu-id="4c713-1227">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-1227">Birthdate</span></span> 
- <span data-ttu-id="4c713-1228">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="4c713-1228">Birthday</span></span> 
- <span data-ttu-id="4c713-1229">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="4c713-1230">	Número de tarjeta de identidad de Chile</span><span class="sxs-lookup"><span data-stu-id="4c713-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1231">Format</span></span>

<span data-ttu-id="4c713-1232">7-8 dígitos más delimitadores, un dígito de control o una letra</span><span class="sxs-lookup"><span data-stu-id="4c713-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1233">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1233">Pattern</span></span>

<span data-ttu-id="4c713-1234">7 u 8 dígitos más delimitadores:</span><span class="sxs-lookup"><span data-stu-id="4c713-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="4c713-1235">1 o 2 dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-1235">1-2 digits</span></span> 
- <span data-ttu-id="4c713-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-1236">A period</span></span> 
- <span data-ttu-id="4c713-1237">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1237">Three digits</span></span> 
- <span data-ttu-id="4c713-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="4c713-1238">A period</span></span> 
- <span data-ttu-id="4c713-1239">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1239">Three digits</span></span> 
- <span data-ttu-id="4c713-1240">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-1240">A dash</span></span> 
- <span data-ttu-id="4c713-1241">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1242">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1242">Checksum</span></span>

<span data-ttu-id="4c713-1243">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1244">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1244">Definition</span></span>

<span data-ttu-id="4c713-1245">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1246">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1247">Se encuentra una palabra clave de Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="4c713-1248">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1248">The checksum passes.</span></span>

<span data-ttu-id="4c713-1249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1250">La función Func_chile_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1251">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1252">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="4c713-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="4c713-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="4c713-1254">Número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="4c713-1254">National Identification Number</span></span> 
- <span data-ttu-id="4c713-1255">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-1255">Identity card</span></span> 
- <span data-ttu-id="4c713-1256">ID</span><span class="sxs-lookup"><span data-stu-id="4c713-1256">ID</span></span> 
- <span data-ttu-id="4c713-1257">Determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-1257">Identification</span></span> 
- <span data-ttu-id="4c713-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="4c713-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="4c713-1259">REALIZAR</span><span class="sxs-lookup"><span data-stu-id="4c713-1259">RUN</span></span> 
- <span data-ttu-id="4c713-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="4c713-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="4c713-1261">ESTANCARSE</span><span class="sxs-lookup"><span data-stu-id="4c713-1261">RUT</span></span> 
- <span data-ttu-id="4c713-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="4c713-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="4c713-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="4c713-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="4c713-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="4c713-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="4c713-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="4c713-1266">	Número de tarjeta de identidad de residente de China (PRC)</span><span class="sxs-lookup"><span data-stu-id="4c713-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1267">Format</span></span>

<span data-ttu-id="4c713-1268">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1269">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1269">Pattern</span></span>

<span data-ttu-id="4c713-1270">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-1270">18 digits:</span></span>
- <span data-ttu-id="4c713-1271">Seis dígitos que son un código de dirección </span><span class="sxs-lookup"><span data-stu-id="4c713-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="4c713-1272">Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4c713-1273">Tres dígitos que son un código de pedido </span><span class="sxs-lookup"><span data-stu-id="4c713-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="4c713-1274">Un dígito que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1275">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1275">Checksum</span></span>

<span data-ttu-id="4c713-1276">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1277">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1277">Definition</span></span>

<span data-ttu-id="4c713-1278">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1279">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1280">Se encuentra una palabra clave de Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="4c713-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="4c713-1281">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1281">The checksum passes.</span></span>

<span data-ttu-id="4c713-1282">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1283">La función Func_china_resident_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1284">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1285">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1285">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="4c713-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="4c713-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="4c713-1287">Tarjeta de identidad de residente</span><span class="sxs-lookup"><span data-stu-id="4c713-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="4c713-1288">China</span><span class="sxs-lookup"><span data-stu-id="4c713-1288">PRC</span></span> 
- <span data-ttu-id="4c713-1289">Tarjeta de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="4c713-1289">National Identification Card</span></span> 
- <span data-ttu-id="4c713-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="4c713-1290">身份证</span></span> 
- <span data-ttu-id="4c713-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="4c713-1291">居民 身份证</span></span> 
- <span data-ttu-id="4c713-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="4c713-1292">居民身份证</span></span> 
- <span data-ttu-id="4c713-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="4c713-1293">鉴定</span></span> 
- <span data-ttu-id="4c713-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-1294">身分證</span></span> 
- <span data-ttu-id="4c713-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-1295">居民 身份證</span></span>
- <span data-ttu-id="4c713-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="4c713-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="4c713-1297">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1298">Format</span></span>

<span data-ttu-id="4c713-1299">16 dígitos que pueden ser formateados o sin formato (dddddddddddddddd) y deben pasar la prueba Luhn.</span><span class="sxs-lookup"><span data-stu-id="4c713-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1300">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1300">Pattern</span></span>

<span data-ttu-id="4c713-1301">Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.</span><span class="sxs-lookup"><span data-stu-id="4c713-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1302">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1302">Checksum</span></span>

<span data-ttu-id="4c713-1303">Sí, la suma de comprobación de Luhn</span><span class="sxs-lookup"><span data-stu-id="4c713-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1304">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1304">Definition</span></span>

<span data-ttu-id="4c713-1305">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1306">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1307">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-1307">One of the following is true:</span></span>
    - <span data-ttu-id="4c713-1308">Se encuentra una palabra clave de Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="4c713-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="4c713-1309">Se encuentra una palabra clave de Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="4c713-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="4c713-1310">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4c713-1311">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1311">The checksum passes.</span></span>

<span data-ttu-id="4c713-1312">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1313">La función Func_credit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1314">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1315">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="4c713-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="4c713-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="4c713-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="4c713-1317">card verification</span></span>
- <span data-ttu-id="4c713-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="4c713-1318">card identification number</span></span>
- <span data-ttu-id="4c713-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="4c713-1319">cvn</span></span>
- <span data-ttu-id="4c713-1320">cid</span><span class="sxs-lookup"><span data-stu-id="4c713-1320">cid</span></span>
- <span data-ttu-id="4c713-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="4c713-1321">cvc2</span></span>
- <span data-ttu-id="4c713-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="4c713-1322">cvv2</span></span>
- <span data-ttu-id="4c713-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="4c713-1323">pin block</span></span>
- <span data-ttu-id="4c713-1324">security code</span><span class="sxs-lookup"><span data-stu-id="4c713-1324">security code</span></span>
- <span data-ttu-id="4c713-1325">security number</span><span class="sxs-lookup"><span data-stu-id="4c713-1325">security number</span></span>
- <span data-ttu-id="4c713-1326">security no</span><span class="sxs-lookup"><span data-stu-id="4c713-1326">security no</span></span>
- <span data-ttu-id="4c713-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="4c713-1327">issue number</span></span>
- <span data-ttu-id="4c713-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="4c713-1328">issue no</span></span>
- <span data-ttu-id="4c713-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="4c713-1329">cryptogramme</span></span>
- <span data-ttu-id="4c713-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="4c713-1330">numéro de sécurité</span></span>
- <span data-ttu-id="4c713-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="4c713-1331">numero de securite</span></span>
- <span data-ttu-id="4c713-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="4c713-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="4c713-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="4c713-1334">prüfziffer</span></span>
- <span data-ttu-id="4c713-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="4c713-1335">prufziffer</span></span>
- <span data-ttu-id="4c713-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="4c713-1336">sicherheits Kode</span></span>
- <span data-ttu-id="4c713-1337">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="4c713-1337">sicherheitscode</span></span>
- <span data-ttu-id="4c713-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="4c713-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="4c713-1339">verfalldatum</span></span>
- <span data-ttu-id="4c713-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="4c713-1340">codice di verifica</span></span>
- <span data-ttu-id="4c713-1341">COD.</span><span class="sxs-lookup"><span data-stu-id="4c713-1341">cod.</span></span> <span data-ttu-id="4c713-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c713-1342">sicurezza</span></span>
- <span data-ttu-id="4c713-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c713-1343">cod sicurezza</span></span>
- <span data-ttu-id="4c713-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4c713-1344">n autorizzazione</span></span>
- <span data-ttu-id="4c713-1345">Código</span><span class="sxs-lookup"><span data-stu-id="4c713-1345">código</span></span>
- <span data-ttu-id="4c713-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="4c713-1346">codigo</span></span>
- <span data-ttu-id="4c713-1347">COD.</span><span class="sxs-lookup"><span data-stu-id="4c713-1347">cod.</span></span> <span data-ttu-id="4c713-1348">seg</span><span class="sxs-lookup"><span data-stu-id="4c713-1348">seg</span></span>
- <span data-ttu-id="4c713-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="4c713-1349">cod seg</span></span>
- <span data-ttu-id="4c713-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1350">código de segurança</span></span>
- <span data-ttu-id="4c713-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="4c713-1351">codigo de seguranca</span></span>
- <span data-ttu-id="4c713-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1352">codigo de segurança</span></span>
- <span data-ttu-id="4c713-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="4c713-1353">código de seguranca</span></span>
- <span data-ttu-id="4c713-1354">campos.</span><span class="sxs-lookup"><span data-stu-id="4c713-1354">cód.</span></span> <span data-ttu-id="4c713-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1355">segurança</span></span>
- <span data-ttu-id="4c713-1356">COD.</span><span class="sxs-lookup"><span data-stu-id="4c713-1356">cod.</span></span> <span data-ttu-id="4c713-1357">DQO SEGURANCA.</span><span class="sxs-lookup"><span data-stu-id="4c713-1357">seguranca cod.</span></span> <span data-ttu-id="4c713-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1358">segurança</span></span>
- <span data-ttu-id="4c713-1359">campos.</span><span class="sxs-lookup"><span data-stu-id="4c713-1359">cód.</span></span> <span data-ttu-id="4c713-1360">SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="4c713-1360">seguranca</span></span>
- <span data-ttu-id="4c713-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1361">cód segurança</span></span>
- <span data-ttu-id="4c713-1362">Bacalao SEGURANCA contra reembolso de segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="4c713-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="4c713-1363">cód seguranca</span></span>
- <span data-ttu-id="4c713-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="4c713-1364">número de verificação</span></span>
- <span data-ttu-id="4c713-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="4c713-1365">numero de verificacao</span></span>
- <span data-ttu-id="4c713-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="4c713-1366">ablauf</span></span>
- <span data-ttu-id="4c713-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="4c713-1367">gültig bis</span></span>
- <span data-ttu-id="4c713-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4c713-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="4c713-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="4c713-1369">gultig bis</span></span>
- <span data-ttu-id="4c713-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4c713-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="4c713-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="4c713-1371">scadenza</span></span>
- <span data-ttu-id="4c713-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="4c713-1372">data scad</span></span>
- <span data-ttu-id="4c713-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="4c713-1373">fecha de expiracion</span></span>
- <span data-ttu-id="4c713-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="4c713-1374">fecha de venc</span></span>
- <span data-ttu-id="4c713-1375">1er</span><span class="sxs-lookup"><span data-stu-id="4c713-1375">vencimiento</span></span>
- <span data-ttu-id="4c713-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="4c713-1376">válido hasta</span></span>
- <span data-ttu-id="4c713-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="4c713-1377">valido hasta</span></span>
- <span data-ttu-id="4c713-1378">vto</span><span class="sxs-lookup"><span data-stu-id="4c713-1378">vto</span></span>
- <span data-ttu-id="4c713-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="4c713-1379">data de expiração</span></span>
- <span data-ttu-id="4c713-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="4c713-1380">data de expiracao</span></span>
- <span data-ttu-id="4c713-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="4c713-1381">data em que expira</span></span>
- <span data-ttu-id="4c713-1382">validade</span><span class="sxs-lookup"><span data-stu-id="4c713-1382">validade</span></span>
- <span data-ttu-id="4c713-1383">valorar</span><span class="sxs-lookup"><span data-stu-id="4c713-1383">valor</span></span>
- <span data-ttu-id="4c713-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="4c713-1384">vencimento</span></span>
- <span data-ttu-id="4c713-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="4c713-1385">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="4c713-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="4c713-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="4c713-1387">AMEX</span><span class="sxs-lookup"><span data-stu-id="4c713-1387">amex</span></span>
- <span data-ttu-id="4c713-1388">american express</span><span class="sxs-lookup"><span data-stu-id="4c713-1388">american express</span></span>
- <span data-ttu-id="4c713-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="4c713-1389">americanexpress</span></span>
- <span data-ttu-id="4c713-1390">Régimen</span><span class="sxs-lookup"><span data-stu-id="4c713-1390">Visa</span></span>
- <span data-ttu-id="4c713-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="4c713-1391">mastercard</span></span>
- <span data-ttu-id="4c713-1392">master card</span><span class="sxs-lookup"><span data-stu-id="4c713-1392">master card</span></span>
- <span data-ttu-id="4c713-1393">valuación</span><span class="sxs-lookup"><span data-stu-id="4c713-1393">mc</span></span> 
- <span data-ttu-id="4c713-1394">MasterCard</span><span class="sxs-lookup"><span data-stu-id="4c713-1394">mastercards</span></span>
- <span data-ttu-id="4c713-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1395">master cards</span></span>
- <span data-ttu-id="4c713-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="4c713-1396">diner's Club</span></span>
- <span data-ttu-id="4c713-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="4c713-1397">diners club</span></span>
- <span data-ttu-id="4c713-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="4c713-1398">dinersclub</span></span>
- <span data-ttu-id="4c713-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="4c713-1399">discover card</span></span>
- <span data-ttu-id="4c713-1400">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1400">discovercard</span></span>
- <span data-ttu-id="4c713-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1401">discover cards</span></span>
- <span data-ttu-id="4c713-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="4c713-1402">JCB</span></span>
- <span data-ttu-id="4c713-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="4c713-1403">japanese card bureau</span></span>
- <span data-ttu-id="4c713-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="4c713-1404">carte blanche</span></span>
- <span data-ttu-id="4c713-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="4c713-1405">carteblanche</span></span>
- <span data-ttu-id="4c713-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="4c713-1406">credit card</span></span>
- <span data-ttu-id="4c713-1407">CC</span><span class="sxs-lookup"><span data-stu-id="4c713-1407">cc#</span></span>
- <span data-ttu-id="4c713-1408"># CC:</span><span class="sxs-lookup"><span data-stu-id="4c713-1408">cc#:</span></span>
- <span data-ttu-id="4c713-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="4c713-1409">expiration date</span></span>
- <span data-ttu-id="4c713-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="4c713-1410">exp date</span></span>
- <span data-ttu-id="4c713-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="4c713-1411">expiry date</span></span>
- <span data-ttu-id="4c713-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="4c713-1412">date d’expiration</span></span>
- <span data-ttu-id="4c713-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="4c713-1413">date d'exp</span></span>
- <span data-ttu-id="4c713-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="4c713-1414">date expiration</span></span>
- <span data-ttu-id="4c713-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="4c713-1415">bank card</span></span>
- <span data-ttu-id="4c713-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="4c713-1416">bankcard</span></span>
- <span data-ttu-id="4c713-1417">card number</span><span class="sxs-lookup"><span data-stu-id="4c713-1417">card number</span></span>
- <span data-ttu-id="4c713-1418">card num</span><span class="sxs-lookup"><span data-stu-id="4c713-1418">card num</span></span>
- <span data-ttu-id="4c713-1419">cardNumber</span><span class="sxs-lookup"><span data-stu-id="4c713-1419">cardnumber</span></span>
- <span data-ttu-id="4c713-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="4c713-1420">cardnumbers</span></span>
- <span data-ttu-id="4c713-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-1421">card numbers</span></span>
- <span data-ttu-id="4c713-1422">crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1422">creditcard</span></span>
- <span data-ttu-id="4c713-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1423">credit cards</span></span>
- <span data-ttu-id="4c713-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="4c713-1424">creditcards</span></span>
- <span data-ttu-id="4c713-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="4c713-1425">ccn</span></span>
- <span data-ttu-id="4c713-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="4c713-1426">card holder</span></span>
- <span data-ttu-id="4c713-1427">titular</span><span class="sxs-lookup"><span data-stu-id="4c713-1427">cardholder</span></span>
- <span data-ttu-id="4c713-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="4c713-1428">card holders</span></span>
- <span data-ttu-id="4c713-1429">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="4c713-1429">cardholders</span></span>
- <span data-ttu-id="4c713-1430">check card</span><span class="sxs-lookup"><span data-stu-id="4c713-1430">check card</span></span>
- <span data-ttu-id="4c713-1431">Checkcard</span><span class="sxs-lookup"><span data-stu-id="4c713-1431">checkcard</span></span>
- <span data-ttu-id="4c713-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1432">check cards</span></span>
- <span data-ttu-id="4c713-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="4c713-1433">checkcards</span></span>
- <span data-ttu-id="4c713-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="4c713-1434">debit card</span></span>
- <span data-ttu-id="4c713-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="4c713-1435">debitcard</span></span>
- <span data-ttu-id="4c713-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1436">debit cards</span></span>
- <span data-ttu-id="4c713-1437">DebitCards</span><span class="sxs-lookup"><span data-stu-id="4c713-1437">debitcards</span></span>
- <span data-ttu-id="4c713-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="4c713-1438">atm card</span></span>
- <span data-ttu-id="4c713-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="4c713-1439">atmcard</span></span>
- <span data-ttu-id="4c713-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1440">atm cards</span></span>
- <span data-ttu-id="4c713-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="4c713-1441">atmcards</span></span>
- <span data-ttu-id="4c713-1442">enrutar</span><span class="sxs-lookup"><span data-stu-id="4c713-1442">enroute</span></span>
- <span data-ttu-id="4c713-1443">en route</span><span class="sxs-lookup"><span data-stu-id="4c713-1443">en route</span></span>
- <span data-ttu-id="4c713-1444">card type</span><span class="sxs-lookup"><span data-stu-id="4c713-1444">card type</span></span>
- <span data-ttu-id="4c713-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="4c713-1445">carte bancaire</span></span>
- <span data-ttu-id="4c713-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="4c713-1446">carte de crédit</span></span>
- <span data-ttu-id="4c713-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="4c713-1447">carte de credit</span></span>
- <span data-ttu-id="4c713-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1448">numéro de carte</span></span>
- <span data-ttu-id="4c713-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1449">numero de carte</span></span>
- <span data-ttu-id="4c713-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1450">nº de la carte</span></span>
- <span data-ttu-id="4c713-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1451">nº de carte</span></span>
- <span data-ttu-id="4c713-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="4c713-1452">kreditkarte</span></span>
- <span data-ttu-id="4c713-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="4c713-1453">karte</span></span>
- <span data-ttu-id="4c713-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="4c713-1454">karteninhaber</span></span>
- <span data-ttu-id="4c713-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="4c713-1455">karteninhabers</span></span>
- <span data-ttu-id="4c713-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="4c713-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="4c713-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="4c713-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="4c713-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="4c713-1458">kreditkartentyp</span></span>
- <span data-ttu-id="4c713-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="4c713-1459">eigentümername</span></span>
- <span data-ttu-id="4c713-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="4c713-1460">kartennr</span></span> 
- <span data-ttu-id="4c713-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1461">kartennummer</span></span>
- <span data-ttu-id="4c713-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1462">kreditkartennummer</span></span>
- <span data-ttu-id="4c713-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="4c713-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1464">carta di credito</span></span>
- <span data-ttu-id="4c713-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1465">carta credito</span></span>
- <span data-ttu-id="4c713-1466">cobro</span><span class="sxs-lookup"><span data-stu-id="4c713-1466">carta</span></span>
- <span data-ttu-id="4c713-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1467">n carta</span></span>
- <span data-ttu-id="4c713-1468">Nº.</span><span class="sxs-lookup"><span data-stu-id="4c713-1468">nr.</span></span> <span data-ttu-id="4c713-1469">cobro</span><span class="sxs-lookup"><span data-stu-id="4c713-1469">carta</span></span>
- <span data-ttu-id="4c713-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1470">nr carta</span></span>
- <span data-ttu-id="4c713-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1471">numero carta</span></span>
- <span data-ttu-id="4c713-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1472">numero della carta</span></span>
- <span data-ttu-id="4c713-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1473">numero di carta</span></span>
- <span data-ttu-id="4c713-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1474">tarjeta credito</span></span>
- <span data-ttu-id="4c713-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1475">tarjeta de credito</span></span>
- <span data-ttu-id="4c713-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1476">tarjeta crédito</span></span>
- <span data-ttu-id="4c713-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="4c713-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="4c713-1478">tarjeta de atm</span></span>
- <span data-ttu-id="4c713-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="4c713-1479">tarjeta atm</span></span>
- <span data-ttu-id="4c713-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1480">tarjeta debito</span></span>
- <span data-ttu-id="4c713-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1481">tarjeta de debito</span></span>
- <span data-ttu-id="4c713-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="4c713-1482">tarjeta débito</span></span>
- <span data-ttu-id="4c713-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="4c713-1483">tarjeta de débito</span></span>
- <span data-ttu-id="4c713-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1484">nº de tarjeta</span></span>
- <span data-ttu-id="4c713-1485">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1485">no.</span></span> <span data-ttu-id="4c713-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1486">de tarjeta</span></span>
- <span data-ttu-id="4c713-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1487">no de tarjeta</span></span>
- <span data-ttu-id="4c713-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1488">numero de tarjeta</span></span>
- <span data-ttu-id="4c713-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1489">número de tarjeta</span></span>
- <span data-ttu-id="4c713-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="4c713-1490">tarjeta no</span></span>
- <span data-ttu-id="4c713-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="4c713-1491">tarjetahabiente</span></span>
- <span data-ttu-id="4c713-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1492">cartão de crédito</span></span>
- <span data-ttu-id="4c713-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1493">cartão de credito</span></span>
- <span data-ttu-id="4c713-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1494">cartao de crédito</span></span>
- <span data-ttu-id="4c713-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1495">cartao de credito</span></span>
- <span data-ttu-id="4c713-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="4c713-1496">cartão de débito</span></span>
- <span data-ttu-id="4c713-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="4c713-1497">cartao de débito</span></span>
- <span data-ttu-id="4c713-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1498">cartão de debito</span></span>
- <span data-ttu-id="4c713-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1499">cartao de debito</span></span>
- <span data-ttu-id="4c713-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="4c713-1500">débito automático</span></span>
- <span data-ttu-id="4c713-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="4c713-1501">debito automatico</span></span>
- <span data-ttu-id="4c713-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1502">número do cartão</span></span>
- <span data-ttu-id="4c713-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1503">numero do cartão</span></span> 
- <span data-ttu-id="4c713-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1504">número do cartao</span></span>
- <span data-ttu-id="4c713-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1505">numero do cartao</span></span>
- <span data-ttu-id="4c713-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1506">número de cartão</span></span>
- <span data-ttu-id="4c713-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1507">numero de cartão</span></span>
- <span data-ttu-id="4c713-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1508">número de cartao</span></span>
- <span data-ttu-id="4c713-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1509">numero de cartao</span></span>
- <span data-ttu-id="4c713-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1510">nº do cartão</span></span>
- <span data-ttu-id="4c713-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1511">nº do cartao</span></span>
- <span data-ttu-id="4c713-1512">Nº.</span><span class="sxs-lookup"><span data-stu-id="4c713-1512">nº.</span></span> <span data-ttu-id="4c713-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1513">do cartão</span></span>
- <span data-ttu-id="4c713-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1514">no do cartão</span></span>
- <span data-ttu-id="4c713-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1515">no do cartao</span></span>
- <span data-ttu-id="4c713-1516">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1516">no.</span></span> <span data-ttu-id="4c713-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1517">do cartão</span></span>
- <span data-ttu-id="4c713-1518">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1518">no.</span></span> <span data-ttu-id="4c713-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="4c713-1520">Número de tarjeta de identidad de Croacia</span><span class="sxs-lookup"><span data-stu-id="4c713-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1521">Format</span></span>

<span data-ttu-id="4c713-1522">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1523">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1523">Pattern</span></span>

<span data-ttu-id="4c713-1524">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1525">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1525">Checksum</span></span>

<span data-ttu-id="4c713-1526">No</span><span class="sxs-lookup"><span data-stu-id="4c713-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1527">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1527">Definition</span></span>

<span data-ttu-id="4c713-1528">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1529">La función Func_croatia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1530">Se encuentra una palabra clave de Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-1531">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1531">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="4c713-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="4c713-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="4c713-1533">Tarjeta de identidad croata</span><span class="sxs-lookup"><span data-stu-id="4c713-1533">Croatian identity card</span></span>
- <span data-ttu-id="4c713-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="4c713-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="4c713-1535">Número de identificación personal de Croacia (OIB)</span><span class="sxs-lookup"><span data-stu-id="4c713-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1536">Format</span></span>

<span data-ttu-id="4c713-1537">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1538">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1538">Pattern</span></span>

<span data-ttu-id="4c713-1539">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-1539">11 digits:</span></span>
- <span data-ttu-id="4c713-1540">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1540">10 digits</span></span> 
- <span data-ttu-id="4c713-1541">El dígito final es un dígito de control para el intercambio internacional de datos, se agregan las letras h antes de los once dígitos.</span><span class="sxs-lookup"><span data-stu-id="4c713-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1542">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1542">Checksum</span></span>

<span data-ttu-id="4c713-1543">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1544">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1544">Definition</span></span>

<span data-ttu-id="4c713-1545">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1546">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1547">Se encuentra una palabra clave de Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="4c713-1548">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1548">The checksum passes.</span></span>

<span data-ttu-id="4c713-1549">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1550">La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1551">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1552">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1552">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="4c713-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="4c713-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="4c713-1554">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="4c713-1554">Personal Identification Number</span></span>
- <span data-ttu-id="4c713-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="4c713-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="4c713-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="4c713-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="4c713-1557">Número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="4c713-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1558">Format</span></span>

<span data-ttu-id="4c713-1559">Nueve dígitos con barra diagonal (formato antiguo) 10 dígitos con barra diagonal (nuevo formato) opcional</span><span class="sxs-lookup"><span data-stu-id="4c713-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1560">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1560">Pattern</span></span>

<span data-ttu-id="4c713-1561">Nueve dígitos (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="4c713-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="4c713-1562">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1562">Nine digits</span></span>

<span data-ttu-id="4c713-1563">O</span><span class="sxs-lookup"><span data-stu-id="4c713-1563">OR</span></span>

- <span data-ttu-id="4c713-1564">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="4c713-1565">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="4c713-1565">A forward slash</span></span>
- <span data-ttu-id="4c713-1566">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1566">Three digits</span></span>

<span data-ttu-id="4c713-1567">10 dígitos (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="4c713-1567">10 digits (new format):</span></span>
- <span data-ttu-id="4c713-1568">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1568">10 digits</span></span>

<span data-ttu-id="4c713-1569">O</span><span class="sxs-lookup"><span data-stu-id="4c713-1569">OR</span></span>

- <span data-ttu-id="4c713-1570">Seis dígitos que representan la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="4c713-1571">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="4c713-1571">A forward slash</span></span> 
- <span data-ttu-id="4c713-1572">Cuatro dígitos donde el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1573">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1573">Checksum</span></span>

<span data-ttu-id="4c713-1574">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1575">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1575">Definition</span></span>

<span data-ttu-id="4c713-1576">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_czech_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="4c713-1577">Se encuentra una palabra clave de Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="4c713-1578">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1578">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="4c713-1579">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1579">Keywords</span></span>

- <span data-ttu-id="4c713-1580">número de identidad personal en Checo</span><span class="sxs-lookup"><span data-stu-id="4c713-1580">czech personal identity number</span></span>
- <span data-ttu-id="4c713-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="4c713-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="4c713-1582">Número de identificación personal de Dinamarca</span><span class="sxs-lookup"><span data-stu-id="4c713-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1583">Format</span></span>

<span data-ttu-id="4c713-1584">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="4c713-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1585">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1585">Pattern</span></span>

<span data-ttu-id="4c713-1586">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-1586">10 digits:</span></span>
- <span data-ttu-id="4c713-1587">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="4c713-1588">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-1588">A hyphen</span></span> 
- <span data-ttu-id="4c713-1589">4 dígitos en los que el último dígito es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1590">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1590">Checksum</span></span>

<span data-ttu-id="4c713-1591">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1592">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1592">Definition</span></span>

<span data-ttu-id="4c713-1593">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_denmark_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="4c713-1594">Se encuentra una palabra clave de Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="4c713-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="4c713-1595">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1595">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-1596">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1596">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="4c713-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="4c713-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="4c713-1598">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="4c713-1598">Personal Identification Number</span></span>
- <span data-ttu-id="4c713-1599">RCP</span><span class="sxs-lookup"><span data-stu-id="4c713-1599">CPR</span></span>
- <span data-ttu-id="4c713-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="4c713-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="4c713-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="4c713-1602">Número de la Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="4c713-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1603">Format</span></span>

<span data-ttu-id="4c713-1604">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1605">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1605">Pattern</span></span>

<span data-ttu-id="4c713-1606">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c713-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="4c713-1607">Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito</span><span class="sxs-lookup"><span data-stu-id="4c713-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="4c713-1608">Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito.</span><span class="sxs-lookup"><span data-stu-id="4c713-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="4c713-1609">Siete dígitos, el último de los cuales es el dígito de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1610">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1610">Checksum</span></span>

<span data-ttu-id="4c713-1611">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1612">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1612">Definition</span></span>

<span data-ttu-id="4c713-1613">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1614">La función Func_dea_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1615">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1615">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-1616">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1616">Keywords</span></span>

<span data-ttu-id="4c713-1617">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4c713-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="4c713-1618">Tarjeta de débito de la UE</span><span class="sxs-lookup"><span data-stu-id="4c713-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1619">Format</span></span>

<span data-ttu-id="4c713-1620">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1621">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1621">Pattern</span></span>

<span data-ttu-id="4c713-1622">Patrón muy complejo y robusto</span><span class="sxs-lookup"><span data-stu-id="4c713-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1623">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1623">Checksum</span></span>

<span data-ttu-id="4c713-1624">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1625">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1625">Definition</span></span>

<span data-ttu-id="4c713-1626">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1627">La función Func_eu_debit_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1628">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="4c713-1629">Se encuentra una palabra clave de Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="4c713-1630">Se encuentra una palabra clave de Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="4c713-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="4c713-1631">Se encuentra una palabra clave de Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="4c713-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="4c713-1632">Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="4c713-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="4c713-1633">La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4c713-1634">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1635">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1635">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="4c713-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="4c713-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="4c713-1637">account number</span><span class="sxs-lookup"><span data-stu-id="4c713-1637">account number</span></span> 
- <span data-ttu-id="4c713-1638">card number</span><span class="sxs-lookup"><span data-stu-id="4c713-1638">card number</span></span> 
- <span data-ttu-id="4c713-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="4c713-1639">card no.</span></span> 
- <span data-ttu-id="4c713-1640">security number</span><span class="sxs-lookup"><span data-stu-id="4c713-1640">security number</span></span> 
- <span data-ttu-id="4c713-1641">CC</span><span class="sxs-lookup"><span data-stu-id="4c713-1641">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="4c713-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="4c713-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="4c713-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="4c713-1643">acct nbr</span></span> 
- <span data-ttu-id="4c713-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="4c713-1644">acct num</span></span> 
- <span data-ttu-id="4c713-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="4c713-1645">acct no</span></span> 
- <span data-ttu-id="4c713-1646">american express</span><span class="sxs-lookup"><span data-stu-id="4c713-1646">american express</span></span> 
- <span data-ttu-id="4c713-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="4c713-1647">americanexpress</span></span> 
- <span data-ttu-id="4c713-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="4c713-1648">americano espresso</span></span> 
- <span data-ttu-id="4c713-1649">AMEX</span><span class="sxs-lookup"><span data-stu-id="4c713-1649">amex</span></span> 
- <span data-ttu-id="4c713-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="4c713-1650">atm card</span></span> 
- <span data-ttu-id="4c713-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1651">atm cards</span></span> 
- <span data-ttu-id="4c713-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1652">atm kaart</span></span> 
- <span data-ttu-id="4c713-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="4c713-1653">atmcard</span></span> 
- <span data-ttu-id="4c713-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="4c713-1654">atmcards</span></span> 
- <span data-ttu-id="4c713-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1655">atmkaart</span></span> 
- <span data-ttu-id="4c713-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="4c713-1656">atmkaarten</span></span> 
- <span data-ttu-id="4c713-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="4c713-1657">bancontact</span></span> 
- <span data-ttu-id="4c713-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="4c713-1658">bank card</span></span> 
- <span data-ttu-id="4c713-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1659">bankkaart</span></span> 
- <span data-ttu-id="4c713-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="4c713-1660">card holder</span></span> 
- <span data-ttu-id="4c713-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="4c713-1661">card holders</span></span> 
- <span data-ttu-id="4c713-1662">card num</span><span class="sxs-lookup"><span data-stu-id="4c713-1662">card num</span></span> 
- <span data-ttu-id="4c713-1663">card number</span><span class="sxs-lookup"><span data-stu-id="4c713-1663">card number</span></span> 
- <span data-ttu-id="4c713-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-1664">card numbers</span></span> 
- <span data-ttu-id="4c713-1665">card type</span><span class="sxs-lookup"><span data-stu-id="4c713-1665">card type</span></span> 
- <span data-ttu-id="4c713-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="4c713-1666">cardano numerico</span></span> 
- <span data-ttu-id="4c713-1667">titular</span><span class="sxs-lookup"><span data-stu-id="4c713-1667">cardholder</span></span> 
- <span data-ttu-id="4c713-1668">titulares de la titular</span><span class="sxs-lookup"><span data-stu-id="4c713-1668">cardholders</span></span> 
- <span data-ttu-id="4c713-1669">cardNumber</span><span class="sxs-lookup"><span data-stu-id="4c713-1669">cardnumber</span></span> 
- <span data-ttu-id="4c713-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="4c713-1670">cardnumbers</span></span> 
- <span data-ttu-id="4c713-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="4c713-1671">carta bianca</span></span> 
- <span data-ttu-id="4c713-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1672">carta credito</span></span> 
- <span data-ttu-id="4c713-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1673">carta di credito</span></span> 
- <span data-ttu-id="4c713-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1674">cartao de credito</span></span> 
- <span data-ttu-id="4c713-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1675">cartao de crédito</span></span> 
- <span data-ttu-id="4c713-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1676">cartao de debito</span></span> 
- <span data-ttu-id="4c713-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="4c713-1677">cartao de débito</span></span> 
- <span data-ttu-id="4c713-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="4c713-1678">carte bancaire</span></span> 
- <span data-ttu-id="4c713-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="4c713-1679">carte blanche</span></span> 
- <span data-ttu-id="4c713-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="4c713-1680">carte bleue</span></span> 
- <span data-ttu-id="4c713-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="4c713-1681">carte de credit</span></span> 
- <span data-ttu-id="4c713-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="4c713-1682">carte de crédit</span></span> 
- <span data-ttu-id="4c713-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1683">carte di credito</span></span> 
- <span data-ttu-id="4c713-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="4c713-1684">carteblanche</span></span> 
- <span data-ttu-id="4c713-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1685">cartão de credito</span></span> 
- <span data-ttu-id="4c713-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1686">cartão de crédito</span></span> 
- <span data-ttu-id="4c713-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1687">cartão de debito</span></span> 
- <span data-ttu-id="4c713-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="4c713-1688">cartão de débito</span></span> 
- <span data-ttu-id="4c713-1689">cb</span><span class="sxs-lookup"><span data-stu-id="4c713-1689">cb</span></span> 
- <span data-ttu-id="4c713-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="4c713-1690">ccn</span></span> 
- <span data-ttu-id="4c713-1691">check card</span><span class="sxs-lookup"><span data-stu-id="4c713-1691">check card</span></span> 
- <span data-ttu-id="4c713-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1692">check cards</span></span> 
- <span data-ttu-id="4c713-1693">Checkcard</span><span class="sxs-lookup"><span data-stu-id="4c713-1693">checkcard</span></span>
- <span data-ttu-id="4c713-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="4c713-1694">checkcards</span></span> 
- <span data-ttu-id="4c713-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1695">chequekaart</span></span> 
- <span data-ttu-id="4c713-1696">Logic</span><span class="sxs-lookup"><span data-stu-id="4c713-1696">cirrus</span></span> 
- <span data-ttu-id="4c713-1697">Cirrus-EDC-maestro</span><span class="sxs-lookup"><span data-stu-id="4c713-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="4c713-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1698">controlekaart</span></span> 
- <span data-ttu-id="4c713-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="4c713-1699">controlekaarten</span></span> 
- <span data-ttu-id="4c713-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="4c713-1700">credit card</span></span> 
- <span data-ttu-id="4c713-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1701">credit cards</span></span> 
- <span data-ttu-id="4c713-1702">crédito</span><span class="sxs-lookup"><span data-stu-id="4c713-1702">creditcard</span></span> 
- <span data-ttu-id="4c713-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="4c713-1703">creditcards</span></span> 
- <span data-ttu-id="4c713-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1704">debetkaart</span></span> 
- <span data-ttu-id="4c713-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="4c713-1705">debetkaarten</span></span> 
- <span data-ttu-id="4c713-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="4c713-1706">debit card</span></span> 
- <span data-ttu-id="4c713-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1707">debit cards</span></span> 
- <span data-ttu-id="4c713-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="4c713-1708">debitcard</span></span> 
- <span data-ttu-id="4c713-1709">DebitCards</span><span class="sxs-lookup"><span data-stu-id="4c713-1709">debitcards</span></span> 
- <span data-ttu-id="4c713-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="4c713-1710">debito automatico</span></span> 
- <span data-ttu-id="4c713-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="4c713-1711">diners club</span></span> 
- <span data-ttu-id="4c713-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="4c713-1712">dinersclub</span></span> 
- <span data-ttu-id="4c713-1713">advierte</span><span class="sxs-lookup"><span data-stu-id="4c713-1713">discover</span></span> 
- <span data-ttu-id="4c713-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="4c713-1714">discover card</span></span> 
- <span data-ttu-id="4c713-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1715">discover cards</span></span> 
- <span data-ttu-id="4c713-1716">detectar tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1716">discovercard</span></span> 
- <span data-ttu-id="4c713-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="4c713-1717">discovercards</span></span> 
- <span data-ttu-id="4c713-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="4c713-1718">débito automático</span></span>
- <span data-ttu-id="4c713-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="4c713-1719">edc</span></span> 
- <span data-ttu-id="4c713-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="4c713-1720">eigentümername</span></span> 
- <span data-ttu-id="4c713-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="4c713-1721">european debit card</span></span> 
- <span data-ttu-id="4c713-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1722">hoofdkaart</span></span> 
- <span data-ttu-id="4c713-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="4c713-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="4c713-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="4c713-1724">in viaggio</span></span> 
- <span data-ttu-id="4c713-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="4c713-1725">japanese card bureau</span></span> 
- <span data-ttu-id="4c713-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="4c713-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="4c713-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="4c713-1727">jcb</span></span> 
- <span data-ttu-id="4c713-1728">Kaart</span><span class="sxs-lookup"><span data-stu-id="4c713-1728">kaart</span></span> 
- <span data-ttu-id="4c713-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="4c713-1729">kaart num</span></span> 
- <span data-ttu-id="4c713-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="4c713-1730">kaartaantal</span></span> 
- <span data-ttu-id="4c713-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="4c713-1731">kaartaantallen</span></span> 
- <span data-ttu-id="4c713-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="4c713-1732">kaarthouder</span></span> 
- <span data-ttu-id="4c713-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="4c713-1733">kaarthouders</span></span> 
- <span data-ttu-id="4c713-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="4c713-1734">karte</span></span>  
- <span data-ttu-id="4c713-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="4c713-1735">karteninhaber</span></span> 
- <span data-ttu-id="4c713-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="4c713-1736">karteninhabers</span></span>
- <span data-ttu-id="4c713-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="4c713-1737">kartennr</span></span> 
- <span data-ttu-id="4c713-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1738">kartennummer</span></span> 
- <span data-ttu-id="4c713-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="4c713-1739">kreditkarte</span></span> 
- <span data-ttu-id="4c713-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="4c713-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="4c713-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="4c713-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="4c713-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="4c713-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="4c713-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="4c713-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="4c713-1745">dispositivos</span><span class="sxs-lookup"><span data-stu-id="4c713-1745">maestro</span></span> 
- <span data-ttu-id="4c713-1746">master card</span><span class="sxs-lookup"><span data-stu-id="4c713-1746">master card</span></span> 
- <span data-ttu-id="4c713-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="4c713-1747">master cards</span></span> 
- <span data-ttu-id="4c713-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="4c713-1748">mastercard</span></span> 
- <span data-ttu-id="4c713-1749">MasterCard</span><span class="sxs-lookup"><span data-stu-id="4c713-1749">mastercards</span></span> 
- <span data-ttu-id="4c713-1750">valuación</span><span class="sxs-lookup"><span data-stu-id="4c713-1750">mc</span></span> 
- <span data-ttu-id="4c713-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="4c713-1751">mister cash</span></span> 
- <span data-ttu-id="4c713-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1752">n carta</span></span> 
- <span data-ttu-id="4c713-1753">cobro</span><span class="sxs-lookup"><span data-stu-id="4c713-1753">carta</span></span> 
- <span data-ttu-id="4c713-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1754">no de tarjeta</span></span> 
- <span data-ttu-id="4c713-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1755">no do cartao</span></span> 
- <span data-ttu-id="4c713-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1756">no do cartão</span></span> 
- <span data-ttu-id="4c713-1757">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1757">no.</span></span> <span data-ttu-id="4c713-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1758">de tarjeta</span></span> 
- <span data-ttu-id="4c713-1759">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1759">no.</span></span> <span data-ttu-id="4c713-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1760">do cartao</span></span> 
- <span data-ttu-id="4c713-1761">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1761">no.</span></span> <span data-ttu-id="4c713-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1762">do cartão</span></span> 
- <span data-ttu-id="4c713-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1763">nr carta</span></span> 
- <span data-ttu-id="4c713-1764">Nº.</span><span class="sxs-lookup"><span data-stu-id="4c713-1764">nr.</span></span> <span data-ttu-id="4c713-1765">cobro</span><span class="sxs-lookup"><span data-stu-id="4c713-1765">carta</span></span> 
- <span data-ttu-id="4c713-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1766">numeri di scheda</span></span> 
- <span data-ttu-id="4c713-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1767">numero carta</span></span> 
- <span data-ttu-id="4c713-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1768">numero de cartao</span></span> 
- <span data-ttu-id="4c713-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1769">numero de carte</span></span> 
- <span data-ttu-id="4c713-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1770">numero de cartão</span></span> 
- <span data-ttu-id="4c713-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1771">numero de tarjeta</span></span>
- <span data-ttu-id="4c713-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1772">numero della carta</span></span> 
- <span data-ttu-id="4c713-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1773">numero di carta</span></span> 
- <span data-ttu-id="4c713-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1774">numero di scheda</span></span> 
- <span data-ttu-id="4c713-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1775">numero do cartao</span></span> 
- <span data-ttu-id="4c713-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1776">numero do cartão</span></span> 
- <span data-ttu-id="4c713-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1777">numéro de carte</span></span> 
- <span data-ttu-id="4c713-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="4c713-1778">nº carta</span></span> 
- <span data-ttu-id="4c713-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1779">nº de carte</span></span> 
- <span data-ttu-id="4c713-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="4c713-1780">nº de la carte</span></span> 
- <span data-ttu-id="4c713-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="4c713-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1782">nº do cartao</span></span> 
- <span data-ttu-id="4c713-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1783">nº do cartão</span></span> 
- <span data-ttu-id="4c713-1784">Nº.</span><span class="sxs-lookup"><span data-stu-id="4c713-1784">nº.</span></span> <span data-ttu-id="4c713-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1785">do cartão</span></span> 
- <span data-ttu-id="4c713-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1786">número de cartao</span></span> 
- <span data-ttu-id="4c713-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="4c713-1787">número de cartão</span></span> 
- <span data-ttu-id="4c713-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4c713-1788">número de tarjeta</span></span> 
- <span data-ttu-id="4c713-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="4c713-1789">número do cartao</span></span> 
- <span data-ttu-id="4c713-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="4c713-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="4c713-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="4c713-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="4c713-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="4c713-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="4c713-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="4c713-1793">scheda della banca</span></span> 
- <span data-ttu-id="4c713-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="4c713-1794">scheda di controllo</span></span> 
- <span data-ttu-id="4c713-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1795">scheda di debito</span></span> 
- <span data-ttu-id="4c713-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="4c713-1796">scheda matrice</span></span> 
- <span data-ttu-id="4c713-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="4c713-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="4c713-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="4c713-1798">schede di controllo</span></span> 
- <span data-ttu-id="4c713-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1799">schede di debito</span></span> 
- <span data-ttu-id="4c713-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="4c713-1800">schede matrici</span></span> 
- <span data-ttu-id="4c713-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="4c713-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="4c713-1802">scoprono le schede</span></span> 
- <span data-ttu-id="4c713-1803">solo</span><span class="sxs-lookup"><span data-stu-id="4c713-1803">solo</span></span> 
- <span data-ttu-id="4c713-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1804">supporti di scheda</span></span> 
- <span data-ttu-id="4c713-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1805">supporto di scheda</span></span> 
- <span data-ttu-id="4c713-1806">cambia</span><span class="sxs-lookup"><span data-stu-id="4c713-1806">switch</span></span> 
- <span data-ttu-id="4c713-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="4c713-1807">tarjeta atm</span></span> 
- <span data-ttu-id="4c713-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1808">tarjeta credito</span></span> 
- <span data-ttu-id="4c713-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="4c713-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="4c713-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="4c713-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="4c713-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="4c713-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="4c713-1812">tarjeta debito</span></span> 
- <span data-ttu-id="4c713-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="4c713-1813">tarjeta no</span></span>
- <span data-ttu-id="4c713-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="4c713-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="4c713-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1815">tipo della scheda</span></span> 
- <span data-ttu-id="4c713-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="4c713-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="4c713-1817">Scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1817">scheda</span></span> 
- <span data-ttu-id="4c713-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="4c713-1818">v pay</span></span> 
- <span data-ttu-id="4c713-1819">v-Pay</span><span class="sxs-lookup"><span data-stu-id="4c713-1819">v-pay</span></span> 
- <span data-ttu-id="4c713-1820">régimen</span><span class="sxs-lookup"><span data-stu-id="4c713-1820">visa</span></span> 
- <span data-ttu-id="4c713-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="4c713-1821">visa plus</span></span> 
- <span data-ttu-id="4c713-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="4c713-1822">visa electron</span></span> 
- <span data-ttu-id="4c713-1823">a</span><span class="sxs-lookup"><span data-stu-id="4c713-1823">visto</span></span> 
- <span data-ttu-id="4c713-1824">visum</span><span class="sxs-lookup"><span data-stu-id="4c713-1824">visum</span></span> 
- <span data-ttu-id="4c713-1825">VPay</span><span class="sxs-lookup"><span data-stu-id="4c713-1825">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="4c713-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="4c713-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="4c713-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="4c713-1827">card identification number</span></span>
- <span data-ttu-id="4c713-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="4c713-1828">card verification</span></span> 
- <span data-ttu-id="4c713-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="4c713-1829">cardi la verifica</span></span> 
- <span data-ttu-id="4c713-1830">cid</span><span class="sxs-lookup"><span data-stu-id="4c713-1830">cid</span></span> 
- <span data-ttu-id="4c713-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="4c713-1831">cod seg</span></span> 
- <span data-ttu-id="4c713-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="4c713-1832">cod seguranca</span></span> 
- <span data-ttu-id="4c713-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1833">cod segurança</span></span> 
- <span data-ttu-id="4c713-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c713-1834">cod sicurezza</span></span> 
- <span data-ttu-id="4c713-1835">COD.</span><span class="sxs-lookup"><span data-stu-id="4c713-1835">cod.</span></span> <span data-ttu-id="4c713-1836">seg</span><span class="sxs-lookup"><span data-stu-id="4c713-1836">seg</span></span> 
- <span data-ttu-id="4c713-1837">COD.</span><span class="sxs-lookup"><span data-stu-id="4c713-1837">cod.</span></span> <span data-ttu-id="4c713-1838">SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="4c713-1838">seguranca</span></span> 
- <span data-ttu-id="4c713-1839">COD.</span><span class="sxs-lookup"><span data-stu-id="4c713-1839">cod.</span></span> <span data-ttu-id="4c713-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1840">segurança</span></span> 
- <span data-ttu-id="4c713-1841">COD.</span><span class="sxs-lookup"><span data-stu-id="4c713-1841">cod.</span></span> <span data-ttu-id="4c713-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c713-1842">sicurezza</span></span> 
- <span data-ttu-id="4c713-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c713-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="4c713-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="4c713-1844">codice di verifica</span></span> 
- <span data-ttu-id="4c713-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="4c713-1845">codigo</span></span> 
- <span data-ttu-id="4c713-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="4c713-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="4c713-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1847">codigo de segurança</span></span> 
- <span data-ttu-id="4c713-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="4c713-1848">crittogramma</span></span> 
- <span data-ttu-id="4c713-1849">criptograma</span><span class="sxs-lookup"><span data-stu-id="4c713-1849">cryptogram</span></span> 
- <span data-ttu-id="4c713-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="4c713-1850">cryptogramme</span></span> 
- <span data-ttu-id="4c713-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="4c713-1851">cv2</span></span> 
- <span data-ttu-id="4c713-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="4c713-1852">cvc</span></span> 
- <span data-ttu-id="4c713-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="4c713-1853">cvc2</span></span> 
- <span data-ttu-id="4c713-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="4c713-1854">cvn</span></span> 
- <span data-ttu-id="4c713-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="4c713-1855">cvv</span></span> 
- <span data-ttu-id="4c713-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="4c713-1856">cvv2</span></span> 
- <span data-ttu-id="4c713-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="4c713-1857">cód seguranca</span></span> 
- <span data-ttu-id="4c713-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1858">cód segurança</span></span> 
- <span data-ttu-id="4c713-1859">campos.</span><span class="sxs-lookup"><span data-stu-id="4c713-1859">cód.</span></span> <span data-ttu-id="4c713-1860">SEGURANCA</span><span class="sxs-lookup"><span data-stu-id="4c713-1860">seguranca</span></span> 
- <span data-ttu-id="4c713-1861">campos.</span><span class="sxs-lookup"><span data-stu-id="4c713-1861">cód.</span></span> <span data-ttu-id="4c713-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1862">segurança</span></span> 
- <span data-ttu-id="4c713-1863">Código</span><span class="sxs-lookup"><span data-stu-id="4c713-1863">código</span></span> 
- <span data-ttu-id="4c713-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="4c713-1864">código de seguranca</span></span> 
- <span data-ttu-id="4c713-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="4c713-1865">código de segurança</span></span> 
- <span data-ttu-id="4c713-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="4c713-1866">de kaart controle</span></span> 
- <span data-ttu-id="4c713-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="4c713-1867">geeft nr uit</span></span> 
- <span data-ttu-id="4c713-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="4c713-1868">issue no</span></span> 
- <span data-ttu-id="4c713-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="4c713-1869">issue number</span></span> 
- <span data-ttu-id="4c713-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="4c713-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="4c713-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="4c713-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="4c713-1873">kwestieaantal</span></span> 
- <span data-ttu-id="4c713-1874">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1874">no.</span></span> <span data-ttu-id="4c713-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="4c713-1875">dell'edizione</span></span> 
- <span data-ttu-id="4c713-1876">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-1876">no.</span></span> <span data-ttu-id="4c713-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c713-1877">di sicurezza</span></span> 
- <span data-ttu-id="4c713-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="4c713-1878">numero de securite</span></span> 
- <span data-ttu-id="4c713-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="4c713-1879">numero de verificacao</span></span> 
- <span data-ttu-id="4c713-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="4c713-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="4c713-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="4c713-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="4c713-1882">Scheda</span><span class="sxs-lookup"><span data-stu-id="4c713-1882">scheda</span></span> 
- <span data-ttu-id="4c713-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c713-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="4c713-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="4c713-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="4c713-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="4c713-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="4c713-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4c713-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="4c713-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="4c713-1887">número de verificação</span></span> 
- <span data-ttu-id="4c713-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="4c713-1888">perno il blocco</span></span> 
- <span data-ttu-id="4c713-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="4c713-1889">pin block</span></span> 
- <span data-ttu-id="4c713-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="4c713-1890">prufziffer</span></span> 
- <span data-ttu-id="4c713-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="4c713-1891">prüfziffer</span></span> 
- <span data-ttu-id="4c713-1892">security code</span><span class="sxs-lookup"><span data-stu-id="4c713-1892">security code</span></span> 
- <span data-ttu-id="4c713-1893">security no</span><span class="sxs-lookup"><span data-stu-id="4c713-1893">security no</span></span> 
- <span data-ttu-id="4c713-1894">security number</span><span class="sxs-lookup"><span data-stu-id="4c713-1894">security number</span></span> 
- <span data-ttu-id="4c713-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="4c713-1895">sicherheits kode</span></span> 
- <span data-ttu-id="4c713-1896">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="4c713-1896">sicherheitscode</span></span> 
- <span data-ttu-id="4c713-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="4c713-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="4c713-1898">speldblok</span></span> 
- <span data-ttu-id="4c713-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="4c713-1899">veiligheid nr</span></span> 
- <span data-ttu-id="4c713-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="4c713-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="4c713-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="4c713-1901">veiligheidscode</span></span> 
- <span data-ttu-id="4c713-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="4c713-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="4c713-1903">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="4c713-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="4c713-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="4c713-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="4c713-1905">ablauf</span></span> 
- <span data-ttu-id="4c713-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="4c713-1906">data de expiracao</span></span> 
- <span data-ttu-id="4c713-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="4c713-1907">data de expiração</span></span> 
- <span data-ttu-id="4c713-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="4c713-1908">data del exp</span></span> 
- <span data-ttu-id="4c713-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="4c713-1909">data di exp</span></span> 
- <span data-ttu-id="4c713-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="4c713-1910">data di scadenza</span></span> 
- <span data-ttu-id="4c713-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="4c713-1911">data em que expira</span></span> 
- <span data-ttu-id="4c713-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="4c713-1912">data scad</span></span> 
- <span data-ttu-id="4c713-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="4c713-1913">data scadenza</span></span> 
- <span data-ttu-id="4c713-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="4c713-1914">date de validité</span></span> 
- <span data-ttu-id="4c713-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="4c713-1915">datum afloop</span></span> 
- <span data-ttu-id="4c713-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="4c713-1916">datum van exp</span></span> 
- <span data-ttu-id="4c713-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="4c713-1917">de afloop</span></span> 
- <span data-ttu-id="4c713-1918">espira</span><span class="sxs-lookup"><span data-stu-id="4c713-1918">espira</span></span> 
- <span data-ttu-id="4c713-1919">espira</span><span class="sxs-lookup"><span data-stu-id="4c713-1919">espira</span></span> 
- <span data-ttu-id="4c713-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="4c713-1920">exp date</span></span> 
- <span data-ttu-id="4c713-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="4c713-1921">exp datum</span></span> 
- <span data-ttu-id="4c713-1922">expiración</span><span class="sxs-lookup"><span data-stu-id="4c713-1922">expiration</span></span> 
- <span data-ttu-id="4c713-1923">expiran</span><span class="sxs-lookup"><span data-stu-id="4c713-1923">expire</span></span> 
- <span data-ttu-id="4c713-1924">expira</span><span class="sxs-lookup"><span data-stu-id="4c713-1924">expires</span></span> 
- <span data-ttu-id="4c713-1925">expiración</span><span class="sxs-lookup"><span data-stu-id="4c713-1925">expiry</span></span> 
- <span data-ttu-id="4c713-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="4c713-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="4c713-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="4c713-1927">fecha de venc</span></span> 
- <span data-ttu-id="4c713-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="4c713-1928">gultig bis</span></span> 
- <span data-ttu-id="4c713-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4c713-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="4c713-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="4c713-1930">gültig bis</span></span> 
- <span data-ttu-id="4c713-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4c713-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="4c713-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="4c713-1932">la scadenza</span></span> 
- <span data-ttu-id="4c713-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="4c713-1933">scadenza</span></span> 
- <span data-ttu-id="4c713-1934">valable</span><span class="sxs-lookup"><span data-stu-id="4c713-1934">valable</span></span> 
- <span data-ttu-id="4c713-1935">validade</span><span class="sxs-lookup"><span data-stu-id="4c713-1935">validade</span></span> 
- <span data-ttu-id="4c713-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="4c713-1936">valido hasta</span></span> 
- <span data-ttu-id="4c713-1937">valorar</span><span class="sxs-lookup"><span data-stu-id="4c713-1937">valor</span></span> 
- <span data-ttu-id="4c713-1938">venc</span><span class="sxs-lookup"><span data-stu-id="4c713-1938">venc</span></span> 
- <span data-ttu-id="4c713-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="4c713-1939">vencimento</span></span> 
- <span data-ttu-id="4c713-1940">1er</span><span class="sxs-lookup"><span data-stu-id="4c713-1940">vencimiento</span></span> 
- <span data-ttu-id="4c713-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="4c713-1941">verloopt</span></span> 
- <span data-ttu-id="4c713-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="4c713-1942">vervaldag</span></span> 
- <span data-ttu-id="4c713-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="4c713-1943">vervaldatum</span></span> 
- <span data-ttu-id="4c713-1944">vto</span><span class="sxs-lookup"><span data-stu-id="4c713-1944">vto</span></span> 
- <span data-ttu-id="4c713-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="4c713-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="4c713-1946">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="4c713-1946">EU Driver's License Number</span></span>

<span data-ttu-id="4c713-1947">Para obtener más información, vea [tipo de información confidencial del número de licencia del conductor de la UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="4c713-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="4c713-1948">Número de identificación nacional de la UE</span><span class="sxs-lookup"><span data-stu-id="4c713-1948">EU National Identification Number</span></span>

<span data-ttu-id="4c713-1949">Para obtener más información, consulte el [tipo de información confidencial de número de identificación nacional de la UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="4c713-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="4c713-1950">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="4c713-1950">EU Passport Number</span></span>

<span data-ttu-id="4c713-1951">Para obtener más información, consulte [EU Number Sensitive Information Type](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="4c713-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="4c713-1952">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="4c713-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="4c713-1953">Para obtener más información, consulte el [número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="4c713-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="4c713-1954">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="4c713-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="4c713-1955">Para obtener más información, vea [tipo de información confidencial de número de identificación de impuestos de la UE](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="4c713-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="4c713-1956">Identificación nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="4c713-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1957">Format</span></span>

<span data-ttu-id="4c713-1958">Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1959">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1959">Pattern</span></span>

<span data-ttu-id="4c713-1960">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c713-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="4c713-1961">Seis dígitos en el formato DDMMAA que son una fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="4c713-1962">Marcador del siglo (ya sea '-', '+' o 'a')</span><span class="sxs-lookup"><span data-stu-id="4c713-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="4c713-1963">Número de identificación personal de tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="4c713-1964">Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1965">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1965">Checksum</span></span>

<span data-ttu-id="4c713-1966">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1967">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1967">Definition</span></span>

<span data-ttu-id="4c713-1968">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1969">La función Func_finnish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1970">Se encuentra una palabra clave de Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="4c713-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="4c713-1971">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-1971">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-1972">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1972">Keywords</span></span>

- <span data-ttu-id="4c713-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="4c713-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="4c713-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="4c713-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="4c713-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="4c713-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="4c713-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="4c713-1976">Personbeteckning</span></span>
- <span data-ttu-id="4c713-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="4c713-1978">Número de pasaporte de Finlandia</span><span class="sxs-lookup"><span data-stu-id="4c713-1978">Finland Passport Number</span></span>

<span data-ttu-id="4c713-1979">Combinación de formato de nueve letras y dígitos de la combinación de los patrones de nueve letras y dígitos: dos letras (no distingue entre mayúsculas y minúsculas) siete dígitos de suma de comprobación no Definition una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="4c713-1980">Se encuentra una palabra clave de Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="4c713-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="4c713-1981"></span></span>
<span data-ttu-id="4c713-1982">Palabras clave Keyword_finland_passport_number Passi de Passport</span><span class="sxs-lookup"><span data-stu-id="4c713-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="4c713-1983">Número de licencia de conductor de Francia</span><span class="sxs-lookup"><span data-stu-id="4c713-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-1984">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-1984">Format</span></span>

<span data-ttu-id="4c713-1985">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-1986">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-1986">Pattern</span></span>

<span data-ttu-id="4c713-1987">12 dígitos con validación para descontar patrones similares como los números de teléfono franceses</span><span class="sxs-lookup"><span data-stu-id="4c713-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-1988">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-1988">Checksum</span></span>

<span data-ttu-id="4c713-1989">No</span><span class="sxs-lookup"><span data-stu-id="4c713-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-1990">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-1990">Definition</span></span>

<span data-ttu-id="4c713-1991">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-1992">La función Func_french_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-1993">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="4c713-1994">Se encuentra una palabra clave de Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="4c713-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="4c713-1995">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-1996">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-1996">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="4c713-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4c713-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="4c713-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="4c713-1998">drivers licence</span></span>
- <span data-ttu-id="4c713-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="4c713-1999">drivers license</span></span>
- <span data-ttu-id="4c713-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="4c713-2000">driving licence</span></span>
- <span data-ttu-id="4c713-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="4c713-2001">driving license</span></span>
- <span data-ttu-id="4c713-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="4c713-2002">permis de conduire</span></span>
- <span data-ttu-id="4c713-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="4c713-2003">licence number</span></span>
- <span data-ttu-id="4c713-2004">license number</span><span class="sxs-lookup"><span data-stu-id="4c713-2004">license number</span></span>
- <span data-ttu-id="4c713-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-2005">licence numbers</span></span>
- <span data-ttu-id="4c713-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="4c713-2007">Tarjeta de identificación nacional de Francia (CNI)</span><span class="sxs-lookup"><span data-stu-id="4c713-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2008">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2008">Format</span></span>

<span data-ttu-id="4c713-2009">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2010">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2010">Pattern</span></span>

<span data-ttu-id="4c713-2011">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2012">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2012">Checksum</span></span>

<span data-ttu-id="4c713-2013">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2014">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2014">Definition</span></span>

<span data-ttu-id="4c713-2015">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2016">La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2017">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2017">Keywords</span></span>

<span data-ttu-id="4c713-2018">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4c713-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="4c713-2019">Número de pasaporte de Francia</span><span class="sxs-lookup"><span data-stu-id="4c713-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2020">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2020">Format</span></span>

<span data-ttu-id="4c713-2021">Nueve dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="4c713-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2022">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2022">Pattern</span></span>

<span data-ttu-id="4c713-2023">Nueve dígitos y letras:</span><span class="sxs-lookup"><span data-stu-id="4c713-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="4c713-2024">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2024">Two digits</span></span> 
- <span data-ttu-id="4c713-2025">Dos letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-2026">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2027">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2027">Checksum</span></span>

<span data-ttu-id="4c713-2028">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2029">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2029">Definition</span></span>

<span data-ttu-id="4c713-2030">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2031">La función Func_fr_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2032">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="4c713-2032">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2033">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2033">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="4c713-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-2034">Keyword_passport</span></span>

- <span data-ttu-id="4c713-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2035">Passport Number</span></span>
- <span data-ttu-id="4c713-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="4c713-2036">Passport No</span></span>
- <span data-ttu-id="4c713-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="4c713-2037">Passport #</span></span>
- <span data-ttu-id="4c713-2038">Usuarios</span><span class="sxs-lookup"><span data-stu-id="4c713-2038">Passport#</span></span>
- <span data-ttu-id="4c713-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="4c713-2039">PassportID</span></span>
- <span data-ttu-id="4c713-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="4c713-2040">Passportno</span></span>
- <span data-ttu-id="4c713-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-2041">passportnumber</span></span>
- <span data-ttu-id="4c713-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="4c713-2042">パスポート</span></span>
- <span data-ttu-id="4c713-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2043">パスポート番号</span></span>
- <span data-ttu-id="4c713-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4c713-2044">パスポートのNum</span></span>
- <span data-ttu-id="4c713-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="4c713-2045">パスポート ＃</span></span> 
- <span data-ttu-id="4c713-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4c713-2046">Numéro de passeport</span></span>
- <span data-ttu-id="4c713-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4c713-2047">Passeport n °</span></span>
- <span data-ttu-id="4c713-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4c713-2048">Passeport Non</span></span>
- <span data-ttu-id="4c713-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-2049">Passeport #</span></span>
- <span data-ttu-id="4c713-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-2050">Passeport#</span></span>
- <span data-ttu-id="4c713-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4c713-2051">PasseportNon</span></span>
- <span data-ttu-id="4c713-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4c713-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="4c713-2053">Número de seguridad social de Francia (INSEE)</span><span class="sxs-lookup"><span data-stu-id="4c713-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2054">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2054">Format</span></span>

<span data-ttu-id="4c713-2055">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2056">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2056">Pattern</span></span>

<span data-ttu-id="4c713-2057">Debe coincidir uno de los dos patrones:</span><span class="sxs-lookup"><span data-stu-id="4c713-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="4c713-2058">13 dígitos seguidos de un espacio seguido de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="4c713-2059">o</span><span class="sxs-lookup"><span data-stu-id="4c713-2059">or</span></span>
- <span data-ttu-id="4c713-2060">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2061">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2061">Checksum</span></span>

<span data-ttu-id="4c713-2062">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2063">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2063">Definition</span></span>

<span data-ttu-id="4c713-2064">Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2065">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2066">Se encuentra una palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="4c713-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="4c713-2067">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2067">The checksum passes.</span></span>

<span data-ttu-id="4c713-2068">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2069">La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2070">No se encuentra ninguna palabra clave de Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="4c713-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="4c713-2071">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2072">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2072">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="4c713-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="4c713-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="4c713-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="4c713-2074">insee</span></span>
- <span data-ttu-id="4c713-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="4c713-2075">securité sociale</span></span>
- <span data-ttu-id="4c713-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="4c713-2076">securite sociale</span></span>
- <span data-ttu-id="4c713-2077">national id</span><span class="sxs-lookup"><span data-stu-id="4c713-2077">national id</span></span>
- <span data-ttu-id="4c713-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="4c713-2078">national identification</span></span>
- <span data-ttu-id="4c713-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="4c713-2079">numéro d'identité</span></span>
- <span data-ttu-id="4c713-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="4c713-2080">no d'identité</span></span>
- <span data-ttu-id="4c713-2081">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-2081">no.</span></span> <span data-ttu-id="4c713-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="4c713-2082">d'identité</span></span>
- <span data-ttu-id="4c713-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="4c713-2083">numero d'identite</span></span>
- <span data-ttu-id="4c713-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="4c713-2084">no d'identite</span></span>
- <span data-ttu-id="4c713-2085">dejan.</span><span class="sxs-lookup"><span data-stu-id="4c713-2085">no.</span></span> <span data-ttu-id="4c713-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="4c713-2086">d'identite</span></span>
- <span data-ttu-id="4c713-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="4c713-2087">social security number</span></span>
- <span data-ttu-id="4c713-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="4c713-2088">social security code</span></span>
- <span data-ttu-id="4c713-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="4c713-2089">social insurance number</span></span>
- <span data-ttu-id="4c713-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="4c713-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="4c713-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="4c713-2091">d'identité nationale</span></span>
- <span data-ttu-id="4c713-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="4c713-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="4c713-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="4c713-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="4c713-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="4c713-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="4c713-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="4c713-2095">numéro de sécu</span></span>
- <span data-ttu-id="4c713-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="4c713-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="4c713-2097">Número de licencia de conductor de Alemania</span><span class="sxs-lookup"><span data-stu-id="4c713-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2098">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2098">Format</span></span>

<span data-ttu-id="4c713-2099">Combinación de 11 dígitos y letras</span><span class="sxs-lookup"><span data-stu-id="4c713-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2100">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2100">Pattern</span></span>

<span data-ttu-id="4c713-2101">11 dígitos y letras (no distingue entre mayúsculas y minúsculas):</span><span class="sxs-lookup"><span data-stu-id="4c713-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="4c713-2102">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="4c713-2102">A digit or letter</span></span> 
- <span data-ttu-id="4c713-2103">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2103">Two digits</span></span> 
- <span data-ttu-id="4c713-2104">Seis dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="4c713-2104">Six digits or letters</span></span> 
- <span data-ttu-id="4c713-2105">Un dígito</span><span class="sxs-lookup"><span data-stu-id="4c713-2105">A digit</span></span> 
- <span data-ttu-id="4c713-2106">Un dígito o letra</span><span class="sxs-lookup"><span data-stu-id="4c713-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2107">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2107">Checksum</span></span>

<span data-ttu-id="4c713-2108">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2109">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2109">Definition</span></span>

<span data-ttu-id="4c713-2110">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2111">La función Func_german_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2112">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="4c713-2113">Se encuentra una palabra clave de Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="4c713-2114">Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="4c713-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="4c713-2115">Se encuentra una palabra clave de Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="4c713-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="4c713-2116">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2117">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2117">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="4c713-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="4c713-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2119">Führerschein</span></span>
- <span data-ttu-id="4c713-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2120">Fuhrerschein</span></span>
- <span data-ttu-id="4c713-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2121">Fuehrerschein</span></span>
- <span data-ttu-id="4c713-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="4c713-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="4c713-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="4c713-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="4c713-2125">Führerschein-</span></span> 
- <span data-ttu-id="4c713-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="4c713-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="4c713-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="4c713-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="4c713-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4c713-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="4c713-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4c713-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="4c713-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4c713-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="4c713-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="4c713-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="4c713-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="4c713-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4c713-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="4c713-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4c713-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="4c713-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4c713-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="4c713-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="4c713-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="4c713-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="4c713-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4c713-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="4c713-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4c713-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="4c713-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4c713-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="4c713-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="4c713-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="4c713-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="4c713-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4c713-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="4c713-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4c713-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="4c713-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4c713-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="4c713-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="4c713-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="4c713-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="4c713-2152">LISTAS</span><span class="sxs-lookup"><span data-stu-id="4c713-2152">DL</span></span> 
- <span data-ttu-id="4c713-2153">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c713-2153">DLS</span></span>
- <span data-ttu-id="4c713-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-2154">Driv Lic</span></span> 
- <span data-ttu-id="4c713-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="4c713-2155">Driv Licen</span></span> 
- <span data-ttu-id="4c713-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="4c713-2156">Driv License</span></span>
- <span data-ttu-id="4c713-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2157">Driv Licenses</span></span> 
- <span data-ttu-id="4c713-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-2158">Driv Licence</span></span> 
- <span data-ttu-id="4c713-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-2159">Driv Licences</span></span> 
- <span data-ttu-id="4c713-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-2160">Driv Lic</span></span> 
- <span data-ttu-id="4c713-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="4c713-2161">Driver Licen</span></span> 
- <span data-ttu-id="4c713-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="4c713-2162">Driver License</span></span> 
- <span data-ttu-id="4c713-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2163">Driver Licenses</span></span> 
- <span data-ttu-id="4c713-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-2164">Driver Licence</span></span> 
- <span data-ttu-id="4c713-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-2165">Driver Licences</span></span> 
- <span data-ttu-id="4c713-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-2166">Drivers Lic</span></span> 
- <span data-ttu-id="4c713-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="4c713-2167">Drivers Licen</span></span> 
- <span data-ttu-id="4c713-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4c713-2168">Drivers License</span></span> 
- <span data-ttu-id="4c713-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="4c713-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-2170">Drivers Licence</span></span> 
- <span data-ttu-id="4c713-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-2171">Drivers Licences</span></span> 
- <span data-ttu-id="4c713-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-2172">Driver's Lic</span></span> 
- <span data-ttu-id="4c713-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="4c713-2173">Driver's Licen</span></span> 
- <span data-ttu-id="4c713-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4c713-2174">Driver's License</span></span> 
- <span data-ttu-id="4c713-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="4c713-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-2176">Driver's Licence</span></span> 
- <span data-ttu-id="4c713-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-2177">Driver's Licences</span></span> 
- <span data-ttu-id="4c713-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-2178">Driving Lic</span></span> 
- <span data-ttu-id="4c713-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="4c713-2179">Driving Licen</span></span> 
- <span data-ttu-id="4c713-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="4c713-2180">Driving License</span></span> 
- <span data-ttu-id="4c713-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2181">Driving Licenses</span></span> 
- <span data-ttu-id="4c713-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="4c713-2182">Driving Licence</span></span> 
- <span data-ttu-id="4c713-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="4c713-2183">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="4c713-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="4c713-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="4c713-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="4c713-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="4c713-2187">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="4c713-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2188">No-Führerschein</span></span> 
- <span data-ttu-id="4c713-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="4c713-2190">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="4c713-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2191">N-Führerschein</span></span> 
- <span data-ttu-id="4c713-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="4c713-2193">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="4c713-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="4c713-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="4c713-2196">Nr-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="4c713-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2197">No-Führerschein</span></span> 
- <span data-ttu-id="4c713-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="4c713-2199">No-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="4c713-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2200">N-Führerschein</span></span> 
- <span data-ttu-id="4c713-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="4c713-2202">N-fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4c713-2202">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="4c713-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4c713-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="4c713-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="4c713-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="4c713-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="4c713-2205">ausstellungsort</span></span>
- <span data-ttu-id="4c713-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="4c713-2206">ausstellende behöde</span></span>
- <span data-ttu-id="4c713-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="4c713-2207">ausstellende behorde</span></span>
- <span data-ttu-id="4c713-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="4c713-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="4c713-2209">Número de pasaporte de Alemania</span><span class="sxs-lookup"><span data-stu-id="4c713-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2210">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2210">Format</span></span>

<span data-ttu-id="4c713-2211">10 dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="4c713-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2212">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2212">Pattern</span></span>

<span data-ttu-id="4c713-2213">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c713-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="4c713-2214">El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="4c713-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="4c713-2215">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2215">Three digits</span></span> 
- <span data-ttu-id="4c713-2216">Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="4c713-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="4c713-2217">Un dígito</span><span class="sxs-lookup"><span data-stu-id="4c713-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2218">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2218">Checksum</span></span>

<span data-ttu-id="4c713-2219">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2220">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2220">Definition</span></span>

<span data-ttu-id="4c713-2221">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2222">La función Func_german_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2223">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="4c713-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="4c713-2224">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2224">The checksum passes.</span></span>

<span data-ttu-id="4c713-2225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2226">La función Func_german_passport_data encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2227">Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="4c713-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="4c713-2228">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2229">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2229">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="4c713-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="4c713-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="4c713-2231">reisepass</span></span>
- <span data-ttu-id="4c713-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="4c713-2232">reisepasse</span></span>
- <span data-ttu-id="4c713-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2233">reisepassnummer</span></span>
- <span data-ttu-id="4c713-2234">usuarios</span><span class="sxs-lookup"><span data-stu-id="4c713-2234">passport</span></span>
- <span data-ttu-id="4c713-2235">passports</span><span class="sxs-lookup"><span data-stu-id="4c713-2235">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="4c713-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="4c713-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="4c713-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="4c713-2237">geburtsdatum</span></span>
- <span data-ttu-id="4c713-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="4c713-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="4c713-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="4c713-2239">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="4c713-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="4c713-2241">No-Reisepass NR-Reisepass</span><span class="sxs-lookup"><span data-stu-id="4c713-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="4c713-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="4c713-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="4c713-2243">Reisepass-NR</span><span class="sxs-lookup"><span data-stu-id="4c713-2243">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="4c713-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="4c713-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="4c713-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="4c713-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="4c713-2246">Número de documento de identidad de Alemania</span><span class="sxs-lookup"><span data-stu-id="4c713-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2247">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2247">Format</span></span>

<span data-ttu-id="4c713-2248">Desde el 1 de noviembre de 2010: nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="4c713-2249">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2250">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2250">Pattern</span></span>

<span data-ttu-id="4c713-2251">Desde el 1 de noviembre de 2010:</span><span class="sxs-lookup"><span data-stu-id="4c713-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="4c713-2252">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-2253">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2253">Eight digits</span></span>

<span data-ttu-id="4c713-2254">Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:</span><span class="sxs-lookup"><span data-stu-id="4c713-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="4c713-2255">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2256">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2256">Checksum</span></span>

<span data-ttu-id="4c713-2257">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2258">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2258">Definition</span></span>

<span data-ttu-id="4c713-2259">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2260">La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2261">Se encuentra una palabra clave de Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2262">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2262">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="4c713-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="4c713-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="4c713-2264">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-2264">Identity Card</span></span>
- <span data-ttu-id="4c713-2265">ID</span><span class="sxs-lookup"><span data-stu-id="4c713-2265">ID</span></span>
- <span data-ttu-id="4c713-2266">Determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-2266">Identification</span></span>
- <span data-ttu-id="4c713-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="4c713-2267">Personalausweis</span></span>
- <span data-ttu-id="4c713-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="4c713-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="4c713-2269">Ausweis</span></span>
- <span data-ttu-id="4c713-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="4c713-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="4c713-2271">Tarjeta de identificación nacional de Grecia</span><span class="sxs-lookup"><span data-stu-id="4c713-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2272">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2272">Format</span></span>

<span data-ttu-id="4c713-2273">Combinación de 7 u 8 letras y números más un guión</span><span class="sxs-lookup"><span data-stu-id="4c713-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2274">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2274">Pattern</span></span>

<span data-ttu-id="4c713-2275">Siete letras y números (formato antiguo):</span><span class="sxs-lookup"><span data-stu-id="4c713-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="4c713-2276">Una letra (cualquier letra del alfabeto griego) </span><span class="sxs-lookup"><span data-stu-id="4c713-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="4c713-2277">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-2277">A dash</span></span> 
- <span data-ttu-id="4c713-2278">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2278">Six digits</span></span>

<span data-ttu-id="4c713-2279">Ocho letras y números (nuevo formato):</span><span class="sxs-lookup"><span data-stu-id="4c713-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="4c713-2280">Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="4c713-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="4c713-2281">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-2281">A dash</span></span> 
- <span data-ttu-id="4c713-2282">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2283">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2283">Checksum</span></span>

<span data-ttu-id="4c713-2284">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2285">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2285">Definition</span></span>

<span data-ttu-id="4c713-2286">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2287">La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2288">Se encuentra una palabra clave de Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2289">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2289">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="4c713-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="4c713-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="4c713-2291">Tarjeta de identidad griega</span><span class="sxs-lookup"><span data-stu-id="4c713-2291">Greek identity Card</span></span>
- <span data-ttu-id="4c713-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="4c713-2292">Tautotita</span></span>
- <span data-ttu-id="4c713-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="4c713-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="4c713-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="4c713-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="4c713-2295">Número de tarjeta de identidad de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="4c713-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2296">Format</span></span>

<span data-ttu-id="4c713-2297">Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final</span><span class="sxs-lookup"><span data-stu-id="4c713-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2298">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2298">Pattern</span></span>

<span data-ttu-id="4c713-2299">Combinación de 8 o 9 letras:</span><span class="sxs-lookup"><span data-stu-id="4c713-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="4c713-2300">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-2301">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2301">Six digits</span></span> 
- <span data-ttu-id="4c713-2302">El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="4c713-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2303">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2303">Checksum</span></span>

<span data-ttu-id="4c713-2304">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2305">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2305">Definition</span></span>

<span data-ttu-id="4c713-2306">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2307">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2308">Se encuentra una palabra clave de Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="4c713-2309">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2309">The checksum passes.</span></span>

<span data-ttu-id="4c713-2310">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2311">La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2312">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2313">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2313">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="4c713-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="4c713-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="4c713-2315">tarjeta de identidad de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="4c713-2315">hong kong identity card</span></span>
- <span data-ttu-id="4c713-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="4c713-2316">HKIDC</span></span>
- <span data-ttu-id="4c713-2317">id card</span><span class="sxs-lookup"><span data-stu-id="4c713-2317">id card</span></span>
- <span data-ttu-id="4c713-2318">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-2318">identity card</span></span>
- <span data-ttu-id="4c713-2319">tarjeta de identidad HK</span><span class="sxs-lookup"><span data-stu-id="4c713-2319">hk identity card</span></span>
- <span data-ttu-id="4c713-2320">ID de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="4c713-2320">hong kong id</span></span>
- <span data-ttu-id="4c713-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2321">香港身份證</span></span>
- <span data-ttu-id="4c713-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="4c713-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2323">身份證</span></span>
- <span data-ttu-id="4c713-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="4c713-2324">身份証</span></span>
- <span data-ttu-id="4c713-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-2325">身分證</span></span>
- <span data-ttu-id="4c713-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="4c713-2326">身分証</span></span>
- <span data-ttu-id="4c713-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="4c713-2327">香港身份証</span></span>
- <span data-ttu-id="4c713-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-2328">香港身分證</span></span>
- <span data-ttu-id="4c713-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="4c713-2329">香港身分証</span></span>
- <span data-ttu-id="4c713-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2330">香港身份證</span></span>
- <span data-ttu-id="4c713-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2331">香港居民身份證</span></span>
- <span data-ttu-id="4c713-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="4c713-2332">香港居民身份証</span></span>
- <span data-ttu-id="4c713-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-2333">香港居民身分證</span></span>
- <span data-ttu-id="4c713-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="4c713-2334">香港居民身分証</span></span>
- <span data-ttu-id="4c713-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4c713-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="4c713-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="4c713-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4c713-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="4c713-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="4c713-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="4c713-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4c713-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="4c713-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="4c713-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4c713-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="4c713-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="4c713-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4c713-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="4c713-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="4c713-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4c713-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="4c713-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="4c713-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4c713-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="4c713-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="4c713-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4c713-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="4c713-2351">Número de cuenta permanente de India (PAN)</span><span class="sxs-lookup"><span data-stu-id="4c713-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2352">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2352">Format</span></span>

<span data-ttu-id="4c713-2353">10 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2354">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2354">Pattern</span></span>

<span data-ttu-id="4c713-2355">10 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2355">10 letters or digits:</span></span>
- <span data-ttu-id="4c713-2356">Cinco letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-2357">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2357">Four digits</span></span> 
- <span data-ttu-id="4c713-2358">Una letra que es un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="4c713-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2359">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2359">Checksum</span></span>

<span data-ttu-id="4c713-2360">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2361">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2361">Definition</span></span>

<span data-ttu-id="4c713-2362">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2363">La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2364">Se encuentra una palabra clave de Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="4c713-2365">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2365">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2366">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="4c713-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="4c713-2368">Número de cuenta permanente</span><span class="sxs-lookup"><span data-stu-id="4c713-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="4c713-2369">MANO</span><span class="sxs-lookup"><span data-stu-id="4c713-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="4c713-2370">Número de identificación único (Aadhaar) de la India</span><span class="sxs-lookup"><span data-stu-id="4c713-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2371">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2371">Format</span></span>

<span data-ttu-id="4c713-2372">12 dígitos que contienen espacios o guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="4c713-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2373">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2373">Pattern</span></span>

<span data-ttu-id="4c713-2374">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2374">12 digits:</span></span>
- <span data-ttu-id="4c713-2375">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2375">Four digits</span></span> 
- <span data-ttu-id="4c713-2376">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="4c713-2376">An optional space or dash</span></span> 
- <span data-ttu-id="4c713-2377">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2377">Four digits</span></span> 
- <span data-ttu-id="4c713-2378">Un guión o un espacio opcional </span><span class="sxs-lookup"><span data-stu-id="4c713-2378">An optional space or dash</span></span> 
- <span data-ttu-id="4c713-2379">El dígito final que es el dígito de control</span><span class="sxs-lookup"><span data-stu-id="4c713-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2380">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2380">Checksum</span></span>

<span data-ttu-id="4c713-2381">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2382">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2382">Definition</span></span>

<span data-ttu-id="4c713-2383">Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="4c713-2384">Se encuentra una palabra clave de Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="4c713-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="4c713-2385">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2385">The checksum passes.</span></span>
<span data-ttu-id="4c713-2386">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="4c713-2387">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2387">The checksum passes.</span></span>
<!-- India Unique Identification (Aadhaar) number -->
<span data-ttu-id="4c713-2388"><Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="4c713-2388"></span></span>

### <a name="keywords"></a><span data-ttu-id="4c713-2389">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2389">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="4c713-2390">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="4c713-2390">Keyword_india_aadhar</span></span>
- <span data-ttu-id="4c713-2391">Aadhar</span><span class="sxs-lookup"><span data-stu-id="4c713-2391">Aadhar</span></span>
- <span data-ttu-id="4c713-2392">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="4c713-2392">Aadhaar</span></span>
- <span data-ttu-id="4c713-2393">UID</span><span class="sxs-lookup"><span data-stu-id="4c713-2393">UID</span></span>
- <span data-ttu-id="4c713-2394">आधार</span><span class="sxs-lookup"><span data-stu-id="4c713-2394">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="4c713-2395">Número de tarjeta de identidad (KTP) de Indonesia</span><span class="sxs-lookup"><span data-stu-id="4c713-2395">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2396">Format</span></span>

<span data-ttu-id="4c713-2397">16 dígitos que contienen puntos opcionales</span><span class="sxs-lookup"><span data-stu-id="4c713-2397">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2398">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2398">Pattern</span></span>

<span data-ttu-id="4c713-2399">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2399">16 digits:</span></span>
- <span data-ttu-id="4c713-2400">Código de la provincia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-2400">Two-digit province code</span></span> 
- <span data-ttu-id="4c713-2401">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2401">A period (optional)</span></span> 
- <span data-ttu-id="4c713-2402">Código de ciudad o regencia de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-2402">Two-digit regency or city code</span></span> 
- <span data-ttu-id="4c713-2403">Código de subdistrito de dos dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-2403">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="4c713-2404">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2404">A period (optional)</span></span> 
- <span data-ttu-id="4c713-2405">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-2405">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="4c713-2406">Un punto (opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2406">A period (optional)</span></span> 
- <span data-ttu-id="4c713-2407">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2407">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2408">Checksum</span></span>

<span data-ttu-id="4c713-2409">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2409">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2410">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2410">Definition</span></span>

<span data-ttu-id="4c713-2411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2412">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2412">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2413">Se encuentra una palabra clave de Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-2413">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="4c713-2414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2415">La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2415">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2416">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2416">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="4c713-2417">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="4c713-2417">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="4c713-2418">KTP</span><span class="sxs-lookup"><span data-stu-id="4c713-2418">KTP</span></span>
- <span data-ttu-id="4c713-2419">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="4c713-2419">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="4c713-2420">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="4c713-2420">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="4c713-2421">Número de cuenta bancaria internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="4c713-2421">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2422">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2422">Format</span></span>

<span data-ttu-id="4c713-2423">Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)
</span><span class="sxs-lookup"><span data-stu-id="4c713-2423">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2424">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2424">Pattern</span></span>

<span data-ttu-id="4c713-2425">El patrón debe incluir todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c713-2425">Pattern must include all of the following:</span></span>

- <span data-ttu-id="4c713-2426">Código de país de dos letras</span><span class="sxs-lookup"><span data-stu-id="4c713-2426">Two-letter country code</span></span>
- <span data-ttu-id="4c713-2427">Dos dígitos de control (seguidos de un espacio opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2427">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="4c713-2428">1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)</span><span class="sxs-lookup"><span data-stu-id="4c713-2428">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="4c713-2429">1-3 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2429">1-3 letters or digits</span></span>

<span data-ttu-id="4c713-p135">El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:</span><span class="sxs-lookup"><span data-stu-id="4c713-p135">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="4c713-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="4c713-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2433">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2433">Checksum</span></span>

<span data-ttu-id="4c713-2434">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2435">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2435">Definition</span></span>

<span data-ttu-id="4c713-2436">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2437">La función Func_iban encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2437">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2438">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2438">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2439">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2439">Keywords</span></span>

<span data-ttu-id="4c713-2440">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4c713-2440">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="4c713-2441">dirección IP</span><span class="sxs-lookup"><span data-stu-id="4c713-2441">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2442">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2442">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="4c713-2443">IPv4</span><span class="sxs-lookup"><span data-stu-id="4c713-2443">IPv4:</span></span>
<span data-ttu-id="4c713-2444">Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="4c713-2444">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="4c713-2445">Protocolo</span><span class="sxs-lookup"><span data-stu-id="4c713-2445">IPv6:</span></span>
<span data-ttu-id="4c713-2446"> Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)</span><span class="sxs-lookup"><span data-stu-id="4c713-2446">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2447">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2447">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2448">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2448">Checksum</span></span>

<span data-ttu-id="4c713-2449">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2449">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2450">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2450">Definition</span></span>

<span data-ttu-id="4c713-2451">Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2451">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2452">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2452">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2453">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="4c713-2453">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="4c713-2454">Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2454">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2455">La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2455">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2456">Se encuentra una palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="4c713-2456">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="4c713-2457">Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2457">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2458">La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2458">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2459">No se encuentra ninguna palabra clave de Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="4c713-2459">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2460">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="4c713-2461">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="4c713-2461">Keyword_ipaddress</span></span>

- <span data-ttu-id="4c713-2462">IP (esta palabra clave distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-2462">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="4c713-2463">dirección IP</span><span class="sxs-lookup"><span data-stu-id="4c713-2463">ip address</span></span> 
- <span data-ttu-id="4c713-2464">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="4c713-2464">ip addresses</span></span>
- <span data-ttu-id="4c713-2465">internet protocol</span><span class="sxs-lookup"><span data-stu-id="4c713-2465">internet protocol</span></span>
- <span data-ttu-id="4c713-2466">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="4c713-2466">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="4c713-2467">Clasificación Internacional de enfermedades (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="4c713-2467">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2468">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2468">Format</span></span>

<span data-ttu-id="4c713-2469">Dictionary</span><span class="sxs-lookup"><span data-stu-id="4c713-2469">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2470">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2470">Pattern</span></span>

<span data-ttu-id="4c713-2471">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2471">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2472">Checksum</span></span>

<span data-ttu-id="4c713-2473">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2474">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2474">Definition</span></span>

<span data-ttu-id="4c713-2475">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2476">Se encuentra una palabra clave de Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="4c713-2476">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="4c713-2477">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2477">Keywords</span></span>

<span data-ttu-id="4c713-2478">Cualquier término del Diccionario de palabras clave de Dictionary_icd_10_cm, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="4c713-2478">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="4c713-2479">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="4c713-2479">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="4c713-2480">Clasificación Internacional de enfermedades (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="4c713-2480">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2481">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2481">Format</span></span>

<span data-ttu-id="4c713-2482">Dictionary</span><span class="sxs-lookup"><span data-stu-id="4c713-2482">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2483">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2483">Pattern</span></span>

<span data-ttu-id="4c713-2484">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2484">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2485">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2485">Checksum</span></span>

<span data-ttu-id="4c713-2486">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2486">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2487">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2487">Definition</span></span>

<span data-ttu-id="4c713-2488">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2488">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2489">Se encuentra una palabra clave de Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="4c713-2489">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2490">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2490">Keywords</span></span>

<span data-ttu-id="4c713-2491">Cualquier término del Diccionario de palabras clave de Dictionary_icd_9_cm, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="4c713-2491">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="4c713-2492">Este tipo solo busca el término, no los códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="4c713-2492">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="4c713-2493">Número de servicio público personal (PPS) de Irlanda</span><span class="sxs-lookup"><span data-stu-id="4c713-2493">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2494">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2494">Format</span></span>

<span data-ttu-id="4c713-2495">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="4c713-2495">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="4c713-2496">Siete dígitos seguidos por 1 o 2 letras </span><span class="sxs-lookup"><span data-stu-id="4c713-2496">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="4c713-2497">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="4c713-2497">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="4c713-2498">Siete dígitos seguidos por dos letras</span><span class="sxs-lookup"><span data-stu-id="4c713-2498">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2499">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2499">Pattern</span></span>

<span data-ttu-id="4c713-2500">Formato antiguo (hasta el 31 de diciembre de 2012):</span><span class="sxs-lookup"><span data-stu-id="4c713-2500">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="4c713-2501">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-2501">Seven digits</span></span> 
- <span data-ttu-id="4c713-2502">1 o 2 letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-2502">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="4c713-2503">Nuevo formato (1 de enero de 2013 y posterior):</span><span class="sxs-lookup"><span data-stu-id="4c713-2503">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="4c713-2504">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-2504">Seven digits</span></span> 
- <span data-ttu-id="4c713-2505">Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético </span><span class="sxs-lookup"><span data-stu-id="4c713-2505">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="4c713-2506">La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-2506">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2507">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2507">Checksum</span></span>

<span data-ttu-id="4c713-2508">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2508">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2509">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2509">Definition</span></span>

<span data-ttu-id="4c713-2510">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2511">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2511">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2512">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-2512">One of the following is true:</span></span>
    - <span data-ttu-id="4c713-2513">Se encuentra una palabra clave de Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="4c713-2513">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="4c713-2514">La función Func_eu_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-2514">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4c713-2515">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2515">The checksum passes.</span></span>

<span data-ttu-id="4c713-2516">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2516">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2517">La función Func_ireland_pps encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2517">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2518">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2518">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2519">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2519">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="4c713-2520">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="4c713-2520">Keyword_ireland_pps</span></span>

- <span data-ttu-id="4c713-2521">Número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="4c713-2521">Personal Public Service Number</span></span> 
- <span data-ttu-id="4c713-2522">Número de PPS</span><span class="sxs-lookup"><span data-stu-id="4c713-2522">PPS Number</span></span> 
- <span data-ttu-id="4c713-2523">Núm. PPS
</span><span class="sxs-lookup"><span data-stu-id="4c713-2523">PPS Num</span></span> 
- <span data-ttu-id="4c713-2524">N.º PPS</span><span class="sxs-lookup"><span data-stu-id="4c713-2524">PPS No.</span></span> 
- <span data-ttu-id="4c713-2525">N.ro PPS</span><span class="sxs-lookup"><span data-stu-id="4c713-2525">PPS #</span></span> 
- <span data-ttu-id="4c713-2526">PPS</span><span class="sxs-lookup"><span data-stu-id="4c713-2526">PPS#</span></span> 
- <span data-ttu-id="4c713-2527">PPSN</span><span class="sxs-lookup"><span data-stu-id="4c713-2527">PPSN</span></span> 
- <span data-ttu-id="4c713-2528">Tarjeta de servicios públicos</span><span class="sxs-lookup"><span data-stu-id="4c713-2528">Public Services Card</span></span> 
- <span data-ttu-id="4c713-2529">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="4c713-2529">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="4c713-2530">Uimh.</span><span class="sxs-lookup"><span data-stu-id="4c713-2530">Uimh.</span></span> <span data-ttu-id="4c713-2531">PSP</span><span class="sxs-lookup"><span data-stu-id="4c713-2531">PSP</span></span> 
- <span data-ttu-id="4c713-2532">PSP</span><span class="sxs-lookup"><span data-stu-id="4c713-2532">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="4c713-2533">Número de cuenta bancaria de Israel</span><span class="sxs-lookup"><span data-stu-id="4c713-2533">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2534">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2534">Format</span></span>

<span data-ttu-id="4c713-2535">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2535">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2536">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2536">Pattern</span></span>

<span data-ttu-id="4c713-2537">Con formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2537">Formatted:</span></span>
- <span data-ttu-id="4c713-2538">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2538">Two digits</span></span> 
- <span data-ttu-id="4c713-2539">Guion</span><span class="sxs-lookup"><span data-stu-id="4c713-2539">A dash</span></span> 
- <span data-ttu-id="4c713-2540">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2540">Three digits</span></span> 
- <span data-ttu-id="4c713-2541">Guion</span><span class="sxs-lookup"><span data-stu-id="4c713-2541">A dash</span></span> 
- <span data-ttu-id="4c713-2542">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2542">Eight digits</span></span>

<span data-ttu-id="4c713-2543">Sin formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2543">Unformatted:</span></span>
- <span data-ttu-id="4c713-2544">	13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-2544">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2545">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2545">Checksum</span></span>

<span data-ttu-id="4c713-2546">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2546">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2547">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2547">Definition</span></span>

<span data-ttu-id="4c713-2548">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2549">La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2549">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2550">Se encuentra una palabra clave de Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2550">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2551">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2551">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="4c713-2552">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2552">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="4c713-2553">Número de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="4c713-2553">Bank Account Number</span></span> 
- <span data-ttu-id="4c713-2554">Cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="4c713-2554">Bank Account</span></span> 
- <span data-ttu-id="4c713-2555">Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2555">Account Number</span></span> 
- <span data-ttu-id="4c713-2556">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="4c713-2556">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="4c713-2557">Identificación nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="4c713-2557">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2558">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2558">Format</span></span>

<span data-ttu-id="4c713-2559">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2559">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2560">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2560">Pattern</span></span>

<span data-ttu-id="4c713-2561">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-2561">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2562">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2562">Checksum</span></span>

<span data-ttu-id="4c713-2563">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2563">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2564">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2564">Definition</span></span>

<span data-ttu-id="4c713-2565">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2565">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2566">La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2566">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2567">Se encuentra una palabra clave de Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="4c713-2567">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="4c713-2568">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2568">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2569">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2569">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="4c713-2570">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="4c713-2570">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="4c713-2571">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="4c713-2571">מספר זהות</span></span> 
- <span data-ttu-id="4c713-2572">National ID Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2572">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="4c713-2573">Número de licencia de conductor de Italia</span><span class="sxs-lookup"><span data-stu-id="4c713-2573">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2574">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2574">Format</span></span>

<span data-ttu-id="4c713-2575">Una combinación de 10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2575">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2576">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2576">Pattern</span></span>

- <span data-ttu-id="4c713-2577">Una combinación de 10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2577">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="4c713-2578">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-2578">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-2579">La letra "A" o "V" (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-2579">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-2580">Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado</span><span class="sxs-lookup"><span data-stu-id="4c713-2580">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="4c713-2581">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-2581">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2582">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2582">Checksum</span></span>

<span data-ttu-id="4c713-2583">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2583">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2584">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2584">Definition</span></span>

<span data-ttu-id="4c713-2585">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2586">La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2586">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2587">Se encuentra una palabra clave de Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2587">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2588">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2588">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="4c713-2589">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2589">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="4c713-2590">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="4c713-2590">numero di patente di guida</span></span> 
- <span data-ttu-id="4c713-2591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="4c713-2591">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="4c713-2592">Número de cuenta bancaria de Japón</span><span class="sxs-lookup"><span data-stu-id="4c713-2592">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2593">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2593">Format</span></span>

<span data-ttu-id="4c713-2594">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2594">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2595">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2595">Pattern</span></span>

<span data-ttu-id="4c713-2596">Número de cuenta bancaria:</span><span class="sxs-lookup"><span data-stu-id="4c713-2596">Bank account number:</span></span>
- <span data-ttu-id="4c713-2597">Siete u ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2597">Seven or eight digits</span></span>
- <span data-ttu-id="4c713-2598">Código de sucursal del banco:</span><span class="sxs-lookup"><span data-stu-id="4c713-2598">Bank account branch code:</span></span>
- <span data-ttu-id="4c713-2599">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2599">Four digits</span></span> 
- <span data-ttu-id="4c713-2600">Un espacio o un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="4c713-2600">A space or dash (optional)</span></span> 
- <span data-ttu-id="4c713-2601">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2601">Three digits</span></span>

<span data-ttu-id="4c713-2602">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2602">Checksum</span></span>

<span data-ttu-id="4c713-2603">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2603">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2604">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2604">Definition</span></span>

<span data-ttu-id="4c713-2605">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2605">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2606">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2606">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2607">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="4c713-2607">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="4c713-2608">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-2608">One of the following is true:</span></span>
- <span data-ttu-id="4c713-2609">La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2609">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2610">Se encuentra una palabra clave de Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="4c713-2610">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="4c713-2611">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2611">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2612">La función Func_jp_bank_account encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2612">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2613">Se encuentra una palabra clave de Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="4c713-2613">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2614">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2614">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="4c713-2615">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="4c713-2615">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="4c713-2616">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2616">Checking Account Number</span></span> 
- <span data-ttu-id="4c713-2617">Checking Account</span><span class="sxs-lookup"><span data-stu-id="4c713-2617">Checking Account</span></span> 
- <span data-ttu-id="4c713-2618">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-2618">Checking Account #</span></span> 
- <span data-ttu-id="4c713-2619">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2619">Checking Acct Number</span></span> 
- <span data-ttu-id="4c713-2620">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-2620">Checking Acct #</span></span> 
- <span data-ttu-id="4c713-2621">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2621">Checking Acct No.</span></span> 
- <span data-ttu-id="4c713-2622">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2622">Checking Account No.</span></span> 
- <span data-ttu-id="4c713-2623">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2623">Bank Account Number</span></span> 
- <span data-ttu-id="4c713-2624">Bank Account</span><span class="sxs-lookup"><span data-stu-id="4c713-2624">Bank Account</span></span> 
- <span data-ttu-id="4c713-2625">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-2625">Bank Account #</span></span> 
- <span data-ttu-id="4c713-2626">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2626">Bank Acct Number</span></span> 
- <span data-ttu-id="4c713-2627">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-2627">Bank Acct #</span></span> 
- <span data-ttu-id="4c713-2628">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2628">Bank Acct No.</span></span> 
- <span data-ttu-id="4c713-2629">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2629">Bank Account No.</span></span> 
- <span data-ttu-id="4c713-2630">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2630">Savings Account Number</span></span> 
- <span data-ttu-id="4c713-2631">Savings Account</span><span class="sxs-lookup"><span data-stu-id="4c713-2631">Savings Account</span></span> 
- <span data-ttu-id="4c713-2632">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-2632">Savings Account #</span></span> 
- <span data-ttu-id="4c713-2633">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2633">Savings Acct Number</span></span> 
- <span data-ttu-id="4c713-2634">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-2634">Savings Acct #</span></span> 
- <span data-ttu-id="4c713-2635">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2635">Savings Acct No.</span></span> 
- <span data-ttu-id="4c713-2636">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2636">Savings Account No.</span></span> 
- <span data-ttu-id="4c713-2637">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2637">Debit Account Number</span></span> 
- <span data-ttu-id="4c713-2638">Debit Account</span><span class="sxs-lookup"><span data-stu-id="4c713-2638">Debit Account</span></span> 
- <span data-ttu-id="4c713-2639">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-2639">Debit Account #</span></span> 
- <span data-ttu-id="4c713-2640">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2640">Debit Acct Number</span></span> 
- <span data-ttu-id="4c713-2641">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-2641">Debit Acct #</span></span> 
- <span data-ttu-id="4c713-2642">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2642">Debit Acct No.</span></span> 
- <span data-ttu-id="4c713-2643">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2643">Debit Account No.</span></span> 
- <span data-ttu-id="4c713-2644">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="4c713-2644">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="4c713-2645">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="4c713-2645">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="4c713-2646">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="4c713-2646">＃勘定の確認</span></span> 
- <span data-ttu-id="4c713-2647">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="4c713-2647">勘定番号の確認</span></span> 
- <span data-ttu-id="4c713-2648">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="4c713-2648">口座番号の確認</span></span> 
- <span data-ttu-id="4c713-2649">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2649">銀行口座番号</span></span> 
- <span data-ttu-id="4c713-2650">銀行口座</span><span class="sxs-lookup"><span data-stu-id="4c713-2650">銀行口座</span></span> 
- <span data-ttu-id="4c713-2651">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="4c713-2651">銀行口座＃</span></span> 
- <span data-ttu-id="4c713-2652">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2652">銀行の勘定番号</span></span> 
- <span data-ttu-id="4c713-2653">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="4c713-2653">銀行のacct＃</span></span> 
- <span data-ttu-id="4c713-2654">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="4c713-2654">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="4c713-2655">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2655">銀行口座番号</span></span>
- <span data-ttu-id="4c713-2656">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2656">普通預金口座番号</span></span> 
- <span data-ttu-id="4c713-2657">預金口座</span><span class="sxs-lookup"><span data-stu-id="4c713-2657">預金口座</span></span> 
- <span data-ttu-id="4c713-2658">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="4c713-2658">貯蓄口座＃</span></span> 
- <span data-ttu-id="4c713-2659">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="4c713-2659">貯蓄勘定の数</span></span> 
- <span data-ttu-id="4c713-2660">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="4c713-2660">貯蓄勘定＃</span></span> 
- <span data-ttu-id="4c713-2661">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2661">貯蓄勘定番号</span></span> 
- <span data-ttu-id="4c713-2662">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2662">普通預金口座番号</span></span> 
- <span data-ttu-id="4c713-2663">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2663">引き落とし口座番号</span></span> 
- <span data-ttu-id="4c713-2664">口座番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2664">口座番号</span></span> 
- <span data-ttu-id="4c713-2665">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="4c713-2665">口座番号＃</span></span> 
- <span data-ttu-id="4c713-2666">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2666">デビットのacct番号</span></span> 
- <span data-ttu-id="4c713-2667">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="4c713-2667">デビット勘定＃</span></span> 
- <span data-ttu-id="4c713-2668">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2668">デビットACCTの番号</span></span> 
- <span data-ttu-id="4c713-2669">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2669">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="4c713-2670">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="4c713-2670">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="4c713-2671">Otemachi</span><span class="sxs-lookup"><span data-stu-id="4c713-2671">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="4c713-2672">Número de licencia de conductor de Japón</span><span class="sxs-lookup"><span data-stu-id="4c713-2672">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2673">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2673">Format</span></span>

<span data-ttu-id="4c713-2674">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2674">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2675">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2675">Pattern</span></span>

<span data-ttu-id="4c713-2676">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-2676">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2677">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2677">Checksum</span></span>

<span data-ttu-id="4c713-2678">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2678">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2679">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2679">Definition</span></span>

<span data-ttu-id="4c713-2680">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2681">La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2681">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2682">Se encuentra una palabra clave de Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2682">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2683">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2683">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="4c713-2684">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2684">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="4c713-2685">listas</span><span class="sxs-lookup"><span data-stu-id="4c713-2685">dl#</span></span> 
- <span data-ttu-id="4c713-2686">LISTAS</span><span class="sxs-lookup"><span data-stu-id="4c713-2686">DL＃</span></span> 
- <span data-ttu-id="4c713-2687">distribución</span><span class="sxs-lookup"><span data-stu-id="4c713-2687">dls#</span></span> 
- <span data-ttu-id="4c713-2688">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c713-2688">DLS＃</span></span> 
- <span data-ttu-id="4c713-2689">driver license</span><span class="sxs-lookup"><span data-stu-id="4c713-2689">driver license</span></span> 
- <span data-ttu-id="4c713-2690">driver licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2690">driver licenses</span></span> 
- <span data-ttu-id="4c713-2691">drivers license</span><span class="sxs-lookup"><span data-stu-id="4c713-2691">drivers license</span></span> 
- <span data-ttu-id="4c713-2692">driver's license</span><span class="sxs-lookup"><span data-stu-id="4c713-2692">driver's license</span></span> 
- <span data-ttu-id="4c713-2693">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2693">drivers licenses</span></span> 
- <span data-ttu-id="4c713-2694">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-2694">driver's licenses</span></span> 
- <span data-ttu-id="4c713-2695">driving licence</span><span class="sxs-lookup"><span data-stu-id="4c713-2695">driving licence</span></span> 
- <span data-ttu-id="4c713-2696">Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-2696">lic#</span></span> 
- <span data-ttu-id="4c713-2697">Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-2697">LIC＃</span></span> 
- <span data-ttu-id="4c713-2698">conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-2698">lics#</span></span> 
- <span data-ttu-id="4c713-2699">state id</span><span class="sxs-lookup"><span data-stu-id="4c713-2699">state id</span></span> 
- <span data-ttu-id="4c713-2700">state identification</span><span class="sxs-lookup"><span data-stu-id="4c713-2700">state identification</span></span> 
- <span data-ttu-id="4c713-2701">state identification number</span><span class="sxs-lookup"><span data-stu-id="4c713-2701">state identification number</span></span> 
- <span data-ttu-id="4c713-2702">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="4c713-2702">低所得国＃</span></span> 
- <span data-ttu-id="4c713-2703">免許証</span><span class="sxs-lookup"><span data-stu-id="4c713-2703">免許証</span></span> 
- <span data-ttu-id="4c713-2704">状態ID</span><span class="sxs-lookup"><span data-stu-id="4c713-2704">状態ID</span></span>
- <span data-ttu-id="4c713-2705">状態の識別</span><span class="sxs-lookup"><span data-stu-id="4c713-2705">状態の識別</span></span> 
- <span data-ttu-id="4c713-2706">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2706">状態の識別番号</span></span> 
- <span data-ttu-id="4c713-2707">運転免許</span><span class="sxs-lookup"><span data-stu-id="4c713-2707">運転免許</span></span> 
- <span data-ttu-id="4c713-2708">運転免許証</span><span class="sxs-lookup"><span data-stu-id="4c713-2708">運転免許証</span></span> 
- <span data-ttu-id="4c713-2709">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2709">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="4c713-2710">Número de pasaporte de Japón</span><span class="sxs-lookup"><span data-stu-id="4c713-2710">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2711">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2711">Format</span></span>

<span data-ttu-id="4c713-2712">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2712">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2713">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2713">Pattern</span></span>

<span data-ttu-id="4c713-2714">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2714">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2715">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2715">Checksum</span></span>

<span data-ttu-id="4c713-2716">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2716">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2717">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2717">Definition</span></span>

<span data-ttu-id="4c713-2718">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2718">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2719">La función Func_jp_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2719">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2720">Se encuentra una palabra clave de Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="4c713-2720">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2721">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2721">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="4c713-2722">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-2722">Keyword_jp_passport</span></span>

- <span data-ttu-id="4c713-2723">パスポート</span><span class="sxs-lookup"><span data-stu-id="4c713-2723">パスポート</span></span> 
- <span data-ttu-id="4c713-2724">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2724">パスポート番号</span></span> 
- <span data-ttu-id="4c713-2725">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4c713-2725">パスポートのNum</span></span> 
- <span data-ttu-id="4c713-2726">パスポート #</span><span class="sxs-lookup"><span data-stu-id="4c713-2726">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="4c713-2727">Número de registro de residente de Japón</span><span class="sxs-lookup"><span data-stu-id="4c713-2727">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2728">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2728">Format</span></span>

<span data-ttu-id="4c713-2729">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2729">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2730">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2730">Pattern</span></span>

<span data-ttu-id="4c713-2731">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-2731">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2732">Checksum</span></span>

<span data-ttu-id="4c713-2733">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2733">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2734">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2734">Definition</span></span>

<span data-ttu-id="4c713-2735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2736">La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2736">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2737">Se encuentra una palabra clave de Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2737">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2738">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="4c713-2739">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2739">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="4c713-2740">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2740">Resident Registration Number</span></span>
- <span data-ttu-id="4c713-2741">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2741">Resident Register Number</span></span> 
- <span data-ttu-id="4c713-2742">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2742">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="4c713-2743">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2743">Resident Registration No.</span></span> 
- <span data-ttu-id="4c713-2744">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2744">Resident Register No.</span></span> 
- <span data-ttu-id="4c713-2745">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2745">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="4c713-2746">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2746">Basic Resident Register No.</span></span> 
- <span data-ttu-id="4c713-2747">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="4c713-2747">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="4c713-2748">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2748">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="4c713-2749">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="4c713-2749">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="4c713-2750">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2750">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="4c713-2751">Número de Seguridad Social de Japón (SIN)</span><span class="sxs-lookup"><span data-stu-id="4c713-2751">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2752">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2752">Format</span></span>

<span data-ttu-id="4c713-2753">De 7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2753">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2754">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2754">Pattern</span></span>

<span data-ttu-id="4c713-2755">7-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2755">7-12 digits:</span></span>
- <span data-ttu-id="4c713-2756">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2756">Four digits</span></span> 
- <span data-ttu-id="4c713-2757">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="4c713-2757">A hyphen (optional)</span></span> 
- <span data-ttu-id="4c713-2758">Seis dígitos o</span><span class="sxs-lookup"><span data-stu-id="4c713-2758">Six digits OR</span></span>
- <span data-ttu-id="4c713-2759">De 7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-2759">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2760">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2760">Checksum</span></span>

<span data-ttu-id="4c713-2761">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2761">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2762">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2762">Definition</span></span>

<span data-ttu-id="4c713-2763">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2763">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2764">La función Func_jp_sin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2764">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2765">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="4c713-2765">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="4c713-2766">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2766">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2767">La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2767">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2768">Se encuentra una palabra clave de Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="4c713-2768">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2769">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2769">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="4c713-2770">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="4c713-2770">Keyword_jp_sin</span></span>

- <span data-ttu-id="4c713-2771">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="4c713-2771">Social Insurance No.</span></span> 
- <span data-ttu-id="4c713-2772">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="4c713-2772">Social Insurance Num</span></span> 
- <span data-ttu-id="4c713-2773">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="4c713-2773">Social Insurance Number</span></span> 
- <span data-ttu-id="4c713-2774">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="4c713-2774">社会保険のテンキー</span></span> 
- <span data-ttu-id="4c713-2775">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2775">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="4c713-2776">Número de tarjeta de residencia japonés</span><span class="sxs-lookup"><span data-stu-id="4c713-2776">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2777">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2777">Format</span></span>

<span data-ttu-id="4c713-2778">12 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2778">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2779">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2779">Pattern</span></span>

<span data-ttu-id="4c713-2780">12 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2780">12 letters and digits:</span></span>
- <span data-ttu-id="4c713-2781">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-2781">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="4c713-2782">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2782">Eight digits</span></span> 
- <span data-ttu-id="4c713-2783">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-2783">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2784">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2784">Checksum</span></span>

<span data-ttu-id="4c713-2785">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2785">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2786">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2786">Definition</span></span>

<span data-ttu-id="4c713-2787">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2788">La expresión regular Regex_jp_residence_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2788">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2789">Se encuentra una palabra clave de Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2789">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2790">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2790">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="4c713-2791">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2791">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="4c713-2792">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="4c713-2792">Residence card number</span></span>
- <span data-ttu-id="4c713-2793">Nº de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="4c713-2793">Residence card no</span></span>
- <span data-ttu-id="4c713-2794">Número de tarjeta de residencia</span><span class="sxs-lookup"><span data-stu-id="4c713-2794">Residence card #</span></span>
- <span data-ttu-id="4c713-2795">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="4c713-2795">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="4c713-2796">Número de la tarjeta de identificación de Malasia</span><span class="sxs-lookup"><span data-stu-id="4c713-2796">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2797">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2797">Format</span></span>

<span data-ttu-id="4c713-2798">12 dígitos que contienen guiones opcionales</span><span class="sxs-lookup"><span data-stu-id="4c713-2798">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2799">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2799">Pattern</span></span>

<span data-ttu-id="4c713-2800">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2800">12 digits:</span></span>
- <span data-ttu-id="4c713-2801">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-2801">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4c713-2802">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2802">A dash (optional)</span></span> 
- <span data-ttu-id="4c713-2803">Código de dos letras del lugar de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-2803">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="4c713-2804">Un guión (opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2804">A dash (optional)</span></span> 
- <span data-ttu-id="4c713-2805">Tres dígitos aleatorios </span><span class="sxs-lookup"><span data-stu-id="4c713-2805">Three random digits</span></span> 
- <span data-ttu-id="4c713-2806">Código de género de un dígito</span><span class="sxs-lookup"><span data-stu-id="4c713-2806">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2807">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2807">Checksum</span></span>

<span data-ttu-id="4c713-2808">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2808">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2809">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2809">Definition</span></span>

<span data-ttu-id="4c713-2810">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2810">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2811">La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2811">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2812">Se encuentra una palabra clave de Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2812">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2813">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2813">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="4c713-2814">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2814">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="4c713-2815">tarjeta de aplicación digital</span><span class="sxs-lookup"><span data-stu-id="4c713-2815">digital application card</span></span>
- <span data-ttu-id="4c713-2816">i/c</span><span class="sxs-lookup"><span data-stu-id="4c713-2816">i/c</span></span>
- <span data-ttu-id="4c713-2817">i/c no</span><span class="sxs-lookup"><span data-stu-id="4c713-2817">i/c no</span></span>
- <span data-ttu-id="4c713-2818">i</span><span class="sxs-lookup"><span data-stu-id="4c713-2818">ic</span></span>
- <span data-ttu-id="4c713-2819">no IC</span><span class="sxs-lookup"><span data-stu-id="4c713-2819">ic no</span></span>
- <span data-ttu-id="4c713-2820">id card</span><span class="sxs-lookup"><span data-stu-id="4c713-2820">id card</span></span>
- <span data-ttu-id="4c713-2821">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="4c713-2821">identification Card</span></span>
- <span data-ttu-id="4c713-2822">documento de identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-2822">identity card</span></span>
- <span data-ttu-id="4c713-2823">k/p</span><span class="sxs-lookup"><span data-stu-id="4c713-2823">k/p</span></span>
- <span data-ttu-id="4c713-2824">k/p no</span><span class="sxs-lookup"><span data-stu-id="4c713-2824">k/p no</span></span>
- <span data-ttu-id="4c713-2825">Kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="4c713-2825">kad akuan diri</span></span>
- <span data-ttu-id="4c713-2826">Kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="4c713-2826">kad aplikasi digital</span></span>
- <span data-ttu-id="4c713-2827">Kad pengenalan Malasia</span><span class="sxs-lookup"><span data-stu-id="4c713-2827">kad pengenalan malaysia</span></span>
- <span data-ttu-id="4c713-2828">PK</span><span class="sxs-lookup"><span data-stu-id="4c713-2828">kp</span></span>
- <span data-ttu-id="4c713-2829">KP no</span><span class="sxs-lookup"><span data-stu-id="4c713-2829">kp no</span></span>
- <span data-ttu-id="4c713-2830">mykad</span><span class="sxs-lookup"><span data-stu-id="4c713-2830">mykad</span></span>
- <span data-ttu-id="4c713-2831">MYKAS</span><span class="sxs-lookup"><span data-stu-id="4c713-2831">mykas</span></span>
- <span data-ttu-id="4c713-2832">mykid</span><span class="sxs-lookup"><span data-stu-id="4c713-2832">mykid</span></span>
- <span data-ttu-id="4c713-2833">mypr</span><span class="sxs-lookup"><span data-stu-id="4c713-2833">mypr</span></span>
- <span data-ttu-id="4c713-2834">mytentera</span><span class="sxs-lookup"><span data-stu-id="4c713-2834">mytentera</span></span>
- <span data-ttu-id="4c713-2835">tarjeta de identidad de Malasia</span><span class="sxs-lookup"><span data-stu-id="4c713-2835">malaysia identity card</span></span>
- <span data-ttu-id="4c713-2836">tarjeta de identidad malasio</span><span class="sxs-lookup"><span data-stu-id="4c713-2836">malaysian identity card</span></span>
- <span data-ttu-id="4c713-2837">NRIC</span><span class="sxs-lookup"><span data-stu-id="4c713-2837">nric</span></span>
- <span data-ttu-id="4c713-2838">tarjeta de identificación personal</span><span class="sxs-lookup"><span data-stu-id="4c713-2838">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="4c713-2839">Número de servicio del ciudadano (BSN) de Países Bajos</span><span class="sxs-lookup"><span data-stu-id="4c713-2839">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2840">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2840">Format</span></span>

<span data-ttu-id="4c713-2841">8 o 9 dígitos que contienen espacios opcionales</span><span class="sxs-lookup"><span data-stu-id="4c713-2841">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2842">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2842">Pattern</span></span>

<span data-ttu-id="4c713-2843">8 o 9 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2843">8-9 digits:</span></span>
- <span data-ttu-id="4c713-2844">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2844">Three digits</span></span> 
- <span data-ttu-id="4c713-2845">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2845">A space (optional)</span></span> 
- <span data-ttu-id="4c713-2846">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2846">Three digits</span></span> 
- <span data-ttu-id="4c713-2847">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="4c713-2847">A space (optional)</span></span> 
- <span data-ttu-id="4c713-2848">2 o 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2848">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2849">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2849">Checksum</span></span>

<span data-ttu-id="4c713-2850">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2850">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2851">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2851">Definition</span></span>

<span data-ttu-id="4c713-2852">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2852">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2853">La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2853">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2854">Se encuentra una palabra clave de Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="4c713-2854">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="4c713-2855">La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-2855">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="4c713-2856">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2857">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2857">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="4c713-2858">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="4c713-2858">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="4c713-2859">Número de servicio de ciudadanía</span><span class="sxs-lookup"><span data-stu-id="4c713-2859">Citizen service number</span></span> 
- <span data-ttu-id="4c713-2860">BSN</span><span class="sxs-lookup"><span data-stu-id="4c713-2860">BSN</span></span> 
- <span data-ttu-id="4c713-2861">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2861">Burgerservicenummer</span></span> 
- <span data-ttu-id="4c713-2862">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2862">Sofinummer</span></span> 
- <span data-ttu-id="4c713-2863">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2863">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="4c713-2864">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2864">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="4c713-2865">Número de Ministerio de salud de Nueva Zelanda</span><span class="sxs-lookup"><span data-stu-id="4c713-2865">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2866">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2866">Format</span></span>

<span data-ttu-id="4c713-2867">Tres letras, un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2867">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2868">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2868">Pattern</span></span>

<span data-ttu-id="4c713-2869">Tres letras (no distingue entre mayúsculas y minúsculas), un espacio (opcional) y cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2869">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2870">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2870">Checksum</span></span>

<span data-ttu-id="4c713-2871">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2871">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2872">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2872">Definition</span></span>

<span data-ttu-id="4c713-2873">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2873">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2874">La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2874">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2875">Se encuentra una palabra clave de Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="4c713-2875">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="4c713-2876">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2876">The checksum passes.</span></span>

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

<span data-ttu-id="4c713-2877">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2877">Keywords</span></span>

<span data-ttu-id="4c713-2878">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="4c713-2878">Keyword_nz_terms</span></span>

- <span data-ttu-id="4c713-2879">NHI</span><span class="sxs-lookup"><span data-stu-id="4c713-2879">NHI</span></span> 
- <span data-ttu-id="4c713-2880">New Zealand</span><span class="sxs-lookup"><span data-stu-id="4c713-2880">New Zealand</span></span> 
- <span data-ttu-id="4c713-2881">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-2881">Health</span></span> 
- <span data-ttu-id="4c713-2882">régimen</span><span class="sxs-lookup"><span data-stu-id="4c713-2882">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="4c713-2883">Número de identificación de Noruega</span><span class="sxs-lookup"><span data-stu-id="4c713-2883">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2884">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2884">Format</span></span>

<span data-ttu-id="4c713-2885">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2885">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2886">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2886">Pattern</span></span>

<span data-ttu-id="4c713-2887">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2887">11 digits:</span></span>
- <span data-ttu-id="4c713-2888">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-2888">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="4c713-2889">Número individual de tres dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-2889">Three-digit individual number</span></span> 
- <span data-ttu-id="4c713-2890">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="4c713-2890">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2891">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2891">Checksum</span></span>

<span data-ttu-id="4c713-2892">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2892">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2893">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2893">Definition</span></span>

<span data-ttu-id="4c713-2894">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2894">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2895">La función Func_norway_id_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2895">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2896">Se encuentra una palabra clave de Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2896">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="4c713-2897">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2897">The checksum passes.</span></span>
- <span data-ttu-id="4c713-2898">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2898">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2899">La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2899">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2900">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2900">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2901">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2901">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="4c713-2902">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2902">Keyword_norway_id_number</span></span>

- <span data-ttu-id="4c713-2903">Número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="4c713-2903">Personal identification number</span></span>
- <span data-ttu-id="4c713-2904">Número de id. noruego</span><span class="sxs-lookup"><span data-stu-id="4c713-2904">Norwegian ID Number</span></span>
- <span data-ttu-id="4c713-2905">Número de id.</span><span class="sxs-lookup"><span data-stu-id="4c713-2905">ID Number</span></span>
- <span data-ttu-id="4c713-2906">Determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-2906">Identification</span></span>
- <span data-ttu-id="4c713-2907">Personnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2907">Personnummer</span></span>
- <span data-ttu-id="4c713-2908">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="4c713-2908">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="4c713-2909">Número de id. universal unificado de Filipinas</span><span class="sxs-lookup"><span data-stu-id="4c713-2909">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2910">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2910">Format</span></span>

<span data-ttu-id="4c713-2911">12 dígitos separados por guiones</span><span class="sxs-lookup"><span data-stu-id="4c713-2911">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2912">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2912">Pattern</span></span>

<span data-ttu-id="4c713-2913">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-2913">12 digits:</span></span>
- <span data-ttu-id="4c713-2914">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2914">Four digits</span></span> 
- <span data-ttu-id="4c713-2915">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-2915">A hyphen</span></span> 
- <span data-ttu-id="4c713-2916">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-2916">Seven digits</span></span> 
- <span data-ttu-id="4c713-2917">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-2917">A hyphen</span></span> 
- <span data-ttu-id="4c713-2918">Un dígito</span><span class="sxs-lookup"><span data-stu-id="4c713-2918">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2919">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2919">Checksum</span></span>

<span data-ttu-id="4c713-2920">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2920">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2921">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2921">Definition</span></span>

<span data-ttu-id="4c713-2922">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2922">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2923">La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2923">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2924">Se encuentra una palabra clave de Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="4c713-2924">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2925">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2925">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="4c713-2926">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="4c713-2926">Keyword_philippines_id</span></span>

- <span data-ttu-id="4c713-2927">Id. universal unificado
</span><span class="sxs-lookup"><span data-stu-id="4c713-2927">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="4c713-2928">UMID</span><span class="sxs-lookup"><span data-stu-id="4c713-2928">UMID</span></span> 
- <span data-ttu-id="4c713-2929">Tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-2929">Identity Card</span></span> 
- <span data-ttu-id="4c713-2930">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="4c713-2930">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="4c713-2931">Tarjeta de identificación de Polonia</span><span class="sxs-lookup"><span data-stu-id="4c713-2931">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2932">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2932">Format</span></span>

<span data-ttu-id="4c713-2933">Tres letras y seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2933">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2934">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2934">Pattern</span></span>

<span data-ttu-id="4c713-2935">Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2935">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2936">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2936">Checksum</span></span>

<span data-ttu-id="4c713-2937">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2937">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2938">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2938">Definition</span></span>

<span data-ttu-id="4c713-2939">Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_polish_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2939">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="4c713-2940">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2940">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="4c713-2941">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2941">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2942">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2942">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="4c713-2943">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2943">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="4c713-2944">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="4c713-2944">Dowód osobisty</span></span>
- <span data-ttu-id="4c713-2945">Numerar dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="4c713-2945">Numer dowodu osobistego</span></span>
- <span data-ttu-id="4c713-2946">Nazwa i número dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="4c713-2946">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="4c713-2947">Nazwa i NR dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="4c713-2947">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="4c713-2948">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="4c713-2948">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="4c713-2949">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="4c713-2949">Dowód Tożsamości</span></span>
- <span data-ttu-id="4c713-2950">Dow.</span><span class="sxs-lookup"><span data-stu-id="4c713-2950">dow.</span></span> <span data-ttu-id="4c713-2951">MacOS.</span><span class="sxs-lookup"><span data-stu-id="4c713-2951">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="4c713-2952">Identificación nacional de Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="4c713-2952">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2953">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2953">Format</span></span>

<span data-ttu-id="4c713-2954">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2954">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2955">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2955">Pattern</span></span>

<span data-ttu-id="4c713-2956">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-2956">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2957">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2957">Checksum</span></span>

<span data-ttu-id="4c713-2958">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2958">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2959">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2959">Definition</span></span>

<span data-ttu-id="4c713-2960">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2960">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2961">La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2961">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2962">Se encuentra una palabra clave de Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2962">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="4c713-2963">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2963">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2964">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2964">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="4c713-2965">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2965">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="4c713-2966">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="4c713-2966">Nr PESEL</span></span>
- <span data-ttu-id="4c713-2967">PESEL</span><span class="sxs-lookup"><span data-stu-id="4c713-2967">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="4c713-2968">Pasaporte de Polonia</span><span class="sxs-lookup"><span data-stu-id="4c713-2968">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2969">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2969">Format</span></span>

<span data-ttu-id="4c713-2970">Dos letras y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2970">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2971">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2971">Pattern</span></span>

<span data-ttu-id="4c713-2972">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2972">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2973">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2973">Checksum</span></span>

<span data-ttu-id="4c713-2974">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-2974">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2975">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2975">Definition</span></span>

<span data-ttu-id="4c713-2976">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2976">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2977">La función Func_polish_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2977">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2978">Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-2978">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="4c713-2979">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-2979">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-2980">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2980">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="4c713-2981">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="4c713-2981">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="4c713-2982">Números paszportu</span><span class="sxs-lookup"><span data-stu-id="4c713-2982">Numer paszportu</span></span>
- <span data-ttu-id="4c713-2983">Nº.</span><span class="sxs-lookup"><span data-stu-id="4c713-2983">Nr.</span></span> <span data-ttu-id="4c713-2984">Paszportu</span><span class="sxs-lookup"><span data-stu-id="4c713-2984">Paszportu</span></span>
- <span data-ttu-id="4c713-2985">Paszport</span><span class="sxs-lookup"><span data-stu-id="4c713-2985">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="4c713-2986">Número de tarjeta del ciudadano de Portugal</span><span class="sxs-lookup"><span data-stu-id="4c713-2986">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-2987">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-2987">Format</span></span>

<span data-ttu-id="4c713-2988">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2988">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-2989">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-2989">Pattern</span></span>

<span data-ttu-id="4c713-2990">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-2990">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-2991">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-2991">Checksum</span></span>

<span data-ttu-id="4c713-2992">No</span><span class="sxs-lookup"><span data-stu-id="4c713-2992">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-2993">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-2993">Definition</span></span>

<span data-ttu-id="4c713-2994">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-2994">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-2995">La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-2995">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-2996">Se encuentra una palabra clave de Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="4c713-2996">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-2997">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-2997">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="4c713-2998">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="4c713-2998">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="4c713-2999">Tarjeta del ciudadano</span><span class="sxs-lookup"><span data-stu-id="4c713-2999">Citizen Card</span></span>
- <span data-ttu-id="4c713-3000">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="4c713-3000">National ID Card</span></span>
- <span data-ttu-id="4c713-3001">CC</span><span class="sxs-lookup"><span data-stu-id="4c713-3001">CC</span></span>
- <span data-ttu-id="4c713-3002">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="4c713-3002">Cartão de Cidadão</span></span>
- <span data-ttu-id="4c713-3003">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="4c713-3003">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="4c713-3004">Identificación nacional de Arabia Saudí</span><span class="sxs-lookup"><span data-stu-id="4c713-3004">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3005">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3005">Format</span></span>

<span data-ttu-id="4c713-3006">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3006">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3007">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3007">Pattern</span></span>

<span data-ttu-id="4c713-3008">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-3008">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3009">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3009">Checksum</span></span>

<span data-ttu-id="4c713-3010">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3010">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3011">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3011">Definition</span></span>

<span data-ttu-id="4c713-3012">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3012">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3013">La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3013">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3014">Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="4c713-3014">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3015">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3015">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="4c713-3016">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="4c713-3016">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="4c713-3017">Identification Card</span><span class="sxs-lookup"><span data-stu-id="4c713-3017">Identification Card</span></span> 
- <span data-ttu-id="4c713-3018">I card number</span><span class="sxs-lookup"><span data-stu-id="4c713-3018">I card number</span></span> 
- <span data-ttu-id="4c713-3019">ID number</span><span class="sxs-lookup"><span data-stu-id="4c713-3019">ID number</span></span> 
- <span data-ttu-id="4c713-3020">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="4c713-3020">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="4c713-3021">Número de tarjeta de identidad de registro nacional (NRIC) de Singapur</span><span class="sxs-lookup"><span data-stu-id="4c713-3021">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3022">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3022">Format</span></span>

<span data-ttu-id="4c713-3023">Nueve letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3023">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3024">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3024">Pattern</span></span>

- <span data-ttu-id="4c713-3025">Nueve letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3025">Nine letters and digits:</span></span>
- <span data-ttu-id="4c713-3026">La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-3026">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-3027">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-3027">Seven digits</span></span> 
- <span data-ttu-id="4c713-3028">Un dígito de control alfabético</span><span class="sxs-lookup"><span data-stu-id="4c713-3028">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3029">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3029">Checksum</span></span>

<span data-ttu-id="4c713-3030">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3030">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3031">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3031">Definition</span></span>

<span data-ttu-id="4c713-3032">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3032">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3033">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3033">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3034">Se encuentra una palabra clave de Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="4c713-3034">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="4c713-3035">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3035">The checksum passes.</span></span>

<span data-ttu-id="4c713-3036">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3036">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3037">La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3037">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3038">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3038">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3039">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3039">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="4c713-3040">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="4c713-3040">Keyword_singapore_nric</span></span>

- <span data-ttu-id="4c713-3041">Tarjeta de identidad de registro nacional</span><span class="sxs-lookup"><span data-stu-id="4c713-3041">National Registration Identity Card</span></span> 
- <span data-ttu-id="4c713-3042">Número de tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-3042">Identity Card Number</span></span> 
- <span data-ttu-id="4c713-3043">NRIC</span><span class="sxs-lookup"><span data-stu-id="4c713-3043">NRIC</span></span> 
- <span data-ttu-id="4c713-3044">I</span><span class="sxs-lookup"><span data-stu-id="4c713-3044">IC</span></span> 
- <span data-ttu-id="4c713-3045">Número de identificación de extranjeros</span><span class="sxs-lookup"><span data-stu-id="4c713-3045">Foreign Identification Number</span></span> 
- <span data-ttu-id="4c713-3046">AC</span><span class="sxs-lookup"><span data-stu-id="4c713-3046">FIN</span></span> 
- <span data-ttu-id="4c713-3047">身份证</span><span class="sxs-lookup"><span data-stu-id="4c713-3047">身份证</span></span> 
- <span data-ttu-id="4c713-3048">身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-3048">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="4c713-3049">Número de identificación de Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="4c713-3049">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3050">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3050">Format</span></span>

<span data-ttu-id="4c713-3051">13 dígitos que pueden contener espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-3051">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3052">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3052">Pattern</span></span>

<span data-ttu-id="4c713-3053">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3053">13 digits:</span></span>
- <span data-ttu-id="4c713-3054">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-3054">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4c713-3055">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3055">Four digits</span></span> 
- <span data-ttu-id="4c713-3056">Un indicador de ciudadanía de un solo dígito </span><span class="sxs-lookup"><span data-stu-id="4c713-3056">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="4c713-3057">El dígito "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="4c713-3057">The digit "8" or "9"</span></span> 
- <span data-ttu-id="4c713-3058">Un dígito que es un dígito de suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3058">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3059">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3059">Checksum</span></span>

<span data-ttu-id="4c713-3060">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3061">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3061">Definition</span></span>

<span data-ttu-id="4c713-3062">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3063">La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3063">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3064">Se encuentra una palabra clave de Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-3064">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="4c713-3065">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3065">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3066">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3066">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="4c713-3067">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="4c713-3067">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="4c713-3068">tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="4c713-3068">Identity card</span></span>
- <span data-ttu-id="4c713-3069">ID</span><span class="sxs-lookup"><span data-stu-id="4c713-3069">ID</span></span>
- <span data-ttu-id="4c713-3070">Determinación</span><span class="sxs-lookup"><span data-stu-id="4c713-3070">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="4c713-3071">Número de registro de residente de Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="4c713-3071">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3072">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3072">Format</span></span>

<span data-ttu-id="4c713-3073">13 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="4c713-3073">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3074">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3074">Pattern</span></span>

<span data-ttu-id="4c713-3075">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3075">13 digits:</span></span>
- <span data-ttu-id="4c713-3076">Seis dígitos en el formato DDMMAA que son la fecha de nacimiento </span><span class="sxs-lookup"><span data-stu-id="4c713-3076">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4c713-3077">Un guión </span><span class="sxs-lookup"><span data-stu-id="4c713-3077">A hyphen</span></span> 
- <span data-ttu-id="4c713-3078">Un dígito determinado por el siglo y el sexo </span><span class="sxs-lookup"><span data-stu-id="4c713-3078">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="4c713-3079">Código de región de nacimiento de cuatro dígitos </span><span class="sxs-lookup"><span data-stu-id="4c713-3079">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="4c713-3080">Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos </span><span class="sxs-lookup"><span data-stu-id="4c713-3080">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="4c713-3081">Un dígito de control.</span><span class="sxs-lookup"><span data-stu-id="4c713-3081">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3082">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3082">Checksum</span></span>

<span data-ttu-id="4c713-3083">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3083">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3084">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3084">Definition</span></span>

<span data-ttu-id="4c713-3085">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3085">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3086">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3086">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3087">Se encuentra una palabra clave de Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-3087">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="4c713-3088">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3088">The checksum passes.</span></span>

<span data-ttu-id="4c713-3089">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3089">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3090">La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3090">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3091">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3091">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3092">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3092">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="4c713-3093">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="4c713-3093">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="4c713-3094">Tarjeta de id. nacional</span><span class="sxs-lookup"><span data-stu-id="4c713-3094">National ID card</span></span> 
- <span data-ttu-id="4c713-3095">Número de registro de ciudadano</span><span class="sxs-lookup"><span data-stu-id="4c713-3095">Citizen's Registration Number</span></span> 
- <span data-ttu-id="4c713-3096">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="4c713-3096">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="4c713-3097">RRN</span><span class="sxs-lookup"><span data-stu-id="4c713-3097">RRN</span></span> 
- <span data-ttu-id="4c713-3098">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="4c713-3098">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="4c713-3099">Número de seguridad social de España (NSS)</span><span class="sxs-lookup"><span data-stu-id="4c713-3099">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3100">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3100">Format</span></span>

<span data-ttu-id="4c713-3101">11 o 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3101">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3102">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3102">Pattern</span></span>

<span data-ttu-id="4c713-3103">11-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3103">11-12 digits:</span></span>
- <span data-ttu-id="4c713-3104">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3104">Two digits</span></span> 
- <span data-ttu-id="4c713-3105">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="4c713-3105">A forward slash (optional)</span></span> 
- <span data-ttu-id="4c713-3106">7-8 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3106">7-8 digits</span></span> 
- <span data-ttu-id="4c713-3107">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="4c713-3107">A forward slash (optional)</span></span> 
- <span data-ttu-id="4c713-3108">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3108">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3109">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3109">Checksum</span></span>

<span data-ttu-id="4c713-3110">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3110">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3111">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3111">Definition</span></span>

<span data-ttu-id="4c713-3112">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3112">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3113">La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3113">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3114">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3114">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3115">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3115">Keywords</span></span>

<span data-ttu-id="4c713-3116">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4c713-3116">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="4c713-3117">Cadena de conexión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c713-3117">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3118">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3118">Format</span></span>

<span data-ttu-id="4c713-3119">La cadena "User ID", "User ID", "UID" o "UserId" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c713-3119">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3120">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3120">Pattern</span></span>

- <span data-ttu-id="4c713-3121">La cadena "User ID", "User ID", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="4c713-3121">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="4c713-3122">Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-3122">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4c713-3123">La cadena "Password" o "pwd" donde "pwd" no está precedida por una letra minúscula.</span><span class="sxs-lookup"><span data-stu-id="4c713-3123">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="4c713-3124">Un signo igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-3124">An equal sign (=)</span></span>
- <span data-ttu-id="4c713-3125">Cualquier carácter que no sea un signo de dólar ($), un símbolo de porcentaje (%), un símbolo mayor que (>), un símbolo de arroba (@), Comillas ("), punto y coma (;), llave izquierda ([) o corchete de apertura ({)</span><span class="sxs-lookup"><span data-stu-id="4c713-3125">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="4c713-3126">Cualquier combinación de 7-128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="4c713-3126">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="4c713-3127">Un punto y coma (;) o comillas (")</span><span class="sxs-lookup"><span data-stu-id="4c713-3127">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3128">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3128">Checksum</span></span>

<span data-ttu-id="4c713-3129">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3129">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3130">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3130">Definition</span></span>

<span data-ttu-id="4c713-3131">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3132">La expresión regular CEP_Regex_SQLServerConnectionString encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3132">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3133">**No** se encuentra una palabra clave de CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="4c713-3133">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="4c713-3134">La expresión regular CEP_PasswordPlaceHolder no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3134">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3135">La expresión regular CEP_CommonExampleKeywords no \*\*\*\* encuentra contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3135">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3136">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3136">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="4c713-3137">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="4c713-3137">CEP_GlobalFilter</span></span>

- <span data-ttu-id="4c713-3138">Some-Password</span><span class="sxs-lookup"><span data-stu-id="4c713-3138">some-password</span></span>
- <span data-ttu-id="4c713-3139">somePassword</span><span class="sxs-lookup"><span data-stu-id="4c713-3139">somepassword</span></span>
- <span data-ttu-id="4c713-3140">secretPassword</span><span class="sxs-lookup"><span data-stu-id="4c713-3140">secretPassword</span></span>
- <span data-ttu-id="4c713-3141">AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="4c713-3141">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="4c713-3142">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="4c713-3142">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="4c713-3143">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-3143">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-3144">Password o pwd seguida de 0-2 espacios, un signo igual (=), 0-2 espacios y un asterisco (\*)--o--</span><span class="sxs-lookup"><span data-stu-id="4c713-3144">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="4c713-3145">Password o pwd seguida de:</span><span class="sxs-lookup"><span data-stu-id="4c713-3145">Password or pwd followed by:</span></span>
    - <span data-ttu-id="4c713-3146">Signo de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4c713-3146">Equal sign (=)</span></span>
    - <span data-ttu-id="4c713-3147">Símbolo menor que (<)</span><span class="sxs-lookup"><span data-stu-id="4c713-3147">Less than symbol (<)</span></span>
    - <span data-ttu-id="4c713-3148">Cualquier combinación de 1-200 caracteres que estén en mayúsculas o minúsculas, dígitos, un asterisco (\*), un guión (-), un subrayado (_) o un carácter de espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="4c713-3148">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="4c713-3149">Símbolo mayor que (>)</span><span class="sxs-lookup"><span data-stu-id="4c713-3149">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="4c713-3150">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4c713-3150">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4c713-3151">(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).</span><span class="sxs-lookup"><span data-stu-id="4c713-3151">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4c713-3152">contoso</span><span class="sxs-lookup"><span data-stu-id="4c713-3152">contoso</span></span>
- <span data-ttu-id="4c713-3153">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4c713-3153">fabrikam</span></span>
- <span data-ttu-id="4c713-3154">Northwind</span><span class="sxs-lookup"><span data-stu-id="4c713-3154">northwind</span></span>
- <span data-ttu-id="4c713-3155">entorno</span><span class="sxs-lookup"><span data-stu-id="4c713-3155">sandbox</span></span>
- <span data-ttu-id="4c713-3156">OneBox</span><span class="sxs-lookup"><span data-stu-id="4c713-3156">onebox</span></span>
- <span data-ttu-id="4c713-3157">localhost</span><span class="sxs-lookup"><span data-stu-id="4c713-3157">localhost</span></span>
- <span data-ttu-id="4c713-3158">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4c713-3158">127.0.0.1</span></span>
- <span data-ttu-id="4c713-3159">testacs.</span><span class="sxs-lookup"><span data-stu-id="4c713-3159">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-3160">Puerto</span><span class="sxs-lookup"><span data-stu-id="4c713-3160">com</span></span>
- <span data-ttu-id="4c713-3161">s-int.</span><span class="sxs-lookup"><span data-stu-id="4c713-3161">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4c713-3162">ADO.net</span><span class="sxs-lookup"><span data-stu-id="4c713-3162">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="4c713-3163">Identificación nacional de Suecia</span><span class="sxs-lookup"><span data-stu-id="4c713-3163">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3164">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3164">Format</span></span>

<span data-ttu-id="4c713-3165">10 o 12 dígitos y un delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="4c713-3165">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3166">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3166">Pattern</span></span>

<span data-ttu-id="4c713-3167">10 o 12 dígitos y un delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="4c713-3167">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="4c713-3168">2-4 dígitos (opcionales)</span><span class="sxs-lookup"><span data-stu-id="4c713-3168">2-4 digits (optional)</span></span> 
- <span data-ttu-id="4c713-3169">Seis dígitos en fecha de formato AAMMDD</span><span class="sxs-lookup"><span data-stu-id="4c713-3169">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="4c713-3170">Delimitador de "-" o "+" (opcional), más</span><span class="sxs-lookup"><span data-stu-id="4c713-3170">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="4c713-3171">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3171">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3172">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3172">Checksum</span></span>

<span data-ttu-id="4c713-3173">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3173">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3174">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3174">Definition</span></span>

<span data-ttu-id="4c713-3175">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3175">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3176">La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3176">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3177">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3177">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3178">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3178">Keywords</span></span>

<span data-ttu-id="4c713-3179">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3179">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="4c713-3180">Número de pasaporte de Suecia</span><span class="sxs-lookup"><span data-stu-id="4c713-3180">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3181">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3181">Format</span></span>

<span data-ttu-id="4c713-3182">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3182">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3183">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3183">Pattern</span></span>

<span data-ttu-id="4c713-3184">Ocho dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-3184">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3185">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3185">Checksum</span></span>

<span data-ttu-id="4c713-3186">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3186">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3187">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3187">Definition</span></span>

<span data-ttu-id="4c713-3188">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3188">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3189">La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3189">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3190">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-3190">One of the following is true:</span></span>
    - <span data-ttu-id="4c713-3191">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="4c713-3191">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="4c713-3192">Se encuentra una palabra clave de Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="4c713-3192">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3193">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3193">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="4c713-3194">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-3194">Keyword_sweden_passport</span></span>

- <span data-ttu-id="4c713-3195">visa requirements</span><span class="sxs-lookup"><span data-stu-id="4c713-3195">visa requirements</span></span> 
- <span data-ttu-id="4c713-3196">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="4c713-3196">Alien Registration Card</span></span> 
- <span data-ttu-id="4c713-3197">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="4c713-3197">Schengen visas</span></span> 
- <span data-ttu-id="4c713-3198">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="4c713-3198">Schengen visa</span></span> 
- <span data-ttu-id="4c713-3199">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="4c713-3199">Visa Processing</span></span> 
- <span data-ttu-id="4c713-3200">Visa Type</span><span class="sxs-lookup"><span data-stu-id="4c713-3200">Visa Type</span></span> 
- <span data-ttu-id="4c713-3201">Single Entry</span><span class="sxs-lookup"><span data-stu-id="4c713-3201">Single Entry</span></span> 
- <span data-ttu-id="4c713-3202">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="4c713-3202">Multiple Entry</span></span> 
- <span data-ttu-id="4c713-3203">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="4c713-3203">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="4c713-3204">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-3204">Keyword_passport</span></span>

- <span data-ttu-id="4c713-3205">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3205">Passport Number</span></span> 
- <span data-ttu-id="4c713-3206">Passport No</span><span class="sxs-lookup"><span data-stu-id="4c713-3206">Passport No</span></span> 
- <span data-ttu-id="4c713-3207">Passport #</span><span class="sxs-lookup"><span data-stu-id="4c713-3207">Passport #</span></span> 
- <span data-ttu-id="4c713-3208">Usuarios</span><span class="sxs-lookup"><span data-stu-id="4c713-3208">Passport#</span></span> 
- <span data-ttu-id="4c713-3209">PassportID</span><span class="sxs-lookup"><span data-stu-id="4c713-3209">PassportID</span></span> 
- <span data-ttu-id="4c713-3210">Passportno</span><span class="sxs-lookup"><span data-stu-id="4c713-3210">Passportno</span></span> 
- <span data-ttu-id="4c713-3211">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-3211">passportnumber</span></span> 
- <span data-ttu-id="4c713-3212">パスポート</span><span class="sxs-lookup"><span data-stu-id="4c713-3212">パスポート</span></span> 
- <span data-ttu-id="4c713-3213">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4c713-3213">パスポート番号</span></span> 
- <span data-ttu-id="4c713-3214">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4c713-3214">パスポートのNum</span></span> 
- <span data-ttu-id="4c713-3215">パスポート #</span><span class="sxs-lookup"><span data-stu-id="4c713-3215">パスポート＃</span></span> 
- <span data-ttu-id="4c713-3216">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4c713-3216">Numéro de passeport</span></span> 
- <span data-ttu-id="4c713-3217">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4c713-3217">Passeport n °</span></span> 
- <span data-ttu-id="4c713-3218">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4c713-3218">Passeport Non</span></span> 
- <span data-ttu-id="4c713-3219">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-3219">Passeport #</span></span> 
- <span data-ttu-id="4c713-3220">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-3220">Passeport#</span></span> 
- <span data-ttu-id="4c713-3221">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4c713-3221">PasseportNon</span></span> 
- <span data-ttu-id="4c713-3222">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4c713-3222">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="4c713-3223">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="4c713-3223">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3224">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3224">Format</span></span>

<span data-ttu-id="4c713-3225">Cuatro letras seguidas de 5 a 31 letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3225">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3226">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3226">Pattern</span></span>

<span data-ttu-id="4c713-3227">Cuatro letras seguidas de 5-31 letras o dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3227">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="4c713-3228">Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-3228">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-3229">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="4c713-3229">An optional space</span></span> 
- <span data-ttu-id="4c713-3230">4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))</span><span class="sxs-lookup"><span data-stu-id="4c713-3230">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="4c713-3231">Un espacio opcional</span><span class="sxs-lookup"><span data-stu-id="4c713-3231">An optional space</span></span> 
- <span data-ttu-id="4c713-3232">1-3 letras o dígitos (el resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="4c713-3232">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3233">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3233">Checksum</span></span>

<span data-ttu-id="4c713-3234">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3234">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3235">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3235">Definition</span></span>

<span data-ttu-id="4c713-3236">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3236">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3237">La expresión regular Regex_swift encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3237">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3238">Se encuentra una palabra clave de Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="4c713-3238">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3239">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3239">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="4c713-3240">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="4c713-3240">Keyword_swift</span></span>

- <span data-ttu-id="4c713-3241">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="4c713-3241">international organization for standardization 9362</span></span> 
- <span data-ttu-id="4c713-3242">iso 9362</span><span class="sxs-lookup"><span data-stu-id="4c713-3242">iso 9362</span></span> 
- <span data-ttu-id="4c713-3243">iso9362</span><span class="sxs-lookup"><span data-stu-id="4c713-3243">iso9362</span></span> 
- <span data-ttu-id="4c713-3244">rápido\#</span><span class="sxs-lookup"><span data-stu-id="4c713-3244">swift\#</span></span> 
- <span data-ttu-id="4c713-3245">Swiftcode</span><span class="sxs-lookup"><span data-stu-id="4c713-3245">swiftcode</span></span> 
- <span data-ttu-id="4c713-3246">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-3246">swiftnumber</span></span> 
- <span data-ttu-id="4c713-3247">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-3247">swiftroutingnumber</span></span> 
- <span data-ttu-id="4c713-3248">swift code</span><span class="sxs-lookup"><span data-stu-id="4c713-3248">swift code</span></span> 
- <span data-ttu-id="4c713-3249">swift number #</span><span class="sxs-lookup"><span data-stu-id="4c713-3249">swift number #</span></span> 
- <span data-ttu-id="4c713-3250">swift routing number</span><span class="sxs-lookup"><span data-stu-id="4c713-3250">swift routing number</span></span> 
- <span data-ttu-id="4c713-3251">bic number</span><span class="sxs-lookup"><span data-stu-id="4c713-3251">bic number</span></span> 
- <span data-ttu-id="4c713-3252">bic code</span><span class="sxs-lookup"><span data-stu-id="4c713-3252">bic code</span></span> 
- <span data-ttu-id="4c713-3253">BIC\#</span><span class="sxs-lookup"><span data-stu-id="4c713-3253">bic \#</span></span> 
- <span data-ttu-id="4c713-3254">BIC\#</span><span class="sxs-lookup"><span data-stu-id="4c713-3254">bic\#</span></span> 
- <span data-ttu-id="4c713-3255">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="4c713-3255">bank identifier code</span></span> 
- <span data-ttu-id="4c713-3256">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="4c713-3256">標準化9362</span></span> 
- <span data-ttu-id="4c713-3257">迅速 #</span><span class="sxs-lookup"><span data-stu-id="4c713-3257">迅速＃</span></span> 
- <span data-ttu-id="4c713-3258">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="4c713-3258">SWIFTコード</span></span> 
- <span data-ttu-id="4c713-3259">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="4c713-3259">SWIFT番号</span></span> 
- <span data-ttu-id="4c713-3260">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="4c713-3260">迅速なルーティング番号</span></span> 
- <span data-ttu-id="4c713-3261">BIC番号</span><span class="sxs-lookup"><span data-stu-id="4c713-3261">BIC番号</span></span> 
- <span data-ttu-id="4c713-3262">BICコード</span><span class="sxs-lookup"><span data-stu-id="4c713-3262">BICコード</span></span> 
- <span data-ttu-id="4c713-3263">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="4c713-3263">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="4c713-3264">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="4c713-3264">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="4c713-3265">rápido\#</span><span class="sxs-lookup"><span data-stu-id="4c713-3265">rapide \#</span></span> 
- <span data-ttu-id="4c713-3266">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="4c713-3266">code SWIFT</span></span> 
- <span data-ttu-id="4c713-3267">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="4c713-3267">le numéro de swift</span></span> 
- <span data-ttu-id="4c713-3268">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="4c713-3268">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="4c713-3269">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="4c713-3269">le numéro BIC</span></span> 
- <span data-ttu-id="4c713-3270">\#BIC</span><span class="sxs-lookup"><span data-stu-id="4c713-3270">\# BIC</span></span> 
- <span data-ttu-id="4c713-3271">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="4c713-3271">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="4c713-3272">Identificación nacional de Taiwán</span><span class="sxs-lookup"><span data-stu-id="4c713-3272">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3273">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3273">Format</span></span>

<span data-ttu-id="4c713-3274">Una letra  seguida de nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3274">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3275">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3275">Pattern</span></span>

<span data-ttu-id="4c713-3276">Una letra seguida de nueve dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3276">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="4c713-3277">Una letra (en inglés, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-3277">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="4c713-3278">El dígito "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="4c713-3278">The digit "1" or "2"</span></span> 
- <span data-ttu-id="4c713-3279">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3279">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3280">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3280">Checksum</span></span>

<span data-ttu-id="4c713-3281">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3281">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3282">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3282">Definition</span></span>

<span data-ttu-id="4c713-3283">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3283">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3284">La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3284">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3285">Se encuentra una palabra clave de Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="4c713-3285">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="4c713-3286">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3286">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3287">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3287">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="4c713-3288">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="4c713-3288">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="4c713-3289">身份證字號</span><span class="sxs-lookup"><span data-stu-id="4c713-3289">身份證字號</span></span> 
- <span data-ttu-id="4c713-3290">身份證</span><span class="sxs-lookup"><span data-stu-id="4c713-3290">身份證</span></span> 
- <span data-ttu-id="4c713-3291">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="4c713-3291">身份證號碼</span></span> 
- <span data-ttu-id="4c713-3292">身份證號</span><span class="sxs-lookup"><span data-stu-id="4c713-3292">身份證號</span></span> 
- <span data-ttu-id="4c713-3293">身分證字號</span><span class="sxs-lookup"><span data-stu-id="4c713-3293">身分證字號</span></span> 
- <span data-ttu-id="4c713-3294">身分證</span><span class="sxs-lookup"><span data-stu-id="4c713-3294">身分證</span></span> 
- <span data-ttu-id="4c713-3295">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="4c713-3295">身分證號碼</span></span> 
- <span data-ttu-id="4c713-3296">身份證號</span><span class="sxs-lookup"><span data-stu-id="4c713-3296">身份證號</span></span> 
- <span data-ttu-id="4c713-3297">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="4c713-3297">身分證統一編號</span></span> 
- <span data-ttu-id="4c713-3298">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="4c713-3298">國民身分證統一編號</span></span> 
- <span data-ttu-id="4c713-3299">簽名</span><span class="sxs-lookup"><span data-stu-id="4c713-3299">簽名</span></span> 
- <span data-ttu-id="4c713-3300">蓋章</span><span class="sxs-lookup"><span data-stu-id="4c713-3300">蓋章</span></span> 
- <span data-ttu-id="4c713-3301">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="4c713-3301">簽名或蓋章</span></span> 
- <span data-ttu-id="4c713-3302">簽章</span><span class="sxs-lookup"><span data-stu-id="4c713-3302">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="4c713-3303">	Número de pasaporte de Taiwán</span><span class="sxs-lookup"><span data-stu-id="4c713-3303">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3304">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3304">Format</span></span>

- <span data-ttu-id="4c713-3305">Número de pasaporte biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3305">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="4c713-3306">Número de pasaporte no biométrico: nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3306">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3307">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3307">Pattern</span></span>
<span data-ttu-id="4c713-3308">Número de pasaporte biométrico:</span><span class="sxs-lookup"><span data-stu-id="4c713-3308">Biometric passport number:</span></span>
- <span data-ttu-id="4c713-3309">El dígito "3" </span><span class="sxs-lookup"><span data-stu-id="4c713-3309">The digit "3"</span></span> 
- <span data-ttu-id="4c713-3310">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3310">Eight digits</span></span>

<span data-ttu-id="4c713-3311">Número de pasaporte no biométrico:</span><span class="sxs-lookup"><span data-stu-id="4c713-3311">Non-biometric passport number:</span></span>
- <span data-ttu-id="4c713-3312">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3312">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3313">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3313">Checksum</span></span>

<span data-ttu-id="4c713-3314">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3314">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3315">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3315">Definition</span></span>

<span data-ttu-id="4c713-3316">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3317">La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3317">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3318">Se encuentra una palabra clave de Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="4c713-3318">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3319">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3319">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="4c713-3320">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-3320">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="4c713-3321">Número de pasaporte ROC</span><span class="sxs-lookup"><span data-stu-id="4c713-3321">ROC passport number</span></span> 
- <span data-ttu-id="4c713-3322">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="4c713-3322">Passport number</span></span> 
- <span data-ttu-id="4c713-3323">Núm. pasaporte
</span><span class="sxs-lookup"><span data-stu-id="4c713-3323">Passport no</span></span> 
- <span data-ttu-id="4c713-3324">N.ro pasaporte</span><span class="sxs-lookup"><span data-stu-id="4c713-3324">Passport Num</span></span> 
- <span data-ttu-id="4c713-3325">N.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="4c713-3325">Passport #</span></span> 
- <span data-ttu-id="4c713-3326">护照</span><span class="sxs-lookup"><span data-stu-id="4c713-3326">护照</span></span> 
- <span data-ttu-id="4c713-3327">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="4c713-3327">中華民國護照</span></span> 
- <span data-ttu-id="4c713-3328">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="4c713-3328">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="4c713-3329">Número de certificado de residente (ARC/TARC) de Taiwán</span><span class="sxs-lookup"><span data-stu-id="4c713-3329">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3330">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3330">Format</span></span>

<span data-ttu-id="4c713-3331">10 letras y dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3331">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3332">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3332">Pattern</span></span>

<span data-ttu-id="4c713-3333">10 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3333">10 letters and digits:</span></span>
- <span data-ttu-id="4c713-3334">Dos letras (no distingue entre mayúsculas y minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4c713-3334">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="4c713-3335">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3335">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3336">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3336">Checksum</span></span>

<span data-ttu-id="4c713-3337">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3337">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3338">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3338">Definition</span></span>

<span data-ttu-id="4c713-3339">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3340">La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3340">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3341">Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="4c713-3341">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3342">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3342">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="4c713-3343">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="4c713-3343">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="4c713-3344">Certificado de residente</span><span class="sxs-lookup"><span data-stu-id="4c713-3344">Resident Certificate</span></span> 
- <span data-ttu-id="4c713-3345">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="4c713-3345">Resident Cert</span></span> 
- <span data-ttu-id="4c713-3346">Cert. residente
</span><span class="sxs-lookup"><span data-stu-id="4c713-3346">Resident Cert.</span></span> 
- <span data-ttu-id="4c713-3347">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="4c713-3347">Identification card</span></span> 
- <span data-ttu-id="4c713-3348">Certificado de residente extranjero</span><span class="sxs-lookup"><span data-stu-id="4c713-3348">Alien Resident Certificate</span></span> 
- <span data-ttu-id="4c713-3349">ARCOS</span><span class="sxs-lookup"><span data-stu-id="4c713-3349">ARC</span></span> 
- <span data-ttu-id="4c713-3350">Certificado de residente en el área de Taiwán</span><span class="sxs-lookup"><span data-stu-id="4c713-3350">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="4c713-3351">TARC</span><span class="sxs-lookup"><span data-stu-id="4c713-3351">TARC</span></span> 
- <span data-ttu-id="4c713-3352">居留證</span><span class="sxs-lookup"><span data-stu-id="4c713-3352">居留證</span></span> 
- <span data-ttu-id="4c713-3353">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="4c713-3353">外僑居留證</span></span> 
- <span data-ttu-id="4c713-3354">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="4c713-3354">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="4c713-3355">Código de identificación de población tailandesa</span><span class="sxs-lookup"><span data-stu-id="4c713-3355">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3356">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3356">Format</span></span>

<span data-ttu-id="4c713-3357">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3357">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3358">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3358">Pattern</span></span>

<span data-ttu-id="4c713-3359">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3359">13 digits:</span></span>
- <span data-ttu-id="4c713-3360">El primer dígito no es 0 ni 9</span><span class="sxs-lookup"><span data-stu-id="4c713-3360">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="4c713-3361">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3361">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3362">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3362">Checksum</span></span>

<span data-ttu-id="4c713-3363">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3363">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3364">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3364">Definition</span></span>

<span data-ttu-id="4c713-3365">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3365">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3366">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3366">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3367">Se encuentra una palabra clave de Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="4c713-3367">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="4c713-3368">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3368">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3369">La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3369">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3370">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3370">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="4c713-3371">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="4c713-3371">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="4c713-3372">Número de id.</span><span class="sxs-lookup"><span data-stu-id="4c713-3372">ID Number</span></span>
- <span data-ttu-id="4c713-3373">Número de identificación</span><span class="sxs-lookup"><span data-stu-id="4c713-3373">Identification Number</span></span>
- <span data-ttu-id="4c713-3374">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4c713-3374">บัตรประชาชน</span></span>
- <span data-ttu-id="4c713-3375">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4c713-3375">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="4c713-3376">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4c713-3376">บัตรประชาชน</span></span>
- <span data-ttu-id="4c713-3377">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4c713-3377">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="4c713-3378">Número de identificación nacional de Turco</span><span class="sxs-lookup"><span data-stu-id="4c713-3378">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3379">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3379">Format</span></span>

<span data-ttu-id="4c713-3380">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3380">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3381">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3381">Pattern</span></span>

<span data-ttu-id="4c713-3382">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3382">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3383">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3383">Checksum</span></span>

<span data-ttu-id="4c713-3384">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3384">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3385">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3385">Definition</span></span>

<span data-ttu-id="4c713-3386">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3386">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3387">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3387">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3388">Se encuentra una palabra clave de Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="4c713-3388">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="4c713-3389">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3390">La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3390">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3391">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3391">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="4c713-3392">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="4c713-3392">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="4c713-3393">TC Kimlik no</span><span class="sxs-lookup"><span data-stu-id="4c713-3393">TC Kimlik No</span></span>
- <span data-ttu-id="4c713-3394">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="4c713-3394">TC Kimlik numarası</span></span>
- <span data-ttu-id="4c713-3395">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="4c713-3395">Vatandaşlık numarası</span></span>
- <span data-ttu-id="4c713-3396">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="4c713-3396">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="4c713-p142">Número de licencia de conductor de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4c713-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3399">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3399">Format</span></span>

<span data-ttu-id="4c713-3400">Combinación de 18 letras y dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="4c713-3400">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3401">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3401">Pattern</span></span>

<span data-ttu-id="4c713-3402">18 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3402">18 letters and digits:</span></span>
- <span data-ttu-id="4c713-3403">Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="4c713-3403">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="4c713-3404">Un dígito</span><span class="sxs-lookup"><span data-stu-id="4c713-3404">One digit</span></span> 
- <span data-ttu-id="4c713-3405">Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-3405">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="4c713-3406">Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra</span><span class="sxs-lookup"><span data-stu-id="4c713-3406">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="4c713-3407">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3407">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3408">Checksum</span></span>

<span data-ttu-id="4c713-3409">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3409">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3410">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3410">Definition</span></span>

<span data-ttu-id="4c713-3411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3412">La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3412">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3413">Se encuentra una palabra clave de Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="4c713-3413">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="4c713-3414">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3414">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3415">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3415">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="4c713-3416">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4c713-3416">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="4c713-3417">DVLA</span><span class="sxs-lookup"><span data-stu-id="4c713-3417">DVLA</span></span> 
- <span data-ttu-id="4c713-3418">light vans</span><span class="sxs-lookup"><span data-stu-id="4c713-3418">light vans</span></span> 
- <span data-ttu-id="4c713-3419">quadbikes</span><span class="sxs-lookup"><span data-stu-id="4c713-3419">quadbikes</span></span> 
- <span data-ttu-id="4c713-3420">motor cars</span><span class="sxs-lookup"><span data-stu-id="4c713-3420">motor cars</span></span> 
- <span data-ttu-id="4c713-3421">125cc</span><span class="sxs-lookup"><span data-stu-id="4c713-3421">125cc</span></span> 
- <span data-ttu-id="4c713-3422">sidecar</span><span class="sxs-lookup"><span data-stu-id="4c713-3422">sidecar</span></span> 
- <span data-ttu-id="4c713-3423">Tricycles</span><span class="sxs-lookup"><span data-stu-id="4c713-3423">tricycles</span></span> 
- <span data-ttu-id="4c713-3424">sidecar</span><span class="sxs-lookup"><span data-stu-id="4c713-3424">motorcycles</span></span> 
- <span data-ttu-id="4c713-3425">photocard licence</span><span class="sxs-lookup"><span data-stu-id="4c713-3425">photocard licence</span></span> 
- <span data-ttu-id="4c713-3426">learner drivers</span><span class="sxs-lookup"><span data-stu-id="4c713-3426">learner drivers</span></span> 
- <span data-ttu-id="4c713-3427">licence holder</span><span class="sxs-lookup"><span data-stu-id="4c713-3427">licence holder</span></span> 
- <span data-ttu-id="4c713-3428">licence holders</span><span class="sxs-lookup"><span data-stu-id="4c713-3428">licence holders</span></span> 
- <span data-ttu-id="4c713-3429">driving licences</span><span class="sxs-lookup"><span data-stu-id="4c713-3429">driving licences</span></span> 
- <span data-ttu-id="4c713-3430">driving licence</span><span class="sxs-lookup"><span data-stu-id="4c713-3430">driving licence</span></span> 
- <span data-ttu-id="4c713-3431">dual control car</span><span class="sxs-lookup"><span data-stu-id="4c713-3431">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="4c713-p143">Número de registro electoral de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4c713-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3434">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3434">Format</span></span>

<span data-ttu-id="4c713-3435">Dos letras seguidas por entre 1 y 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3435">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3436">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3436">Pattern</span></span>

<span data-ttu-id="4c713-3437">Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números</span><span class="sxs-lookup"><span data-stu-id="4c713-3437">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3438">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3438">Checksum</span></span>

<span data-ttu-id="4c713-3439">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3439">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3440">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3440">Definition</span></span>

<span data-ttu-id="4c713-3441">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3441">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3442">La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3442">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3443">Se encuentra una palabra clave de Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="4c713-3443">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3444">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3444">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="4c713-3445">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="4c713-3445">Keyword_uk_electoral</span></span>

- <span data-ttu-id="4c713-3446">council nomination</span><span class="sxs-lookup"><span data-stu-id="4c713-3446">council nomination</span></span> 
- <span data-ttu-id="4c713-3447">nomination form</span><span class="sxs-lookup"><span data-stu-id="4c713-3447">nomination form</span></span> 
- <span data-ttu-id="4c713-3448">electoral register</span><span class="sxs-lookup"><span data-stu-id="4c713-3448">electoral register</span></span> 
- <span data-ttu-id="4c713-3449">electoral roll</span><span class="sxs-lookup"><span data-stu-id="4c713-3449">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="4c713-p144">Número de Servicio Nacional de Salud de Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4c713-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3452">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3452">Format</span></span>

<span data-ttu-id="4c713-3453">De 10 a 17 dígitos separados por espacios</span><span class="sxs-lookup"><span data-stu-id="4c713-3453">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3454">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3454">Pattern</span></span>

<span data-ttu-id="4c713-3455">10-17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4c713-3455">10-17 digits:</span></span>
- <span data-ttu-id="4c713-3456">3 o 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3456">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="4c713-3457">Un espacio</span><span class="sxs-lookup"><span data-stu-id="4c713-3457">A space</span></span> 
- <span data-ttu-id="4c713-3458">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3458">Three digits</span></span> 
- <span data-ttu-id="4c713-3459">Un espacio</span><span class="sxs-lookup"><span data-stu-id="4c713-3459">A space</span></span> 
- <span data-ttu-id="4c713-3460">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3460">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3461">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3461">Checksum</span></span>

<span data-ttu-id="4c713-3462">Sí</span><span class="sxs-lookup"><span data-stu-id="4c713-3462">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3463">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3463">Definition</span></span>

<span data-ttu-id="4c713-3464">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3464">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3465">La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3465">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3466">Una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-3466">One of the following is true:</span></span>
    - <span data-ttu-id="4c713-3467">Se encuentra una palabra clave de Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="4c713-3467">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="4c713-3468">Se encuentra una palabra clave de Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="4c713-3468">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="4c713-3469">Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="4c713-3469">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="4c713-3470">Se supera la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4c713-3470">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3471">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3471">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="4c713-3472">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="4c713-3472">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="4c713-3473">national health service</span><span class="sxs-lookup"><span data-stu-id="4c713-3473">national health service</span></span> 
- <span data-ttu-id="4c713-3474">del NHS del</span><span class="sxs-lookup"><span data-stu-id="4c713-3474">nhs</span></span> 
- <span data-ttu-id="4c713-3475">health services authority</span><span class="sxs-lookup"><span data-stu-id="4c713-3475">health services authority</span></span> 
- <span data-ttu-id="4c713-3476">health authority</span><span class="sxs-lookup"><span data-stu-id="4c713-3476">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="4c713-3477">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="4c713-3477">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="4c713-3478">patient id</span><span class="sxs-lookup"><span data-stu-id="4c713-3478">patient id</span></span> 
- <span data-ttu-id="4c713-3479">patient identification</span><span class="sxs-lookup"><span data-stu-id="4c713-3479">patient identification</span></span> 
- <span data-ttu-id="4c713-3480">patient no</span><span class="sxs-lookup"><span data-stu-id="4c713-3480">patient no</span></span> 
- <span data-ttu-id="4c713-3481">patient number</span><span class="sxs-lookup"><span data-stu-id="4c713-3481">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="4c713-3482">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="4c713-3482">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="4c713-3483">EON</span><span class="sxs-lookup"><span data-stu-id="4c713-3483">GP</span></span> 
- <span data-ttu-id="4c713-3484">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="4c713-3484">DOB</span></span> 
- <span data-ttu-id="4c713-3485">D. O. B</span><span class="sxs-lookup"><span data-stu-id="4c713-3485">D.O.B</span></span> 
- <span data-ttu-id="4c713-3486">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-3486">Date of Birth</span></span> 
- <span data-ttu-id="4c713-3487">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-3487">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="4c713-p145">Número de seguro nacional de Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="4c713-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3490">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3490">Format</span></span>

<span data-ttu-id="4c713-3491">7 caracteres o 9 caracteres separados por espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="4c713-3491">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3492">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3492">Pattern</span></span>

<span data-ttu-id="4c713-3493">Dos patrones posibles:</span><span class="sxs-lookup"><span data-stu-id="4c713-3493">Two possible patterns:</span></span>

- <span data-ttu-id="4c713-3494">Dos letras (los NINO válidos usan solo caracteres determinados en este prefijo, que valida este patrón; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-3494">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="4c713-3495">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3495">Six digits</span></span>
- <span data-ttu-id="4c713-3496">' A ', ' B ', ' C ' o ' T ' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4c713-3496">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="4c713-3497">O</span><span class="sxs-lookup"><span data-stu-id="4c713-3497">OR</span></span>

- <span data-ttu-id="4c713-3498">Dos letras</span><span class="sxs-lookup"><span data-stu-id="4c713-3498">Two letters</span></span>
- <span data-ttu-id="4c713-3499">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-3499">A space or dash</span></span>
- <span data-ttu-id="4c713-3500">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3500">Two digits</span></span>
- <span data-ttu-id="4c713-3501">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-3501">A space or dash</span></span>
- <span data-ttu-id="4c713-3502">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3502">Two digits</span></span>
- <span data-ttu-id="4c713-3503">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-3503">A space or dash</span></span>
- <span data-ttu-id="4c713-3504">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3504">Two digits</span></span>
- <span data-ttu-id="4c713-3505">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-3505">A space or dash</span></span>
- <span data-ttu-id="4c713-3506">' A ', ' B ', ' C ' o ' T '</span><span class="sxs-lookup"><span data-stu-id="4c713-3506">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3507">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3507">Checksum</span></span>

<span data-ttu-id="4c713-3508">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3508">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3509">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3509">Definition</span></span>

<span data-ttu-id="4c713-3510">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3511">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3511">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3512">Se encuentra una palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="4c713-3512">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="4c713-3513">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3513">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3514">La función Func_uk_nino encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3514">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3515">No se encuentra ninguna palabra clave de Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="4c713-3515">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3516">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3516">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="4c713-3517">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="4c713-3517">Keyword_uk_nino</span></span>

- <span data-ttu-id="4c713-3518">national insurance number</span><span class="sxs-lookup"><span data-stu-id="4c713-3518">national insurance number</span></span> 
- <span data-ttu-id="4c713-3519">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="4c713-3519">national insurance contributions</span></span> 
- <span data-ttu-id="4c713-3520">protection act</span><span class="sxs-lookup"><span data-stu-id="4c713-3520">protection act</span></span> 
- <span data-ttu-id="4c713-3521">Pensión</span><span class="sxs-lookup"><span data-stu-id="4c713-3521">insurance</span></span> 
- <span data-ttu-id="4c713-3522">social security number</span><span class="sxs-lookup"><span data-stu-id="4c713-3522">social security number</span></span> 
- <span data-ttu-id="4c713-3523">insurance application</span><span class="sxs-lookup"><span data-stu-id="4c713-3523">insurance application</span></span> 
- <span data-ttu-id="4c713-3524">medical application</span><span class="sxs-lookup"><span data-stu-id="4c713-3524">medical application</span></span> 
- <span data-ttu-id="4c713-3525">social insurance</span><span class="sxs-lookup"><span data-stu-id="4c713-3525">social insurance</span></span> 
- <span data-ttu-id="4c713-3526">medical attention</span><span class="sxs-lookup"><span data-stu-id="4c713-3526">medical attention</span></span> 
- <span data-ttu-id="4c713-3527">social security</span><span class="sxs-lookup"><span data-stu-id="4c713-3527">social security</span></span> 
- <span data-ttu-id="4c713-3528">great britain</span><span class="sxs-lookup"><span data-stu-id="4c713-3528">great britain</span></span> 
- <span data-ttu-id="4c713-3529">Pensión</span><span class="sxs-lookup"><span data-stu-id="4c713-3529">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="4c713-p146">Número de pasaporte EE. UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4c713-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3532">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3532">Format</span></span>

<span data-ttu-id="4c713-3533">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3534">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3534">Pattern</span></span>

<span data-ttu-id="4c713-3535">Nueve dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-3535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3536">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3536">Checksum</span></span>

<span data-ttu-id="4c713-3537">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3537">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3538">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3538">Definition</span></span>

<span data-ttu-id="4c713-3539">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3540">La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3540">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3541">Se encuentra una palabra clave de Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="4c713-3541">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3542">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3542">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="4c713-3543">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4c713-3543">Keyword_passport</span></span>

- <span data-ttu-id="4c713-3544">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3544">Passport Number</span></span> 
- <span data-ttu-id="4c713-3545">Passport No</span><span class="sxs-lookup"><span data-stu-id="4c713-3545">Passport No</span></span> 
- <span data-ttu-id="4c713-3546">Passport #</span><span class="sxs-lookup"><span data-stu-id="4c713-3546">Passport #</span></span> 
- <span data-ttu-id="4c713-3547">Usuarios</span><span class="sxs-lookup"><span data-stu-id="4c713-3547">Passport#</span></span> 
- <span data-ttu-id="4c713-3548">PassportID</span><span class="sxs-lookup"><span data-stu-id="4c713-3548">PassportID</span></span> 
- <span data-ttu-id="4c713-3549">Passportno</span><span class="sxs-lookup"><span data-stu-id="4c713-3549">Passportno</span></span> 
- <span data-ttu-id="4c713-3550">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4c713-3550">passportnumber</span></span> 
- <span data-ttu-id="4c713-3551">パスポート</span><span class="sxs-lookup"><span data-stu-id="4c713-3551">パスポート</span></span> 
- <span data-ttu-id="4c713-3552">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4c713-3552">パスポート番号</span></span> 
- <span data-ttu-id="4c713-3553">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4c713-3553">パスポートのNum</span></span> 
- <span data-ttu-id="4c713-3554">パスポート #</span><span class="sxs-lookup"><span data-stu-id="4c713-3554">パスポート＃</span></span> 
- <span data-ttu-id="4c713-3555">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4c713-3555">Numéro de passeport</span></span> 
- <span data-ttu-id="4c713-3556">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4c713-3556">Passeport n °</span></span> 
- <span data-ttu-id="4c713-3557">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4c713-3557">Passeport Non</span></span> 
- <span data-ttu-id="4c713-3558">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-3558">Passeport #</span></span> 
- <span data-ttu-id="4c713-3559">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4c713-3559">Passeport#</span></span> 
- <span data-ttu-id="4c713-3560">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4c713-3560">PasseportNon</span></span> 
- <span data-ttu-id="4c713-3561">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4c713-3561">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="4c713-3562">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="4c713-3562">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3563">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3563">Format</span></span>

<span data-ttu-id="4c713-3564">Entre 8 y 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3564">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3565">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3565">Pattern</span></span>

<span data-ttu-id="4c713-3566">Entre 8 y 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4c713-3566">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3567">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3567">Checksum</span></span>

<span data-ttu-id="4c713-3568">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3568">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3569">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3569">Definition</span></span>

<span data-ttu-id="4c713-3570">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3571">La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3571">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3572">Se encuentra una palabra clave de Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="4c713-3572">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4c713-3573">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3573">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="4c713-3574">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="4c713-3574">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="4c713-3575">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3575">Checking Account Number</span></span> 
- <span data-ttu-id="4c713-3576">Checking Account</span><span class="sxs-lookup"><span data-stu-id="4c713-3576">Checking Account</span></span> 
- <span data-ttu-id="4c713-3577">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-3577">Checking Account #</span></span> 
- <span data-ttu-id="4c713-3578">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3578">Checking Acct Number</span></span> 
- <span data-ttu-id="4c713-3579">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-3579">Checking Acct #</span></span> 
- <span data-ttu-id="4c713-3580">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3580">Checking Acct No.</span></span> 
- <span data-ttu-id="4c713-3581">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3581">Checking Account No.</span></span> 
- <span data-ttu-id="4c713-3582">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3582">Bank Account Number</span></span> 
- <span data-ttu-id="4c713-3583">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-3583">Bank Account #</span></span> 
- <span data-ttu-id="4c713-3584">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3584">Bank Acct Number</span></span> 
- <span data-ttu-id="4c713-3585">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-3585">Bank Acct #</span></span> 
- <span data-ttu-id="4c713-3586">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3586">Bank Acct No.</span></span> 
- <span data-ttu-id="4c713-3587">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3587">Bank Account No.</span></span> 
- <span data-ttu-id="4c713-3588">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3588">Savings Account Number</span></span> 
- <span data-ttu-id="4c713-3589">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="4c713-3589">Savings Account.</span></span> 
- <span data-ttu-id="4c713-3590">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-3590">Savings Account #</span></span> 
- <span data-ttu-id="4c713-3591">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3591">Savings Acct Number</span></span> 
- <span data-ttu-id="4c713-3592">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-3592">Savings Acct #</span></span> 
- <span data-ttu-id="4c713-3593">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3593">Savings Acct No.</span></span> 
- <span data-ttu-id="4c713-3594">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3594">Savings Account No.</span></span> 
- <span data-ttu-id="4c713-3595">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3595">Debit Account Number</span></span> 
- <span data-ttu-id="4c713-3596">Debit Account</span><span class="sxs-lookup"><span data-stu-id="4c713-3596">Debit Account</span></span> 
- <span data-ttu-id="4c713-3597">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="4c713-3597">Debit Account #</span></span> 
- <span data-ttu-id="4c713-3598">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="4c713-3598">Debit Acct Number</span></span> 
- <span data-ttu-id="4c713-3599">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="4c713-3599">Debit Acct #</span></span> 
- <span data-ttu-id="4c713-3600">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3600">Debit Acct No.</span></span> 
- <span data-ttu-id="4c713-3601">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="4c713-3601">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="4c713-3602">Número de licencia de conductor de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="4c713-3602">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3603">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3603">Format</span></span>

<span data-ttu-id="4c713-3604">Depende del estado</span><span class="sxs-lookup"><span data-stu-id="4c713-3604">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3605">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3605">Pattern</span></span>

<span data-ttu-id="4c713-3606">Depende del estado, por ejemplo, Nueva York:</span><span class="sxs-lookup"><span data-stu-id="4c713-3606">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="4c713-3607">Nueve dígitos con formato como DDD DDD DDD coincidirán.</span><span class="sxs-lookup"><span data-stu-id="4c713-3607">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="4c713-3608">Nueve dígitos como ddddddddd no coinciden con el formato.</span><span class="sxs-lookup"><span data-stu-id="4c713-3608">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3609">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3609">Checksum</span></span>

<span data-ttu-id="4c713-3610">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3610">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3611">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3611">Definition</span></span>

<span data-ttu-id="4c713-3612">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3612">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3613">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3613">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3614">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="4c713-3614">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="4c713-3615">Se encuentra una palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="4c713-3615">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="4c713-3616">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3616">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3617">La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3617">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3618">Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="4c713-3618">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="4c713-3619">Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="4c713-3619">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="4c713-3620">No se encuentra ninguna palabra clave de Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="4c713-3620">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3621">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="4c713-3622">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="4c713-3622">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="4c713-3623">LISTAS</span><span class="sxs-lookup"><span data-stu-id="4c713-3623">DL</span></span> 
- <span data-ttu-id="4c713-3624">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c713-3624">DLS</span></span> 
- <span data-ttu-id="4c713-3625">CDL</span><span class="sxs-lookup"><span data-stu-id="4c713-3625">CDL</span></span> 
- <span data-ttu-id="4c713-3626">CDLS</span><span class="sxs-lookup"><span data-stu-id="4c713-3626">CDLS</span></span> 
- <span data-ttu-id="4c713-3627">ID</span><span class="sxs-lookup"><span data-stu-id="4c713-3627">ID</span></span> 
- <span data-ttu-id="4c713-3628">Falta</span><span class="sxs-lookup"><span data-stu-id="4c713-3628">IDs</span></span> 
- <span data-ttu-id="4c713-3629">LISTAS</span><span class="sxs-lookup"><span data-stu-id="4c713-3629">DL#</span></span> 
- <span data-ttu-id="4c713-3630">DISTRIBUCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c713-3630">DLS#</span></span> 
- <span data-ttu-id="4c713-3631">CDL</span><span class="sxs-lookup"><span data-stu-id="4c713-3631">CDL#</span></span> 
- <span data-ttu-id="4c713-3632">CDLS #</span><span class="sxs-lookup"><span data-stu-id="4c713-3632">CDLS#</span></span> 
- <span data-ttu-id="4c713-3633">IDENTIFICADOR</span><span class="sxs-lookup"><span data-stu-id="4c713-3633">ID#</span></span>
- <span data-ttu-id="4c713-3634">Falta</span><span class="sxs-lookup"><span data-stu-id="4c713-3634">IDs#</span></span> 
- <span data-ttu-id="4c713-3635">ID number</span><span class="sxs-lookup"><span data-stu-id="4c713-3635">ID number</span></span> 
- <span data-ttu-id="4c713-3636">ID numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-3636">ID numbers</span></span> 
- <span data-ttu-id="4c713-3637">LIC</span><span class="sxs-lookup"><span data-stu-id="4c713-3637">LIC</span></span> 
- <span data-ttu-id="4c713-3638">Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-3638">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="4c713-3639">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4c713-3639">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="4c713-3640">DriverLic</span><span class="sxs-lookup"><span data-stu-id="4c713-3640">DriverLic</span></span> 
- <span data-ttu-id="4c713-3641">DriverLics</span><span class="sxs-lookup"><span data-stu-id="4c713-3641">DriverLics</span></span> 
- <span data-ttu-id="4c713-3642">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-3642">DriverLicense</span></span> 
- <span data-ttu-id="4c713-3643">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-3643">DriverLicenses</span></span> 
- <span data-ttu-id="4c713-3644">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-3644">Driver Lic</span></span> 
- <span data-ttu-id="4c713-3645">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-3645">Driver Lics</span></span> 
- <span data-ttu-id="4c713-3646">Driver License</span><span class="sxs-lookup"><span data-stu-id="4c713-3646">Driver License</span></span> 
- <span data-ttu-id="4c713-3647">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-3647">Driver Licenses</span></span> 
- <span data-ttu-id="4c713-3648">DriversLic</span><span class="sxs-lookup"><span data-stu-id="4c713-3648">DriversLic</span></span> 
- <span data-ttu-id="4c713-3649">DriversLics</span><span class="sxs-lookup"><span data-stu-id="4c713-3649">DriversLics</span></span> 
- <span data-ttu-id="4c713-3650">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-3650">DriversLicense</span></span> 
- <span data-ttu-id="4c713-3651">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-3651">DriversLicenses</span></span> 
- <span data-ttu-id="4c713-3652">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-3652">Drivers Lic</span></span> 
- <span data-ttu-id="4c713-3653">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-3653">Drivers Lics</span></span> 
- <span data-ttu-id="4c713-3654">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4c713-3654">Drivers License</span></span> 
- <span data-ttu-id="4c713-3655">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-3655">Drivers Licenses</span></span> 
- <span data-ttu-id="4c713-3656">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-3656">Driver'Lic</span></span> 
- <span data-ttu-id="4c713-3657">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-3657">Driver'Lics</span></span> 
- <span data-ttu-id="4c713-3658">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-3658">Driver'License</span></span> 
- <span data-ttu-id="4c713-3659">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-3659">Driver'Licenses</span></span> 
- <span data-ttu-id="4c713-3660">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-3660">Driver' Lic</span></span> 
- <span data-ttu-id="4c713-3661">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-3661">Driver' Lics</span></span> 
- <span data-ttu-id="4c713-3662">Driver' License</span><span class="sxs-lookup"><span data-stu-id="4c713-3662">Driver' License</span></span> 
- <span data-ttu-id="4c713-3663">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="4c713-3663">Driver' Licenses</span></span>
- <span data-ttu-id="4c713-3664">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="4c713-3664">Driver'sLic</span></span> 
- <span data-ttu-id="4c713-3665">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="4c713-3665">Driver'sLics</span></span> 
- <span data-ttu-id="4c713-3666">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="4c713-3666">Driver'sLicense</span></span> 
- <span data-ttu-id="4c713-3667">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="4c713-3667">Driver'sLicenses</span></span> 
- <span data-ttu-id="4c713-3668">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4c713-3668">Driver's Lic</span></span> 
- <span data-ttu-id="4c713-3669">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="4c713-3669">Driver's Lics</span></span> 
- <span data-ttu-id="4c713-3670">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4c713-3670">Driver's License</span></span> 
- <span data-ttu-id="4c713-3671">Permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-3671">Driver's Licenses</span></span> 
- <span data-ttu-id="4c713-3672">identification number</span><span class="sxs-lookup"><span data-stu-id="4c713-3672">identification number</span></span> 
- <span data-ttu-id="4c713-3673">identification numbers</span><span class="sxs-lookup"><span data-stu-id="4c713-3673">identification numbers</span></span> 
- <span data-ttu-id="4c713-3674">identification #</span><span class="sxs-lookup"><span data-stu-id="4c713-3674">identification #</span></span> 
- <span data-ttu-id="4c713-3675">id card</span><span class="sxs-lookup"><span data-stu-id="4c713-3675">id card</span></span> 
- <span data-ttu-id="4c713-3676">id cards</span><span class="sxs-lookup"><span data-stu-id="4c713-3676">id cards</span></span> 
- <span data-ttu-id="4c713-3677">identification card</span><span class="sxs-lookup"><span data-stu-id="4c713-3677">identification card</span></span> 
- <span data-ttu-id="4c713-3678">identification cards</span><span class="sxs-lookup"><span data-stu-id="4c713-3678">identification cards</span></span> 
- <span data-ttu-id="4c713-3679">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-3679">DriverLic#</span></span> 
- <span data-ttu-id="4c713-3680">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-3680">DriverLics#</span></span> 
- <span data-ttu-id="4c713-3681">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-3681">DriverLicense#</span></span> 
- <span data-ttu-id="4c713-3682">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-3682">DriverLicenses#</span></span> 
- <span data-ttu-id="4c713-3683">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-3683">Driver Lic#</span></span> 
- <span data-ttu-id="4c713-3684">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-3684">Driver Lics#</span></span> 
- <span data-ttu-id="4c713-3685">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4c713-3685">Driver License#</span></span> 
- <span data-ttu-id="4c713-3686">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-3686">Driver Licenses#</span></span> 
- <span data-ttu-id="4c713-3687">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-3687">DriversLic#</span></span> 
- <span data-ttu-id="4c713-3688">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-3688">DriversLics#</span></span> 
- <span data-ttu-id="4c713-3689">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-3689">DriversLicense#</span></span> 
- <span data-ttu-id="4c713-3690">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-3690">DriversLicenses#</span></span> 
- <span data-ttu-id="4c713-3691">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-3691">Drivers Lic#</span></span> 
- <span data-ttu-id="4c713-3692">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-3692">Drivers Lics#</span></span> 
- <span data-ttu-id="4c713-3693">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="4c713-3693">Drivers License#</span></span> 
- <span data-ttu-id="4c713-3694">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-3694">Drivers Licenses#</span></span> 
- <span data-ttu-id="4c713-3695">N.º carné</span><span class="sxs-lookup"><span data-stu-id="4c713-3695">Driver'Lic#</span></span> 
- <span data-ttu-id="4c713-3696">N.º carnés</span><span class="sxs-lookup"><span data-stu-id="4c713-3696">Driver'Lics#</span></span> 
- <span data-ttu-id="4c713-3697">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-3697">Driver'License#</span></span> 
- <span data-ttu-id="4c713-3698">Conducción</span><span class="sxs-lookup"><span data-stu-id="4c713-3698">Driver'Licenses#</span></span> 
- <span data-ttu-id="4c713-3699">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-3699">Driver' Lic#</span></span> 
- <span data-ttu-id="4c713-3700">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-3700">Driver' Lics#</span></span> 
- <span data-ttu-id="4c713-3701">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="4c713-3701">Driver' License#</span></span> 
- <span data-ttu-id="4c713-3702">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-3702">Driver' Licenses#</span></span> 
- <span data-ttu-id="4c713-3703">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="4c713-3703">Driver'sLic#</span></span> 
- <span data-ttu-id="4c713-3704">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="4c713-3704">Driver'sLics#</span></span> 
- <span data-ttu-id="4c713-3705">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="4c713-3705">Driver'sLicense#</span></span> 
- <span data-ttu-id="4c713-3706">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="4c713-3706">Driver'sLicenses#</span></span> 
- <span data-ttu-id="4c713-3707">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="4c713-3707">Driver's Lic#</span></span> 
- <span data-ttu-id="4c713-3708">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="4c713-3708">Driver's Lics#</span></span> 
- <span data-ttu-id="4c713-3709">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="4c713-3709">Driver's License#</span></span> 
- <span data-ttu-id="4c713-3710">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="4c713-3710">Driver's Licenses#</span></span> 
- <span data-ttu-id="4c713-3711">id card#</span><span class="sxs-lookup"><span data-stu-id="4c713-3711">id card#</span></span> 
- <span data-ttu-id="4c713-3712">id cards#</span><span class="sxs-lookup"><span data-stu-id="4c713-3712">id cards#</span></span> 
- <span data-ttu-id="4c713-3713">identification card#</span><span class="sxs-lookup"><span data-stu-id="4c713-3713">identification card#</span></span> 
- <span data-ttu-id="4c713-3714">identification cards#</span><span class="sxs-lookup"><span data-stu-id="4c713-3714">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="4c713-3715">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="4c713-3715">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="4c713-3716">Abreviatura del estado (por ejemplo, "NY")</span><span class="sxs-lookup"><span data-stu-id="4c713-3716">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="4c713-3717">Nombre del estado (por ejemplo, "New York")</span><span class="sxs-lookup"><span data-stu-id="4c713-3717">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="4c713-3718">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="4c713-3718">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3719">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3719">Format</span></span>

<span data-ttu-id="4c713-3720">Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones</span><span class="sxs-lookup"><span data-stu-id="4c713-3720">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3721">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3721">Pattern</span></span>

<span data-ttu-id="4c713-3722">Con formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3722">Formatted:</span></span>
- <span data-ttu-id="4c713-3723">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="4c713-3723">The digit "9"</span></span> 
- <span data-ttu-id="4c713-3724">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3724">Two digits</span></span> 
- <span data-ttu-id="4c713-3725">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-3725">A space or dash</span></span> 
- <span data-ttu-id="4c713-3726">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="4c713-3726">A "7" or "8"</span></span> 
- <span data-ttu-id="4c713-3727">Un dígito</span><span class="sxs-lookup"><span data-stu-id="4c713-3727">A digit</span></span> 
- <span data-ttu-id="4c713-3728">Un espacio o un guion</span><span class="sxs-lookup"><span data-stu-id="4c713-3728">A space, or dash</span></span> 
- <span data-ttu-id="4c713-3729">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3729">Four digits</span></span>

<span data-ttu-id="4c713-3730">Sin formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3730">Unformatted:</span></span>
- <span data-ttu-id="4c713-3731">El dígito "9"</span><span class="sxs-lookup"><span data-stu-id="4c713-3731">The digit "9"</span></span> 
- <span data-ttu-id="4c713-3732">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3732">Two digits</span></span> 
- <span data-ttu-id="4c713-3733">Un "7" o "8"</span><span class="sxs-lookup"><span data-stu-id="4c713-3733">A "7" or "8"</span></span> 
- <span data-ttu-id="4c713-3734">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4c713-3734">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3735">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3735">Checksum</span></span>

<span data-ttu-id="4c713-3736">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3736">No</span></span>

### <a name="definition"></a><span data-ttu-id="4c713-3737">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3737">Definition</span></span>

<span data-ttu-id="4c713-3738">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3738">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3739">La función Func_formatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3739">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3740">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-3740">At least one of the following is true:</span></span>
    - <span data-ttu-id="4c713-3741">Se encuentra una palabra clave de Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="4c713-3741">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="4c713-3742">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-3742">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="4c713-3743">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-3743">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="4c713-3744">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="4c713-3744">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="4c713-3745">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3745">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3746">La función Func_unformatted_itin encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3746">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3747">Al menos una de las siguientes opciones es verdadera:</span><span class="sxs-lookup"><span data-stu-id="4c713-3747">At least one of the following is true:</span></span>
    - <span data-ttu-id="4c713-3748">Se encuentra una palabra clave de Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="4c713-3748">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="4c713-3749">La función Func_us_address encuentra una dirección en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-3749">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="4c713-3750">La función Func_us_date encuentra una fecha en el formato de fecha correcto.</span><span class="sxs-lookup"><span data-stu-id="4c713-3750">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3751">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3751">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="4c713-3752">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="4c713-3752">Keyword_itin</span></span>

- <span data-ttu-id="4c713-3753">contribuyente</span><span class="sxs-lookup"><span data-stu-id="4c713-3753">taxpayer</span></span> 
- <span data-ttu-id="4c713-3754">tax id</span><span class="sxs-lookup"><span data-stu-id="4c713-3754">tax id</span></span> 
- <span data-ttu-id="4c713-3755">tax identification</span><span class="sxs-lookup"><span data-stu-id="4c713-3755">tax identification</span></span> 
- <span data-ttu-id="4c713-3756">élen</span><span class="sxs-lookup"><span data-stu-id="4c713-3756">itin</span></span> 
- <span data-ttu-id="4c713-3757">SSN</span><span class="sxs-lookup"><span data-stu-id="4c713-3757">ssn</span></span> 
- <span data-ttu-id="4c713-3758">/</span><span class="sxs-lookup"><span data-stu-id="4c713-3758">tin</span></span> 
- <span data-ttu-id="4c713-3759">social security</span><span class="sxs-lookup"><span data-stu-id="4c713-3759">social security</span></span> 
- <span data-ttu-id="4c713-3760">tax payer</span><span class="sxs-lookup"><span data-stu-id="4c713-3760">tax payer</span></span> 
- <span data-ttu-id="4c713-3761">ITINs</span><span class="sxs-lookup"><span data-stu-id="4c713-3761">itins</span></span> 
- <span data-ttu-id="4c713-3762">taxi</span><span class="sxs-lookup"><span data-stu-id="4c713-3762">taxid</span></span> 
- <span data-ttu-id="4c713-3763">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="4c713-3763">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="4c713-3764">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="4c713-3764">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="4c713-3765">License</span><span class="sxs-lookup"><span data-stu-id="4c713-3765">License</span></span> 
- <span data-ttu-id="4c713-3766">LISTAS</span><span class="sxs-lookup"><span data-stu-id="4c713-3766">DL</span></span> 
- <span data-ttu-id="4c713-3767">NACIMIENTO</span><span class="sxs-lookup"><span data-stu-id="4c713-3767">DOB</span></span> 
- <span data-ttu-id="4c713-3768">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-3768">Birthdate</span></span> 
- <span data-ttu-id="4c713-3769">Cumpleaños</span><span class="sxs-lookup"><span data-stu-id="4c713-3769">Birthday</span></span> 
- <span data-ttu-id="4c713-3770">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="4c713-3770">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="4c713-3771">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="4c713-3771">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="4c713-3772">Formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3772">Format</span></span>

<span data-ttu-id="4c713-3773">9 dígitos, que pueden ser un patrón con o sin formato</span><span class="sxs-lookup"><span data-stu-id="4c713-3773">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="4c713-3774">Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="4c713-3774">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="4c713-3775">Patrón</span><span class="sxs-lookup"><span data-stu-id="4c713-3775">Pattern</span></span>

<span data-ttu-id="4c713-3776">Cuatro funciones buscan SSN en cuatro patrones diferentes:</span><span class="sxs-lookup"><span data-stu-id="4c713-3776">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="4c713-3777">Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="4c713-3777">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="4c713-3778">Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="4c713-3778">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="4c713-3779">Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="4c713-3779">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="4c713-3780">Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="4c713-3780">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="4c713-3781">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4c713-3781">Checksum</span></span>

<span data-ttu-id="4c713-3782">No</span><span class="sxs-lookup"><span data-stu-id="4c713-3782">No</span></span>


### <a name="definition"></a><span data-ttu-id="4c713-3783">Definición</span><span class="sxs-lookup"><span data-stu-id="4c713-3783">Definition</span></span>

<span data-ttu-id="4c713-3784">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3785">La función Func_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3785">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3786">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="4c713-3786">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="4c713-3787">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3788">La función Func_unformatted_ssn busca contenido que coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3788">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3789">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="4c713-3789">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="4c713-3790">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3790">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3791">La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3791">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3792">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="4c713-3792">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="4c713-3793">La función Func_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3793">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="4c713-3794">Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c713-3794">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4c713-3795">La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3795">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4c713-3796">Se encuentra una palabra clave de Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="4c713-3796">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="4c713-3797">La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4c713-3797">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4c713-3798">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c713-3798">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="4c713-3799">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="4c713-3799">Keyword_ssn</span></span>

- <span data-ttu-id="4c713-3800">Social Security</span><span class="sxs-lookup"><span data-stu-id="4c713-3800">Social Security</span></span> 
- <span data-ttu-id="4c713-3801">Social Security#</span><span class="sxs-lookup"><span data-stu-id="4c713-3801">Social Security#</span></span> 
- <span data-ttu-id="4c713-3802">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="4c713-3802">Soc Sec</span></span> 
- <span data-ttu-id="4c713-3803">SSN</span><span class="sxs-lookup"><span data-stu-id="4c713-3803">SSN</span></span> 
- <span data-ttu-id="4c713-3804">SSN</span><span class="sxs-lookup"><span data-stu-id="4c713-3804">SSNS</span></span> 
- <span data-ttu-id="4c713-3805">SSN</span><span class="sxs-lookup"><span data-stu-id="4c713-3805">SSN#</span></span> 
- <span data-ttu-id="4c713-3806">SS</span><span class="sxs-lookup"><span data-stu-id="4c713-3806">SS#</span></span> 
- <span data-ttu-id="4c713-3807">SSID</span><span class="sxs-lookup"><span data-stu-id="4c713-3807">SSID</span></span> 
   

