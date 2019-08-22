---
title: Número de identificación nacional de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación nacional de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: cbcacb3f85877f5a84238468fb52d612d90f5f0b
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490777"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="79c77-104">Número de identificación nacional de la UE</span><span class="sxs-lookup"><span data-stu-id="79c77-104">EU National Identification Number</span></span>

<span data-ttu-id="79c77-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación nacional de la UE.</span><span class="sxs-lookup"><span data-stu-id="79c77-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="79c77-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="79c77-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="79c77-107">Austria</span><span class="sxs-lookup"><span data-stu-id="79c77-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="79c77-108">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-108">Format</span></span>

<span data-ttu-id="79c77-109">Una combinación de letras, dígitos y caracteres especiales de 24 caracteres</span><span class="sxs-lookup"><span data-stu-id="79c77-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-110">Pattern</span></span>

<span data-ttu-id="79c77-111">24 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-111">24 characters:</span></span>
  
-  <span data-ttu-id="79c77-112">22 letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más</span><span class="sxs-lookup"><span data-stu-id="79c77-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="79c77-113">Dos letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales, signos más o signos igual</span><span class="sxs-lookup"><span data-stu-id="79c77-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-114">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-114">Checksum</span></span>

<span data-ttu-id="79c77-115">No aplicable</span><span class="sxs-lookup"><span data-stu-id="79c77-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-116">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-116">Definition</span></span>

<span data-ttu-id="79c77-117">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-118">La expresión `Regex_austria_eu_national_id_card` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-119">Se encuentra una `Keywords_austria_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-120">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="79c77-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="79c77-122">número de identidad austriaco</span><span class="sxs-lookup"><span data-stu-id="79c77-122">austrian identity number</span></span>
  
<span data-ttu-id="79c77-123">número de identidad nacional</span><span class="sxs-lookup"><span data-stu-id="79c77-123">national identity number</span></span>
  
<span data-ttu-id="79c77-124">número de identidad</span><span class="sxs-lookup"><span data-stu-id="79c77-124">identity number</span></span>
  
<span data-ttu-id="79c77-125">national id</span><span class="sxs-lookup"><span data-stu-id="79c77-125">national id</span></span>
  
<span data-ttu-id="79c77-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="79c77-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="79c77-127">Bélgica</span><span class="sxs-lookup"><span data-stu-id="79c77-127">Belgium</span></span>

<span data-ttu-id="79c77-128">Para obtener más información, consulte la sección "número nacional de Bélgica" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="79c77-129">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="79c77-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="79c77-130">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-130">Format</span></span>

<span data-ttu-id="79c77-131">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-132">Pattern</span></span>

<span data-ttu-id="79c77-133">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="79c77-134">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="79c77-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="79c77-135">Dos dígitos que corresponden a la orden de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="79c77-136">Un dígito que corresponde al género: un dígito par para macho y un dígito impar para hembra</span><span class="sxs-lookup"><span data-stu-id="79c77-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="79c77-137">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-138">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-138">Checksum</span></span>

<span data-ttu-id="79c77-139">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-140">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-140">Definition</span></span>

<span data-ttu-id="79c77-141">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-142">La función `Func_bulgaria_national_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-143">Se encuentra una `Keywords_bulgaria_national_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="79c77-144">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-145">La función `Func_bulgaria_national_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="79c77-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="79c77-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="79c77-148">egn</span><span class="sxs-lookup"><span data-stu-id="79c77-148">egn</span></span>
  
<span data-ttu-id="79c77-149">egn #</span><span class="sxs-lookup"><span data-stu-id="79c77-149">egn#</span></span>
  
<span data-ttu-id="79c77-150">número nacional búlgaro</span><span class="sxs-lookup"><span data-stu-id="79c77-150">bulgarian national number</span></span>
  
<span data-ttu-id="79c77-151">número nacional</span><span class="sxs-lookup"><span data-stu-id="79c77-151">national number</span></span>
  
<span data-ttu-id="79c77-152">social security number</span><span class="sxs-lookup"><span data-stu-id="79c77-152">social security number</span></span>
  
<span data-ttu-id="79c77-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="79c77-153">nationalnumber#</span></span>
  
<span data-ttu-id="79c77-154">SSN #</span><span class="sxs-lookup"><span data-stu-id="79c77-154">ssn#</span></span>
  
<span data-ttu-id="79c77-155">SSN</span><span class="sxs-lookup"><span data-stu-id="79c77-155">ssn</span></span>
  
<span data-ttu-id="79c77-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="79c77-156">nationalnumber</span></span>
  
<span data-ttu-id="79c77-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="79c77-157">bnn#</span></span>
  
<span data-ttu-id="79c77-158">bnn</span><span class="sxs-lookup"><span data-stu-id="79c77-158">bnn</span></span>
  
<span data-ttu-id="79c77-159">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-159">personal id number</span></span>
  
<span data-ttu-id="79c77-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="79c77-160">personalidnumber#</span></span>
  
<span data-ttu-id="79c77-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="79c77-161">единен граждански номер</span></span>
  
<span data-ttu-id="79c77-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="79c77-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="79c77-163">егн</span><span class="sxs-lookup"><span data-stu-id="79c77-163">егн</span></span>
  
<span data-ttu-id="79c77-164">егн #</span><span class="sxs-lookup"><span data-stu-id="79c77-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="79c77-165">Croacia</span><span class="sxs-lookup"><span data-stu-id="79c77-165">Croatia</span></span>

<span data-ttu-id="79c77-166">Para obtener más información, consulte la sección "número de identidad de Croacia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="79c77-167">Chipre</span><span class="sxs-lookup"><span data-stu-id="79c77-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="79c77-168">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-168">Format</span></span>

<span data-ttu-id="79c77-169">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-170">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-170">Pattern</span></span>

 <span data-ttu-id="79c77-171">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="79c77-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="79c77-172">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-172">Checksum</span></span>

<span data-ttu-id="79c77-173">No aplicable</span><span class="sxs-lookup"><span data-stu-id="79c77-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-174">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-174">Definition</span></span>

<span data-ttu-id="79c77-175">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-176">La expresión `Regex_cyprus_eu_national_id_card` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-177">Se encuentra una `Keywords_cyprus_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-178">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="79c77-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="79c77-180">número de tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="79c77-180">id card number</span></span>
  
<span data-ttu-id="79c77-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="79c77-181">national identification number</span></span>
  
<span data-ttu-id="79c77-182">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-182">personal id number</span></span>
  
<span data-ttu-id="79c77-183">número de tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="79c77-183">identity card number</span></span>
  
<span data-ttu-id="79c77-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="79c77-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="79c77-185">Chequia</span><span class="sxs-lookup"><span data-stu-id="79c77-185">Czech Republic</span></span>

<span data-ttu-id="79c77-186">Para obtener más información, consulte la sección "número de identidad nacional Checa" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="79c77-187">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="79c77-187">Denmark</span></span>

<span data-ttu-id="79c77-188">Para obtener más información, vea la sección sobre el número de identificación personal de Dinamarca en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="79c77-189">Estonia</span><span class="sxs-lookup"><span data-stu-id="79c77-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="79c77-190">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-190">Format</span></span>

<span data-ttu-id="79c77-191">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-192">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-192">Pattern</span></span>

<span data-ttu-id="79c77-193">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="79c77-193">11 digits:</span></span>
  
- <span data-ttu-id="79c77-194">Un dígito que corresponde al sexo y al siglo de nacimiento (número impar macho, par hembra; 1-2: siglo XIX; 3-4: siglo XX; 5-6: siglo XXI)</span><span class="sxs-lookup"><span data-stu-id="79c77-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="79c77-195">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="79c77-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="79c77-196">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha</span><span class="sxs-lookup"><span data-stu-id="79c77-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="79c77-197">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-198">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-198">Checksum</span></span>

<span data-ttu-id="79c77-199">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-200">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-200">Definition</span></span>

<span data-ttu-id="79c77-201">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-202">La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-203">Se encuentra una `Keywords_estonia_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-204">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-205">La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-206">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="79c77-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="79c77-208">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-208">personal identification code</span></span>
  
<span data-ttu-id="79c77-209">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-209">personal identification number</span></span>
  
<span data-ttu-id="79c77-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="79c77-210">national identification number</span></span>
  
<span data-ttu-id="79c77-211">número nacional</span><span class="sxs-lookup"><span data-stu-id="79c77-211">national number</span></span>
  
<span data-ttu-id="79c77-212">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-212">personal id number</span></span>
  
<span data-ttu-id="79c77-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="79c77-213">personalidnumber#</span></span>
  
<span data-ttu-id="79c77-214">IK</span><span class="sxs-lookup"><span data-stu-id="79c77-214">ik</span></span>
  
<span data-ttu-id="79c77-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="79c77-215">isikukood</span></span>
  
<span data-ttu-id="79c77-216">ID-Kaart</span><span class="sxs-lookup"><span data-stu-id="79c77-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="79c77-217">Finlandia</span><span class="sxs-lookup"><span data-stu-id="79c77-217">Finland</span></span>

<span data-ttu-id="79c77-218">Para obtener más información, consulte la sección "identificación nacional de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="79c77-219">Francia</span><span class="sxs-lookup"><span data-stu-id="79c77-219">France</span></span>

<span data-ttu-id="79c77-220">Para obtener más información, vea la sección sobre la tarjeta de identificación nacional (CNI) de Francia en la [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="79c77-221">Alemania</span><span class="sxs-lookup"><span data-stu-id="79c77-221">Germany</span></span>

<span data-ttu-id="79c77-222">Para obtener más información, consulte la sección "número de tarjeta de identidades Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="79c77-223">Grecia</span><span class="sxs-lookup"><span data-stu-id="79c77-223">Greece</span></span>

<span data-ttu-id="79c77-224">Para obtener más información, consulte la sección "tarjeta de identificación nacional de Grecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="79c77-225">Hungría</span><span class="sxs-lookup"><span data-stu-id="79c77-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="79c77-226">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-226">Format</span></span>

<span data-ttu-id="79c77-227">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="79c77-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-228">Pattern</span></span>

<span data-ttu-id="79c77-229">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="79c77-229">11 digits:</span></span>
  
-  <span data-ttu-id="79c77-230">Un dígito que corresponde a sexo (1-macho, 2-hembra, otros números también son posibles para los ciudadanos nacidos antes del 1900 o los ciudadanos con doble nacionalidad)</span><span class="sxs-lookup"><span data-stu-id="79c77-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="79c77-231">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="79c77-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="79c77-232">Tres dígitos que corresponden a un número de serie</span><span class="sxs-lookup"><span data-stu-id="79c77-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="79c77-233">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-234">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-234">Checksum</span></span>

<span data-ttu-id="79c77-235">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-236">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-236">Definition</span></span>

<span data-ttu-id="79c77-237">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-238">La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-239">Se encuentra una `Keywords_hungary_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-240">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-241">La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-242">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="79c77-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="79c77-244">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-244">personal identification number</span></span>
  
<span data-ttu-id="79c77-245">identification number</span><span class="sxs-lookup"><span data-stu-id="79c77-245">identification number</span></span>
  
<span data-ttu-id="79c77-246">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-246">personal id number</span></span>
  
<span data-ttu-id="79c77-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="79c77-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="79c77-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="79c77-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="79c77-249">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-249">Format</span></span>

<span data-ttu-id="79c77-250">Una combinación de Letras de nueve caracteres, dígitos y un espacio en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="79c77-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-251">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-251">Pattern</span></span>

<span data-ttu-id="79c77-252">Una combinación de Letras de nueve caracteres, dígitos y un espacio en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="79c77-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="79c77-253">De 01 de enero de 2013 a ahora:</span><span class="sxs-lookup"><span data-stu-id="79c77-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="79c77-254">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="79c77-254">Seven digits</span></span> 
    
- <span data-ttu-id="79c77-255">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-255">One check digit</span></span>
    
- <span data-ttu-id="79c77-256">Un espacio o la letra mayúscula "W" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="79c77-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="79c77-257">Antes del 01 de enero de 2013:</span><span class="sxs-lookup"><span data-stu-id="79c77-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="79c77-258">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="79c77-258">Seven digits</span></span> 
    
- <span data-ttu-id="79c77-259">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-259">One check digit</span></span>
    
- <span data-ttu-id="79c77-260">Un espacio o una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="79c77-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-261">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-261">Checksum</span></span>

<span data-ttu-id="79c77-262">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-263">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-263">Definition</span></span>

<span data-ttu-id="79c77-264">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-265">La función busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="79c77-266">Se encuentra una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-266">A keyword from is found.</span></span>
    
<span data-ttu-id="79c77-267">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-268">La función busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-269">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="79c77-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="79c77-271">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="79c77-271">personal public service number</span></span>
  
<span data-ttu-id="79c77-272">n.º de PPS</span><span class="sxs-lookup"><span data-stu-id="79c77-272">pps no</span></span>
  
<span data-ttu-id="79c77-273">número de la seguridad social y de ingresos</span><span class="sxs-lookup"><span data-stu-id="79c77-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="79c77-274">RSI no</span><span class="sxs-lookup"><span data-stu-id="79c77-274">rsi no</span></span>
  
<span data-ttu-id="79c77-275">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-275">personal identification number</span></span>
  
<span data-ttu-id="79c77-276">identification number</span><span class="sxs-lookup"><span data-stu-id="79c77-276">identification number</span></span>
  
<span data-ttu-id="79c77-277">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-277">personal id number</span></span>
  
<span data-ttu-id="79c77-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="79c77-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="79c77-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="79c77-279">uimh.</span></span> <span data-ttu-id="79c77-280">PSP</span><span class="sxs-lookup"><span data-stu-id="79c77-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="79c77-281">Italia</span><span class="sxs-lookup"><span data-stu-id="79c77-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="79c77-282">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-282">Format</span></span>

<span data-ttu-id="79c77-283">Una combinación de letras y dígitos de 16 caracteres en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="79c77-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-284">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-284">Pattern</span></span>

<span data-ttu-id="79c77-285">Una combinación de letras y dígitos de 16 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="79c77-286">Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="79c77-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="79c77-287">Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre</span><span class="sxs-lookup"><span data-stu-id="79c77-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="79c77-288">Dos dígitos que corresponden a los últimos dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="79c77-289">Una letra que corresponde a la carta del mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="79c77-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="79c77-290">Dos dígitos que corresponden al día del mes de nacimiento: para diferenciar entre los sexos, 40 se agrega al día de nacimiento para las mujeres</span><span class="sxs-lookup"><span data-stu-id="79c77-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="79c77-291">Cuatro dígitos que corresponden al código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros)</span><span class="sxs-lookup"><span data-stu-id="79c77-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="79c77-292">Un dígito de paridad</span><span class="sxs-lookup"><span data-stu-id="79c77-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-293">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-293">Checksum</span></span>

<span data-ttu-id="79c77-294">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-295">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-295">Definition</span></span>

<span data-ttu-id="79c77-296">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-297">La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-298">Se encuentra una `Keywords_italy_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-299">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-300">La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-301">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="79c77-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="79c77-303">código personal</span><span class="sxs-lookup"><span data-stu-id="79c77-303">personal code</span></span>
  
<span data-ttu-id="79c77-304">número de código personal</span><span class="sxs-lookup"><span data-stu-id="79c77-304">personal code number</span></span>
  
<span data-ttu-id="79c77-305">número de certificado personal</span><span class="sxs-lookup"><span data-stu-id="79c77-305">personal certificate number</span></span>
  
<span data-ttu-id="79c77-306">Código fiscal</span><span class="sxs-lookup"><span data-stu-id="79c77-306">fiscal code</span></span>
  
<span data-ttu-id="79c77-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="79c77-307">personalcodeno#</span></span>
  
<span data-ttu-id="79c77-308">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-308">personal id number</span></span>
  
<span data-ttu-id="79c77-309">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-309">personal id code</span></span>
  
<span data-ttu-id="79c77-310">personal Codice</span><span class="sxs-lookup"><span data-stu-id="79c77-310">codice personale</span></span>
  
<span data-ttu-id="79c77-311">numero certificato personal</span><span class="sxs-lookup"><span data-stu-id="79c77-311">numero certificato personale</span></span>
  
<span data-ttu-id="79c77-312">personal numero</span><span class="sxs-lookup"><span data-stu-id="79c77-312">numero personale</span></span>
  
<span data-ttu-id="79c77-313">personal del identificador numero</span><span class="sxs-lookup"><span data-stu-id="79c77-313">numero id personale</span></span>
  
<span data-ttu-id="79c77-314">personal del identificador Codice</span><span class="sxs-lookup"><span data-stu-id="79c77-314">codice id personale</span></span>
  
<span data-ttu-id="79c77-315">Codice fiscal</span><span class="sxs-lookup"><span data-stu-id="79c77-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="79c77-316">Letonia</span><span class="sxs-lookup"><span data-stu-id="79c77-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="79c77-317">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-317">Format</span></span>

<span data-ttu-id="79c77-318">11 dígitos y un guión en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="79c77-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-319">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-319">Pattern</span></span>

<span data-ttu-id="79c77-320">11 dígitos y un guión:</span><span class="sxs-lookup"><span data-stu-id="79c77-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="79c77-321">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="79c77-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="79c77-322">Un guión </span><span class="sxs-lookup"><span data-stu-id="79c77-322">A hyphen</span></span>
    
- <span data-ttu-id="79c77-323">Un dígito que corresponde al siglo de nacimiento ("0" para el siglo XIX, "1" para el siglo XX y "2" para el siglo XXI)</span><span class="sxs-lookup"><span data-stu-id="79c77-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="79c77-324">Cuatro dígitos, generados aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="79c77-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-325">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-325">Checksum</span></span>

<span data-ttu-id="79c77-326">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-327">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-327">Definition</span></span>

<span data-ttu-id="79c77-328">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-329">La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-330">Se encuentra una `Keywords_latvia_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-331">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-332">La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-333">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="79c77-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="79c77-335">código personal</span><span class="sxs-lookup"><span data-stu-id="79c77-335">personal code</span></span>
  
<span data-ttu-id="79c77-336">número de código personal</span><span class="sxs-lookup"><span data-stu-id="79c77-336">personal code number</span></span>
  
<span data-ttu-id="79c77-337">número de certificado personal</span><span class="sxs-lookup"><span data-stu-id="79c77-337">personal certificate number</span></span>
  
<span data-ttu-id="79c77-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="79c77-338">personalcodeno#</span></span>
  
<span data-ttu-id="79c77-339">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-339">personal id number</span></span>
  
<span data-ttu-id="79c77-340">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-340">personal id code</span></span>
  
<span data-ttu-id="79c77-341">roles kods</span><span class="sxs-lookup"><span data-stu-id="79c77-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="79c77-342">Lituania</span><span class="sxs-lookup"><span data-stu-id="79c77-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="79c77-343">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-343">Format</span></span>

<span data-ttu-id="79c77-344">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-345">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-345">Pattern</span></span>

<span data-ttu-id="79c77-346">11 dígitos sin espacios y delimitadores:</span><span class="sxs-lookup"><span data-stu-id="79c77-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="79c77-347">Un dígito que corresponde al sexo de la persona y al siglo de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="79c77-348">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="79c77-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="79c77-349">Tres dígitos que corresponden al número de serie de la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="79c77-350">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-351">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-351">Checksum</span></span>

<span data-ttu-id="79c77-352">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-353">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-353">Definition</span></span>

<span data-ttu-id="79c77-354">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-355">La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-356">Se encuentra una `Keywords_lithuania_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-357">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-358">La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-359">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="79c77-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="79c77-361">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="79c77-361">personal numeric code</span></span>
  
<span data-ttu-id="79c77-362">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="79c77-362">unique identification number</span></span>
  
<span data-ttu-id="79c77-363">número de servicio de ciudadanos</span><span class="sxs-lookup"><span data-stu-id="79c77-363">citizen service number</span></span>
  
<span data-ttu-id="79c77-364">número de identidad único</span><span class="sxs-lookup"><span data-stu-id="79c77-364">unique identity number</span></span>
  
<span data-ttu-id="79c77-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="79c77-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="79c77-366">código personal.</span><span class="sxs-lookup"><span data-stu-id="79c77-366">personal code.</span></span>
  
<span data-ttu-id="79c77-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="79c77-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="79c77-368">unikalus identifikavimo número</span><span class="sxs-lookup"><span data-stu-id="79c77-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="79c77-369">piliečio paslaugos número</span><span class="sxs-lookup"><span data-stu-id="79c77-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="79c77-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="79c77-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="79c77-371">asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="79c77-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="79c77-372">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="79c77-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="79c77-373">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-373">Format</span></span>

<span data-ttu-id="79c77-374">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-375">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-375">Pattern</span></span>

<span data-ttu-id="79c77-376">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="79c77-376">11 digits</span></span>
  
- <span data-ttu-id="79c77-377">Un dígito que corresponde al sexo de la persona y al siglo de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="79c77-378">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="79c77-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="79c77-379">Tres dígitos que corresponden al número de serie de la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="79c77-380">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-381">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-381">Checksum</span></span>

<span data-ttu-id="79c77-382">No aplicable</span><span class="sxs-lookup"><span data-stu-id="79c77-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-383">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-383">Definition</span></span>

<span data-ttu-id="79c77-384">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-385">La expresión `Regex_luxemburg_eu_national_id_card` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-386">Se encuentra una `Keywords_luxemburg_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-387">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="79c77-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="79c77-389">identificador personal</span><span class="sxs-lookup"><span data-stu-id="79c77-389">personal id</span></span>
  
<span data-ttu-id="79c77-390">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-390">personal id number</span></span>
  
<span data-ttu-id="79c77-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="79c77-391">personalidno#</span></span>
  
<span data-ttu-id="79c77-392">número de identificador único</span><span class="sxs-lookup"><span data-stu-id="79c77-392">unique id number</span></span>
  
<span data-ttu-id="79c77-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="79c77-393">personalidnumber#</span></span>
  
<span data-ttu-id="79c77-394">clave de identificador única</span><span class="sxs-lookup"><span data-stu-id="79c77-394">unique id key</span></span>
  
<span data-ttu-id="79c77-395">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-395">personal id code</span></span>
  
<span data-ttu-id="79c77-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="79c77-396">uniqueidkey#</span></span>
  
<span data-ttu-id="79c77-397">Código individual</span><span class="sxs-lookup"><span data-stu-id="79c77-397">individual code</span></span>
  
<span data-ttu-id="79c77-398">identificador individual</span><span class="sxs-lookup"><span data-stu-id="79c77-398">individual id</span></span>
  
<span data-ttu-id="79c77-399">eindeutige ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="79c77-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="79c77-400">identificador eindeutige</span><span class="sxs-lookup"><span data-stu-id="79c77-400">eindeutige id</span></span>
  
<span data-ttu-id="79c77-401">identificador personnelle</span><span class="sxs-lookup"><span data-stu-id="79c77-401">id personnelle</span></span>
  
<span data-ttu-id="79c77-402">personal de numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="79c77-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="79c77-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="79c77-403">idpersonnelle#</span></span>
  
<span data-ttu-id="79c77-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="79c77-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="79c77-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="79c77-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="79c77-406">Malta</span><span class="sxs-lookup"><span data-stu-id="79c77-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="79c77-407">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-407">Format</span></span>

<span data-ttu-id="79c77-408">Siete dígitos seguidos de una letra</span><span class="sxs-lookup"><span data-stu-id="79c77-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-409">Pattern</span></span>

<span data-ttu-id="79c77-410">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="79c77-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="79c77-411">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="79c77-411">Seven digits</span></span> 
    
- <span data-ttu-id="79c77-412">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="79c77-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-413">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-413">Checksum</span></span>

<span data-ttu-id="79c77-414">No aplicable</span><span class="sxs-lookup"><span data-stu-id="79c77-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-415">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-415">Definition</span></span>

<span data-ttu-id="79c77-416">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-417">La expresión `Regex_malta_eu_national_id_card` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-418">Se encuentra una `Keywords_malta_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-419">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-420">La expresión `Regex_malta_eu_national_id_card` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-421">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="79c77-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="79c77-423">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="79c77-423">personal numeric code</span></span>
  
<span data-ttu-id="79c77-424">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="79c77-424">unique identification number</span></span>
  
<span data-ttu-id="79c77-425">número de servicio de ciudadanos</span><span class="sxs-lookup"><span data-stu-id="79c77-425">citizen service number</span></span>
  
<span data-ttu-id="79c77-426">número de identidad único</span><span class="sxs-lookup"><span data-stu-id="79c77-426">unique identity number</span></span>
  
<span data-ttu-id="79c77-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="79c77-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="79c77-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="79c77-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="79c77-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="79c77-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="79c77-430">numru Servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="79c77-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="79c77-431">numru ta ' Identità uniku</span><span class="sxs-lookup"><span data-stu-id="79c77-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="79c77-432">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="79c77-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="79c77-433">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-433">Format</span></span>

<span data-ttu-id="79c77-434">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-435">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-435">Pattern</span></span>

<span data-ttu-id="79c77-436">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="79c77-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79c77-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-437">Checksum</span></span>

<span data-ttu-id="79c77-438">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-439">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-439">Definition</span></span>

<span data-ttu-id="79c77-440">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-441">La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-442">Se encuentra una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-442">A keyword from is found.</span></span>
    
<span data-ttu-id="79c77-443">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-444">La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-445">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="79c77-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="79c77-447">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="79c77-447">personal numeric code</span></span>
  
<span data-ttu-id="79c77-448">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="79c77-448">unique identification number</span></span>
  
<span data-ttu-id="79c77-449">número de servicio de ciudadanos</span><span class="sxs-lookup"><span data-stu-id="79c77-449">citizen service number</span></span>
  
<span data-ttu-id="79c77-450">número de identidad único</span><span class="sxs-lookup"><span data-stu-id="79c77-450">unique identity number</span></span>
  
<span data-ttu-id="79c77-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="79c77-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="79c77-452">BSN</span><span class="sxs-lookup"><span data-stu-id="79c77-452">bsn</span></span>
  
<span data-ttu-id="79c77-453">BSN #</span><span class="sxs-lookup"><span data-stu-id="79c77-453">bsn#</span></span>
  
<span data-ttu-id="79c77-454">persoonlijke numerieke código</span><span class="sxs-lookup"><span data-stu-id="79c77-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="79c77-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="79c77-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="79c77-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="79c77-456">burgerservicenummer</span></span>
  
<span data-ttu-id="79c77-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="79c77-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="79c77-458">Polonia</span><span class="sxs-lookup"><span data-stu-id="79c77-458">Poland</span></span>

<span data-ttu-id="79c77-459">Para obtener más información, consulte la sección "identificación nacional (PESEL) de Polonia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="79c77-460">Portugal</span><span class="sxs-lookup"><span data-stu-id="79c77-460">Portugal</span></span>

<span data-ttu-id="79c77-461">Para obtener más información, consulte la sección "número de tarjeta de ciudadano de Portugal" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="79c77-462">Rumania</span><span class="sxs-lookup"><span data-stu-id="79c77-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="79c77-463">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-463">Format</span></span>

<span data-ttu-id="79c77-464">13 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-465">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-465">Pattern</span></span>

<span data-ttu-id="79c77-466">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="79c77-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79c77-467">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-467">Checksum</span></span>

<span data-ttu-id="79c77-468">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-469">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-469">Definition</span></span>

<span data-ttu-id="79c77-470">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-471">La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-472">Se encuentra una `Keywords_romania_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-473">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-474">La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-475">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="79c77-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="79c77-477">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="79c77-477">personal numeric code</span></span>
  
<span data-ttu-id="79c77-478">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="79c77-478">unique identification number</span></span>
  
<span data-ttu-id="79c77-479">cnp</span><span class="sxs-lookup"><span data-stu-id="79c77-479">cnp</span></span>
  
<span data-ttu-id="79c77-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="79c77-480">cnp#</span></span>
  
<span data-ttu-id="79c77-481">patilla</span><span class="sxs-lookup"><span data-stu-id="79c77-481">pin</span></span>
  
<span data-ttu-id="79c77-482">patilla #</span><span class="sxs-lookup"><span data-stu-id="79c77-482">pin#</span></span>
  
<span data-ttu-id="79c77-483">número de seguro</span><span class="sxs-lookup"><span data-stu-id="79c77-483">insurance number</span></span>
  
<span data-ttu-id="79c77-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="79c77-484">insurancenumber#</span></span>
  
<span data-ttu-id="79c77-485">número de identidad único</span><span class="sxs-lookup"><span data-stu-id="79c77-485">unique identity number</span></span>
  
<span data-ttu-id="79c77-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="79c77-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="79c77-487">personal numérico de pago</span><span class="sxs-lookup"><span data-stu-id="79c77-487">cod numeric personal</span></span>
  
<span data-ttu-id="79c77-488">c.o.d. identificare personal</span><span class="sxs-lookup"><span data-stu-id="79c77-488">cod identificare personal</span></span>
  
<span data-ttu-id="79c77-489">Bacalao UNIC identificare</span><span class="sxs-lookup"><span data-stu-id="79c77-489">cod unic identificare</span></span>
  
<span data-ttu-id="79c77-490">număr personal UNIC</span><span class="sxs-lookup"><span data-stu-id="79c77-490">număr personal unic</span></span>
  
<span data-ttu-id="79c77-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="79c77-491">număr identitate</span></span>
  
<span data-ttu-id="79c77-492">număr identificare personal</span><span class="sxs-lookup"><span data-stu-id="79c77-492">număr identificare personal</span></span>
  
<span data-ttu-id="79c77-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="79c77-493">număridentitate#</span></span>
  
<span data-ttu-id="79c77-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="79c77-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="79c77-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="79c77-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="79c77-496">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="79c77-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="79c77-497">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-497">Format</span></span>

<span data-ttu-id="79c77-498">Diez dígitos que contienen una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="79c77-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-499">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-499">Pattern</span></span>

<span data-ttu-id="79c77-500">Diez dígitos que contienen una barra diagonal inversa:</span><span class="sxs-lookup"><span data-stu-id="79c77-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79c77-501">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-501">Checksum</span></span>

<span data-ttu-id="79c77-502">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-503">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-503">Definition</span></span>

<span data-ttu-id="79c77-504">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-505">La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-506">Se encuentra una `Keywords_slovakia_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-507">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-508">La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-509">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="79c77-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="79c77-511">número de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-511">birth number</span></span>
  
<span data-ttu-id="79c77-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="79c77-512">national identification number</span></span>
  
<span data-ttu-id="79c77-513">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-513">personal identification number</span></span>
  
<span data-ttu-id="79c77-514">social security number</span><span class="sxs-lookup"><span data-stu-id="79c77-514">social security number</span></span>
  
<span data-ttu-id="79c77-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="79c77-515">nationalnumber#</span></span>
  
<span data-ttu-id="79c77-516">SSN #</span><span class="sxs-lookup"><span data-stu-id="79c77-516">ssn#</span></span>
  
<span data-ttu-id="79c77-517">SSN</span><span class="sxs-lookup"><span data-stu-id="79c77-517">ssn</span></span>
  
<span data-ttu-id="79c77-518">número nacional</span><span class="sxs-lookup"><span data-stu-id="79c77-518">national number</span></span>
  
<span data-ttu-id="79c77-519">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-519">personal id number</span></span>
  
<span data-ttu-id="79c77-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="79c77-520">personalidnumber#</span></span>
  
<span data-ttu-id="79c77-521">rč</span><span class="sxs-lookup"><span data-stu-id="79c77-521">rč</span></span>
  
<span data-ttu-id="79c77-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="79c77-522">rodné číslo</span></span>
  
<span data-ttu-id="79c77-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="79c77-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="79c77-524">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="79c77-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="79c77-525">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-525">Format</span></span>

<span data-ttu-id="79c77-526">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="79c77-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-527">Pattern</span></span>

<span data-ttu-id="79c77-528">13 dígitos en el patrón especificado:</span><span class="sxs-lookup"><span data-stu-id="79c77-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="79c77-529">Siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL) donde "LLL" corresponde a los tres últimos dígitos del año de nacimiento.</span><span class="sxs-lookup"><span data-stu-id="79c77-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="79c77-530">Dos dígitos que corresponden al área de nacimiento</span><span class="sxs-lookup"><span data-stu-id="79c77-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="79c77-531">Tres dígitos que corresponden a una combinación de sexo y número de serie de las personas nacidos el mismo día (000-499 para macho y 500-999 para hembras)</span><span class="sxs-lookup"><span data-stu-id="79c77-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="79c77-532">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="79c77-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-533">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-533">Checksum</span></span>

<span data-ttu-id="79c77-534">Sí</span><span class="sxs-lookup"><span data-stu-id="79c77-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-535">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-535">Definition</span></span>

<span data-ttu-id="79c77-536">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-537">La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-538">Se encuentra una `Keywords_slovenia_eu_national_id_card` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="79c77-539">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-540">La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-541">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="79c77-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="79c77-543">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="79c77-543">personal numeric code</span></span>
  
<span data-ttu-id="79c77-544">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="79c77-544">unique identification number</span></span>
  
<span data-ttu-id="79c77-545">número de registro único</span><span class="sxs-lookup"><span data-stu-id="79c77-545">unique registration number</span></span>
  
<span data-ttu-id="79c77-546">número de identidad único</span><span class="sxs-lookup"><span data-stu-id="79c77-546">unique identity number</span></span>
  
<span data-ttu-id="79c77-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="79c77-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="79c77-548">número único de ciudadano principal</span><span class="sxs-lookup"><span data-stu-id="79c77-548">unique master citizen number</span></span>
  
<span data-ttu-id="79c77-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="79c77-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="79c77-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="79c77-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="79c77-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="79c77-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="79c77-552">emšo</span><span class="sxs-lookup"><span data-stu-id="79c77-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="79c77-553">España</span><span class="sxs-lookup"><span data-stu-id="79c77-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="79c77-554">Formato</span><span class="sxs-lookup"><span data-stu-id="79c77-554">Format</span></span>

<span data-ttu-id="79c77-555">Siete dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="79c77-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79c77-556">Patrón</span><span class="sxs-lookup"><span data-stu-id="79c77-556">Pattern</span></span>

<span data-ttu-id="79c77-557">Siete dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="79c77-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="79c77-558">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="79c77-558">Seven digits</span></span>
    
- <span data-ttu-id="79c77-559">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="79c77-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79c77-560">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="79c77-560">Checksum</span></span>

<span data-ttu-id="79c77-561">No aplicable</span><span class="sxs-lookup"><span data-stu-id="79c77-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79c77-562">Definición</span><span class="sxs-lookup"><span data-stu-id="79c77-562">Definition</span></span>

<span data-ttu-id="79c77-563">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="79c77-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79c77-564">La expresión `Regex_spain_eu_national_id_card` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="79c77-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79c77-565">Se encuentra una `Keywords_spain_eu_national_id_card"` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="79c77-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79c77-566">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79c77-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="79c77-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="79c77-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="79c77-568">DNI</span><span class="sxs-lookup"><span data-stu-id="79c77-568">dni</span></span>
  
<span data-ttu-id="79c77-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="79c77-569">national identification number</span></span>
  
<span data-ttu-id="79c77-570">número de identidad nacional</span><span class="sxs-lookup"><span data-stu-id="79c77-570">national identity number</span></span>
  
<span data-ttu-id="79c77-571">número de seguro</span><span class="sxs-lookup"><span data-stu-id="79c77-571">insurance number</span></span>
  
<span data-ttu-id="79c77-572">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="79c77-572">personal identification number</span></span>
  
<span data-ttu-id="79c77-573">identidad nacional</span><span class="sxs-lookup"><span data-stu-id="79c77-573">national identity</span></span>
  
<span data-ttu-id="79c77-574">número de la identidad personal</span><span class="sxs-lookup"><span data-stu-id="79c77-574">personal identity no</span></span>
  
<span data-ttu-id="79c77-575">número de identidad único</span><span class="sxs-lookup"><span data-stu-id="79c77-575">unique identity number</span></span>
  
<span data-ttu-id="79c77-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="79c77-576">nationalidno#</span></span>
  
<span data-ttu-id="79c77-577">UniqueID #</span><span class="sxs-lookup"><span data-stu-id="79c77-577">uniqueid#</span></span>
  
<span data-ttu-id="79c77-578">DNI #</span><span class="sxs-lookup"><span data-stu-id="79c77-578">dni#</span></span>
  
<span data-ttu-id="79c77-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="79c77-579">nationalid#</span></span>
  
<span data-ttu-id="79c77-580">NIE #</span><span class="sxs-lookup"><span data-stu-id="79c77-580">nie#</span></span>
  
<span data-ttu-id="79c77-581">NIE</span><span class="sxs-lookup"><span data-stu-id="79c77-581">nie</span></span>
  
<span data-ttu-id="79c77-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="79c77-582">nienúmero#</span></span>
  
<span data-ttu-id="79c77-583">NIE número</span><span class="sxs-lookup"><span data-stu-id="79c77-583">nie número</span></span>
  
<span data-ttu-id="79c77-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="79c77-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="79c77-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="79c77-585">identidad único</span></span>
  
<span data-ttu-id="79c77-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="79c77-586">número nacional identidad</span></span>
  
<span data-ttu-id="79c77-587">número de DNI</span><span class="sxs-lookup"><span data-stu-id="79c77-587">dni número</span></span>
  
<span data-ttu-id="79c77-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="79c77-588">dninúmero#</span></span>
  
<span data-ttu-id="79c77-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="79c77-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="79c77-590">Suecia</span><span class="sxs-lookup"><span data-stu-id="79c77-590">Sweden</span></span>

<span data-ttu-id="79c77-591">Para obtener más información, consulte la sección "identificación nacional de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79c77-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79c77-592">Vea también</span><span class="sxs-lookup"><span data-stu-id="79c77-592">See also</span></span>

[<span data-ttu-id="79c77-593">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="79c77-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

