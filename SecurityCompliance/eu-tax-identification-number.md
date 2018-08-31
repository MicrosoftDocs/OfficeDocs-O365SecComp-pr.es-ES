---
title: Número de identificación fiscal de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial del número de identificación de impuestos de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536170"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="53387-104">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="53387-104">EU Tax Identification Number</span></span>

<span data-ttu-id="53387-p102">En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial del número de identificación fiscal (TIN) de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="53387-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="53387-107">Austria</span><span class="sxs-lookup"><span data-stu-id="53387-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="53387-108">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-108">Format</span></span>

<span data-ttu-id="53387-109">Nueve dígitos con guión opcional y barra diagonal</span><span class="sxs-lookup"><span data-stu-id="53387-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-110">Pattern</span></span>

<span data-ttu-id="53387-111">Nueve dígitos con guión opcional y barra diagonal hacia delante:</span><span class="sxs-lookup"><span data-stu-id="53387-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="53387-112">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-112">Two digits</span></span> 
    
- <span data-ttu-id="53387-113">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="53387-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="53387-114">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-114">Three digits</span></span>
    
- <span data-ttu-id="53387-115">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="53387-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="53387-116">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-117">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-117">Checksum</span></span>

<span data-ttu-id="53387-118">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-119">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-119">Definition</span></span>

<span data-ttu-id="53387-120">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-121">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-122">Una palabra clave de `Keywords_austria_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-123">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-124">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-125">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="53387-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="53387-127">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-127">tax number</span></span>
  
<span data-ttu-id="53387-128">número</span><span class="sxs-lookup"><span data-stu-id="53387-128">number</span></span>
  
<span data-ttu-id="53387-129">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-129">tax registration number</span></span>
  
<span data-ttu-id="53387-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-130">tax id</span></span>
  
<span data-ttu-id="53387-131">St.nr.</span><span class="sxs-lookup"><span data-stu-id="53387-131">st.nr.</span></span>
  
<span data-ttu-id="53387-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="53387-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="53387-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="53387-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="53387-134">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-134">Format</span></span>

<span data-ttu-id="53387-135">11 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-136">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-136">Pattern</span></span>

<span data-ttu-id="53387-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="53387-137">11 digits:</span></span>
  
- <span data-ttu-id="53387-138">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-138">Two digits</span></span>
    
- <span data-ttu-id="53387-139">Un "0" o "1"</span><span class="sxs-lookup"><span data-stu-id="53387-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="53387-140">Un dígito</span><span class="sxs-lookup"><span data-stu-id="53387-140">One digit</span></span>
    
- <span data-ttu-id="53387-141">Un "0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="53387-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="53387-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-143">Checksum</span></span>

<span data-ttu-id="53387-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-145">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-145">Definition</span></span>

<span data-ttu-id="53387-146">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-147">La expresión regular `Regex_belgium_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-148">Una palabra clave de `Keywords_belgium_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-149">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="53387-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="53387-151">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-151">tax number</span></span>
  
<span data-ttu-id="53387-152">número de registro nacional</span><span class="sxs-lookup"><span data-stu-id="53387-152">national registration number</span></span>
  
<span data-ttu-id="53387-153">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-153">tax registration number</span></span>
  
<span data-ttu-id="53387-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-154">tax id</span></span>
  
<span data-ttu-id="53387-155">NIF</span><span class="sxs-lookup"><span data-stu-id="53387-155">nif</span></span>
  
<span data-ttu-id="53387-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="53387-156">nif#</span></span>
  
<span data-ttu-id="53387-157">numéro de registre nacional</span><span class="sxs-lookup"><span data-stu-id="53387-157">numéro de registre national</span></span>
  
<span data-ttu-id="53387-158">numéro de identificación fiscale</span><span class="sxs-lookup"><span data-stu-id="53387-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="53387-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="53387-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="53387-160">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-160">Format</span></span>

<span data-ttu-id="53387-161">Diez dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-162">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-162">Pattern</span></span>

<span data-ttu-id="53387-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-164">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-164">Checksum</span></span>

<span data-ttu-id="53387-165">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-166">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-166">Definition</span></span>

<span data-ttu-id="53387-167">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-168">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-169">Una palabra clave de `Keywords_bulgaria_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-170">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-171">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-172">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="53387-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="53387-174">bucn</span><span class="sxs-lookup"><span data-stu-id="53387-174">bucn</span></span>
  
<span data-ttu-id="53387-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="53387-175">uniform civil number</span></span>
  
<span data-ttu-id="53387-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="53387-176">bucn#</span></span>
  
<span data-ttu-id="53387-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="53387-178">identificador uniforme de civil</span><span class="sxs-lookup"><span data-stu-id="53387-178">uniform civil id</span></span>
  
<span data-ttu-id="53387-179">no civil uniforme</span><span class="sxs-lookup"><span data-stu-id="53387-179">uniform civil no</span></span>
  
<span data-ttu-id="53387-180">egn</span><span class="sxs-lookup"><span data-stu-id="53387-180">egn</span></span>
  
<span data-ttu-id="53387-181">número civil uniforme búlgaro</span><span class="sxs-lookup"><span data-stu-id="53387-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="53387-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="53387-182">uniformcivilno#</span></span>
  
<span data-ttu-id="53387-183">egn #</span><span class="sxs-lookup"><span data-stu-id="53387-183">egn#</span></span>
  
<span data-ttu-id="53387-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="53387-184">униформ граждански номер</span></span>
  
<span data-ttu-id="53387-185">Identificador de униформ</span><span class="sxs-lookup"><span data-stu-id="53387-185">униформ id</span></span>
  
<span data-ttu-id="53387-186">Identificador граждански униформ</span><span class="sxs-lookup"><span data-stu-id="53387-186">униформ граждански id</span></span>
  
<span data-ttu-id="53387-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="53387-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="53387-188">Croacia</span><span class="sxs-lookup"><span data-stu-id="53387-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="53387-189">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-189">Format</span></span>

<span data-ttu-id="53387-190">11 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-191">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-191">Pattern</span></span>

<span data-ttu-id="53387-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="53387-192">11 digits:</span></span>
  
- <span data-ttu-id="53387-193">Diez dígitos, elegidos de manera aleatoria</span><span class="sxs-lookup"><span data-stu-id="53387-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="53387-194">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="53387-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-195">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-195">Checksum</span></span>

<span data-ttu-id="53387-196">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-197">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-197">Definition</span></span>

<span data-ttu-id="53387-198">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-199">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-200">Una palabra clave de `Keywords_croatia_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-201">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-202">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-203">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="53387-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="53387-205">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-205">tax number</span></span>
  
<span data-ttu-id="53387-206">impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-206">tax</span></span>
  
<span data-ttu-id="53387-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-207">tax id</span></span>
  
<span data-ttu-id="53387-208">OID</span><span class="sxs-lookup"><span data-stu-id="53387-208">oid</span></span>
  
<span data-ttu-id="53387-209">OID #</span><span class="sxs-lookup"><span data-stu-id="53387-209">oid#</span></span>
  
<span data-ttu-id="53387-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="53387-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="53387-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="53387-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="53387-212">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-212">Format</span></span>

<span data-ttu-id="53387-213">Ocho dígitos y una carta en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="53387-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-214">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-214">Pattern</span></span>

<span data-ttu-id="53387-215">Ocho dígitos y una carta:</span><span class="sxs-lookup"><span data-stu-id="53387-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="53387-216">UN "0"</span><span class="sxs-lookup"><span data-stu-id="53387-216">A "0"</span></span> 
    
- <span data-ttu-id="53387-217">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="53387-217">Seven digits</span></span>
    
- <span data-ttu-id="53387-218">Una letra (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-219">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-219">Checksum</span></span>

<span data-ttu-id="53387-220">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-221">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-221">Definition</span></span>

<span data-ttu-id="53387-222">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-223">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-224">Una palabra clave de `Keywords_cyprus_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-226">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-227">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="53387-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="53387-229">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-229">tax number</span></span>
  
<span data-ttu-id="53387-230">impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-230">tax</span></span>
  
<span data-ttu-id="53387-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-231">tax id</span></span>
  
<span data-ttu-id="53387-232">código de identificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-232">tax identification code</span></span>
  
<span data-ttu-id="53387-233">TIC</span><span class="sxs-lookup"><span data-stu-id="53387-233">tic</span></span>
  
<span data-ttu-id="53387-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="53387-234">tic#</span></span>
  
<span data-ttu-id="53387-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="53387-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="53387-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="53387-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="53387-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="53387-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="53387-238">República Checa</span><span class="sxs-lookup"><span data-stu-id="53387-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="53387-239">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-239">Format</span></span>

<span data-ttu-id="53387-240">Nueve o diez dígitos con una barra diagonal inversa opcional</span><span class="sxs-lookup"><span data-stu-id="53387-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-241">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-241">Pattern</span></span>

<span data-ttu-id="53387-242">Nueve o diez dígitos con un backslashl opcional:</span><span class="sxs-lookup"><span data-stu-id="53387-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="53387-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-243">Six digits</span></span> 
    
- <span data-ttu-id="53387-244">Una barra diagonal inversa (opcional)</span><span class="sxs-lookup"><span data-stu-id="53387-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="53387-245">Tres o cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-246">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-246">Checksum</span></span>

<span data-ttu-id="53387-247">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-248">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-248">Definition</span></span>

<span data-ttu-id="53387-249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-250">La expresión regular `Regex_czech_republic_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-251">Una palabra clave de `Keywords_czech_republic_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-252">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="53387-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="53387-254">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-254">tax number</span></span>
  
<span data-ttu-id="53387-255">impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-255">tax</span></span>
  
<span data-ttu-id="53387-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-256">tax id</span></span>
  
<span data-ttu-id="53387-257">número de personal</span><span class="sxs-lookup"><span data-stu-id="53387-257">personal number</span></span>
  
<span data-ttu-id="53387-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="53387-258">daňové číslo</span></span>
  
<span data-ttu-id="53387-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="53387-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="53387-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="53387-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="53387-261">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-261">Format</span></span>

<span data-ttu-id="53387-262">Diez dígitos que contiene un guión</span><span class="sxs-lookup"><span data-stu-id="53387-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-263">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-263">Pattern</span></span>

<span data-ttu-id="53387-264">Diez dígitos que contiene un hyphenl:</span><span class="sxs-lookup"><span data-stu-id="53387-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="53387-265">Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="53387-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="53387-266">Un guión </span><span class="sxs-lookup"><span data-stu-id="53387-266">A hyphen</span></span>
    
- <span data-ttu-id="53387-267">Cuatro dígitos que se corresponden con un número de secuencia donde el primer dígito corresponde a la century de nacimiento y el último dígito corresponde al género del individuo (impar para hombre e incluso para hembra)</span><span class="sxs-lookup"><span data-stu-id="53387-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-268">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-268">Checksum</span></span>

<span data-ttu-id="53387-269">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-270">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-270">Definition</span></span>

<span data-ttu-id="53387-271">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-272">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-273">Una palabra clave de `Keywords_denmark_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-275">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-276">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="53387-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="53387-278">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-278">tax number</span></span>
  
<span data-ttu-id="53387-279">impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-279">tax</span></span>
  
<span data-ttu-id="53387-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-280">tax id</span></span>
  
<span data-ttu-id="53387-281">número de rcp</span><span class="sxs-lookup"><span data-stu-id="53387-281">cpr number</span></span>
  
<span data-ttu-id="53387-282">rcp #</span><span class="sxs-lookup"><span data-stu-id="53387-282">cpr#</span></span>
  
<span data-ttu-id="53387-283">Skat nummer</span><span class="sxs-lookup"><span data-stu-id="53387-283">skat nummer</span></span>
  
<span data-ttu-id="53387-284">identificador de Skat</span><span class="sxs-lookup"><span data-stu-id="53387-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="53387-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="53387-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="53387-286">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-286">Format</span></span>

<span data-ttu-id="53387-287">11 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-288">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-288">Pattern</span></span>

<span data-ttu-id="53387-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="53387-289">11 digits:</span></span>
  
-  <span data-ttu-id="53387-290">Un dígito que corresponde al género y century de nacimiento donde un número impar indica masculino y el número par indica hembra de la siguiente manera: 1, 2 para el century 19; 3, 4 para el vigésimo century; y 5, 6 para el century 21</span><span class="sxs-lookup"><span data-stu-id="53387-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="53387-291">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="53387-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="53387-292">Tres dígitos que se corresponden con un número de serie separación de nacimiento en la misma fecha de personas</span><span class="sxs-lookup"><span data-stu-id="53387-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="53387-293">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="53387-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-294">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-294">Checksum</span></span>

<span data-ttu-id="53387-295">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-296">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-296">Definition</span></span>

<span data-ttu-id="53387-297">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-298">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-299">Una palabra clave de `Keywords_estonia_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-300">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-301">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-302">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="53387-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="53387-304">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-304">tax number</span></span>
  
<span data-ttu-id="53387-305">impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-305">tax</span></span>
  
<span data-ttu-id="53387-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-306">tax id</span></span>
  
<span data-ttu-id="53387-307">código personal</span><span class="sxs-lookup"><span data-stu-id="53387-307">personal code</span></span>
  
<span data-ttu-id="53387-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="53387-308">maksunumber</span></span>
  
<span data-ttu-id="53387-309">identificador de maksu</span><span class="sxs-lookup"><span data-stu-id="53387-309">maksu id</span></span>
  
<span data-ttu-id="53387-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="53387-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="53387-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="53387-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="53387-312">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-312">Format</span></span>

<span data-ttu-id="53387-313">Una combinación de 11 caracteres de dígitos, letras, y más y menos de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="53387-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-314">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-314">Pattern</span></span>

<span data-ttu-id="53387-315">Una combinación de 11 caracteres de dígitos, letras, y más y menos de inicio de sesión:</span><span class="sxs-lookup"><span data-stu-id="53387-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="53387-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-316">Six digits</span></span>
    
- <span data-ttu-id="53387-317">Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distinguir mayúsculas de minúsculas), donde el signo más significa nacimiento entre 1800-1899, el signo menos iniciar sesión significa nacimiento entre 1900-1999 y "A" significa nacida 2000 y posterior</span><span class="sxs-lookup"><span data-stu-id="53387-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="53387-318">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-318">Three digits</span></span>
    
- <span data-ttu-id="53387-319">Una letra o un número</span><span class="sxs-lookup"><span data-stu-id="53387-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-320">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-320">Checksum</span></span>

<span data-ttu-id="53387-321">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-322">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-322">Definition</span></span>

<span data-ttu-id="53387-323">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-324">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-325">Una palabra clave de `Keywords_finland_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-326">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-327">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-328">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="53387-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="53387-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="53387-330">identification number</span></span>
  
<span data-ttu-id="53387-331">identificador personal</span><span class="sxs-lookup"><span data-stu-id="53387-331">personal id</span></span>
  
<span data-ttu-id="53387-332">número de identidad</span><span class="sxs-lookup"><span data-stu-id="53387-332">identity number</span></span>
  
<span data-ttu-id="53387-333">número de identificación nacional finlandés</span><span class="sxs-lookup"><span data-stu-id="53387-333">finnish national id number</span></span>
  
<span data-ttu-id="53387-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-334">personalidnumber#</span></span>
  
<span data-ttu-id="53387-335">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="53387-335">national identification number</span></span>
  
<span data-ttu-id="53387-336">número de Id.</span><span class="sxs-lookup"><span data-stu-id="53387-336">id number</span></span>
  
<span data-ttu-id="53387-337">identificador de nacional no.</span><span class="sxs-lookup"><span data-stu-id="53387-337">national id no.</span></span>
  
<span data-ttu-id="53387-338">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="53387-338">national id number</span></span>
  
<span data-ttu-id="53387-339">identificador de ningún</span><span class="sxs-lookup"><span data-stu-id="53387-339">id no</span></span>
  
<span data-ttu-id="53387-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="53387-340">tunnistenumero</span></span>
  
<span data-ttu-id="53387-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="53387-341">henkilötunnus</span></span>
  
<span data-ttu-id="53387-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="53387-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="53387-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="53387-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="53387-344">numero de identiteetti</span><span class="sxs-lookup"><span data-stu-id="53387-344">identiteetti numero</span></span>
  
<span data-ttu-id="53387-345">Suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="53387-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="53387-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="53387-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="53387-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="53387-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="53387-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="53387-348">tunnusnumero</span></span>
  
<span data-ttu-id="53387-349">numero de tunnus kansallinen</span><span class="sxs-lookup"><span data-stu-id="53387-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="53387-350">Francia</span><span class="sxs-lookup"><span data-stu-id="53387-350">France</span></span>

### <a name="format"></a><span data-ttu-id="53387-351">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-351">Format</span></span>

<span data-ttu-id="53387-352">13 dígitos para individuos y nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="53387-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-353">Pattern</span></span>

<span data-ttu-id="53387-354">13 dígitos para las personas:</span><span class="sxs-lookup"><span data-stu-id="53387-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="53387-355">Un dígito que debe ser 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="53387-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="53387-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-356">12 digits</span></span>
    
<span data-ttu-id="53387-357">Nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="53387-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-358">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-358">Checksum</span></span>

<span data-ttu-id="53387-359">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-360">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-360">Definition</span></span>

<span data-ttu-id="53387-361">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-362">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-363">Una palabra clave de `Keywords_france_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-365">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-366">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="53387-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="53387-368">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-368">tax identification number</span></span>
  
<span data-ttu-id="53387-369">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-369">tax number</span></span>
  
<span data-ttu-id="53387-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-370">tax id</span></span>
  
<span data-ttu-id="53387-371">numéro de identificación fiscale</span><span class="sxs-lookup"><span data-stu-id="53387-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="53387-372">Alemania</span><span class="sxs-lookup"><span data-stu-id="53387-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="53387-373">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-373">Format</span></span>

<span data-ttu-id="53387-374">11 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-375">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-375">Pattern</span></span>

<span data-ttu-id="53387-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="53387-376">11 digits :</span></span>
  
-  <span data-ttu-id="53387-377">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-377">Ten digits</span></span> 
    
- <span data-ttu-id="53387-378">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="53387-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-379">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-379">Checksum</span></span>

<span data-ttu-id="53387-380">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-381">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-381">Definition</span></span>

<span data-ttu-id="53387-382">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-383">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-384">Una palabra clave de `Keywords_germany_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-385">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-386">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-387">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="53387-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="53387-389">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-389">tax number</span></span>
  
<span data-ttu-id="53387-390">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-390">tax no.</span></span>
  
<span data-ttu-id="53387-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-391">taxno#</span></span>
  
<span data-ttu-id="53387-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-392">taxnumber#</span></span>
  
<span data-ttu-id="53387-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-393">taxnumber</span></span>
  
<span data-ttu-id="53387-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-394">tax id</span></span>
  
<span data-ttu-id="53387-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-395">taxid#</span></span>
  
<span data-ttu-id="53387-396">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-396">tax identification number</span></span>
  
<span data-ttu-id="53387-397">identificación de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-397">tax identification no.</span></span>
  
<span data-ttu-id="53387-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="53387-398">steuernummer</span></span>
  
<span data-ttu-id="53387-399">identificador de steuer</span><span class="sxs-lookup"><span data-stu-id="53387-399">steuer id</span></span>
  
<span data-ttu-id="53387-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="53387-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="53387-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="53387-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="53387-402">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-402">Format</span></span>

<span data-ttu-id="53387-403">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-404">Pattern</span></span>

<span data-ttu-id="53387-405">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-406">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-406">Checksum</span></span>

<span data-ttu-id="53387-407">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-408">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-408">Definition</span></span>

<span data-ttu-id="53387-409">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-410">La expresión regular `Regex_greece_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-411">Una palabra clave de `Keywords_greece_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-412">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="53387-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="53387-414">AFM</span><span class="sxs-lookup"><span data-stu-id="53387-414">afm</span></span>
  
<span data-ttu-id="53387-415">tin
</span><span class="sxs-lookup"><span data-stu-id="53387-415">tin</span></span>
  
<span data-ttu-id="53387-416">identificador de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-416">tax id no.</span></span>
  
<span data-ttu-id="53387-417">identificador de impuestos no</span><span class="sxs-lookup"><span data-stu-id="53387-417">tax id no</span></span>
  
<span data-ttu-id="53387-418">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-418">tax identification number</span></span>
  
<span data-ttu-id="53387-419">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-419">tax registry number</span></span>
  
<span data-ttu-id="53387-420">el registro de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-420">tax registry no.</span></span>
  
<span data-ttu-id="53387-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="53387-421">afm#</span></span>
  
<span data-ttu-id="53387-422">estaño #</span><span class="sxs-lookup"><span data-stu-id="53387-422">tin#</span></span>
  
<span data-ttu-id="53387-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="53387-423">taxidno#</span></span>
  
<span data-ttu-id="53387-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="53387-424">taxregistryno#</span></span>
  
<span data-ttu-id="53387-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="53387-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="53387-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="53387-426">aφμ</span></span>
  
<span data-ttu-id="53387-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="53387-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="53387-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ.</span><span class="sxs-lookup"><span data-stu-id="53387-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="53387-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="53387-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="53387-430">Hungría</span><span class="sxs-lookup"><span data-stu-id="53387-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="53387-431">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-431">Format</span></span>

<span data-ttu-id="53387-432">Diez dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-433">Pattern</span></span>

<span data-ttu-id="53387-434">Diez dígitos:</span><span class="sxs-lookup"><span data-stu-id="53387-434">Ten digits:</span></span>
  
-  <span data-ttu-id="53387-435">Un dígito que debe ser "8"</span><span class="sxs-lookup"><span data-stu-id="53387-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="53387-436">Cinco dígitos que se corresponden con el número de días entre la fecha 01/01/1867 y la fecha de nacimiento de la persona</span><span class="sxs-lookup"><span data-stu-id="53387-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="53387-437">Tres dígitos que se corresponden con el número generado al azar para diferenciar los individuos nacidos en el mismo día</span><span class="sxs-lookup"><span data-stu-id="53387-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="53387-438">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="53387-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-439">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-439">Checksum</span></span>

<span data-ttu-id="53387-440">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-441">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-441">Definition</span></span>

<span data-ttu-id="53387-442">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-443">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-444">Una palabra clave de `Keywords_hungary_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-445">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-446">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-447">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="53387-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="53387-449">número de identificación fiscal húngaro</span><span class="sxs-lookup"><span data-stu-id="53387-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="53387-450">estaño húngaro</span><span class="sxs-lookup"><span data-stu-id="53387-450">hungarian tin</span></span>
  
<span data-ttu-id="53387-451">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-451">tax id number</span></span>
  
<span data-ttu-id="53387-452">CIF</span><span class="sxs-lookup"><span data-stu-id="53387-452">vat number</span></span>
  
<span data-ttu-id="53387-453">autoridad fiscal no</span><span class="sxs-lookup"><span data-stu-id="53387-453">tax authority no</span></span>
  
<span data-ttu-id="53387-454">número de identidad de impuestos de impuestos Id.</span><span class="sxs-lookup"><span data-stu-id="53387-454">tax id tax identity number</span></span>
  
<span data-ttu-id="53387-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-455">taxidnumber#</span></span>
  
<span data-ttu-id="53387-456">estaño #</span><span class="sxs-lookup"><span data-stu-id="53387-456">tin#</span></span>
  
<span data-ttu-id="53387-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="53387-457">hungatiantin#</span></span>
  
<span data-ttu-id="53387-458">identificación de impuestos no</span><span class="sxs-lookup"><span data-stu-id="53387-458">tax identification no</span></span>
  
<span data-ttu-id="53387-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="53387-459">taxidno#</span></span>
  
<span data-ttu-id="53387-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="53387-460">adóazonosító szám</span></span>
  
<span data-ttu-id="53387-461">adószám</span><span class="sxs-lookup"><span data-stu-id="53387-461">adószám</span></span>
  
<span data-ttu-id="53387-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="53387-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="53387-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="53387-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="53387-464">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-464">Format</span></span>

<span data-ttu-id="53387-465">Siete dígitos seguidos de una letra sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-466">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-466">Pattern</span></span>

<span data-ttu-id="53387-467">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="53387-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="53387-468">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="53387-468">Seven digits</span></span> 
    
- <span data-ttu-id="53387-469">Una letra (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-470">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-470">Checksum</span></span>

<span data-ttu-id="53387-471">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-472">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-472">Definition</span></span>

<span data-ttu-id="53387-473">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-474">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-475">Una palabra clave de `Keywords_ireland_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-476">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-477">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-478">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="53387-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="53387-480">servicio público no</span><span class="sxs-lookup"><span data-stu-id="53387-480">public service no</span></span>
  
<span data-ttu-id="53387-481">servicio público personal no</span><span class="sxs-lookup"><span data-stu-id="53387-481">personal public service no</span></span>
  
<span data-ttu-id="53387-482">PPS no</span><span class="sxs-lookup"><span data-stu-id="53387-482">pps no</span></span>
  
<span data-ttu-id="53387-483">personal de servicio no</span><span class="sxs-lookup"><span data-stu-id="53387-483">personal service no</span></span>
  
<span data-ttu-id="53387-484">no de servicio de PPS</span><span class="sxs-lookup"><span data-stu-id="53387-484">pps service no</span></span>
  
<span data-ttu-id="53387-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="53387-485">ppsno#</span></span>
  
<span data-ttu-id="53387-486">Irlandés pps no</span><span class="sxs-lookup"><span data-stu-id="53387-486">irish pps no</span></span>
  
<span data-ttu-id="53387-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="53387-487">publicserviceno#</span></span>
  
<span data-ttu-id="53387-488">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="53387-488">personal public service number</span></span>
  
<span data-ttu-id="53387-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="53387-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="53387-490">uimh de PPS</span><span class="sxs-lookup"><span data-stu-id="53387-490">pps uimh</span></span>
  
<span data-ttu-id="53387-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="53387-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="53387-492">Italia</span><span class="sxs-lookup"><span data-stu-id="53387-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="53387-493">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-493">Format</span></span>

<span data-ttu-id="53387-494">16 letras y dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="53387-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-495">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-495">Pattern</span></span>

<span data-ttu-id="53387-496">16 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="53387-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="53387-497">Tres letras que corresponden a los tres primeros consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="53387-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="53387-498">Tres letras que corresponden a la primera, tercera y cuarta consonantes en el nombre</span><span class="sxs-lookup"><span data-stu-id="53387-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="53387-499">Dos dígitos que corresponden a la última dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="53387-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="53387-500">Un dígito que corresponde al mes de nacimiento: letras se usan en orden alfabético, pero se usan sólo las letras A E, H, L, M, P, R a T (por lo tanto, es enero y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="53387-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="53387-501">Dos dígitos que se corresponden con el día del mes de nacimiento donde 40 se agrega en el día de nacimiento para mujeres diferenciar de machos</span><span class="sxs-lookup"><span data-stu-id="53387-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="53387-502">Cuatro dígitos que se corresponden con un código de área específico para el ayuntamiento donde surgió la persona, los códigos de país se usan para países extranjeros</span><span class="sxs-lookup"><span data-stu-id="53387-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="53387-503">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="53387-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-504">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-504">Checksum</span></span>

<span data-ttu-id="53387-505">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-506">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-506">Definition</span></span>

<span data-ttu-id="53387-507">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-508">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-509">Una palabra clave de `Keywords_italy_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-510">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-511">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-512">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="53387-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="53387-514">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-514">tax number</span></span>
  
<span data-ttu-id="53387-515">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-515">tax no.</span></span>
  
<span data-ttu-id="53387-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-516">taxno#</span></span>
  
<span data-ttu-id="53387-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-517">taxnumber#</span></span>
  
<span data-ttu-id="53387-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-518">taxnumber</span></span>
  
<span data-ttu-id="53387-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-519">tax id</span></span>
  
<span data-ttu-id="53387-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-520">taxid#</span></span>
  
<span data-ttu-id="53387-521">código fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-521">fiscal code</span></span>
  
<span data-ttu-id="53387-522">Codice fiscale</span><span class="sxs-lookup"><span data-stu-id="53387-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="53387-523">Letonia</span><span class="sxs-lookup"><span data-stu-id="53387-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="53387-524">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-524">Format</span></span>

<span data-ttu-id="53387-525">11 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-526">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-526">Pattern</span></span>

<span data-ttu-id="53387-527">11 dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="53387-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="53387-528">Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="53387-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="53387-529">Un dígito que corresponde a la century de nacimiento donde "0" corresponde a century 19, "1" corresponde a century 20, y "2" corresponde a century 21</span><span class="sxs-lookup"><span data-stu-id="53387-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="53387-530">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-531">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-531">Checksum</span></span>

<span data-ttu-id="53387-532">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-533">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-533">Definition</span></span>

<span data-ttu-id="53387-534">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-535">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-536">Una palabra clave de `Keywords_latvia_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-537">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-538">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-539">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="53387-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="53387-541">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-541">tax number</span></span>
  
<span data-ttu-id="53387-542">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-542">tax no.</span></span>
  
<span data-ttu-id="53387-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-543">taxno#</span></span>
  
<span data-ttu-id="53387-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-544">taxnumber#</span></span>
  
<span data-ttu-id="53387-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-545">taxnumber</span></span>
  
<span data-ttu-id="53387-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-546">tax id</span></span>
  
<span data-ttu-id="53387-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-547">taxid#</span></span>
  
<span data-ttu-id="53387-548">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-548">tax identification number</span></span>
  
<span data-ttu-id="53387-549">identificación de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-549">tax identification no.</span></span>
  
<span data-ttu-id="53387-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="53387-550">nodokļa numurs</span></span>
  
<span data-ttu-id="53387-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="53387-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="53387-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="53387-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="53387-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="53387-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="53387-554">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-554">Format</span></span>

<span data-ttu-id="53387-555">11 dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-556">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-556">Pattern</span></span>

<span data-ttu-id="53387-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-558">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-558">Checksum</span></span>

<span data-ttu-id="53387-559">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-560">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-560">Definition</span></span>

<span data-ttu-id="53387-561">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-562">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-563">Una palabra clave de `Keywords_lithuania_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-564">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-565">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-566">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="53387-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="53387-568">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-568">tax number</span></span>
  
<span data-ttu-id="53387-569">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-569">tax no.</span></span>
  
<span data-ttu-id="53387-570">fiscal no #</span><span class="sxs-lookup"><span data-stu-id="53387-570">tax no#</span></span>
  
<span data-ttu-id="53387-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-571">taxnumber#</span></span>
  
<span data-ttu-id="53387-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-572">taxnumber</span></span>
  
<span data-ttu-id="53387-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-573">tax id</span></span>
  
<span data-ttu-id="53387-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-574">taxid#</span></span>
  
<span data-ttu-id="53387-575">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-575">tax identification number</span></span>
  
<span data-ttu-id="53387-576">identificación de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-576">tax identification no.</span></span>
  
<span data-ttu-id="53387-577">identificador de mokesčių</span><span class="sxs-lookup"><span data-stu-id="53387-577">mokesčių id</span></span>
  
<span data-ttu-id="53387-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="53387-578">mokesčių numeris</span></span>
  
<span data-ttu-id="53387-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="53387-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="53387-580">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="53387-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="53387-581">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-581">Format</span></span>

<span data-ttu-id="53387-582">13 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-583">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-583">Pattern</span></span>

<span data-ttu-id="53387-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="53387-584">13 digits:</span></span>
  
-  <span data-ttu-id="53387-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-585">11 digits</span></span> 
    
- <span data-ttu-id="53387-586">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="53387-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-587">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-587">Checksum</span></span>

<span data-ttu-id="53387-588">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-589">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-589">Definition</span></span>

<span data-ttu-id="53387-590">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-591">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-592">Una palabra clave de `Keywords_luxemburg_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-593">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-594">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-595">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="53387-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="53387-597">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-597">tax number</span></span>
  
<span data-ttu-id="53387-598">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-598">tax no.</span></span>
  
<span data-ttu-id="53387-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-599">taxno#</span></span>
  
<span data-ttu-id="53387-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-600">taxnumber#</span></span>
  
<span data-ttu-id="53387-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-601">taxnumber</span></span>
  
<span data-ttu-id="53387-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-602">tax id</span></span>
  
<span data-ttu-id="53387-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-603">taxid#</span></span>
  
<span data-ttu-id="53387-604">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-604">tax identification number</span></span>
  
<span data-ttu-id="53387-605">identificación de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-605">tax identification no.</span></span>
  
<span data-ttu-id="53387-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="53387-606">steuernummer</span></span>
  
<span data-ttu-id="53387-607">identificador de steuer</span><span class="sxs-lookup"><span data-stu-id="53387-607">steuer id</span></span>
  
<span data-ttu-id="53387-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="53387-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="53387-609">Malta</span><span class="sxs-lookup"><span data-stu-id="53387-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="53387-610">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-610">Format</span></span>

<span data-ttu-id="53387-611">Para los nacionales Maltés: 7 dígitos y una carta en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="53387-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="53387-612">No Maltés nacionales y entidades Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-613">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-613">Pattern</span></span>

<span data-ttu-id="53387-614">Maltés nacionales: 7 dígitos y una carta</span><span class="sxs-lookup"><span data-stu-id="53387-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="53387-615">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="53387-615">Seven digits</span></span> 
    
- <span data-ttu-id="53387-616">Una letra (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="53387-617">No Maltés nacionales y entidades Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="53387-618">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="53387-619">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-619">Checksum</span></span>

<span data-ttu-id="53387-620">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-621">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-621">Definition</span></span>

<span data-ttu-id="53387-622">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-623">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-624">Una palabra clave de `Keywords_malta_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-625">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-626">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-627">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="53387-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="53387-629">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-629">tax number</span></span>
  
<span data-ttu-id="53387-630">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-630">tax no.</span></span>
  
<span data-ttu-id="53387-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-631">taxno#</span></span>
  
<span data-ttu-id="53387-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-632">taxnumber#</span></span>
  
<span data-ttu-id="53387-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-633">taxnumber</span></span>
  
<span data-ttu-id="53387-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-634">tax id</span></span>
  
<span data-ttu-id="53387-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-635">taxid#</span></span>
  
<span data-ttu-id="53387-636">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-636">tax identification number</span></span>
  
<span data-ttu-id="53387-637">identificación de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-637">tax identification no.</span></span>
  
<span data-ttu-id="53387-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="53387-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="53387-639">identificador tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="53387-639">id tat-taxxa</span></span>
  
<span data-ttu-id="53387-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="53387-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="53387-641">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="53387-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="53387-642">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-642">Format</span></span>

<span data-ttu-id="53387-643">Nueve dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-644">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-644">Pattern</span></span>

<span data-ttu-id="53387-645">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="53387-646">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-646">Checksum</span></span>

<span data-ttu-id="53387-647">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-648">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-648">Definition</span></span>

<span data-ttu-id="53387-649">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-650">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-651">Una palabra clave de `Keywords_netherlands_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-652">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-653">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-654">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="53387-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="53387-656">número de identificación fiscal (Países Bajos)</span><span class="sxs-lookup"><span data-stu-id="53387-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="53387-657">identificación de impuestos (Países Bajos)</span><span class="sxs-lookup"><span data-stu-id="53387-657">netherlands tax identification</span></span>
  
<span data-ttu-id="53387-658">número de identificación de impuestos de países bajos</span><span class="sxs-lookup"><span data-stu-id="53387-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="53387-659">identificación de impuestos de países bajos</span><span class="sxs-lookup"><span data-stu-id="53387-659">netherland's tax identification</span></span>
  
<span data-ttu-id="53387-660">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-660">tax identification number</span></span>
  
<span data-ttu-id="53387-661">id de impuestos holandés</span><span class="sxs-lookup"><span data-stu-id="53387-661">dutch tax id</span></span>
  
<span data-ttu-id="53387-662">número de identificación fiscal neerlandés</span><span class="sxs-lookup"><span data-stu-id="53387-662">dutch tax identification number</span></span>
  
<span data-ttu-id="53387-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-663">tax id</span></span>
  
<span data-ttu-id="53387-664">identificador de impuestos #</span><span class="sxs-lookup"><span data-stu-id="53387-664">tax id#</span></span>
  
<span data-ttu-id="53387-665">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-665">tax number</span></span>
  
<span data-ttu-id="53387-666">fiscal no #</span><span class="sxs-lookup"><span data-stu-id="53387-666">tax no#</span></span>
  
<span data-ttu-id="53387-667">impuestos #</span><span class="sxs-lookup"><span data-stu-id="53387-667">tax#</span></span>
  
<span data-ttu-id="53387-668">tin
</span><span class="sxs-lookup"><span data-stu-id="53387-668">tin</span></span>
  
<span data-ttu-id="53387-669">estaño #</span><span class="sxs-lookup"><span data-stu-id="53387-669">tin#</span></span>
  
<span data-ttu-id="53387-670">estaño (Países Bajos)</span><span class="sxs-lookup"><span data-stu-id="53387-670">netherlands tin</span></span>
  
<span data-ttu-id="53387-671">estaño de países bajos</span><span class="sxs-lookup"><span data-stu-id="53387-671">netherland's tin</span></span>
  
<span data-ttu-id="53387-672">países bajos belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="53387-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="53387-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="53387-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="53387-674">belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="53387-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="53387-675">países bajos belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="53387-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="53387-676">países bajos belasting identificador nummer</span><span class="sxs-lookup"><span data-stu-id="53387-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="53387-677">países bajos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="53387-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="53387-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="53387-678">btw nummer</span></span>
  
<span data-ttu-id="53387-679">Nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="53387-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="53387-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="53387-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="53387-681">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-681">Format</span></span>

<span data-ttu-id="53387-682">Once dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-683">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-683">Pattern</span></span>

<span data-ttu-id="53387-684">Once dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-685">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-685">Checksum</span></span>

<span data-ttu-id="53387-686">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-687">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-687">Definition</span></span>

<span data-ttu-id="53387-688">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-689">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-690">Una palabra clave de `Keywords_poland_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-691">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-692">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-693">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="53387-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="53387-695">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-695">tax number</span></span>
  
<span data-ttu-id="53387-696">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-696">tax no.</span></span>
  
<span data-ttu-id="53387-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-697">taxno#</span></span>
  
<span data-ttu-id="53387-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-698">taxnumber#</span></span>
  
<span data-ttu-id="53387-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-699">taxnumber</span></span>
  
<span data-ttu-id="53387-700">NIP</span><span class="sxs-lookup"><span data-stu-id="53387-700">nip</span></span>
  
<span data-ttu-id="53387-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="53387-701">nip#</span></span>
  
<span data-ttu-id="53387-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-702">tax id</span></span>
  
<span data-ttu-id="53387-703">identificador de impuestos #</span><span class="sxs-lookup"><span data-stu-id="53387-703">tax id#</span></span>
  
<span data-ttu-id="53387-704">identificador de NIP</span><span class="sxs-lookup"><span data-stu-id="53387-704">nip id</span></span>
  
<span data-ttu-id="53387-705">identificador de NIP #</span><span class="sxs-lookup"><span data-stu-id="53387-705">nip id#</span></span>
  
<span data-ttu-id="53387-706">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-706">tax identification number</span></span>
  
<span data-ttu-id="53387-707">identificación de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-707">tax identification no.</span></span>
  
<span data-ttu-id="53387-708">CIF</span><span class="sxs-lookup"><span data-stu-id="53387-708">vat number</span></span>
  
<span data-ttu-id="53387-709">Nº de IVA.</span><span class="sxs-lookup"><span data-stu-id="53387-709">vat no.</span></span>
  
<span data-ttu-id="53387-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="53387-710">vatno#</span></span>
  
<span data-ttu-id="53387-711">identificador de RFC</span><span class="sxs-lookup"><span data-stu-id="53387-711">vat id</span></span>
  
<span data-ttu-id="53387-712">identificador de RFC #</span><span class="sxs-lookup"><span data-stu-id="53387-712">vat id#</span></span>
  
<span data-ttu-id="53387-713">número identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="53387-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="53387-714">Polski número identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="53387-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="53387-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="53387-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="53387-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="53387-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="53387-717">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-717">Format</span></span>

<span data-ttu-id="53387-718">Nueve dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-719">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-719">Pattern</span></span>

<span data-ttu-id="53387-720">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-721">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-721">Checksum</span></span>

<span data-ttu-id="53387-722">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-723">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-723">Definition</span></span>

<span data-ttu-id="53387-724">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-725">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-726">Una palabra clave de `Keywords_portugal_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-727">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-728">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-729">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="53387-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="53387-731">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-731">tax number</span></span>
  
<span data-ttu-id="53387-732">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-732">tax no.</span></span>
  
<span data-ttu-id="53387-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-733">taxno#</span></span>
  
<span data-ttu-id="53387-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="53387-734">taxnumber#</span></span>
  
<span data-ttu-id="53387-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="53387-735">taxnumber</span></span>
  
<span data-ttu-id="53387-736">NIF</span><span class="sxs-lookup"><span data-stu-id="53387-736">nif</span></span>
  
<span data-ttu-id="53387-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="53387-737">nif#</span></span>
  
<span data-ttu-id="53387-738">numero fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-738">numero fiscal</span></span>
  
<span data-ttu-id="53387-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="53387-740">Rumania</span><span class="sxs-lookup"><span data-stu-id="53387-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="53387-741">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-741">Format</span></span>

<span data-ttu-id="53387-742">13 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-743">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-743">Pattern</span></span>

<span data-ttu-id="53387-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-745">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-745">Checksum</span></span>

<span data-ttu-id="53387-746">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-747">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-747">Definition</span></span>

<span data-ttu-id="53387-748">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-749">La expresión regular `Regex_romania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-750">Una palabra clave de `Keywords_romania_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-751">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="53387-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="53387-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-753">tax id</span></span>
  
<span data-ttu-id="53387-754">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-754">tax id number</span></span>
  
<span data-ttu-id="53387-755">archivo de impuestos no</span><span class="sxs-lookup"><span data-stu-id="53387-755">tax file no</span></span>
  
<span data-ttu-id="53387-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="53387-756">tax file number</span></span>
  
<span data-ttu-id="53387-757">fiscal no</span><span class="sxs-lookup"><span data-stu-id="53387-757">tax no</span></span>
  
<span data-ttu-id="53387-758">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-758">tax number</span></span>
  
<span data-ttu-id="53387-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-759">taxid#</span></span>
  
<span data-ttu-id="53387-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-760">taxno#</span></span>
  
<span data-ttu-id="53387-761">identificador ul taxei</span><span class="sxs-lookup"><span data-stu-id="53387-761">id-ul taxei</span></span>
  
<span data-ttu-id="53387-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="53387-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="53387-763">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="53387-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="53387-764">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-764">Format</span></span>

<span data-ttu-id="53387-765">10 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-766">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-766">Pattern</span></span>

<span data-ttu-id="53387-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-768">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-768">Checksum</span></span>

<span data-ttu-id="53387-769">No aplicable</span><span class="sxs-lookup"><span data-stu-id="53387-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-770">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-770">Definition</span></span>

<span data-ttu-id="53387-771">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-772">La expresión regular `Regex_slovakia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-773">Una palabra clave de `Keywords_slovakia_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-774">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="53387-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="53387-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-776">tax id</span></span>
  
<span data-ttu-id="53387-777">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-777">tax id number</span></span>
  
<span data-ttu-id="53387-778">identificador de estaño</span><span class="sxs-lookup"><span data-stu-id="53387-778">tin id</span></span>
  
<span data-ttu-id="53387-779">no estaño</span><span class="sxs-lookup"><span data-stu-id="53387-779">tin no</span></span>
  
<span data-ttu-id="53387-780">identificador de estaño eslovaco</span><span class="sxs-lookup"><span data-stu-id="53387-780">slovakian tin id</span></span>
  
<span data-ttu-id="53387-781">tin
</span><span class="sxs-lookup"><span data-stu-id="53387-781">tin</span></span>
  
<span data-ttu-id="53387-782">archivo de impuestos no</span><span class="sxs-lookup"><span data-stu-id="53387-782">tax file no</span></span>
  
<span data-ttu-id="53387-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="53387-783">tax file number</span></span>
  
<span data-ttu-id="53387-784">fiscal no</span><span class="sxs-lookup"><span data-stu-id="53387-784">tax no</span></span>
  
<span data-ttu-id="53387-785">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-785">tax number</span></span>
  
<span data-ttu-id="53387-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-786">taxid#</span></span>
  
<span data-ttu-id="53387-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-787">taxno#</span></span>
  
<span data-ttu-id="53387-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="53387-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="53387-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="53387-789">daňové číslo</span></span>
  
<span data-ttu-id="53387-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="53387-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="53387-791">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="53387-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="53387-792">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-792">Format</span></span>

<span data-ttu-id="53387-793">Ocho dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-794">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-794">Pattern</span></span>

<span data-ttu-id="53387-795">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-796">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-796">Checksum</span></span>

<span data-ttu-id="53387-797">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-798">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-798">Definition</span></span>

<span data-ttu-id="53387-799">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-800">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-801">Una palabra clave de `Keywords_slovenia_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-802">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-803">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-804">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="53387-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="53387-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-806">tax id</span></span>
  
<span data-ttu-id="53387-807">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-807">tax id number</span></span>
  
<span data-ttu-id="53387-808">identificador de estaño</span><span class="sxs-lookup"><span data-stu-id="53387-808">tin id</span></span>
  
<span data-ttu-id="53387-809">no estaño</span><span class="sxs-lookup"><span data-stu-id="53387-809">tin no</span></span>
  
<span data-ttu-id="53387-810">identificador de estaño esloveno</span><span class="sxs-lookup"><span data-stu-id="53387-810">slovenian tin id</span></span>
  
<span data-ttu-id="53387-811">tin
</span><span class="sxs-lookup"><span data-stu-id="53387-811">tin</span></span>
  
<span data-ttu-id="53387-812">archivo de impuestos no</span><span class="sxs-lookup"><span data-stu-id="53387-812">tax file no</span></span>
  
<span data-ttu-id="53387-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="53387-813">tax file number</span></span>
  
<span data-ttu-id="53387-814">fiscal no</span><span class="sxs-lookup"><span data-stu-id="53387-814">tax no</span></span>
  
<span data-ttu-id="53387-815">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-815">tax number</span></span>
  
<span data-ttu-id="53387-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-816">taxid#</span></span>
  
<span data-ttu-id="53387-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-817">taxno#</span></span>
  
<span data-ttu-id="53387-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="53387-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="53387-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="53387-819">davčna številka</span></span>
  
<span data-ttu-id="53387-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="53387-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="53387-821">España</span><span class="sxs-lookup"><span data-stu-id="53387-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="53387-822">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-822">Format</span></span>

<span data-ttu-id="53387-823">Siete u ocho dígitos y uno o dos letras en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="53387-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-824">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-824">Pattern</span></span>

<span data-ttu-id="53387-825">Personas físicas españolas con una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="53387-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="53387-826">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-826">Eight digits</span></span> 
    
- <span data-ttu-id="53387-827">Una letra mayúscula (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="53387-828">No residente Spaniards sin una tarjeta de identidad nacional de España</span><span class="sxs-lookup"><span data-stu-id="53387-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="53387-829">Una letra mayúscula "L" (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="53387-830">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="53387-830">Seven digits</span></span>
    
- <span data-ttu-id="53387-831">Una letra mayúscula (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="53387-832">Spaniards residente menores de 14 años sin una tarjeta de identidad de nacionales de España:</span><span class="sxs-lookup"><span data-stu-id="53387-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="53387-833">Una letra mayúscula "K" (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="53387-834">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="53387-834">Seven digits</span></span> 
    
- <span data-ttu-id="53387-835">Una letra mayúscula (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="53387-836">Foreigners con el número de identificación de un Foreigner</span><span class="sxs-lookup"><span data-stu-id="53387-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="53387-837">Uno en mayúsculas es decir letra "X", "Y" o "Z" (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="53387-838">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="53387-838">Seven digits</span></span>
    
- <span data-ttu-id="53387-839">Una letra mayúscula (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="53387-840">Foreigners sin número de identificación de un Foreigner</span><span class="sxs-lookup"><span data-stu-id="53387-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="53387-841">Una letra mayúscula que es "M" (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="53387-842">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="53387-842">Seven digits</span></span>
    
- <span data-ttu-id="53387-843">Una letra mayúscula (distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="53387-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="53387-844">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-844">Checksum</span></span>

<span data-ttu-id="53387-845">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-846">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-846">Definition</span></span>

<span data-ttu-id="53387-847">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-848">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-849">Una palabra clave de `Keywords_spain_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-850">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-851">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-852">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="53387-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="53387-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-854">tax id</span></span>
  
<span data-ttu-id="53387-855">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-855">tax id number</span></span>
  
<span data-ttu-id="53387-856">identificador de CIF</span><span class="sxs-lookup"><span data-stu-id="53387-856">cif id</span></span>
  
<span data-ttu-id="53387-857">CIF no</span><span class="sxs-lookup"><span data-stu-id="53387-857">cif no</span></span>
  
<span data-ttu-id="53387-858">identificador de cif español</span><span class="sxs-lookup"><span data-stu-id="53387-858">spanish cif id</span></span>
  
<span data-ttu-id="53387-859">CIF</span><span class="sxs-lookup"><span data-stu-id="53387-859">cif</span></span>
  
<span data-ttu-id="53387-860">archivo de impuestos no</span><span class="sxs-lookup"><span data-stu-id="53387-860">tax file no</span></span>
  
<span data-ttu-id="53387-861">número de cif español</span><span class="sxs-lookup"><span data-stu-id="53387-861">spanish cif number</span></span>
  
<span data-ttu-id="53387-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="53387-862">tax file number</span></span>
  
<span data-ttu-id="53387-863">Español cif no</span><span class="sxs-lookup"><span data-stu-id="53387-863">spanish cif no</span></span>
  
<span data-ttu-id="53387-864">fiscal no</span><span class="sxs-lookup"><span data-stu-id="53387-864">tax no</span></span>
  
<span data-ttu-id="53387-865">número de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-865">tax number</span></span>
  
<span data-ttu-id="53387-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-866">taxid#</span></span>
  
<span data-ttu-id="53387-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="53387-867">taxno#</span></span>
  
<span data-ttu-id="53387-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="53387-868">cifid#</span></span>
  
<span data-ttu-id="53387-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="53387-869">spanishcifid#</span></span>
  
<span data-ttu-id="53387-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="53387-870">spanishcifno#</span></span>
  
<span data-ttu-id="53387-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="53387-871">número de contribuyente</span></span>
  
<span data-ttu-id="53387-872">número de impuesto Entreprise</span><span class="sxs-lookup"><span data-stu-id="53387-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="53387-873">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="53387-874">número de CIF</span><span class="sxs-lookup"><span data-stu-id="53387-874">cif número</span></span>
  
<span data-ttu-id="53387-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="53387-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="53387-876">Suecia</span><span class="sxs-lookup"><span data-stu-id="53387-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="53387-877">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-877">Format</span></span>

<span data-ttu-id="53387-878">Diez dígitos y un símbolo en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="53387-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-879">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-879">Pattern</span></span>

<span data-ttu-id="53387-880">Diez dígitos y un símbolo:</span><span class="sxs-lookup"><span data-stu-id="53387-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="53387-881">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="53387-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="53387-882">Un signo más, signo menos o barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="53387-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="53387-883">Tres dígitos que hacen que la identificación de número único where:</span><span class="sxs-lookup"><span data-stu-id="53387-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="53387-884">Para los números emitidos antes de 1990, el dígito séptimo y octavo identificar la provincia de nacimiento o personas foreign-born</span><span class="sxs-lookup"><span data-stu-id="53387-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="53387-885">El dígito en la posición noveno indica género por puede ser impar para hombre o incluso para hembra</span><span class="sxs-lookup"><span data-stu-id="53387-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="53387-886">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="53387-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="53387-887">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-887">Checksum</span></span>

<span data-ttu-id="53387-888">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-889">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-889">Definition</span></span>

<span data-ttu-id="53387-890">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-891">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-892">Una palabra clave de `Keywords_sweden_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="53387-893">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-894">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-895">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="53387-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="53387-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-897">tax id</span></span>
  
<span data-ttu-id="53387-898">identificador de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-898">tax id no.</span></span>
  
<span data-ttu-id="53387-899">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-899">tax id number</span></span>
  
<span data-ttu-id="53387-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="53387-900">tax identification</span></span>
  
<span data-ttu-id="53387-901">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="53387-901">tax identification#</span></span>
  
<span data-ttu-id="53387-902">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-902">tax no.</span></span>
  
<span data-ttu-id="53387-903">impuestos #</span><span class="sxs-lookup"><span data-stu-id="53387-903">tax#</span></span>
  
<span data-ttu-id="53387-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-904">taxid#</span></span>
  
<span data-ttu-id="53387-905">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-905">tax file</span></span>
  
<span data-ttu-id="53387-906">archivo de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-906">tax file no.</span></span>
  
<span data-ttu-id="53387-907">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="53387-907">personal id number</span></span>
  
<span data-ttu-id="53387-908">skatt identificador nummer</span><span class="sxs-lookup"><span data-stu-id="53387-908">skatt id nummer</span></span>
  
<span data-ttu-id="53387-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="53387-909">skatt identifikation</span></span>
  
<span data-ttu-id="53387-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="53387-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="53387-911">REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="53387-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="53387-912">Formato</span><span class="sxs-lookup"><span data-stu-id="53387-912">Format</span></span>

<span data-ttu-id="53387-913">Referencia de contribuyente única (UTR): 10 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="53387-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="53387-p103">Número de seguros National (NINO): Para obtener información detallada, vea la sección "Reino Unido número nacional seguro (NINO)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="53387-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="53387-916">Patrón</span><span class="sxs-lookup"><span data-stu-id="53387-916">Pattern</span></span>

<span data-ttu-id="53387-917">Referencia de contribuyente única (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="53387-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="53387-p104">Número de seguros National (NINO): Para obtener información detallada, vea la sección "Reino Unido número nacional seguro (NINO)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="53387-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="53387-920">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="53387-920">Checksum</span></span>

<span data-ttu-id="53387-921">Sí</span><span class="sxs-lookup"><span data-stu-id="53387-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="53387-922">Definición</span><span class="sxs-lookup"><span data-stu-id="53387-922">Definition</span></span>

<span data-ttu-id="53387-923">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="53387-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="53387-924">La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="53387-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="53387-925">Una palabra clave de `Keywords_uk_eu_tax_file_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="53387-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="53387-926">Keywords</span><span class="sxs-lookup"><span data-stu-id="53387-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="53387-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="53387-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="53387-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="53387-928">tax id</span></span>
  
<span data-ttu-id="53387-929">identificador de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-929">tax id no.</span></span>
  
<span data-ttu-id="53387-930">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="53387-930">tax id number</span></span>
  
<span data-ttu-id="53387-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="53387-931">tax identification</span></span>
  
<span data-ttu-id="53387-932">identificación de impuestos #</span><span class="sxs-lookup"><span data-stu-id="53387-932">tax identification#</span></span>
  
<span data-ttu-id="53387-933">fiscal no.</span><span class="sxs-lookup"><span data-stu-id="53387-933">tax no.</span></span>
  
<span data-ttu-id="53387-934">impuestos #</span><span class="sxs-lookup"><span data-stu-id="53387-934">tax#</span></span>
  
<span data-ttu-id="53387-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="53387-935">taxid#</span></span>
  
<span data-ttu-id="53387-936">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="53387-936">tax file</span></span>
  
<span data-ttu-id="53387-937">archivo de impuestos no.</span><span class="sxs-lookup"><span data-stu-id="53387-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53387-938">Vea también</span><span class="sxs-lookup"><span data-stu-id="53387-938">See also</span></span>

[<span data-ttu-id="53387-939">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="53387-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

