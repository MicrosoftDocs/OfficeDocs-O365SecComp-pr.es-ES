---
title: Número de identificación de la UE nacional
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de número nacional de identificación de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536137"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="3d602-104">Número de identificación de la UE nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-104">EU National Identification Number</span></span>

<span data-ttu-id="3d602-p102">En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de número nacional de identificación de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="3d602-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3d602-107">Austria</span><span class="sxs-lookup"><span data-stu-id="3d602-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3d602-108">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-108">Format</span></span>

<span data-ttu-id="3d602-109">Una combinación de 24 caracteres de letras, números y caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="3d602-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-110">Pattern</span></span>

<span data-ttu-id="3d602-111">24 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-111">24 characters:</span></span>
  
-  <span data-ttu-id="3d602-112">22 letras (no distingue mayúsculas de minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más</span><span class="sxs-lookup"><span data-stu-id="3d602-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="3d602-113">(No distingue mayúsculas de minúsculas) de dos letras, dígitos, barras diagonales inversas, barras diagonales, signos más o signos igual</span><span class="sxs-lookup"><span data-stu-id="3d602-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-114">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-114">Checksum</span></span>

<span data-ttu-id="3d602-115">No aplicable</span><span class="sxs-lookup"><span data-stu-id="3d602-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-116">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-116">Definition</span></span>

<span data-ttu-id="3d602-117">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-118">La expresión regular `Regex_austria_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-119">Una palabra clave de `Keywords_austria_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3d602-120">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="3d602-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="3d602-122">número de identidad austriaco</span><span class="sxs-lookup"><span data-stu-id="3d602-122">austrian identity number</span></span>
  
<span data-ttu-id="3d602-123">número de identidad nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-123">national identity number</span></span>
  
<span data-ttu-id="3d602-124">número de identidad</span><span class="sxs-lookup"><span data-stu-id="3d602-124">identity number</span></span>
  
<span data-ttu-id="3d602-125">
national id</span><span class="sxs-lookup"><span data-stu-id="3d602-125">national id</span></span>
  
<span data-ttu-id="3d602-126">personalausweis República österreich</span><span class="sxs-lookup"><span data-stu-id="3d602-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="3d602-127">Bélgica</span><span class="sxs-lookup"><span data-stu-id="3d602-127">Belgium</span></span>

<span data-ttu-id="3d602-128">Para obtener información detallada, vea la sección "Número nacional de Bélgica" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="3d602-129">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="3d602-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3d602-130">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-130">Format</span></span>

<span data-ttu-id="3d602-131">Diez dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-132">Pattern</span></span>

<span data-ttu-id="3d602-133">Diez dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="3d602-134">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="3d602-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="3d602-135">Dos dígitos que se corresponden con el orden de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="3d602-136">Un dígito que corresponde al género: un dígito par para masculino y un dígito impar para hembra</span><span class="sxs-lookup"><span data-stu-id="3d602-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="3d602-137">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-138">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-138">Checksum</span></span>

<span data-ttu-id="3d602-139">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-140">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-140">Definition</span></span>

<span data-ttu-id="3d602-141">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-142">La función `Func_bulgaria_national_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-143">Una palabra clave de `Keywords_bulgaria_national_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="3d602-144">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-145">La función `Func_bulgaria_national_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-146">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="3d602-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="3d602-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="3d602-148">egn</span><span class="sxs-lookup"><span data-stu-id="3d602-148">egn</span></span>
  
<span data-ttu-id="3d602-149">egn #</span><span class="sxs-lookup"><span data-stu-id="3d602-149">egn#</span></span>
  
<span data-ttu-id="3d602-150">Búlgaro número nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-150">bulgarian national number</span></span>
  
<span data-ttu-id="3d602-151">número nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-151">national number</span></span>
  
<span data-ttu-id="3d602-152">social security number
</span><span class="sxs-lookup"><span data-stu-id="3d602-152">social security number</span></span>
  
<span data-ttu-id="3d602-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="3d602-153">nationalnumber#</span></span>
  
<span data-ttu-id="3d602-154">ssn #</span><span class="sxs-lookup"><span data-stu-id="3d602-154">ssn#</span></span>
  
<span data-ttu-id="3d602-155">ssn</span><span class="sxs-lookup"><span data-stu-id="3d602-155">ssn</span></span>
  
<span data-ttu-id="3d602-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="3d602-156">nationalnumber</span></span>
  
<span data-ttu-id="3d602-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="3d602-157">bnn#</span></span>
  
<span data-ttu-id="3d602-158">bnn</span><span class="sxs-lookup"><span data-stu-id="3d602-158">bnn</span></span>
  
<span data-ttu-id="3d602-159">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-159">personal id number</span></span>
  
<span data-ttu-id="3d602-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3d602-160">personalidnumber#</span></span>
  
<span data-ttu-id="3d602-161">ЕДИНЕН ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="3d602-161">единен граждански номер</span></span>
  
<span data-ttu-id="3d602-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="3d602-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="3d602-163">ЕГН</span><span class="sxs-lookup"><span data-stu-id="3d602-163">егн</span></span>
  
<span data-ttu-id="3d602-164">ЕГН #</span><span class="sxs-lookup"><span data-stu-id="3d602-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="3d602-165">Croacia</span><span class="sxs-lookup"><span data-stu-id="3d602-165">Croatia</span></span>

<span data-ttu-id="3d602-166">Para obtener información detallada, vea la sección "Número de identidad Croacia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="3d602-167">Chipre</span><span class="sxs-lookup"><span data-stu-id="3d602-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3d602-168">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-168">Format</span></span>

<span data-ttu-id="3d602-169">Diez dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-170">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-170">Pattern</span></span>

 <span data-ttu-id="3d602-171">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="3d602-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3d602-172">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-172">Checksum</span></span>

<span data-ttu-id="3d602-173">No aplicable</span><span class="sxs-lookup"><span data-stu-id="3d602-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-174">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-174">Definition</span></span>

<span data-ttu-id="3d602-175">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-176">La expresión regular `Regex_cyprus_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-177">Una palabra clave de `Keywords_cyprus_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3d602-178">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="3d602-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="3d602-180">número de identificador de tarjeta</span><span class="sxs-lookup"><span data-stu-id="3d602-180">id card number</span></span>
  
<span data-ttu-id="3d602-181">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-181">national identification number</span></span>
  
<span data-ttu-id="3d602-182">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-182">personal id number</span></span>
  
<span data-ttu-id="3d602-183">número de tarjeta de identidad</span><span class="sxs-lookup"><span data-stu-id="3d602-183">identity card number</span></span>
  
<span data-ttu-id="3d602-184">ΤΑΥΤΟΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="3d602-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="3d602-185">República Checa</span><span class="sxs-lookup"><span data-stu-id="3d602-185">Czech Republic</span></span>

<span data-ttu-id="3d602-186">Para obtener información detallada, vea la sección "Número nacional de identidad de checo" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="3d602-187">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="3d602-187">Denmark</span></span>

<span data-ttu-id="3d602-188">Para obtener información detallada, vea la sección "Número de identificación Personal de Dinamarca" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="3d602-189">Estonia</span><span class="sxs-lookup"><span data-stu-id="3d602-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3d602-190">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-190">Format</span></span>

<span data-ttu-id="3d602-191">11 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-192">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-192">Pattern</span></span>

<span data-ttu-id="3d602-193">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="3d602-193">11 digits:</span></span>
  
- <span data-ttu-id="3d602-194">Un dígito que corresponde al sexo y century de nacimiento (masculino número impar, número par femenino; 1-2: 19 century; 3-4: 20 century; 5-6: century 21)</span><span class="sxs-lookup"><span data-stu-id="3d602-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="3d602-195">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="3d602-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="3d602-196">Tres dígitos que se corresponden con un número de serie separación de nacimiento en la misma fecha de personas</span><span class="sxs-lookup"><span data-stu-id="3d602-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="3d602-197">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-198">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-198">Checksum</span></span>

<span data-ttu-id="3d602-199">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-200">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-200">Definition</span></span>

<span data-ttu-id="3d602-201">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-202">La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-203">Una palabra clave de `Keywords_estonia_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-204">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-205">La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-206">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="3d602-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="3d602-208">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-208">personal identification code</span></span>
  
<span data-ttu-id="3d602-209">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-209">personal identification number</span></span>
  
<span data-ttu-id="3d602-210">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-210">national identification number</span></span>
  
<span data-ttu-id="3d602-211">número nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-211">national number</span></span>
  
<span data-ttu-id="3d602-212">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-212">personal id number</span></span>
  
<span data-ttu-id="3d602-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3d602-213">personalidnumber#</span></span>
  
<span data-ttu-id="3d602-214">IK</span><span class="sxs-lookup"><span data-stu-id="3d602-214">ik</span></span>
  
<span data-ttu-id="3d602-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="3d602-215">isikukood</span></span>
  
<span data-ttu-id="3d602-216">identificador de kaart</span><span class="sxs-lookup"><span data-stu-id="3d602-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="3d602-217">Finlandia</span><span class="sxs-lookup"><span data-stu-id="3d602-217">Finland</span></span>

<span data-ttu-id="3d602-218">Para obtener información detallada, vea la sección "Finlandia nacional ID" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="3d602-219">Francia</span><span class="sxs-lookup"><span data-stu-id="3d602-219">France</span></span>

<span data-ttu-id="3d602-220">Para obtener información detallada, vea la sección "Francia nacional tarjeta de identificación (CNI)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3d602-221">Alemania</span><span class="sxs-lookup"><span data-stu-id="3d602-221">Germany</span></span>

<span data-ttu-id="3d602-222">Para obtener información detallada, vea la sección "Número de tarjeta de identidad de Alemania" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3d602-223">Grecia</span><span class="sxs-lookup"><span data-stu-id="3d602-223">Greece</span></span>

<span data-ttu-id="3d602-224">Para obtener información detallada, vea la sección "tarjeta de identificación nacional Grecia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="3d602-225">Hungría</span><span class="sxs-lookup"><span data-stu-id="3d602-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3d602-226">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-226">Format</span></span>

<span data-ttu-id="3d602-227">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="3d602-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-228">Pattern</span></span>

<span data-ttu-id="3d602-229">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="3d602-229">11 digits:</span></span>
  
-  <span data-ttu-id="3d602-230">Un dígito que corresponde al género (hombre de 1, 2-hembra, de otros números también son posibles para los ciudadanos nacidos antes de 1900 o los ciudadanos con posea doble)</span><span class="sxs-lookup"><span data-stu-id="3d602-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="3d602-231">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="3d602-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="3d602-232">Tres dígitos que se corresponden con un número de serie</span><span class="sxs-lookup"><span data-stu-id="3d602-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="3d602-233">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-234">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-234">Checksum</span></span>

<span data-ttu-id="3d602-235">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-236">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-236">Definition</span></span>

<span data-ttu-id="3d602-237">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-238">La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-239">Una palabra clave de `Keywords_hungary_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-240">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-241">La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-242">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="3d602-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="3d602-244">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-244">personal identification number</span></span>
  
<span data-ttu-id="3d602-245">identification number
</span><span class="sxs-lookup"><span data-stu-id="3d602-245">identification number</span></span>
  
<span data-ttu-id="3d602-246">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-246">personal id number</span></span>
  
<span data-ttu-id="3d602-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="3d602-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="3d602-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="3d602-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3d602-249">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-249">Format</span></span>

<span data-ttu-id="3d602-250">Una combinación de nueve caracteres de letras, dígitos y un espacio en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="3d602-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-251">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-251">Pattern</span></span>

<span data-ttu-id="3d602-252">Una combinación de nueve caracteres de letras, dígitos y un espacio en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="3d602-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="3d602-253">Desde 01 de enero de 2013 hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="3d602-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="3d602-254">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="3d602-254">Seven digits</span></span> 
    
- <span data-ttu-id="3d602-255">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-255">One check digit</span></span>
    
- <span data-ttu-id="3d602-256">Un espacio o la letra mayúscula "W" (se distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3d602-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="3d602-257">Antes de 01 de enero de 2013:</span><span class="sxs-lookup"><span data-stu-id="3d602-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="3d602-258">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="3d602-258">Seven digits</span></span> 
    
- <span data-ttu-id="3d602-259">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-259">One check digit</span></span>
    
- <span data-ttu-id="3d602-260">Un espacio o una letra mayúscula (distinguir mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3d602-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-261">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-261">Checksum</span></span>

<span data-ttu-id="3d602-262">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-263">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-263">Definition</span></span>

<span data-ttu-id="3d602-264">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-265">La función busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="3d602-266">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="3d602-266">A keyword from is found.</span></span>
    
<span data-ttu-id="3d602-267">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-268">La función busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-269">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="3d602-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="3d602-271">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="3d602-271">personal public service number</span></span>
  
<span data-ttu-id="3d602-272">PPS no</span><span class="sxs-lookup"><span data-stu-id="3d602-272">pps no</span></span>
  
<span data-ttu-id="3d602-273">número de ingresos y seguridad social</span><span class="sxs-lookup"><span data-stu-id="3d602-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="3d602-274">RSI no</span><span class="sxs-lookup"><span data-stu-id="3d602-274">rsi no</span></span>
  
<span data-ttu-id="3d602-275">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-275">personal identification number</span></span>
  
<span data-ttu-id="3d602-276">identification number
</span><span class="sxs-lookup"><span data-stu-id="3d602-276">identification number</span></span>
  
<span data-ttu-id="3d602-277">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-277">personal id number</span></span>
  
<span data-ttu-id="3d602-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="3d602-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="3d602-p103">uimh. PSP</span><span class="sxs-lookup"><span data-stu-id="3d602-p103">uimh. psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="3d602-281">Italia</span><span class="sxs-lookup"><span data-stu-id="3d602-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="3d602-282">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-282">Format</span></span>

<span data-ttu-id="3d602-283">Una combinación de 16 caracteres de letras y dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="3d602-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-284">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-284">Pattern</span></span>

<span data-ttu-id="3d602-285">Una combinación de 16 caracteres de letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="3d602-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="3d602-286">Tres letras que corresponden a los tres primeros consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="3d602-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="3d602-287">Tres letras que corresponden a la primera, tercera y cuarta consonantes en el nombre</span><span class="sxs-lookup"><span data-stu-id="3d602-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="3d602-288">Dos dígitos que corresponden a la última dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="3d602-289">Una letra que corresponde a la letra para el mes de nacimiento: letras se usan en orden alfabético, pero se usan sólo las letras A E, H, L, M, P, R a T (por lo tanto, es enero y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="3d602-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="3d602-290">Dos dígitos que se corresponden con el día del mes de nacimiento, con el fin de diferenciar entre sexos, 40 se agrega en el día de nacimiento para mujeres</span><span class="sxs-lookup"><span data-stu-id="3d602-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="3d602-291">Cuatro dígitos que se corresponde con el código de área específico para el ayuntamiento donde surgió la persona (códigos de todo el país se usan para países externas)</span><span class="sxs-lookup"><span data-stu-id="3d602-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="3d602-292">Un dígito de paridad</span><span class="sxs-lookup"><span data-stu-id="3d602-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-293">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-293">Checksum</span></span>

<span data-ttu-id="3d602-294">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-295">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-295">Definition</span></span>

<span data-ttu-id="3d602-296">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-297">La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-298">Una palabra clave de `Keywords_italy_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-299">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-300">La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-301">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="3d602-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="3d602-303">código personal</span><span class="sxs-lookup"><span data-stu-id="3d602-303">personal code</span></span>
  
<span data-ttu-id="3d602-304">número de código personal</span><span class="sxs-lookup"><span data-stu-id="3d602-304">personal code number</span></span>
  
<span data-ttu-id="3d602-305">número de certificado personal</span><span class="sxs-lookup"><span data-stu-id="3d602-305">personal certificate number</span></span>
  
<span data-ttu-id="3d602-306">código fiscal</span><span class="sxs-lookup"><span data-stu-id="3d602-306">fiscal code</span></span>
  
<span data-ttu-id="3d602-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="3d602-307">personalcodeno#</span></span>
  
<span data-ttu-id="3d602-308">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-308">personal id number</span></span>
  
<span data-ttu-id="3d602-309">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-309">personal id code</span></span>
  
<span data-ttu-id="3d602-310">Codice personale</span><span class="sxs-lookup"><span data-stu-id="3d602-310">codice personale</span></span>
  
<span data-ttu-id="3d602-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="3d602-311">numero certificato personale</span></span>
  
<span data-ttu-id="3d602-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="3d602-312">numero personale</span></span>
  
<span data-ttu-id="3d602-313">numero identificador personale</span><span class="sxs-lookup"><span data-stu-id="3d602-313">numero id personale</span></span>
  
<span data-ttu-id="3d602-314">Codice identificador personale</span><span class="sxs-lookup"><span data-stu-id="3d602-314">codice id personale</span></span>
  
<span data-ttu-id="3d602-315">Codice fiscale</span><span class="sxs-lookup"><span data-stu-id="3d602-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="3d602-316">Italia</span><span class="sxs-lookup"><span data-stu-id="3d602-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="3d602-317">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-317">Format</span></span>

<span data-ttu-id="3d602-318">de 11 dígitos y un guión en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="3d602-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-319">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-319">Pattern</span></span>

<span data-ttu-id="3d602-320">de 11 dígitos y un guión:</span><span class="sxs-lookup"><span data-stu-id="3d602-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="3d602-321">Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="3d602-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="3d602-322">Un guión </span><span class="sxs-lookup"><span data-stu-id="3d602-322">A hyphen</span></span>
    
- <span data-ttu-id="3d602-323">Un dígito que corresponde a la century de nacimiento ("0" para century 19, "1" para century 20 y "2" para century 21)</span><span class="sxs-lookup"><span data-stu-id="3d602-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="3d602-324">Cuatro dígitos, generadas de forma aleatoria</span><span class="sxs-lookup"><span data-stu-id="3d602-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-325">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-325">Checksum</span></span>

<span data-ttu-id="3d602-326">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-327">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-327">Definition</span></span>

<span data-ttu-id="3d602-328">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-329">La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-330">Una palabra clave de `Keywords_latvia_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-331">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-332">La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-333">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="3d602-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="3d602-335">código personal</span><span class="sxs-lookup"><span data-stu-id="3d602-335">personal code</span></span>
  
<span data-ttu-id="3d602-336">número de código personal</span><span class="sxs-lookup"><span data-stu-id="3d602-336">personal code number</span></span>
  
<span data-ttu-id="3d602-337">número de certificado personal</span><span class="sxs-lookup"><span data-stu-id="3d602-337">personal certificate number</span></span>
  
<span data-ttu-id="3d602-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="3d602-338">personalcodeno#</span></span>
  
<span data-ttu-id="3d602-339">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-339">personal id number</span></span>
  
<span data-ttu-id="3d602-340">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-340">personal id code</span></span>
  
<span data-ttu-id="3d602-341">kods roles</span><span class="sxs-lookup"><span data-stu-id="3d602-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="3d602-342">Lituania</span><span class="sxs-lookup"><span data-stu-id="3d602-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3d602-343">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-343">Format</span></span>

<span data-ttu-id="3d602-344">11 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-345">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-345">Pattern</span></span>

<span data-ttu-id="3d602-346">11 dígitos sin espacios y los delimitadores:</span><span class="sxs-lookup"><span data-stu-id="3d602-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="3d602-347">Un dígito que corresponde a la persona género y century de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="3d602-348">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="3d602-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="3d602-349">Tres dígitos que se corresponden con el número de serie de la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="3d602-350">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-351">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-351">Checksum</span></span>

<span data-ttu-id="3d602-352">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-353">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-353">Definition</span></span>

<span data-ttu-id="3d602-354">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-355">La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-356">Una palabra clave de `Keywords_lithuania_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-357">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-358">La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-359">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="3d602-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="3d602-361">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="3d602-361">personal numeric code</span></span>
  
<span data-ttu-id="3d602-362">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="3d602-362">unique identification number</span></span>
  
<span data-ttu-id="3d602-363">número de servicio de ciudadanos</span><span class="sxs-lookup"><span data-stu-id="3d602-363">citizen service number</span></span>
  
<span data-ttu-id="3d602-364">número de identidad única</span><span class="sxs-lookup"><span data-stu-id="3d602-364">unique identity number</span></span>
  
<span data-ttu-id="3d602-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="3d602-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="3d602-366">código personal.</span><span class="sxs-lookup"><span data-stu-id="3d602-366">personal code.</span></span>
  
<span data-ttu-id="3d602-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="3d602-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="3d602-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="3d602-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="3d602-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="3d602-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="3d602-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="3d602-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="3d602-371">asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="3d602-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="3d602-372">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="3d602-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3d602-373">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-373">Format</span></span>

<span data-ttu-id="3d602-374">11 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-375">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-375">Pattern</span></span>

<span data-ttu-id="3d602-376">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="3d602-376">11 digits</span></span>
  
- <span data-ttu-id="3d602-377">Un dígito que corresponde a la persona género y century de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="3d602-378">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="3d602-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="3d602-379">Tres dígitos que se corresponden con el número de serie de la fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="3d602-380">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-381">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-381">Checksum</span></span>

<span data-ttu-id="3d602-382">No aplicable</span><span class="sxs-lookup"><span data-stu-id="3d602-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-383">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-383">Definition</span></span>

<span data-ttu-id="3d602-384">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-385">La expresión regular `Regex_luxemburg_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-386">Una palabra clave de `Keywords_luxemburg_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3d602-387">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="3d602-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="3d602-389">identificador personal</span><span class="sxs-lookup"><span data-stu-id="3d602-389">personal id</span></span>
  
<span data-ttu-id="3d602-390">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-390">personal id number</span></span>
  
<span data-ttu-id="3d602-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="3d602-391">personalidno#</span></span>
  
<span data-ttu-id="3d602-392">número de identificador único</span><span class="sxs-lookup"><span data-stu-id="3d602-392">unique id number</span></span>
  
<span data-ttu-id="3d602-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3d602-393">personalidnumber#</span></span>
  
<span data-ttu-id="3d602-394">clave de identificador único</span><span class="sxs-lookup"><span data-stu-id="3d602-394">unique id key</span></span>
  
<span data-ttu-id="3d602-395">código de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-395">personal id code</span></span>
  
<span data-ttu-id="3d602-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="3d602-396">uniqueidkey#</span></span>
  
<span data-ttu-id="3d602-397">código individual</span><span class="sxs-lookup"><span data-stu-id="3d602-397">individual code</span></span>
  
<span data-ttu-id="3d602-398">identificador de individual</span><span class="sxs-lookup"><span data-stu-id="3d602-398">individual id</span></span>
  
<span data-ttu-id="3d602-399">identificador de eindeutige-nummer</span><span class="sxs-lookup"><span data-stu-id="3d602-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="3d602-400">identificador de eindeutige</span><span class="sxs-lookup"><span data-stu-id="3d602-400">eindeutige id</span></span>
  
<span data-ttu-id="3d602-401">identificador personal</span><span class="sxs-lookup"><span data-stu-id="3d602-401">id personnelle</span></span>
  
<span data-ttu-id="3d602-402">numéro de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="3d602-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="3d602-403">idpersonnelle#</span></span>
  
<span data-ttu-id="3d602-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="3d602-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="3d602-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="3d602-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="3d602-406">Malta</span><span class="sxs-lookup"><span data-stu-id="3d602-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3d602-407">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-407">Format</span></span>

<span data-ttu-id="3d602-408">Siete dígitos seguidos de una letra</span><span class="sxs-lookup"><span data-stu-id="3d602-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-409">Pattern</span></span>

<span data-ttu-id="3d602-410">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="3d602-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="3d602-411">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="3d602-411">Seven digits</span></span> 
    
- <span data-ttu-id="3d602-412">Una letra mayúscula (se distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3d602-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-413">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-413">Checksum</span></span>

<span data-ttu-id="3d602-414">No aplicable</span><span class="sxs-lookup"><span data-stu-id="3d602-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-415">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-415">Definition</span></span>

<span data-ttu-id="3d602-416">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-417">La expresión regular `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-418">Una palabra clave de `Keywords_malta_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-419">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-420">La expresión regular `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-421">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="3d602-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="3d602-423">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="3d602-423">personal numeric code</span></span>
  
<span data-ttu-id="3d602-424">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="3d602-424">unique identification number</span></span>
  
<span data-ttu-id="3d602-425">número de servicio de ciudadanos</span><span class="sxs-lookup"><span data-stu-id="3d602-425">citizen service number</span></span>
  
<span data-ttu-id="3d602-426">número de identidad única</span><span class="sxs-lookup"><span data-stu-id="3d602-426">unique identity number</span></span>
  
<span data-ttu-id="3d602-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="3d602-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="3d602-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="3d602-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="3d602-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="3d602-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="3d602-430">tareas servizz de numru taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="3d602-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="3d602-431">numru ta' identità uniku</span><span class="sxs-lookup"><span data-stu-id="3d602-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="3d602-432">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="3d602-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3d602-433">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-433">Format</span></span>

<span data-ttu-id="3d602-434">Nueve dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-435">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-435">Pattern</span></span>

<span data-ttu-id="3d602-436">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="3d602-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3d602-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-437">Checksum</span></span>

<span data-ttu-id="3d602-438">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-439">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-439">Definition</span></span>

<span data-ttu-id="3d602-440">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-441">La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-442">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="3d602-442">A keyword from is found.</span></span>
    
<span data-ttu-id="3d602-443">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-444">La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-445">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="3d602-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="3d602-447">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="3d602-447">personal numeric code</span></span>
  
<span data-ttu-id="3d602-448">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="3d602-448">unique identification number</span></span>
  
<span data-ttu-id="3d602-449">número de servicio de ciudadanos</span><span class="sxs-lookup"><span data-stu-id="3d602-449">citizen service number</span></span>
  
<span data-ttu-id="3d602-450">número de identidad única</span><span class="sxs-lookup"><span data-stu-id="3d602-450">unique identity number</span></span>
  
<span data-ttu-id="3d602-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="3d602-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="3d602-452">bsn</span><span class="sxs-lookup"><span data-stu-id="3d602-452">bsn</span></span>
  
<span data-ttu-id="3d602-453">bsn #</span><span class="sxs-lookup"><span data-stu-id="3d602-453">bsn#</span></span>
  
<span data-ttu-id="3d602-454">código de numerieke persoonlijke</span><span class="sxs-lookup"><span data-stu-id="3d602-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="3d602-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="3d602-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="3d602-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="3d602-456">burgerservicenummer</span></span>
  
<span data-ttu-id="3d602-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="3d602-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="3d602-458">Polonia</span><span class="sxs-lookup"><span data-stu-id="3d602-458">Poland</span></span>

<span data-ttu-id="3d602-459">Para obtener información detallada, vea la sección "Polonia nacional identificador (PESEL)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="3d602-460">Portugal</span><span class="sxs-lookup"><span data-stu-id="3d602-460">Portugal</span></span>

<span data-ttu-id="3d602-461">Para obtener información detallada, vea la sección "Número de tarjeta de Portugal ciudadanos" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="3d602-462">Rumania</span><span class="sxs-lookup"><span data-stu-id="3d602-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3d602-463">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-463">Format</span></span>

<span data-ttu-id="3d602-464">13 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-465">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-465">Pattern</span></span>

<span data-ttu-id="3d602-466">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="3d602-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3d602-467">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-467">Checksum</span></span>

<span data-ttu-id="3d602-468">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-469">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-469">Definition</span></span>

<span data-ttu-id="3d602-470">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-471">La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-472">Una palabra clave de `Keywords_romania_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-473">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-474">La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-475">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="3d602-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="3d602-477">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="3d602-477">personal numeric code</span></span>
  
<span data-ttu-id="3d602-478">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="3d602-478">unique identification number</span></span>
  
<span data-ttu-id="3d602-479">cnp</span><span class="sxs-lookup"><span data-stu-id="3d602-479">cnp</span></span>
  
<span data-ttu-id="3d602-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="3d602-480">cnp#</span></span>
  
<span data-ttu-id="3d602-481">anclar</span><span class="sxs-lookup"><span data-stu-id="3d602-481">pin</span></span>
  
<span data-ttu-id="3d602-482">PIN #</span><span class="sxs-lookup"><span data-stu-id="3d602-482">pin#</span></span>
  
<span data-ttu-id="3d602-483">número de seguro</span><span class="sxs-lookup"><span data-stu-id="3d602-483">insurance number</span></span>
  
<span data-ttu-id="3d602-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="3d602-484">insurancenumber#</span></span>
  
<span data-ttu-id="3d602-485">número de identidad única</span><span class="sxs-lookup"><span data-stu-id="3d602-485">unique identity number</span></span>
  
<span data-ttu-id="3d602-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="3d602-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="3d602-487">COD numérico personal</span><span class="sxs-lookup"><span data-stu-id="3d602-487">cod numeric personal</span></span>
  
<span data-ttu-id="3d602-488">bacalao identificare personal</span><span class="sxs-lookup"><span data-stu-id="3d602-488">cod identificare personal</span></span>
  
<span data-ttu-id="3d602-489">COD unic identificare</span><span class="sxs-lookup"><span data-stu-id="3d602-489">cod unic identificare</span></span>
  
<span data-ttu-id="3d602-490">număr personal unic</span><span class="sxs-lookup"><span data-stu-id="3d602-490">număr personal unic</span></span>
  
<span data-ttu-id="3d602-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="3d602-491">număr identitate</span></span>
  
<span data-ttu-id="3d602-492">număr identificare personal</span><span class="sxs-lookup"><span data-stu-id="3d602-492">număr identificare personal</span></span>
  
<span data-ttu-id="3d602-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="3d602-493">număridentitate#</span></span>
  
<span data-ttu-id="3d602-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="3d602-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="3d602-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="3d602-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="3d602-496">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="3d602-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3d602-497">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-497">Format</span></span>

<span data-ttu-id="3d602-498">Diez dígitos que contiene una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="3d602-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-499">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-499">Pattern</span></span>

<span data-ttu-id="3d602-500">Diez dígitos que contiene una barra diagonal inversa:</span><span class="sxs-lookup"><span data-stu-id="3d602-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3d602-501">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-501">Checksum</span></span>

<span data-ttu-id="3d602-502">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-503">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-503">Definition</span></span>

<span data-ttu-id="3d602-504">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-505">La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-506">Una palabra clave de `Keywords_slovakia_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-507">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-508">La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-509">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="3d602-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="3d602-511">número de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-511">birth number</span></span>
  
<span data-ttu-id="3d602-512">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-512">national identification number</span></span>
  
<span data-ttu-id="3d602-513">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-513">personal identification number</span></span>
  
<span data-ttu-id="3d602-514">social security number
</span><span class="sxs-lookup"><span data-stu-id="3d602-514">social security number</span></span>
  
<span data-ttu-id="3d602-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="3d602-515">nationalnumber#</span></span>
  
<span data-ttu-id="3d602-516">ssn #</span><span class="sxs-lookup"><span data-stu-id="3d602-516">ssn#</span></span>
  
<span data-ttu-id="3d602-517">ssn</span><span class="sxs-lookup"><span data-stu-id="3d602-517">ssn</span></span>
  
<span data-ttu-id="3d602-518">número nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-518">national number</span></span>
  
<span data-ttu-id="3d602-519">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-519">personal id number</span></span>
  
<span data-ttu-id="3d602-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3d602-520">personalidnumber#</span></span>
  
<span data-ttu-id="3d602-521">rč</span><span class="sxs-lookup"><span data-stu-id="3d602-521">rč</span></span>
  
<span data-ttu-id="3d602-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="3d602-522">rodné číslo</span></span>
  
<span data-ttu-id="3d602-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="3d602-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="3d602-524">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="3d602-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3d602-525">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-525">Format</span></span>

<span data-ttu-id="3d602-526">13 dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="3d602-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-527">Pattern</span></span>

<span data-ttu-id="3d602-528">13 dígitos en el patrón especificado:</span><span class="sxs-lookup"><span data-stu-id="3d602-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="3d602-529">Siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL), donde "LLL" corresponde a la última tres dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="3d602-530">Dos dígitos que se corresponden con el área de nacimiento</span><span class="sxs-lookup"><span data-stu-id="3d602-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="3d602-531">Tres dígitos que se corresponden con una combinación de género y número de serie para las personas nacidas en el mismo día (000-499 para hombre) y 500-999 para hembra</span><span class="sxs-lookup"><span data-stu-id="3d602-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="3d602-532">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="3d602-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-533">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-533">Checksum</span></span>

<span data-ttu-id="3d602-534">Sí</span><span class="sxs-lookup"><span data-stu-id="3d602-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-535">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-535">Definition</span></span>

<span data-ttu-id="3d602-536">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-537">La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-538">Una palabra clave de `Keywords_slovenia_eu_national_id_card` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="3d602-539">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-540">La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3d602-541">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="3d602-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="3d602-543">código numérico personal</span><span class="sxs-lookup"><span data-stu-id="3d602-543">personal numeric code</span></span>
  
<span data-ttu-id="3d602-544">número de identificación único</span><span class="sxs-lookup"><span data-stu-id="3d602-544">unique identification number</span></span>
  
<span data-ttu-id="3d602-545">número de registro único</span><span class="sxs-lookup"><span data-stu-id="3d602-545">unique registration number</span></span>
  
<span data-ttu-id="3d602-546">número de identidad única</span><span class="sxs-lookup"><span data-stu-id="3d602-546">unique identity number</span></span>
  
<span data-ttu-id="3d602-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="3d602-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="3d602-548">número único ciudadanos maestra</span><span class="sxs-lookup"><span data-stu-id="3d602-548">unique master citizen number</span></span>
  
<span data-ttu-id="3d602-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="3d602-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="3d602-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="3d602-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="3d602-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="3d602-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="3d602-552">emšo</span><span class="sxs-lookup"><span data-stu-id="3d602-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="3d602-553">España</span><span class="sxs-lookup"><span data-stu-id="3d602-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3d602-554">Formato</span><span class="sxs-lookup"><span data-stu-id="3d602-554">Format</span></span>

<span data-ttu-id="3d602-555">Siete dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="3d602-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3d602-556">Patrón</span><span class="sxs-lookup"><span data-stu-id="3d602-556">Pattern</span></span>

<span data-ttu-id="3d602-557">Siete dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="3d602-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="3d602-558">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="3d602-558">Seven digits</span></span>
    
- <span data-ttu-id="3d602-559">Un dígito o letra (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3d602-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3d602-560">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="3d602-560">Checksum</span></span>

<span data-ttu-id="3d602-561">No aplicable</span><span class="sxs-lookup"><span data-stu-id="3d602-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3d602-562">Definición</span><span class="sxs-lookup"><span data-stu-id="3d602-562">Definition</span></span>

<span data-ttu-id="3d602-563">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3d602-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3d602-564">La expresión regular `Regex_spain_eu_national_id_card` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="3d602-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3d602-565">Una palabra clave de `Keywords_spain_eu_national_id_card"` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3d602-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3d602-566">Keywords</span><span class="sxs-lookup"><span data-stu-id="3d602-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="3d602-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="3d602-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="3d602-568">DNI</span><span class="sxs-lookup"><span data-stu-id="3d602-568">dni</span></span>
  
<span data-ttu-id="3d602-569">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-569">national identification number</span></span>
  
<span data-ttu-id="3d602-570">número de identidad nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-570">national identity number</span></span>
  
<span data-ttu-id="3d602-571">número de seguro</span><span class="sxs-lookup"><span data-stu-id="3d602-571">insurance number</span></span>
  
<span data-ttu-id="3d602-572">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="3d602-572">personal identification number</span></span>
  
<span data-ttu-id="3d602-573">identidad nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-573">national identity</span></span>
  
<span data-ttu-id="3d602-574">identidad personal no</span><span class="sxs-lookup"><span data-stu-id="3d602-574">personal identity no</span></span>
  
<span data-ttu-id="3d602-575">número de identidad única</span><span class="sxs-lookup"><span data-stu-id="3d602-575">unique identity number</span></span>
  
<span data-ttu-id="3d602-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="3d602-576">nationalidno#</span></span>
  
<span data-ttu-id="3d602-577">UniqueID #</span><span class="sxs-lookup"><span data-stu-id="3d602-577">uniqueid#</span></span>
  
<span data-ttu-id="3d602-578">DNI #</span><span class="sxs-lookup"><span data-stu-id="3d602-578">dni#</span></span>
  
<span data-ttu-id="3d602-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="3d602-579">nationalid#</span></span>
  
<span data-ttu-id="3d602-580">NIE #</span><span class="sxs-lookup"><span data-stu-id="3d602-580">nie#</span></span>
  
<span data-ttu-id="3d602-581">NIE</span><span class="sxs-lookup"><span data-stu-id="3d602-581">nie</span></span>
  
<span data-ttu-id="3d602-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="3d602-582">nienúmero#</span></span>
  
<span data-ttu-id="3d602-583">número de NIE</span><span class="sxs-lookup"><span data-stu-id="3d602-583">nie número</span></span>
  
<span data-ttu-id="3d602-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="3d602-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="3d602-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="3d602-585">identidad único</span></span>
  
<span data-ttu-id="3d602-586">identidad de número nacional</span><span class="sxs-lookup"><span data-stu-id="3d602-586">número nacional identidad</span></span>
  
<span data-ttu-id="3d602-587">número de DNI</span><span class="sxs-lookup"><span data-stu-id="3d602-587">dni número</span></span>
  
<span data-ttu-id="3d602-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="3d602-588">dninúmero#</span></span>
  
<span data-ttu-id="3d602-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="3d602-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="3d602-590">Suecia</span><span class="sxs-lookup"><span data-stu-id="3d602-590">Sweden</span></span>

<span data-ttu-id="3d602-591">Para obtener información detallada, vea la sección "Suecia nacional ID" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3d602-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d602-592">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d602-592">See also</span></span>

[<span data-ttu-id="3d602-593">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="3d602-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

