---
title: Número de identificación fiscal de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación de impuestos de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: f851cce4be70fd41c24a7876d97c452f0a738eda
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213830"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="16174-104">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="16174-104">EU Tax Identification Number</span></span>

<span data-ttu-id="16174-p102">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de identificación fiscal (CIF) de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="16174-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="16174-107">Austria</span><span class="sxs-lookup"><span data-stu-id="16174-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="16174-108">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-108">Format</span></span>

<span data-ttu-id="16174-109">Nueve dígitos con guión opcional y barra diagonal</span><span class="sxs-lookup"><span data-stu-id="16174-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-110">Pattern</span></span>

<span data-ttu-id="16174-111">Nueve dígitos con guión opcional y barra diagonal:</span><span class="sxs-lookup"><span data-stu-id="16174-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="16174-112">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-112">Two digits</span></span> 
    
- <span data-ttu-id="16174-113">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="16174-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="16174-114">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-114">Three digits</span></span>
    
- <span data-ttu-id="16174-115">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="16174-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="16174-116">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-117">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-117">Checksum</span></span>

<span data-ttu-id="16174-118">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-119">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-119">Definition</span></span>

<span data-ttu-id="16174-120">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-121">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-122">Se encuentra una `Keywords_austria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-123">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-124">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-125">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="16174-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="16174-127">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-127">tax number</span></span>
  
<span data-ttu-id="16174-128">números</span><span class="sxs-lookup"><span data-stu-id="16174-128">number</span></span>
  
<span data-ttu-id="16174-129">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="16174-129">tax registration number</span></span>
  
<span data-ttu-id="16174-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-130">tax id</span></span>
  
<span data-ttu-id="16174-131">St.Nr.</span><span class="sxs-lookup"><span data-stu-id="16174-131">st.nr.</span></span>
  
<span data-ttu-id="16174-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="16174-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="16174-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="16174-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="16174-134">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-134">Format</span></span>

<span data-ttu-id="16174-135">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-136">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-136">Pattern</span></span>

<span data-ttu-id="16174-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16174-137">11 digits:</span></span>
  
- <span data-ttu-id="16174-138">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-138">Two digits</span></span>
    
- <span data-ttu-id="16174-139">Un "0" o "1"</span><span class="sxs-lookup"><span data-stu-id="16174-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="16174-140">Un dígito</span><span class="sxs-lookup"><span data-stu-id="16174-140">One digit</span></span>
    
- <span data-ttu-id="16174-141">Un "0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="16174-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="16174-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-143">Checksum</span></span>

<span data-ttu-id="16174-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-145">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-145">Definition</span></span>

<span data-ttu-id="16174-146">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-147">La expresión `Regex_belgium_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-148">Se encuentra una `Keywords_belgium_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16174-149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="16174-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="16174-151">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-151">tax number</span></span>
  
<span data-ttu-id="16174-152">número de registro nacional</span><span class="sxs-lookup"><span data-stu-id="16174-152">national registration number</span></span>
  
<span data-ttu-id="16174-153">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="16174-153">tax registration number</span></span>
  
<span data-ttu-id="16174-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-154">tax id</span></span>
  
<span data-ttu-id="16174-155">NIF</span><span class="sxs-lookup"><span data-stu-id="16174-155">nif</span></span>
  
<span data-ttu-id="16174-156">NIF</span><span class="sxs-lookup"><span data-stu-id="16174-156">nif#</span></span>
  
<span data-ttu-id="16174-157">numéro de registros nacionales</span><span class="sxs-lookup"><span data-stu-id="16174-157">numéro de registre national</span></span>
  
<span data-ttu-id="16174-158">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="16174-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="16174-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="16174-160">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-160">Format</span></span>

<span data-ttu-id="16174-161">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-162">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-162">Pattern</span></span>

<span data-ttu-id="16174-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-164">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-164">Checksum</span></span>

<span data-ttu-id="16174-165">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-166">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-166">Definition</span></span>

<span data-ttu-id="16174-167">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-168">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-169">Se encuentra una `Keywords_bulgaria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-170">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-171">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-172">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="16174-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="16174-174">bucn</span><span class="sxs-lookup"><span data-stu-id="16174-174">bucn</span></span>
  
<span data-ttu-id="16174-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="16174-175">uniform civil number</span></span>
  
<span data-ttu-id="16174-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="16174-176">bucn#</span></span>
  
<span data-ttu-id="16174-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="16174-178">identificador civil uniforme</span><span class="sxs-lookup"><span data-stu-id="16174-178">uniform civil id</span></span>
  
<span data-ttu-id="16174-179">Uniform civil no</span><span class="sxs-lookup"><span data-stu-id="16174-179">uniform civil no</span></span>
  
<span data-ttu-id="16174-180">EGN</span><span class="sxs-lookup"><span data-stu-id="16174-180">egn</span></span>
  
<span data-ttu-id="16174-181">número civil uniforme de búlgaro</span><span class="sxs-lookup"><span data-stu-id="16174-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="16174-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="16174-182">uniformcivilno#</span></span>
  
<span data-ttu-id="16174-183">EGN #</span><span class="sxs-lookup"><span data-stu-id="16174-183">egn#</span></span>
  
<span data-ttu-id="16174-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="16174-184">униформ граждански номер</span></span>
  
<span data-ttu-id="16174-185">identificador униформ</span><span class="sxs-lookup"><span data-stu-id="16174-185">униформ id</span></span>
  
<span data-ttu-id="16174-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="16174-186">униформ граждански id</span></span>
  
<span data-ttu-id="16174-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="16174-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="16174-188">Croacia</span><span class="sxs-lookup"><span data-stu-id="16174-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="16174-189">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-189">Format</span></span>

<span data-ttu-id="16174-190">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-191">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-191">Pattern</span></span>

<span data-ttu-id="16174-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16174-192">11 digits:</span></span>
  
- <span data-ttu-id="16174-193">Diez dígitos, elegidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="16174-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="16174-194">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16174-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-195">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-195">Checksum</span></span>

<span data-ttu-id="16174-196">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-197">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-197">Definition</span></span>

<span data-ttu-id="16174-198">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-199">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-200">Se encuentra una `Keywords_croatia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-201">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-202">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-203">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="16174-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="16174-205">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-205">tax number</span></span>
  
<span data-ttu-id="16174-206">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-206">tax</span></span>
  
<span data-ttu-id="16174-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-207">tax id</span></span>
  
<span data-ttu-id="16174-208">OID</span><span class="sxs-lookup"><span data-stu-id="16174-208">oid</span></span>
  
<span data-ttu-id="16174-209">OID</span><span class="sxs-lookup"><span data-stu-id="16174-209">oid#</span></span>
  
<span data-ttu-id="16174-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="16174-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="16174-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="16174-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="16174-212">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-212">Format</span></span>

<span data-ttu-id="16174-213">Ocho dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="16174-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-214">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-214">Pattern</span></span>

<span data-ttu-id="16174-215">Ocho dígitos y una letra:</span><span class="sxs-lookup"><span data-stu-id="16174-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="16174-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="16174-216">A "0"</span></span> 
    
- <span data-ttu-id="16174-217">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16174-217">Seven digits</span></span>
    
- <span data-ttu-id="16174-218">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-219">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-219">Checksum</span></span>

<span data-ttu-id="16174-220">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-221">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-221">Definition</span></span>

<span data-ttu-id="16174-222">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-223">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-224">Se encuentra una `Keywords_cyprus_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-226">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="16174-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="16174-229">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-229">tax number</span></span>
  
<span data-ttu-id="16174-230">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-230">tax</span></span>
  
<span data-ttu-id="16174-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-231">tax id</span></span>
  
<span data-ttu-id="16174-232">código de identificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-232">tax identification code</span></span>
  
<span data-ttu-id="16174-233">verticales</span><span class="sxs-lookup"><span data-stu-id="16174-233">tic</span></span>
  
<span data-ttu-id="16174-234">verticales</span><span class="sxs-lookup"><span data-stu-id="16174-234">tic#</span></span>
  
<span data-ttu-id="16174-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="16174-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="16174-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="16174-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="16174-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="16174-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="16174-238">Chequia</span><span class="sxs-lookup"><span data-stu-id="16174-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="16174-239">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-239">Format</span></span>

<span data-ttu-id="16174-240">Nueve o diez dígitos con una barra diagonal inversa opcional</span><span class="sxs-lookup"><span data-stu-id="16174-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-241">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-241">Pattern</span></span>

<span data-ttu-id="16174-242">Nueve o diez dígitos con una barra diagonal inversa opcional:</span><span class="sxs-lookup"><span data-stu-id="16174-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="16174-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-243">Six digits</span></span> 
    
- <span data-ttu-id="16174-244">Una barra diagonal inversa (opcional)</span><span class="sxs-lookup"><span data-stu-id="16174-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="16174-245">Tres o cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-246">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-246">Checksum</span></span>

<span data-ttu-id="16174-247">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-248">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-248">Definition</span></span>

<span data-ttu-id="16174-249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-250">La expresión `Regex_czech_republic_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-251">Se encuentra una `Keywords_czech_republic_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16174-252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="16174-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="16174-254">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-254">tax number</span></span>
  
<span data-ttu-id="16174-255">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-255">tax</span></span>
  
<span data-ttu-id="16174-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-256">tax id</span></span>
  
<span data-ttu-id="16174-257">número personal</span><span class="sxs-lookup"><span data-stu-id="16174-257">personal number</span></span>
  
<span data-ttu-id="16174-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="16174-258">daňové číslo</span></span>
  
<span data-ttu-id="16174-259">Osobní číslo</span><span class="sxs-lookup"><span data-stu-id="16174-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="16174-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="16174-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="16174-261">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-261">Format</span></span>

<span data-ttu-id="16174-262">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="16174-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-263">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-263">Pattern</span></span>

<span data-ttu-id="16174-264">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="16174-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="16174-265">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="16174-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="16174-266">Un guión </span><span class="sxs-lookup"><span data-stu-id="16174-266">A hyphen</span></span>
    
- <span data-ttu-id="16174-267">Cuatro dígitos que corresponden a un número de secuencia en el que el primer dígito corresponde al siglo de nacimiento y el último dígito corresponde al sexo de la persona (impar para macho e incluso para hembras)</span><span class="sxs-lookup"><span data-stu-id="16174-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-268">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-268">Checksum</span></span>

<span data-ttu-id="16174-269">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-270">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-270">Definition</span></span>

<span data-ttu-id="16174-271">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-272">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-273">Se encuentra una `Keywords_denmark_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-275">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-276">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="16174-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="16174-278">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-278">tax number</span></span>
  
<span data-ttu-id="16174-279">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-279">tax</span></span>
  
<span data-ttu-id="16174-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-280">tax id</span></span>
  
<span data-ttu-id="16174-281">RCP número</span><span class="sxs-lookup"><span data-stu-id="16174-281">cpr number</span></span>
  
<span data-ttu-id="16174-282">RCP</span><span class="sxs-lookup"><span data-stu-id="16174-282">cpr#</span></span>
  
<span data-ttu-id="16174-283">Nummer de patinaje</span><span class="sxs-lookup"><span data-stu-id="16174-283">skat nummer</span></span>
  
<span data-ttu-id="16174-284">identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="16174-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="16174-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="16174-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="16174-286">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-286">Format</span></span>

<span data-ttu-id="16174-287">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-288">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-288">Pattern</span></span>

<span data-ttu-id="16174-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16174-289">11 digits:</span></span>
  
-  <span data-ttu-id="16174-290">Un dígito que corresponde al sexo y al siglo de nacimiento donde un número impar indica macho y el número par indica hembra de la siguiente manera: 1,2 para el siglo XIX; 3, 4 para el siglo XX; y 5, 6 para el siglo XXI</span><span class="sxs-lookup"><span data-stu-id="16174-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="16174-291">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="16174-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="16174-292">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha</span><span class="sxs-lookup"><span data-stu-id="16174-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="16174-293">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16174-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-294">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-294">Checksum</span></span>

<span data-ttu-id="16174-295">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-296">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-296">Definition</span></span>

<span data-ttu-id="16174-297">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-298">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-299">Se encuentra una `Keywords_estonia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-300">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-301">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-302">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="16174-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="16174-304">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-304">tax number</span></span>
  
<span data-ttu-id="16174-305">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-305">tax</span></span>
  
<span data-ttu-id="16174-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-306">tax id</span></span>
  
<span data-ttu-id="16174-307">código personal</span><span class="sxs-lookup"><span data-stu-id="16174-307">personal code</span></span>
  
<span data-ttu-id="16174-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="16174-308">maksunumber</span></span>
  
<span data-ttu-id="16174-309">identificador maksu</span><span class="sxs-lookup"><span data-stu-id="16174-309">maksu id</span></span>
  
<span data-ttu-id="16174-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="16174-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="16174-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="16174-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="16174-312">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-312">Format</span></span>

<span data-ttu-id="16174-313">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos</span><span class="sxs-lookup"><span data-stu-id="16174-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-314">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-314">Pattern</span></span>

<span data-ttu-id="16174-315">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos:</span><span class="sxs-lookup"><span data-stu-id="16174-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="16174-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-316">Six digits</span></span>
    
- <span data-ttu-id="16174-317">Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distingue entre mayúsculas y minúsculas) donde el signo más significa que nació entre 1800-1899, el signo menos significa que nació entre 1900-1999, y "A" significa que nació 2000 y posterior</span><span class="sxs-lookup"><span data-stu-id="16174-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="16174-318">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-318">Three digits</span></span>
    
- <span data-ttu-id="16174-319">Una letra o un número</span><span class="sxs-lookup"><span data-stu-id="16174-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-320">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-320">Checksum</span></span>

<span data-ttu-id="16174-321">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-322">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-322">Definition</span></span>

<span data-ttu-id="16174-323">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-324">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-325">Se encuentra una `Keywords_finland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-326">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-327">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-328">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="16174-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="16174-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="16174-330">identification number</span></span>
  
<span data-ttu-id="16174-331">identificador personal</span><span class="sxs-lookup"><span data-stu-id="16174-331">personal id</span></span>
  
<span data-ttu-id="16174-332">número de identidad</span><span class="sxs-lookup"><span data-stu-id="16174-332">identity number</span></span>
  
<span data-ttu-id="16174-333">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="16174-333">finnish national id number</span></span>
  
<span data-ttu-id="16174-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-334">personalidnumber#</span></span>
  
<span data-ttu-id="16174-335">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="16174-335">national identification number</span></span>
  
<span data-ttu-id="16174-336">número de identificador</span><span class="sxs-lookup"><span data-stu-id="16174-336">id number</span></span>
  
<span data-ttu-id="16174-337">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="16174-337">national id no.</span></span>
  
<span data-ttu-id="16174-338">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="16174-338">national id number</span></span>
  
<span data-ttu-id="16174-339">identificador no</span><span class="sxs-lookup"><span data-stu-id="16174-339">id no</span></span>
  
<span data-ttu-id="16174-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="16174-340">tunnistenumero</span></span>
  
<span data-ttu-id="16174-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="16174-341">henkilötunnus</span></span>
  
<span data-ttu-id="16174-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="16174-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="16174-343">Ainutlaatuinen henkilökohtainen Tunnus</span><span class="sxs-lookup"><span data-stu-id="16174-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="16174-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="16174-344">identiteetti numero</span></span>
  
<span data-ttu-id="16174-345">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="16174-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="16174-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="16174-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="16174-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="16174-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="16174-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="16174-348">tunnusnumero</span></span>
  
<span data-ttu-id="16174-349">Kansallinen Tunnus numero</span><span class="sxs-lookup"><span data-stu-id="16174-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="16174-350">Francia</span><span class="sxs-lookup"><span data-stu-id="16174-350">France</span></span>

### <a name="format"></a><span data-ttu-id="16174-351">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-351">Format</span></span>

<span data-ttu-id="16174-352">13 dígitos para personas y nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="16174-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-353">Pattern</span></span>

<span data-ttu-id="16174-354">13 dígitos para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="16174-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="16174-355">Un dígito que debe ser 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="16174-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="16174-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-356">12 digits</span></span>
    
<span data-ttu-id="16174-357">Nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="16174-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-358">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-358">Checksum</span></span>

<span data-ttu-id="16174-359">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-360">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-360">Definition</span></span>

<span data-ttu-id="16174-361">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-362">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-363">Se encuentra una `Keywords_france_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-365">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="16174-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="16174-368">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-368">tax identification number</span></span>
  
<span data-ttu-id="16174-369">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-369">tax number</span></span>
  
<span data-ttu-id="16174-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-370">tax id</span></span>
  
<span data-ttu-id="16174-371">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="16174-372">Alemania</span><span class="sxs-lookup"><span data-stu-id="16174-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="16174-373">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-373">Format</span></span>

<span data-ttu-id="16174-374">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-375">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-375">Pattern</span></span>

<span data-ttu-id="16174-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16174-376">11 digits :</span></span>
  
-  <span data-ttu-id="16174-377">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-377">Ten digits</span></span> 
    
- <span data-ttu-id="16174-378">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16174-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-379">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-379">Checksum</span></span>

<span data-ttu-id="16174-380">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-381">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-381">Definition</span></span>

<span data-ttu-id="16174-382">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-383">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-384">Se encuentra una `Keywords_germany_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-385">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-386">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-387">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="16174-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="16174-389">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-389">tax number</span></span>
  
<span data-ttu-id="16174-390">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-390">tax no.</span></span>
  
<span data-ttu-id="16174-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-391">taxno#</span></span>
  
<span data-ttu-id="16174-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-392">taxnumber#</span></span>
  
<span data-ttu-id="16174-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-393">taxnumber</span></span>
  
<span data-ttu-id="16174-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-394">tax id</span></span>
  
<span data-ttu-id="16174-395">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-395">taxid#</span></span>
  
<span data-ttu-id="16174-396">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-396">tax identification number</span></span>
  
<span data-ttu-id="16174-397">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="16174-397">tax identification no.</span></span>
  
<span data-ttu-id="16174-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="16174-398">steuernummer</span></span>
  
<span data-ttu-id="16174-399">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="16174-399">steuer id</span></span>
  
<span data-ttu-id="16174-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="16174-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="16174-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="16174-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="16174-402">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-402">Format</span></span>

<span data-ttu-id="16174-403">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-404">Pattern</span></span>

<span data-ttu-id="16174-405">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-406">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-406">Checksum</span></span>

<span data-ttu-id="16174-407">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-408">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-408">Definition</span></span>

<span data-ttu-id="16174-409">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-410">La expresión `Regex_greece_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-411">Se encuentra una `Keywords_greece_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16174-412">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="16174-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="16174-414">AFM</span><span class="sxs-lookup"><span data-stu-id="16174-414">afm</span></span>
  
<span data-ttu-id="16174-415">tin
</span><span class="sxs-lookup"><span data-stu-id="16174-415">tin</span></span>
  
<span data-ttu-id="16174-416">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-416">tax id no.</span></span>
  
<span data-ttu-id="16174-417">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-417">tax id no</span></span>
  
<span data-ttu-id="16174-418">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-418">tax identification number</span></span>
  
<span data-ttu-id="16174-419">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-419">tax registry number</span></span>
  
<span data-ttu-id="16174-420">n.º de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-420">tax registry no.</span></span>
  
<span data-ttu-id="16174-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="16174-421">afm#</span></span>
  
<span data-ttu-id="16174-422">/</span><span class="sxs-lookup"><span data-stu-id="16174-422">tin#</span></span>
  
<span data-ttu-id="16174-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="16174-423">taxidno#</span></span>
  
<span data-ttu-id="16174-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="16174-424">taxregistryno#</span></span>
  
<span data-ttu-id="16174-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="16174-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="16174-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="16174-426">aφμ</span></span>
  
<span data-ttu-id="16174-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="16174-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="16174-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="16174-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="16174-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="16174-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="16174-430">Hungría</span><span class="sxs-lookup"><span data-stu-id="16174-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="16174-431">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-431">Format</span></span>

<span data-ttu-id="16174-432">Diez dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-433">Pattern</span></span>

<span data-ttu-id="16174-434">Diez dígitos:</span><span class="sxs-lookup"><span data-stu-id="16174-434">Ten digits:</span></span>
  
-  <span data-ttu-id="16174-435">Un dígito que debe ser "8"</span><span class="sxs-lookup"><span data-stu-id="16174-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="16174-436">Cinco dígitos que corresponden al número de días entre la fecha 01/01/1867 y la fecha de nacimiento del individuo.</span><span class="sxs-lookup"><span data-stu-id="16174-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="16174-437">Tres dígitos que corresponden al número generado por oportunidad para diferenciar a los individuos nacidos en el mismo día</span><span class="sxs-lookup"><span data-stu-id="16174-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="16174-438">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16174-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-439">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-439">Checksum</span></span>

<span data-ttu-id="16174-440">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-441">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-441">Definition</span></span>

<span data-ttu-id="16174-442">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-443">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-444">Se encuentra una `Keywords_hungary_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-445">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-446">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-447">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="16174-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="16174-449">número de identificación fiscal húngara</span><span class="sxs-lookup"><span data-stu-id="16174-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="16174-450">NIF Húngaro</span><span class="sxs-lookup"><span data-stu-id="16174-450">hungarian tin</span></span>
  
<span data-ttu-id="16174-451">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-451">tax id number</span></span>
  
<span data-ttu-id="16174-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="16174-452">vat number</span></span>
  
<span data-ttu-id="16174-453">n.º de autoridad fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-453">tax authority no</span></span>
  
<span data-ttu-id="16174-454">número de identidad fiscal de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-454">tax id tax identity number</span></span>
  
<span data-ttu-id="16174-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-455">taxidnumber#</span></span>
  
<span data-ttu-id="16174-456">/</span><span class="sxs-lookup"><span data-stu-id="16174-456">tin#</span></span>
  
<span data-ttu-id="16174-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="16174-457">hungatiantin#</span></span>
  
<span data-ttu-id="16174-458">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-458">tax identification no</span></span>
  
<span data-ttu-id="16174-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="16174-459">taxidno#</span></span>
  
<span data-ttu-id="16174-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="16174-460">adóazonosító szám</span></span>
  
<span data-ttu-id="16174-461">adószám</span><span class="sxs-lookup"><span data-stu-id="16174-461">adószám</span></span>
  
<span data-ttu-id="16174-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="16174-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="16174-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="16174-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="16174-464">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-464">Format</span></span>

<span data-ttu-id="16174-465">Siete dígitos seguidos de una letra sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-466">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-466">Pattern</span></span>

<span data-ttu-id="16174-467">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="16174-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="16174-468">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16174-468">Seven digits</span></span> 
    
- <span data-ttu-id="16174-469">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-470">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-470">Checksum</span></span>

<span data-ttu-id="16174-471">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-472">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-472">Definition</span></span>

<span data-ttu-id="16174-473">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-474">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-475">Se encuentra una `Keywords_ireland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-476">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-477">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="16174-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="16174-480">n.º de servicio público</span><span class="sxs-lookup"><span data-stu-id="16174-480">public service no</span></span>
  
<span data-ttu-id="16174-481">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="16174-481">personal public service no</span></span>
  
<span data-ttu-id="16174-482">n.º de PPS</span><span class="sxs-lookup"><span data-stu-id="16174-482">pps no</span></span>
  
<span data-ttu-id="16174-483">n.º de servicio personal</span><span class="sxs-lookup"><span data-stu-id="16174-483">personal service no</span></span>
  
<span data-ttu-id="16174-484">n.º de servicio de PPS</span><span class="sxs-lookup"><span data-stu-id="16174-484">pps service no</span></span>
  
<span data-ttu-id="16174-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="16174-485">ppsno#</span></span>
  
<span data-ttu-id="16174-486">n.º de PPS irlandés</span><span class="sxs-lookup"><span data-stu-id="16174-486">irish pps no</span></span>
  
<span data-ttu-id="16174-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="16174-487">publicserviceno#</span></span>
  
<span data-ttu-id="16174-488">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="16174-488">personal public service number</span></span>
  
<span data-ttu-id="16174-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="16174-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="16174-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="16174-490">pps uimh</span></span>
  
<span data-ttu-id="16174-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="16174-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="16174-492">Italia</span><span class="sxs-lookup"><span data-stu-id="16174-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="16174-493">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-493">Format</span></span>

<span data-ttu-id="16174-494">16 letras y dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="16174-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-495">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-495">Pattern</span></span>

<span data-ttu-id="16174-496">16 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="16174-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="16174-497">Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="16174-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="16174-498">Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre</span><span class="sxs-lookup"><span data-stu-id="16174-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="16174-499">Dos dígitos que corresponden a los últimos dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="16174-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="16174-500">Un dígito que corresponde al mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="16174-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="16174-501">Dos dígitos que corresponden al día del mes de nacimiento donde se agrega 40 al día de nacimiento para hembras para diferenciar de machos</span><span class="sxs-lookup"><span data-stu-id="16174-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="16174-502">Cuatro dígitos que corresponden a un código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros).</span><span class="sxs-lookup"><span data-stu-id="16174-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="16174-503">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16174-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-504">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-504">Checksum</span></span>

<span data-ttu-id="16174-505">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-506">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-506">Definition</span></span>

<span data-ttu-id="16174-507">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-508">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-509">Se encuentra una `Keywords_italy_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-510">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-511">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-512">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="16174-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="16174-514">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-514">tax number</span></span>
  
<span data-ttu-id="16174-515">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-515">tax no.</span></span>
  
<span data-ttu-id="16174-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-516">taxno#</span></span>
  
<span data-ttu-id="16174-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-517">taxnumber#</span></span>
  
<span data-ttu-id="16174-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-518">taxnumber</span></span>
  
<span data-ttu-id="16174-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-519">tax id</span></span>
  
<span data-ttu-id="16174-520">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-520">taxid#</span></span>
  
<span data-ttu-id="16174-521">Código fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-521">fiscal code</span></span>
  
<span data-ttu-id="16174-522">Codice fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="16174-523">Letonia</span><span class="sxs-lookup"><span data-stu-id="16174-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="16174-524">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-524">Format</span></span>

<span data-ttu-id="16174-525">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-526">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-526">Pattern</span></span>

<span data-ttu-id="16174-527">11 dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="16174-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="16174-528">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="16174-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="16174-529">Un dígito que corresponde al siglo de nacimiento en el que "0" corresponde al siglo XIX, "1" corresponde al siglo XX y "2" corresponde al siglo XXI.</span><span class="sxs-lookup"><span data-stu-id="16174-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="16174-530">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-531">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-531">Checksum</span></span>

<span data-ttu-id="16174-532">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-533">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-533">Definition</span></span>

<span data-ttu-id="16174-534">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-535">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-536">Se encuentra una `Keywords_latvia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-537">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-538">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-539">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="16174-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="16174-541">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-541">tax number</span></span>
  
<span data-ttu-id="16174-542">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-542">tax no.</span></span>
  
<span data-ttu-id="16174-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-543">taxno#</span></span>
  
<span data-ttu-id="16174-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-544">taxnumber#</span></span>
  
<span data-ttu-id="16174-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-545">taxnumber</span></span>
  
<span data-ttu-id="16174-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-546">tax id</span></span>
  
<span data-ttu-id="16174-547">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-547">taxid#</span></span>
  
<span data-ttu-id="16174-548">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-548">tax identification number</span></span>
  
<span data-ttu-id="16174-549">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="16174-549">tax identification no.</span></span>
  
<span data-ttu-id="16174-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="16174-550">nodokļa numurs</span></span>
  
<span data-ttu-id="16174-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="16174-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="16174-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="16174-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="16174-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="16174-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="16174-554">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-554">Format</span></span>

<span data-ttu-id="16174-555">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-556">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-556">Pattern</span></span>

<span data-ttu-id="16174-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-558">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-558">Checksum</span></span>

<span data-ttu-id="16174-559">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-560">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-560">Definition</span></span>

<span data-ttu-id="16174-561">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-562">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-563">Se encuentra una `Keywords_lithuania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-564">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-565">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-566">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="16174-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="16174-568">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-568">tax number</span></span>
  
<span data-ttu-id="16174-569">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-569">tax no.</span></span>
  
<span data-ttu-id="16174-570">impto.</span><span class="sxs-lookup"><span data-stu-id="16174-570">tax no#</span></span>
  
<span data-ttu-id="16174-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-571">taxnumber#</span></span>
  
<span data-ttu-id="16174-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-572">taxnumber</span></span>
  
<span data-ttu-id="16174-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-573">tax id</span></span>
  
<span data-ttu-id="16174-574">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-574">taxid#</span></span>
  
<span data-ttu-id="16174-575">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-575">tax identification number</span></span>
  
<span data-ttu-id="16174-576">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="16174-576">tax identification no.</span></span>
  
<span data-ttu-id="16174-577">identificador mokesčių</span><span class="sxs-lookup"><span data-stu-id="16174-577">mokesčių id</span></span>
  
<span data-ttu-id="16174-578">numeración mokesčių</span><span class="sxs-lookup"><span data-stu-id="16174-578">mokesčių numeris</span></span>
  
<span data-ttu-id="16174-579">mokesčių identifikavimas número</span><span class="sxs-lookup"><span data-stu-id="16174-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="16174-580">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="16174-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="16174-581">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-581">Format</span></span>

<span data-ttu-id="16174-582">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-583">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-583">Pattern</span></span>

<span data-ttu-id="16174-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="16174-584">13 digits:</span></span>
  
-  <span data-ttu-id="16174-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-585">11 digits</span></span> 
    
- <span data-ttu-id="16174-586">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="16174-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-587">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-587">Checksum</span></span>

<span data-ttu-id="16174-588">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-589">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-589">Definition</span></span>

<span data-ttu-id="16174-590">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-591">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-592">Se encuentra una `Keywords_luxemburg_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-593">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-594">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-595">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="16174-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="16174-597">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-597">tax number</span></span>
  
<span data-ttu-id="16174-598">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-598">tax no.</span></span>
  
<span data-ttu-id="16174-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-599">taxno#</span></span>
  
<span data-ttu-id="16174-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-600">taxnumber#</span></span>
  
<span data-ttu-id="16174-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-601">taxnumber</span></span>
  
<span data-ttu-id="16174-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-602">tax id</span></span>
  
<span data-ttu-id="16174-603">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-603">taxid#</span></span>
  
<span data-ttu-id="16174-604">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-604">tax identification number</span></span>
  
<span data-ttu-id="16174-605">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="16174-605">tax identification no.</span></span>
  
<span data-ttu-id="16174-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="16174-606">steuernummer</span></span>
  
<span data-ttu-id="16174-607">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="16174-607">steuer id</span></span>
  
<span data-ttu-id="16174-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="16174-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="16174-609">Malta</span><span class="sxs-lookup"><span data-stu-id="16174-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="16174-610">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-610">Format</span></span>

<span data-ttu-id="16174-611">Para los nacionales de Maltés: 7 dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="16174-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="16174-612">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-613">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-613">Pattern</span></span>

<span data-ttu-id="16174-614">Nacionales de Malta: 7 dígitos y una letra</span><span class="sxs-lookup"><span data-stu-id="16174-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="16174-615">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16174-615">Seven digits</span></span> 
    
- <span data-ttu-id="16174-616">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="16174-617">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="16174-618">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="16174-619">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-619">Checksum</span></span>

<span data-ttu-id="16174-620">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-621">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-621">Definition</span></span>

<span data-ttu-id="16174-622">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-623">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-624">Se encuentra una `Keywords_malta_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-625">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-626">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-627">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="16174-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="16174-629">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-629">tax number</span></span>
  
<span data-ttu-id="16174-630">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-630">tax no.</span></span>
  
<span data-ttu-id="16174-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-631">taxno#</span></span>
  
<span data-ttu-id="16174-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-632">taxnumber#</span></span>
  
<span data-ttu-id="16174-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-633">taxnumber</span></span>
  
<span data-ttu-id="16174-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-634">tax id</span></span>
  
<span data-ttu-id="16174-635">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-635">taxid#</span></span>
  
<span data-ttu-id="16174-636">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-636">tax identification number</span></span>
  
<span data-ttu-id="16174-637">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="16174-637">tax identification no.</span></span>
  
<span data-ttu-id="16174-638">numru TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="16174-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="16174-639">identificador TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="16174-639">id tat-taxxa</span></span>
  
<span data-ttu-id="16174-640">numru ta ' identifikazzjoni TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="16174-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="16174-641">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="16174-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="16174-642">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-642">Format</span></span>

<span data-ttu-id="16174-643">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-644">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-644">Pattern</span></span>

<span data-ttu-id="16174-645">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="16174-646">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-646">Checksum</span></span>

<span data-ttu-id="16174-647">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-648">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-648">Definition</span></span>

<span data-ttu-id="16174-649">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-650">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-651">Se encuentra una `Keywords_netherlands_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-652">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-653">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-654">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="16174-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="16174-656">número de identificación fiscal de países bajos</span><span class="sxs-lookup"><span data-stu-id="16174-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="16174-657">identificación de impuestos de países bajos</span><span class="sxs-lookup"><span data-stu-id="16174-657">netherlands tax identification</span></span>
  
<span data-ttu-id="16174-658">número de identificación fiscal de Netherland</span><span class="sxs-lookup"><span data-stu-id="16174-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="16174-659">identificación de impuestos de Netherland</span><span class="sxs-lookup"><span data-stu-id="16174-659">netherland's tax identification</span></span>
  
<span data-ttu-id="16174-660">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-660">tax identification number</span></span>
  
<span data-ttu-id="16174-661">identificador fiscal holandés</span><span class="sxs-lookup"><span data-stu-id="16174-661">dutch tax id</span></span>
  
<span data-ttu-id="16174-662">número de identificación fiscal holandes</span><span class="sxs-lookup"><span data-stu-id="16174-662">dutch tax identification number</span></span>
  
<span data-ttu-id="16174-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-663">tax id</span></span>
  
<span data-ttu-id="16174-664">n.º de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-664">tax id#</span></span>
  
<span data-ttu-id="16174-665">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-665">tax number</span></span>
  
<span data-ttu-id="16174-666">impto.</span><span class="sxs-lookup"><span data-stu-id="16174-666">tax no#</span></span>
  
<span data-ttu-id="16174-667">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-667">tax#</span></span>
  
<span data-ttu-id="16174-668">tin
</span><span class="sxs-lookup"><span data-stu-id="16174-668">tin</span></span>
  
<span data-ttu-id="16174-669">/</span><span class="sxs-lookup"><span data-stu-id="16174-669">tin#</span></span>
  
<span data-ttu-id="16174-670">NIF-Países Bajos</span><span class="sxs-lookup"><span data-stu-id="16174-670">netherlands tin</span></span>
  
<span data-ttu-id="16174-671">estaño de Netherland</span><span class="sxs-lookup"><span data-stu-id="16174-671">netherland's tin</span></span>
  
<span data-ttu-id="16174-672">último países de la identificatienummer</span><span class="sxs-lookup"><span data-stu-id="16174-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="16174-673">identificatienummerto de furgoneta</span><span class="sxs-lookup"><span data-stu-id="16174-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="16174-674">identificatienummer en último lugar</span><span class="sxs-lookup"><span data-stu-id="16174-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="16174-675">último países de la identificatie</span><span class="sxs-lookup"><span data-stu-id="16174-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="16174-676">último identificador de Nummer de países bajos</span><span class="sxs-lookup"><span data-stu-id="16174-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="16174-677">Países Bajos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="16174-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="16174-678">BTW Nummer</span><span class="sxs-lookup"><span data-stu-id="16174-678">btw nummer</span></span>
  
<span data-ttu-id="16174-679">Nederlandse de la última identificatie</span><span class="sxs-lookup"><span data-stu-id="16174-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="16174-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="16174-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="16174-681">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-681">Format</span></span>

<span data-ttu-id="16174-682">Once dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-683">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-683">Pattern</span></span>

<span data-ttu-id="16174-684">Once dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-685">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-685">Checksum</span></span>

<span data-ttu-id="16174-686">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-687">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-687">Definition</span></span>

<span data-ttu-id="16174-688">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-689">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-690">Se encuentra una `Keywords_poland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-691">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-692">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-693">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="16174-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="16174-695">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-695">tax number</span></span>
  
<span data-ttu-id="16174-696">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-696">tax no.</span></span>
  
<span data-ttu-id="16174-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-697">taxno#</span></span>
  
<span data-ttu-id="16174-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-698">taxnumber#</span></span>
  
<span data-ttu-id="16174-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-699">taxnumber</span></span>
  
<span data-ttu-id="16174-700">NIP</span><span class="sxs-lookup"><span data-stu-id="16174-700">nip</span></span>
  
<span data-ttu-id="16174-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="16174-701">nip#</span></span>
  
<span data-ttu-id="16174-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-702">tax id</span></span>
  
<span data-ttu-id="16174-703">n.º de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-703">tax id#</span></span>
  
<span data-ttu-id="16174-704">identificador NIP</span><span class="sxs-lookup"><span data-stu-id="16174-704">nip id</span></span>
  
<span data-ttu-id="16174-705">número de identificador de NIP</span><span class="sxs-lookup"><span data-stu-id="16174-705">nip id#</span></span>
  
<span data-ttu-id="16174-706">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-706">tax identification number</span></span>
  
<span data-ttu-id="16174-707">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="16174-707">tax identification no.</span></span>
  
<span data-ttu-id="16174-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="16174-708">vat number</span></span>
  
<span data-ttu-id="16174-709">n.º de IVA</span><span class="sxs-lookup"><span data-stu-id="16174-709">vat no.</span></span>
  
<span data-ttu-id="16174-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="16174-710">vatno#</span></span>
  
<span data-ttu-id="16174-711">NIF</span><span class="sxs-lookup"><span data-stu-id="16174-711">vat id</span></span>
  
<span data-ttu-id="16174-712">n.º de ID de IVA</span><span class="sxs-lookup"><span data-stu-id="16174-712">vat id#</span></span>
  
<span data-ttu-id="16174-713">numerar identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="16174-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="16174-714">Polski número de identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="16174-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="16174-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="16174-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="16174-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="16174-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="16174-717">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-717">Format</span></span>

<span data-ttu-id="16174-718">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-719">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-719">Pattern</span></span>

<span data-ttu-id="16174-720">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-721">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-721">Checksum</span></span>

<span data-ttu-id="16174-722">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-723">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-723">Definition</span></span>

<span data-ttu-id="16174-724">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-725">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-726">Se encuentra una `Keywords_portugal_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-727">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-728">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-729">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="16174-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="16174-731">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-731">tax number</span></span>
  
<span data-ttu-id="16174-732">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-732">tax no.</span></span>
  
<span data-ttu-id="16174-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-733">taxno#</span></span>
  
<span data-ttu-id="16174-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="16174-734">taxnumber#</span></span>
  
<span data-ttu-id="16174-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="16174-735">taxnumber</span></span>
  
<span data-ttu-id="16174-736">NIF</span><span class="sxs-lookup"><span data-stu-id="16174-736">nif</span></span>
  
<span data-ttu-id="16174-737">NIF</span><span class="sxs-lookup"><span data-stu-id="16174-737">nif#</span></span>
  
<span data-ttu-id="16174-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="16174-738">numero fiscal</span></span>
  
<span data-ttu-id="16174-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="16174-740">Rumania</span><span class="sxs-lookup"><span data-stu-id="16174-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="16174-741">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-741">Format</span></span>

<span data-ttu-id="16174-742">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-743">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-743">Pattern</span></span>

<span data-ttu-id="16174-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-745">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-745">Checksum</span></span>

<span data-ttu-id="16174-746">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-747">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-747">Definition</span></span>

<span data-ttu-id="16174-748">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-749">La expresión `Regex_romania_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-750">Se encuentra una `Keywords_romania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16174-751">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="16174-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="16174-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-753">tax id</span></span>
  
<span data-ttu-id="16174-754">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-754">tax id number</span></span>
  
<span data-ttu-id="16174-755">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-755">tax file no</span></span>
  
<span data-ttu-id="16174-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="16174-756">tax file number</span></span>
  
<span data-ttu-id="16174-757">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-757">tax no</span></span>
  
<span data-ttu-id="16174-758">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-758">tax number</span></span>
  
<span data-ttu-id="16174-759">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-759">taxid#</span></span>
  
<span data-ttu-id="16174-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-760">taxno#</span></span>
  
<span data-ttu-id="16174-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="16174-761">id-ul taxei</span></span>
  
<span data-ttu-id="16174-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="16174-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="16174-763">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="16174-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="16174-764">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-764">Format</span></span>

<span data-ttu-id="16174-765">10 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-766">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-766">Pattern</span></span>

<span data-ttu-id="16174-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-768">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-768">Checksum</span></span>

<span data-ttu-id="16174-769">No aplicable</span><span class="sxs-lookup"><span data-stu-id="16174-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-770">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-770">Definition</span></span>

<span data-ttu-id="16174-771">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-772">La expresión `Regex_slovakia_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-773">Se encuentra una `Keywords_slovakia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16174-774">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="16174-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="16174-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-776">tax id</span></span>
  
<span data-ttu-id="16174-777">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-777">tax id number</span></span>
  
<span data-ttu-id="16174-778">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="16174-778">tin id</span></span>
  
<span data-ttu-id="16174-779">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="16174-779">tin no</span></span>
  
<span data-ttu-id="16174-780">ID de estaño de eslovaco</span><span class="sxs-lookup"><span data-stu-id="16174-780">slovakian tin id</span></span>
  
<span data-ttu-id="16174-781">tin
</span><span class="sxs-lookup"><span data-stu-id="16174-781">tin</span></span>
  
<span data-ttu-id="16174-782">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-782">tax file no</span></span>
  
<span data-ttu-id="16174-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="16174-783">tax file number</span></span>
  
<span data-ttu-id="16174-784">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-784">tax no</span></span>
  
<span data-ttu-id="16174-785">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-785">tax number</span></span>
  
<span data-ttu-id="16174-786">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-786">taxid#</span></span>
  
<span data-ttu-id="16174-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-787">taxno#</span></span>
  
<span data-ttu-id="16174-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="16174-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="16174-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="16174-789">daňové číslo</span></span>
  
<span data-ttu-id="16174-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="16174-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="16174-791">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="16174-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="16174-792">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-792">Format</span></span>

<span data-ttu-id="16174-793">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-794">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-794">Pattern</span></span>

<span data-ttu-id="16174-795">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-796">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-796">Checksum</span></span>

<span data-ttu-id="16174-797">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-798">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-798">Definition</span></span>

<span data-ttu-id="16174-799">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-800">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-801">Se encuentra una `Keywords_slovenia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-802">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-803">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-804">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="16174-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="16174-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-806">tax id</span></span>
  
<span data-ttu-id="16174-807">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-807">tax id number</span></span>
  
<span data-ttu-id="16174-808">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="16174-808">tin id</span></span>
  
<span data-ttu-id="16174-809">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="16174-809">tin no</span></span>
  
<span data-ttu-id="16174-810">ID de estaño de esloveno</span><span class="sxs-lookup"><span data-stu-id="16174-810">slovenian tin id</span></span>
  
<span data-ttu-id="16174-811">tin
</span><span class="sxs-lookup"><span data-stu-id="16174-811">tin</span></span>
  
<span data-ttu-id="16174-812">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-812">tax file no</span></span>
  
<span data-ttu-id="16174-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="16174-813">tax file number</span></span>
  
<span data-ttu-id="16174-814">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-814">tax no</span></span>
  
<span data-ttu-id="16174-815">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-815">tax number</span></span>
  
<span data-ttu-id="16174-816">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-816">taxid#</span></span>
  
<span data-ttu-id="16174-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-817">taxno#</span></span>
  
<span data-ttu-id="16174-818">identifikacijska številka Davka</span><span class="sxs-lookup"><span data-stu-id="16174-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="16174-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="16174-819">davčna številka</span></span>
  
<span data-ttu-id="16174-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="16174-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="16174-821">España</span><span class="sxs-lookup"><span data-stu-id="16174-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="16174-822">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-822">Format</span></span>

<span data-ttu-id="16174-823">Siete u ocho dígitos y una o dos letras en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="16174-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-824">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-824">Pattern</span></span>

<span data-ttu-id="16174-825">Personas físicas españolas con una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="16174-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="16174-826">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-826">Eight digits</span></span> 
    
- <span data-ttu-id="16174-827">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="16174-828">Spaniards no residente sin una tarjeta de identidad nacional de España</span><span class="sxs-lookup"><span data-stu-id="16174-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="16174-829">Una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="16174-830">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16174-830">Seven digits</span></span>
    
- <span data-ttu-id="16174-831">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="16174-832">Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="16174-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="16174-833">Una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="16174-834">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16174-834">Seven digits</span></span> 
    
- <span data-ttu-id="16174-835">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="16174-836">Foreigners con un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="16174-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="16174-837">Una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="16174-838">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16174-838">Seven digits</span></span>
    
- <span data-ttu-id="16174-839">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="16174-840">Foreigners sin un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="16174-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="16174-841">Una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="16174-842">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="16174-842">Seven digits</span></span>
    
- <span data-ttu-id="16174-843">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="16174-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="16174-844">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-844">Checksum</span></span>

<span data-ttu-id="16174-845">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-846">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-846">Definition</span></span>

<span data-ttu-id="16174-847">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-848">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-849">Se encuentra una `Keywords_spain_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-850">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-851">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-852">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="16174-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="16174-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-854">tax id</span></span>
  
<span data-ttu-id="16174-855">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-855">tax id number</span></span>
  
<span data-ttu-id="16174-856">identificador CIF</span><span class="sxs-lookup"><span data-stu-id="16174-856">cif id</span></span>
  
<span data-ttu-id="16174-857">n.º CIF</span><span class="sxs-lookup"><span data-stu-id="16174-857">cif no</span></span>
  
<span data-ttu-id="16174-858">identificador CIF en Español</span><span class="sxs-lookup"><span data-stu-id="16174-858">spanish cif id</span></span>
  
<span data-ttu-id="16174-859">precio</span><span class="sxs-lookup"><span data-stu-id="16174-859">cif</span></span>
  
<span data-ttu-id="16174-860">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-860">tax file no</span></span>
  
<span data-ttu-id="16174-861">Número CIF en Español</span><span class="sxs-lookup"><span data-stu-id="16174-861">spanish cif number</span></span>
  
<span data-ttu-id="16174-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="16174-862">tax file number</span></span>
  
<span data-ttu-id="16174-863">Número CIF de Español</span><span class="sxs-lookup"><span data-stu-id="16174-863">spanish cif no</span></span>
  
<span data-ttu-id="16174-864">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-864">tax no</span></span>
  
<span data-ttu-id="16174-865">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="16174-865">tax number</span></span>
  
<span data-ttu-id="16174-866">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-866">taxid#</span></span>
  
<span data-ttu-id="16174-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="16174-867">taxno#</span></span>
  
<span data-ttu-id="16174-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="16174-868">cifid#</span></span>
  
<span data-ttu-id="16174-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="16174-869">spanishcifid#</span></span>
  
<span data-ttu-id="16174-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="16174-870">spanishcifno#</span></span>
  
<span data-ttu-id="16174-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="16174-871">número de contribuyente</span></span>
  
<span data-ttu-id="16174-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="16174-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="16174-873">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="16174-874">Número CIF</span><span class="sxs-lookup"><span data-stu-id="16174-874">cif número</span></span>
  
<span data-ttu-id="16174-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="16174-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="16174-876">Suecia</span><span class="sxs-lookup"><span data-stu-id="16174-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="16174-877">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-877">Format</span></span>

<span data-ttu-id="16174-878">Diez dígitos y un símbolo en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="16174-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-879">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-879">Pattern</span></span>

<span data-ttu-id="16174-880">Diez dígitos y un símbolo:</span><span class="sxs-lookup"><span data-stu-id="16174-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="16174-881">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="16174-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="16174-882">Un signo más, un signo menos o una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="16174-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="16174-883">Tres dígitos que hacen que el número de identificación sea único donde:</span><span class="sxs-lookup"><span data-stu-id="16174-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="16174-884">Para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero</span><span class="sxs-lookup"><span data-stu-id="16174-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="16174-885">El dígito en la novena posición indica el género, ya sea impar o incluso para hembras</span><span class="sxs-lookup"><span data-stu-id="16174-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="16174-886">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="16174-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="16174-887">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-887">Checksum</span></span>

<span data-ttu-id="16174-888">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-889">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-889">Definition</span></span>

<span data-ttu-id="16174-890">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-891">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-892">Se encuentra una `Keywords_sweden_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="16174-893">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-894">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="16174-895">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="16174-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="16174-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-897">tax id</span></span>
  
<span data-ttu-id="16174-898">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-898">tax id no.</span></span>
  
<span data-ttu-id="16174-899">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-899">tax id number</span></span>
  
<span data-ttu-id="16174-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="16174-900">tax identification</span></span>
  
<span data-ttu-id="16174-901">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-901">tax identification#</span></span>
  
<span data-ttu-id="16174-902">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-902">tax no.</span></span>
  
<span data-ttu-id="16174-903">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-903">tax#</span></span>
  
<span data-ttu-id="16174-904">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-904">taxid#</span></span>
  
<span data-ttu-id="16174-905">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-905">tax file</span></span>
  
<span data-ttu-id="16174-906">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="16174-906">tax file no.</span></span>
  
<span data-ttu-id="16174-907">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="16174-907">personal id number</span></span>
  
<span data-ttu-id="16174-908">Nummer de identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="16174-908">skatt id nummer</span></span>
  
<span data-ttu-id="16174-909">Identifikation de patinaje</span><span class="sxs-lookup"><span data-stu-id="16174-909">skatt identifikation</span></span>
  
<span data-ttu-id="16174-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="16174-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="16174-911">LIBRA</span><span class="sxs-lookup"><span data-stu-id="16174-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="16174-912">Formato</span><span class="sxs-lookup"><span data-stu-id="16174-912">Format</span></span>

<span data-ttu-id="16174-913">Referencia fiscal única (UTR): 10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="16174-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="16174-p103">Número de seguro nacional (NINO): para obtener más información, consulte la sección "número de seguro nacional del Reino Unido (NINO)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="16174-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="16174-916">Patrón</span><span class="sxs-lookup"><span data-stu-id="16174-916">Pattern</span></span>

<span data-ttu-id="16174-917">Referencia de contribuyente única (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="16174-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="16174-p104">Número de seguro nacional (NINO): para obtener más información, consulte la sección "número de seguro nacional del Reino Unido (NINO)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="16174-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="16174-920">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="16174-920">Checksum</span></span>

<span data-ttu-id="16174-921">Sí</span><span class="sxs-lookup"><span data-stu-id="16174-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="16174-922">Definición</span><span class="sxs-lookup"><span data-stu-id="16174-922">Definition</span></span>

<span data-ttu-id="16174-923">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="16174-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="16174-924">La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="16174-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="16174-925">Se encuentra una `Keywords_uk_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="16174-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16174-926">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16174-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="16174-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="16174-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="16174-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="16174-928">tax id</span></span>
  
<span data-ttu-id="16174-929">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-929">tax id no.</span></span>
  
<span data-ttu-id="16174-930">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-930">tax id number</span></span>
  
<span data-ttu-id="16174-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="16174-931">tax identification</span></span>
  
<span data-ttu-id="16174-932">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="16174-932">tax identification#</span></span>
  
<span data-ttu-id="16174-933">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-933">tax no.</span></span>
  
<span data-ttu-id="16174-934">Tax</span><span class="sxs-lookup"><span data-stu-id="16174-934">tax#</span></span>
  
<span data-ttu-id="16174-935">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="16174-935">taxid#</span></span>
  
<span data-ttu-id="16174-936">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="16174-936">tax file</span></span>
  
<span data-ttu-id="16174-937">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="16174-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16174-938">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16174-938">See also</span></span>

[<span data-ttu-id="16174-939">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="16174-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

