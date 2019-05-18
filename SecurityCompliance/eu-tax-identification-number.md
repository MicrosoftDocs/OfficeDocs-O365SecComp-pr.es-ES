---
title: Número de identificación fiscal de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de identificación de impuestos de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152962"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="719e8-104">Número de identificación fiscal de la UE</span><span class="sxs-lookup"><span data-stu-id="719e8-104">EU Tax Identification Number</span></span>

<span data-ttu-id="719e8-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de identificación fiscal (CIF) de la UE.</span><span class="sxs-lookup"><span data-stu-id="719e8-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="719e8-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="719e8-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="719e8-107">Austria</span><span class="sxs-lookup"><span data-stu-id="719e8-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="719e8-108">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-108">Format</span></span>

<span data-ttu-id="719e8-109">Nueve dígitos con guión opcional y barra diagonal</span><span class="sxs-lookup"><span data-stu-id="719e8-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-110">Pattern</span></span>

<span data-ttu-id="719e8-111">Nueve dígitos con guión opcional y barra diagonal:</span><span class="sxs-lookup"><span data-stu-id="719e8-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="719e8-112">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-112">Two digits</span></span> 
    
- <span data-ttu-id="719e8-113">Un guion (opcional)</span><span class="sxs-lookup"><span data-stu-id="719e8-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="719e8-114">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-114">Three digits</span></span>
    
- <span data-ttu-id="719e8-115">Una barra diagonal (opcional)</span><span class="sxs-lookup"><span data-stu-id="719e8-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="719e8-116">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-117">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-117">Checksum</span></span>

<span data-ttu-id="719e8-118">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-119">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-119">Definition</span></span>

<span data-ttu-id="719e8-120">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-121">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-122">Se encuentra una `Keywords_austria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-123">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-124">La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-125">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="719e8-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-127">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-127">tax number</span></span>
  
<span data-ttu-id="719e8-128">número</span><span class="sxs-lookup"><span data-stu-id="719e8-128">number</span></span>
  
<span data-ttu-id="719e8-129">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="719e8-129">tax registration number</span></span>
  
<span data-ttu-id="719e8-130">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-130">tax id</span></span>
  
<span data-ttu-id="719e8-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="719e8-131">st.nr.</span></span>
  
<span data-ttu-id="719e8-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="719e8-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="719e8-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="719e8-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="719e8-134">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-134">Format</span></span>

<span data-ttu-id="719e8-135">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-136">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-136">Pattern</span></span>

<span data-ttu-id="719e8-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="719e8-137">11 digits:</span></span>
  
- <span data-ttu-id="719e8-138">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-138">Two digits</span></span>
    
- <span data-ttu-id="719e8-139">Un "0" o "1"</span><span class="sxs-lookup"><span data-stu-id="719e8-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="719e8-140">Un dígito</span><span class="sxs-lookup"><span data-stu-id="719e8-140">One digit</span></span>
    
- <span data-ttu-id="719e8-141">Un "0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="719e8-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="719e8-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-143">Checksum</span></span>

<span data-ttu-id="719e8-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-145">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-145">Definition</span></span>

<span data-ttu-id="719e8-146">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-147">La expresión `Regex_belgium_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-148">Se encuentra una `Keywords_belgium_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="719e8-149">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="719e8-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-151">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-151">tax number</span></span>
  
<span data-ttu-id="719e8-152">número de registro nacional</span><span class="sxs-lookup"><span data-stu-id="719e8-152">national registration number</span></span>
  
<span data-ttu-id="719e8-153">NIF-CIF</span><span class="sxs-lookup"><span data-stu-id="719e8-153">tax registration number</span></span>
  
<span data-ttu-id="719e8-154">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-154">tax id</span></span>
  
<span data-ttu-id="719e8-155">NIF</span><span class="sxs-lookup"><span data-stu-id="719e8-155">nif</span></span>
  
<span data-ttu-id="719e8-156">NIF</span><span class="sxs-lookup"><span data-stu-id="719e8-156">nif#</span></span>
  
<span data-ttu-id="719e8-157">numéro de registros nacionales</span><span class="sxs-lookup"><span data-stu-id="719e8-157">numéro de registre national</span></span>
  
<span data-ttu-id="719e8-158">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="719e8-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="719e8-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="719e8-160">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-160">Format</span></span>

<span data-ttu-id="719e8-161">Diez dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-162">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-162">Pattern</span></span>

<span data-ttu-id="719e8-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-164">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-164">Checksum</span></span>

<span data-ttu-id="719e8-165">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-166">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-166">Definition</span></span>

<span data-ttu-id="719e8-167">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-168">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-169">Se encuentra una `Keywords_bulgaria_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-170">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-171">La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-172">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="719e8-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-174">bucn</span><span class="sxs-lookup"><span data-stu-id="719e8-174">bucn</span></span>
  
<span data-ttu-id="719e8-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="719e8-175">uniform civil number</span></span>
  
<span data-ttu-id="719e8-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="719e8-176">bucn#</span></span>
  
<span data-ttu-id="719e8-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="719e8-178">identificador civil uniforme</span><span class="sxs-lookup"><span data-stu-id="719e8-178">uniform civil id</span></span>
  
<span data-ttu-id="719e8-179">Uniform civil no</span><span class="sxs-lookup"><span data-stu-id="719e8-179">uniform civil no</span></span>
  
<span data-ttu-id="719e8-180">egn</span><span class="sxs-lookup"><span data-stu-id="719e8-180">egn</span></span>
  
<span data-ttu-id="719e8-181">número civil uniforme de búlgaro</span><span class="sxs-lookup"><span data-stu-id="719e8-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="719e8-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="719e8-182">uniformcivilno#</span></span>
  
<span data-ttu-id="719e8-183">egn#</span><span class="sxs-lookup"><span data-stu-id="719e8-183">egn#</span></span>
  
<span data-ttu-id="719e8-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="719e8-184">униформ граждански номер</span></span>
  
<span data-ttu-id="719e8-185">identificador униформ</span><span class="sxs-lookup"><span data-stu-id="719e8-185">униформ id</span></span>
  
<span data-ttu-id="719e8-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="719e8-186">униформ граждански id</span></span>
  
<span data-ttu-id="719e8-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="719e8-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="719e8-188">Croacia</span><span class="sxs-lookup"><span data-stu-id="719e8-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="719e8-189">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-189">Format</span></span>

<span data-ttu-id="719e8-190">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-191">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-191">Pattern</span></span>

<span data-ttu-id="719e8-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="719e8-192">11 digits:</span></span>
  
- <span data-ttu-id="719e8-193">Diez dígitos, elegidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="719e8-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="719e8-194">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="719e8-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-195">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-195">Checksum</span></span>

<span data-ttu-id="719e8-196">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-197">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-197">Definition</span></span>

<span data-ttu-id="719e8-198">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-199">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-200">Se encuentra una `Keywords_croatia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-201">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-202">La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-203">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="719e8-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-205">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-205">tax number</span></span>
  
<span data-ttu-id="719e8-206">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-206">tax</span></span>
  
<span data-ttu-id="719e8-207">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-207">tax id</span></span>
  
<span data-ttu-id="719e8-208">oid</span><span class="sxs-lookup"><span data-stu-id="719e8-208">oid</span></span>
  
<span data-ttu-id="719e8-209">OID</span><span class="sxs-lookup"><span data-stu-id="719e8-209">oid#</span></span>
  
<span data-ttu-id="719e8-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="719e8-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="719e8-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="719e8-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="719e8-212">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-212">Format</span></span>

<span data-ttu-id="719e8-213">Ocho dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="719e8-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-214">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-214">Pattern</span></span>

<span data-ttu-id="719e8-215">Ocho dígitos y una letra:</span><span class="sxs-lookup"><span data-stu-id="719e8-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="719e8-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="719e8-216">A "0"</span></span> 
    
- <span data-ttu-id="719e8-217">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="719e8-217">Seven digits</span></span>
    
- <span data-ttu-id="719e8-218">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-219">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-219">Checksum</span></span>

<span data-ttu-id="719e8-220">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-221">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-221">Definition</span></span>

<span data-ttu-id="719e8-222">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-223">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-224">Se encuentra una `Keywords_cyprus_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-225">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-226">La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-227">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="719e8-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-229">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-229">tax number</span></span>
  
<span data-ttu-id="719e8-230">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-230">tax</span></span>
  
<span data-ttu-id="719e8-231">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-231">tax id</span></span>
  
<span data-ttu-id="719e8-232">código de identificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-232">tax identification code</span></span>
  
<span data-ttu-id="719e8-233">verticales</span><span class="sxs-lookup"><span data-stu-id="719e8-233">tic</span></span>
  
<span data-ttu-id="719e8-234">verticales</span><span class="sxs-lookup"><span data-stu-id="719e8-234">tic#</span></span>
  
<span data-ttu-id="719e8-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="719e8-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="719e8-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="719e8-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="719e8-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="719e8-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="719e8-238">Chequia</span><span class="sxs-lookup"><span data-stu-id="719e8-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="719e8-239">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-239">Format</span></span>

<span data-ttu-id="719e8-240">Nueve o diez dígitos con una barra diagonal inversa opcional</span><span class="sxs-lookup"><span data-stu-id="719e8-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-241">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-241">Pattern</span></span>

<span data-ttu-id="719e8-242">Nueve o diez dígitos con una barra diagonal inversa opcional:</span><span class="sxs-lookup"><span data-stu-id="719e8-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="719e8-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-243">Six digits</span></span> 
    
- <span data-ttu-id="719e8-244">Una barra diagonal inversa (opcional)</span><span class="sxs-lookup"><span data-stu-id="719e8-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="719e8-245">Tres o cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-246">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-246">Checksum</span></span>

<span data-ttu-id="719e8-247">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-248">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-248">Definition</span></span>

<span data-ttu-id="719e8-249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-250">La expresión `Regex_czech_republic_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-251">Se encuentra una `Keywords_czech_republic_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="719e8-252">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="719e8-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-254">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-254">tax number</span></span>
  
<span data-ttu-id="719e8-255">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-255">tax</span></span>
  
<span data-ttu-id="719e8-256">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-256">tax id</span></span>
  
<span data-ttu-id="719e8-257">número personal</span><span class="sxs-lookup"><span data-stu-id="719e8-257">personal number</span></span>
  
<span data-ttu-id="719e8-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="719e8-258">daňové číslo</span></span>
  
<span data-ttu-id="719e8-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="719e8-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="719e8-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="719e8-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="719e8-261">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-261">Format</span></span>

<span data-ttu-id="719e8-262">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="719e8-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-263">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-263">Pattern</span></span>

<span data-ttu-id="719e8-264">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="719e8-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="719e8-265">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="719e8-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="719e8-266">Un guión </span><span class="sxs-lookup"><span data-stu-id="719e8-266">A hyphen</span></span>
    
- <span data-ttu-id="719e8-267">Cuatro dígitos que corresponden a un número de secuencia en el que el primer dígito corresponde al siglo de nacimiento y el último dígito corresponde al sexo de la persona (impar para macho e incluso para hembras)</span><span class="sxs-lookup"><span data-stu-id="719e8-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-268">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-268">Checksum</span></span>

<span data-ttu-id="719e8-269">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-270">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-270">Definition</span></span>

<span data-ttu-id="719e8-271">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-272">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-273">Se encuentra una `Keywords_denmark_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-275">La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-276">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="719e8-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-278">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-278">tax number</span></span>
  
<span data-ttu-id="719e8-279">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-279">tax</span></span>
  
<span data-ttu-id="719e8-280">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-280">tax id</span></span>
  
<span data-ttu-id="719e8-281">RCP número</span><span class="sxs-lookup"><span data-stu-id="719e8-281">cpr number</span></span>
  
<span data-ttu-id="719e8-282">RCP</span><span class="sxs-lookup"><span data-stu-id="719e8-282">cpr#</span></span>
  
<span data-ttu-id="719e8-283">Nummer de patinaje</span><span class="sxs-lookup"><span data-stu-id="719e8-283">skat nummer</span></span>
  
<span data-ttu-id="719e8-284">identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="719e8-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="719e8-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="719e8-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="719e8-286">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-286">Format</span></span>

<span data-ttu-id="719e8-287">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-288">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-288">Pattern</span></span>

<span data-ttu-id="719e8-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="719e8-289">11 digits:</span></span>
  
-  <span data-ttu-id="719e8-290">Un dígito que corresponde al sexo y al siglo de nacimiento donde un número impar indica macho y el número par indica hembra de la siguiente manera: 1,2 para el siglo XIX; 3, 4 para el siglo XX; y 5, 6 para el siglo XXI</span><span class="sxs-lookup"><span data-stu-id="719e8-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="719e8-291">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="719e8-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="719e8-292">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha</span><span class="sxs-lookup"><span data-stu-id="719e8-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="719e8-293">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="719e8-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-294">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-294">Checksum</span></span>

<span data-ttu-id="719e8-295">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-296">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-296">Definition</span></span>

<span data-ttu-id="719e8-297">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-298">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-299">Se encuentra una `Keywords_estonia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-300">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-301">La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-302">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="719e8-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-304">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-304">tax number</span></span>
  
<span data-ttu-id="719e8-305">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-305">tax</span></span>
  
<span data-ttu-id="719e8-306">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-306">tax id</span></span>
  
<span data-ttu-id="719e8-307">código personal</span><span class="sxs-lookup"><span data-stu-id="719e8-307">personal code</span></span>
  
<span data-ttu-id="719e8-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="719e8-308">maksunumber</span></span>
  
<span data-ttu-id="719e8-309">identificador maksu</span><span class="sxs-lookup"><span data-stu-id="719e8-309">maksu id</span></span>
  
<span data-ttu-id="719e8-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="719e8-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="719e8-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="719e8-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="719e8-312">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-312">Format</span></span>

<span data-ttu-id="719e8-313">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos</span><span class="sxs-lookup"><span data-stu-id="719e8-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-314">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-314">Pattern</span></span>

<span data-ttu-id="719e8-315">Una combinación de 11 caracteres de dígitos, letras y más y un signo menos:</span><span class="sxs-lookup"><span data-stu-id="719e8-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="719e8-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-316">Six digits</span></span>
    
- <span data-ttu-id="719e8-317">Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distingue entre mayúsculas y minúsculas) donde el signo más significa que nació entre 1800-1899, el signo menos significa que nació entre 1900-1999, y "A" significa que nació 2000 y posterior</span><span class="sxs-lookup"><span data-stu-id="719e8-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="719e8-318">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-318">Three digits</span></span>
    
- <span data-ttu-id="719e8-319">Una letra o un número</span><span class="sxs-lookup"><span data-stu-id="719e8-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-320">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-320">Checksum</span></span>

<span data-ttu-id="719e8-321">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-322">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-322">Definition</span></span>

<span data-ttu-id="719e8-323">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-324">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-325">Se encuentra una `Keywords_finland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-326">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-327">La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-328">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="719e8-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-330">identification number</span><span class="sxs-lookup"><span data-stu-id="719e8-330">identification number</span></span>
  
<span data-ttu-id="719e8-331">identificador personal</span><span class="sxs-lookup"><span data-stu-id="719e8-331">personal id</span></span>
  
<span data-ttu-id="719e8-332">número de identidad</span><span class="sxs-lookup"><span data-stu-id="719e8-332">identity number</span></span>
  
<span data-ttu-id="719e8-333">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="719e8-333">finnish national id number</span></span>
  
<span data-ttu-id="719e8-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-334">personalidnumber#</span></span>
  
<span data-ttu-id="719e8-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="719e8-335">national identification number</span></span>
  
<span data-ttu-id="719e8-336">número de identificador</span><span class="sxs-lookup"><span data-stu-id="719e8-336">id number</span></span>
  
<span data-ttu-id="719e8-337">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="719e8-337">national id no.</span></span>
  
<span data-ttu-id="719e8-338">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="719e8-338">national id number</span></span>
  
<span data-ttu-id="719e8-339">identificador no</span><span class="sxs-lookup"><span data-stu-id="719e8-339">id no</span></span>
  
<span data-ttu-id="719e8-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="719e8-340">tunnistenumero</span></span>
  
<span data-ttu-id="719e8-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="719e8-341">henkilötunnus</span></span>
  
<span data-ttu-id="719e8-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="719e8-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="719e8-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="719e8-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="719e8-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="719e8-344">identiteetti numero</span></span>
  
<span data-ttu-id="719e8-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="719e8-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="719e8-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="719e8-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="719e8-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="719e8-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="719e8-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="719e8-348">tunnusnumero</span></span>
  
<span data-ttu-id="719e8-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="719e8-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="719e8-350">Francia</span><span class="sxs-lookup"><span data-stu-id="719e8-350">France</span></span>

### <a name="format"></a><span data-ttu-id="719e8-351">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-351">Format</span></span>

<span data-ttu-id="719e8-352">13 dígitos para personas y nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="719e8-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-353">Pattern</span></span>

<span data-ttu-id="719e8-354">13 dígitos para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="719e8-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="719e8-355">Un dígito que debe ser 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="719e8-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="719e8-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-356">12 digits</span></span>
    
<span data-ttu-id="719e8-357">Nueve dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="719e8-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-358">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-358">Checksum</span></span>

<span data-ttu-id="719e8-359">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-360">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-360">Definition</span></span>

<span data-ttu-id="719e8-361">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-362">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-363">Se encuentra una `Keywords_france_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-364">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-365">La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-366">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="719e8-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-368">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-368">tax identification number</span></span>
  
<span data-ttu-id="719e8-369">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-369">tax number</span></span>
  
<span data-ttu-id="719e8-370">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-370">tax id</span></span>
  
<span data-ttu-id="719e8-371">numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="719e8-372">Alemania</span><span class="sxs-lookup"><span data-stu-id="719e8-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="719e8-373">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-373">Format</span></span>

<span data-ttu-id="719e8-374">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-375">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-375">Pattern</span></span>

<span data-ttu-id="719e8-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="719e8-376">11 digits :</span></span>
  
-  <span data-ttu-id="719e8-377">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-377">Ten digits</span></span> 
    
- <span data-ttu-id="719e8-378">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="719e8-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-379">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-379">Checksum</span></span>

<span data-ttu-id="719e8-380">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-381">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-381">Definition</span></span>

<span data-ttu-id="719e8-382">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-383">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-384">Se encuentra una `Keywords_germany_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-385">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-386">La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-387">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="719e8-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-389">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-389">tax number</span></span>
  
<span data-ttu-id="719e8-390">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-390">tax no.</span></span>
  
<span data-ttu-id="719e8-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-391">taxno#</span></span>
  
<span data-ttu-id="719e8-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-392">taxnumber#</span></span>
  
<span data-ttu-id="719e8-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-393">taxnumber</span></span>
  
<span data-ttu-id="719e8-394">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-394">tax id</span></span>
  
<span data-ttu-id="719e8-395">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-395">taxid#</span></span>
  
<span data-ttu-id="719e8-396">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-396">tax identification number</span></span>
  
<span data-ttu-id="719e8-397">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-397">tax identification no.</span></span>
  
<span data-ttu-id="719e8-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="719e8-398">steuernummer</span></span>
  
<span data-ttu-id="719e8-399">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="719e8-399">steuer id</span></span>
  
<span data-ttu-id="719e8-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="719e8-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="719e8-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="719e8-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="719e8-402">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-402">Format</span></span>

<span data-ttu-id="719e8-403">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-404">Pattern</span></span>

<span data-ttu-id="719e8-405">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-406">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-406">Checksum</span></span>

<span data-ttu-id="719e8-407">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-408">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-408">Definition</span></span>

<span data-ttu-id="719e8-409">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-410">La expresión `Regex_greece_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-411">Se encuentra una `Keywords_greece_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="719e8-412">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="719e8-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-414">afm</span><span class="sxs-lookup"><span data-stu-id="719e8-414">afm</span></span>
  
<span data-ttu-id="719e8-415">/</span><span class="sxs-lookup"><span data-stu-id="719e8-415">tin</span></span>
  
<span data-ttu-id="719e8-416">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-416">tax id no.</span></span>
  
<span data-ttu-id="719e8-417">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-417">tax id no</span></span>
  
<span data-ttu-id="719e8-418">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-418">tax identification number</span></span>
  
<span data-ttu-id="719e8-419">número de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-419">tax registry number</span></span>
  
<span data-ttu-id="719e8-420">n.º de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-420">tax registry no.</span></span>
  
<span data-ttu-id="719e8-421">afm#</span><span class="sxs-lookup"><span data-stu-id="719e8-421">afm#</span></span>
  
<span data-ttu-id="719e8-422">/</span><span class="sxs-lookup"><span data-stu-id="719e8-422">tin#</span></span>
  
<span data-ttu-id="719e8-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="719e8-423">taxidno#</span></span>
  
<span data-ttu-id="719e8-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="719e8-424">taxregistryno#</span></span>
  
<span data-ttu-id="719e8-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="719e8-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="719e8-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="719e8-426">aφμ</span></span>
  
<span data-ttu-id="719e8-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="719e8-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="719e8-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="719e8-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="719e8-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="719e8-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="719e8-430">Hungría</span><span class="sxs-lookup"><span data-stu-id="719e8-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="719e8-431">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-431">Format</span></span>

<span data-ttu-id="719e8-432">Diez dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-433">Pattern</span></span>

<span data-ttu-id="719e8-434">Diez dígitos:</span><span class="sxs-lookup"><span data-stu-id="719e8-434">Ten digits:</span></span>
  
-  <span data-ttu-id="719e8-435">Un dígito que debe ser "8"</span><span class="sxs-lookup"><span data-stu-id="719e8-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="719e8-436">Cinco dígitos que corresponden al número de días entre la fecha 01/01/1867 y la fecha de nacimiento del individuo.</span><span class="sxs-lookup"><span data-stu-id="719e8-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="719e8-437">Tres dígitos que corresponden al número generado por oportunidad para diferenciar a los individuos nacidos en el mismo día</span><span class="sxs-lookup"><span data-stu-id="719e8-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="719e8-438">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="719e8-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-439">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-439">Checksum</span></span>

<span data-ttu-id="719e8-440">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-441">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-441">Definition</span></span>

<span data-ttu-id="719e8-442">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-443">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-444">Se encuentra una `Keywords_hungary_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-445">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-446">La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-447">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="719e8-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-449">número de identificación fiscal húngara</span><span class="sxs-lookup"><span data-stu-id="719e8-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="719e8-450">NIF Húngaro</span><span class="sxs-lookup"><span data-stu-id="719e8-450">hungarian tin</span></span>
  
<span data-ttu-id="719e8-451">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-451">tax id number</span></span>
  
<span data-ttu-id="719e8-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="719e8-452">vat number</span></span>
  
<span data-ttu-id="719e8-453">n.º de autoridad fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-453">tax authority no</span></span>
  
<span data-ttu-id="719e8-454">número de identidad fiscal de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-454">tax id tax identity number</span></span>
  
<span data-ttu-id="719e8-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-455">taxidnumber#</span></span>
  
<span data-ttu-id="719e8-456">/</span><span class="sxs-lookup"><span data-stu-id="719e8-456">tin#</span></span>
  
<span data-ttu-id="719e8-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="719e8-457">hungatiantin#</span></span>
  
<span data-ttu-id="719e8-458">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-458">tax identification no</span></span>
  
<span data-ttu-id="719e8-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="719e8-459">taxidno#</span></span>
  
<span data-ttu-id="719e8-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="719e8-460">adóazonosító szám</span></span>
  
<span data-ttu-id="719e8-461">adószám</span><span class="sxs-lookup"><span data-stu-id="719e8-461">adószám</span></span>
  
<span data-ttu-id="719e8-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="719e8-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="719e8-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="719e8-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="719e8-464">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-464">Format</span></span>

<span data-ttu-id="719e8-465">Siete dígitos seguidos de una letra sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-466">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-466">Pattern</span></span>

<span data-ttu-id="719e8-467">Siete dígitos seguidos de una letra:</span><span class="sxs-lookup"><span data-stu-id="719e8-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="719e8-468">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="719e8-468">Seven digits</span></span> 
    
- <span data-ttu-id="719e8-469">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-470">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-470">Checksum</span></span>

<span data-ttu-id="719e8-471">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-472">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-472">Definition</span></span>

<span data-ttu-id="719e8-473">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-474">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-475">Se encuentra una `Keywords_ireland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-476">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-477">La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="719e8-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-480">n.º de servicio público</span><span class="sxs-lookup"><span data-stu-id="719e8-480">public service no</span></span>
  
<span data-ttu-id="719e8-481">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="719e8-481">personal public service no</span></span>
  
<span data-ttu-id="719e8-482">n.º de PPS</span><span class="sxs-lookup"><span data-stu-id="719e8-482">pps no</span></span>
  
<span data-ttu-id="719e8-483">n.º de servicio personal</span><span class="sxs-lookup"><span data-stu-id="719e8-483">personal service no</span></span>
  
<span data-ttu-id="719e8-484">n.º de servicio de PPS</span><span class="sxs-lookup"><span data-stu-id="719e8-484">pps service no</span></span>
  
<span data-ttu-id="719e8-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="719e8-485">ppsno#</span></span>
  
<span data-ttu-id="719e8-486">n.º de PPS irlandés</span><span class="sxs-lookup"><span data-stu-id="719e8-486">irish pps no</span></span>
  
<span data-ttu-id="719e8-487">publicserviceno#</span><span class="sxs-lookup"><span data-stu-id="719e8-487">publicserviceno#</span></span>
  
<span data-ttu-id="719e8-488">número de servicio público personal</span><span class="sxs-lookup"><span data-stu-id="719e8-488">personal public service number</span></span>
  
<span data-ttu-id="719e8-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="719e8-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="719e8-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="719e8-490">pps uimh</span></span>
  
<span data-ttu-id="719e8-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="719e8-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="719e8-492">Italia</span><span class="sxs-lookup"><span data-stu-id="719e8-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="719e8-493">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-493">Format</span></span>

<span data-ttu-id="719e8-494">16 letras y dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="719e8-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-495">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-495">Pattern</span></span>

<span data-ttu-id="719e8-496">16 letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="719e8-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="719e8-497">Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia</span><span class="sxs-lookup"><span data-stu-id="719e8-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="719e8-498">Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre</span><span class="sxs-lookup"><span data-stu-id="719e8-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="719e8-499">Dos dígitos que corresponden a los últimos dígitos del año de nacimiento</span><span class="sxs-lookup"><span data-stu-id="719e8-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="719e8-500">Un dígito que corresponde al mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)</span><span class="sxs-lookup"><span data-stu-id="719e8-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="719e8-501">Dos dígitos que corresponden al día del mes de nacimiento donde se agrega 40 al día de nacimiento para hembras para diferenciar de machos</span><span class="sxs-lookup"><span data-stu-id="719e8-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="719e8-502">Cuatro dígitos que corresponden a un código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros).</span><span class="sxs-lookup"><span data-stu-id="719e8-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="719e8-503">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="719e8-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-504">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-504">Checksum</span></span>

<span data-ttu-id="719e8-505">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-506">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-506">Definition</span></span>

<span data-ttu-id="719e8-507">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-508">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-509">Se encuentra una `Keywords_italy_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-510">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-511">La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-512">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="719e8-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-514">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-514">tax number</span></span>
  
<span data-ttu-id="719e8-515">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-515">tax no.</span></span>
  
<span data-ttu-id="719e8-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-516">taxno#</span></span>
  
<span data-ttu-id="719e8-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-517">taxnumber#</span></span>
  
<span data-ttu-id="719e8-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-518">taxnumber</span></span>
  
<span data-ttu-id="719e8-519">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-519">tax id</span></span>
  
<span data-ttu-id="719e8-520">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-520">taxid#</span></span>
  
<span data-ttu-id="719e8-521">Código fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-521">fiscal code</span></span>
  
<span data-ttu-id="719e8-522">Codice fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="719e8-523">Letonia</span><span class="sxs-lookup"><span data-stu-id="719e8-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="719e8-524">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-524">Format</span></span>

<span data-ttu-id="719e8-525">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-526">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-526">Pattern</span></span>

<span data-ttu-id="719e8-527">11 dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="719e8-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="719e8-528">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="719e8-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="719e8-529">Un dígito que corresponde al siglo de nacimiento en el que "0" corresponde al siglo XIX, "1" corresponde al siglo XX y "2" corresponde al siglo XXI.</span><span class="sxs-lookup"><span data-stu-id="719e8-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="719e8-530">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-531">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-531">Checksum</span></span>

<span data-ttu-id="719e8-532">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-533">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-533">Definition</span></span>

<span data-ttu-id="719e8-534">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-535">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-536">Se encuentra una `Keywords_latvia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-537">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-538">La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-539">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="719e8-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-541">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-541">tax number</span></span>
  
<span data-ttu-id="719e8-542">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-542">tax no.</span></span>
  
<span data-ttu-id="719e8-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-543">taxno#</span></span>
  
<span data-ttu-id="719e8-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-544">taxnumber#</span></span>
  
<span data-ttu-id="719e8-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-545">taxnumber</span></span>
  
<span data-ttu-id="719e8-546">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-546">tax id</span></span>
  
<span data-ttu-id="719e8-547">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-547">taxid#</span></span>
  
<span data-ttu-id="719e8-548">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-548">tax identification number</span></span>
  
<span data-ttu-id="719e8-549">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-549">tax identification no.</span></span>
  
<span data-ttu-id="719e8-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="719e8-550">nodokļa numurs</span></span>
  
<span data-ttu-id="719e8-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="719e8-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="719e8-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="719e8-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="719e8-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="719e8-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="719e8-554">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-554">Format</span></span>

<span data-ttu-id="719e8-555">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-556">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-556">Pattern</span></span>

<span data-ttu-id="719e8-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-558">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-558">Checksum</span></span>

<span data-ttu-id="719e8-559">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-560">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-560">Definition</span></span>

<span data-ttu-id="719e8-561">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-562">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-563">Se encuentra una `Keywords_lithuania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-564">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-565">La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-566">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="719e8-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-568">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-568">tax number</span></span>
  
<span data-ttu-id="719e8-569">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-569">tax no.</span></span>
  
<span data-ttu-id="719e8-570">impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-570">tax no#</span></span>
  
<span data-ttu-id="719e8-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-571">taxnumber#</span></span>
  
<span data-ttu-id="719e8-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-572">taxnumber</span></span>
  
<span data-ttu-id="719e8-573">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-573">tax id</span></span>
  
<span data-ttu-id="719e8-574">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-574">taxid#</span></span>
  
<span data-ttu-id="719e8-575">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-575">tax identification number</span></span>
  
<span data-ttu-id="719e8-576">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-576">tax identification no.</span></span>
  
<span data-ttu-id="719e8-577">identificador mokesčių</span><span class="sxs-lookup"><span data-stu-id="719e8-577">mokesčių id</span></span>
  
<span data-ttu-id="719e8-578">numeración mokesčių</span><span class="sxs-lookup"><span data-stu-id="719e8-578">mokesčių numeris</span></span>
  
<span data-ttu-id="719e8-579">mokesčių identifikavimas número</span><span class="sxs-lookup"><span data-stu-id="719e8-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="719e8-580">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="719e8-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="719e8-581">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-581">Format</span></span>

<span data-ttu-id="719e8-582">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-583">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-583">Pattern</span></span>

<span data-ttu-id="719e8-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="719e8-584">13 digits:</span></span>
  
-  <span data-ttu-id="719e8-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-585">11 digits</span></span> 
    
- <span data-ttu-id="719e8-586">Dos dígitos de control</span><span class="sxs-lookup"><span data-stu-id="719e8-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-587">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-587">Checksum</span></span>

<span data-ttu-id="719e8-588">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-589">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-589">Definition</span></span>

<span data-ttu-id="719e8-590">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-591">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-592">Se encuentra una `Keywords_luxemburg_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-593">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-594">La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-595">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="719e8-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-597">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-597">tax number</span></span>
  
<span data-ttu-id="719e8-598">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-598">tax no.</span></span>
  
<span data-ttu-id="719e8-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-599">taxno#</span></span>
  
<span data-ttu-id="719e8-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-600">taxnumber#</span></span>
  
<span data-ttu-id="719e8-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-601">taxnumber</span></span>
  
<span data-ttu-id="719e8-602">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-602">tax id</span></span>
  
<span data-ttu-id="719e8-603">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-603">taxid#</span></span>
  
<span data-ttu-id="719e8-604">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-604">tax identification number</span></span>
  
<span data-ttu-id="719e8-605">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-605">tax identification no.</span></span>
  
<span data-ttu-id="719e8-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="719e8-606">steuernummer</span></span>
  
<span data-ttu-id="719e8-607">identificador Steuer</span><span class="sxs-lookup"><span data-stu-id="719e8-607">steuer id</span></span>
  
<span data-ttu-id="719e8-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="719e8-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="719e8-609">Malta</span><span class="sxs-lookup"><span data-stu-id="719e8-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="719e8-610">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-610">Format</span></span>

<span data-ttu-id="719e8-611">Para los nacionales de Maltés: 7 dígitos y una letra en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="719e8-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="719e8-612">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-613">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-613">Pattern</span></span>

<span data-ttu-id="719e8-614">Nacionales de Malta: 7 dígitos y una letra</span><span class="sxs-lookup"><span data-stu-id="719e8-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="719e8-615">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="719e8-615">Seven digits</span></span> 
    
- <span data-ttu-id="719e8-616">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="719e8-617">Nacionales no Maltés y entidades de Maltés: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="719e8-618">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="719e8-619">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-619">Checksum</span></span>

<span data-ttu-id="719e8-620">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-621">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-621">Definition</span></span>

<span data-ttu-id="719e8-622">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-623">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-624">Se encuentra una `Keywords_malta_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-625">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-626">La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-627">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="719e8-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-629">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-629">tax number</span></span>
  
<span data-ttu-id="719e8-630">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-630">tax no.</span></span>
  
<span data-ttu-id="719e8-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-631">taxno#</span></span>
  
<span data-ttu-id="719e8-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-632">taxnumber#</span></span>
  
<span data-ttu-id="719e8-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-633">taxnumber</span></span>
  
<span data-ttu-id="719e8-634">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-634">tax id</span></span>
  
<span data-ttu-id="719e8-635">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-635">taxid#</span></span>
  
<span data-ttu-id="719e8-636">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-636">tax identification number</span></span>
  
<span data-ttu-id="719e8-637">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-637">tax identification no.</span></span>
  
<span data-ttu-id="719e8-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="719e8-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="719e8-639">identificador TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="719e8-639">id tat-taxxa</span></span>
  
<span data-ttu-id="719e8-640">numru ta ' identifikazzjoni TAT-taxxa</span><span class="sxs-lookup"><span data-stu-id="719e8-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="719e8-641">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="719e8-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="719e8-642">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-642">Format</span></span>

<span data-ttu-id="719e8-643">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-644">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-644">Pattern</span></span>

<span data-ttu-id="719e8-645">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="719e8-646">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-646">Checksum</span></span>

<span data-ttu-id="719e8-647">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-648">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-648">Definition</span></span>

<span data-ttu-id="719e8-649">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-650">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-651">Se encuentra una `Keywords_netherlands_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-652">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-653">La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-654">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="719e8-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-656">número de identificación fiscal de países bajos</span><span class="sxs-lookup"><span data-stu-id="719e8-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="719e8-657">identificación de impuestos de países bajos</span><span class="sxs-lookup"><span data-stu-id="719e8-657">netherlands tax identification</span></span>
  
<span data-ttu-id="719e8-658">número de identificación fiscal de Netherland</span><span class="sxs-lookup"><span data-stu-id="719e8-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="719e8-659">identificación de impuestos de Netherland</span><span class="sxs-lookup"><span data-stu-id="719e8-659">netherland's tax identification</span></span>
  
<span data-ttu-id="719e8-660">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-660">tax identification number</span></span>
  
<span data-ttu-id="719e8-661">identificador fiscal holandés</span><span class="sxs-lookup"><span data-stu-id="719e8-661">dutch tax id</span></span>
  
<span data-ttu-id="719e8-662">número de identificación fiscal holandes</span><span class="sxs-lookup"><span data-stu-id="719e8-662">dutch tax identification number</span></span>
  
<span data-ttu-id="719e8-663">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-663">tax id</span></span>
  
<span data-ttu-id="719e8-664">n.º de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-664">tax id#</span></span>
  
<span data-ttu-id="719e8-665">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-665">tax number</span></span>
  
<span data-ttu-id="719e8-666">impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-666">tax no#</span></span>
  
<span data-ttu-id="719e8-667">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-667">tax#</span></span>
  
<span data-ttu-id="719e8-668">/</span><span class="sxs-lookup"><span data-stu-id="719e8-668">tin</span></span>
  
<span data-ttu-id="719e8-669">/</span><span class="sxs-lookup"><span data-stu-id="719e8-669">tin#</span></span>
  
<span data-ttu-id="719e8-670">NIF-Países Bajos</span><span class="sxs-lookup"><span data-stu-id="719e8-670">netherlands tin</span></span>
  
<span data-ttu-id="719e8-671">estaño de Netherland</span><span class="sxs-lookup"><span data-stu-id="719e8-671">netherland's tin</span></span>
  
<span data-ttu-id="719e8-672">último países de la identificatienummer</span><span class="sxs-lookup"><span data-stu-id="719e8-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="719e8-673">identificatienummerto de furgoneta</span><span class="sxs-lookup"><span data-stu-id="719e8-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="719e8-674">identificatienummer en último lugar</span><span class="sxs-lookup"><span data-stu-id="719e8-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="719e8-675">último países de la identificatie</span><span class="sxs-lookup"><span data-stu-id="719e8-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="719e8-676">último identificador de Nummer de países bajos</span><span class="sxs-lookup"><span data-stu-id="719e8-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="719e8-677">Países Bajos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="719e8-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="719e8-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="719e8-678">btw nummer</span></span>
  
<span data-ttu-id="719e8-679">Nederlandse de la última identificatie</span><span class="sxs-lookup"><span data-stu-id="719e8-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="719e8-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="719e8-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="719e8-681">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-681">Format</span></span>

<span data-ttu-id="719e8-682">Once dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-683">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-683">Pattern</span></span>

<span data-ttu-id="719e8-684">Once dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-685">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-685">Checksum</span></span>

<span data-ttu-id="719e8-686">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-687">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-687">Definition</span></span>

<span data-ttu-id="719e8-688">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-689">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-690">Se encuentra una `Keywords_poland_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-691">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-692">La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-693">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="719e8-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-695">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-695">tax number</span></span>
  
<span data-ttu-id="719e8-696">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-696">tax no.</span></span>
  
<span data-ttu-id="719e8-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-697">taxno#</span></span>
  
<span data-ttu-id="719e8-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-698">taxnumber#</span></span>
  
<span data-ttu-id="719e8-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-699">taxnumber</span></span>
  
<span data-ttu-id="719e8-700">nip</span><span class="sxs-lookup"><span data-stu-id="719e8-700">nip</span></span>
  
<span data-ttu-id="719e8-701">nip#</span><span class="sxs-lookup"><span data-stu-id="719e8-701">nip#</span></span>
  
<span data-ttu-id="719e8-702">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-702">tax id</span></span>
  
<span data-ttu-id="719e8-703">n.º de identificador de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-703">tax id#</span></span>
  
<span data-ttu-id="719e8-704">identificador NIP</span><span class="sxs-lookup"><span data-stu-id="719e8-704">nip id</span></span>
  
<span data-ttu-id="719e8-705">número de identificador de NIP</span><span class="sxs-lookup"><span data-stu-id="719e8-705">nip id#</span></span>
  
<span data-ttu-id="719e8-706">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-706">tax identification number</span></span>
  
<span data-ttu-id="719e8-707">Nº identificación impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-707">tax identification no.</span></span>
  
<span data-ttu-id="719e8-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="719e8-708">vat number</span></span>
  
<span data-ttu-id="719e8-709">n.º de IVA</span><span class="sxs-lookup"><span data-stu-id="719e8-709">vat no.</span></span>
  
<span data-ttu-id="719e8-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="719e8-710">vatno#</span></span>
  
<span data-ttu-id="719e8-711">NIF</span><span class="sxs-lookup"><span data-stu-id="719e8-711">vat id</span></span>
  
<span data-ttu-id="719e8-712">n.º de ID de IVA</span><span class="sxs-lookup"><span data-stu-id="719e8-712">vat id#</span></span>
  
<span data-ttu-id="719e8-713">numerar identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="719e8-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="719e8-714">Polski número de identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="719e8-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="719e8-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="719e8-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="719e8-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="719e8-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="719e8-717">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-717">Format</span></span>

<span data-ttu-id="719e8-718">Nueve dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-719">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-719">Pattern</span></span>

<span data-ttu-id="719e8-720">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-721">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-721">Checksum</span></span>

<span data-ttu-id="719e8-722">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-723">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-723">Definition</span></span>

<span data-ttu-id="719e8-724">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-725">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-726">Se encuentra una `Keywords_portugal_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-727">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-728">La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-729">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="719e8-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-731">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-731">tax number</span></span>
  
<span data-ttu-id="719e8-732">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-732">tax no.</span></span>
  
<span data-ttu-id="719e8-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-733">taxno#</span></span>
  
<span data-ttu-id="719e8-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="719e8-734">taxnumber#</span></span>
  
<span data-ttu-id="719e8-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="719e8-735">taxnumber</span></span>
  
<span data-ttu-id="719e8-736">NIF</span><span class="sxs-lookup"><span data-stu-id="719e8-736">nif</span></span>
  
<span data-ttu-id="719e8-737">NIF</span><span class="sxs-lookup"><span data-stu-id="719e8-737">nif#</span></span>
  
<span data-ttu-id="719e8-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="719e8-738">numero fiscal</span></span>
  
<span data-ttu-id="719e8-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="719e8-740">Rumania</span><span class="sxs-lookup"><span data-stu-id="719e8-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="719e8-741">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-741">Format</span></span>

<span data-ttu-id="719e8-742">13 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-743">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-743">Pattern</span></span>

<span data-ttu-id="719e8-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-745">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-745">Checksum</span></span>

<span data-ttu-id="719e8-746">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-747">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-747">Definition</span></span>

<span data-ttu-id="719e8-748">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-749">La expresión `Regex_romania_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-750">Se encuentra una `Keywords_romania_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="719e8-751">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="719e8-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-753">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-753">tax id</span></span>
  
<span data-ttu-id="719e8-754">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-754">tax id number</span></span>
  
<span data-ttu-id="719e8-755">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-755">tax file no</span></span>
  
<span data-ttu-id="719e8-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="719e8-756">tax file number</span></span>
  
<span data-ttu-id="719e8-757">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-757">tax no</span></span>
  
<span data-ttu-id="719e8-758">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-758">tax number</span></span>
  
<span data-ttu-id="719e8-759">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-759">taxid#</span></span>
  
<span data-ttu-id="719e8-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-760">taxno#</span></span>
  
<span data-ttu-id="719e8-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="719e8-761">id-ul taxei</span></span>
  
<span data-ttu-id="719e8-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="719e8-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="719e8-763">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="719e8-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="719e8-764">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-764">Format</span></span>

<span data-ttu-id="719e8-765">10 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-766">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-766">Pattern</span></span>

<span data-ttu-id="719e8-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-768">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-768">Checksum</span></span>

<span data-ttu-id="719e8-769">No aplicable</span><span class="sxs-lookup"><span data-stu-id="719e8-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-770">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-770">Definition</span></span>

<span data-ttu-id="719e8-771">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-772">La expresión `Regex_slovakia_eu_tax_file_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-773">Se encuentra una `Keywords_slovakia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="719e8-774">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="719e8-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-776">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-776">tax id</span></span>
  
<span data-ttu-id="719e8-777">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-777">tax id number</span></span>
  
<span data-ttu-id="719e8-778">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="719e8-778">tin id</span></span>
  
<span data-ttu-id="719e8-779">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="719e8-779">tin no</span></span>
  
<span data-ttu-id="719e8-780">ID de estaño de eslovaco</span><span class="sxs-lookup"><span data-stu-id="719e8-780">slovakian tin id</span></span>
  
<span data-ttu-id="719e8-781">/</span><span class="sxs-lookup"><span data-stu-id="719e8-781">tin</span></span>
  
<span data-ttu-id="719e8-782">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-782">tax file no</span></span>
  
<span data-ttu-id="719e8-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="719e8-783">tax file number</span></span>
  
<span data-ttu-id="719e8-784">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-784">tax no</span></span>
  
<span data-ttu-id="719e8-785">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-785">tax number</span></span>
  
<span data-ttu-id="719e8-786">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-786">taxid#</span></span>
  
<span data-ttu-id="719e8-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-787">taxno#</span></span>
  
<span data-ttu-id="719e8-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="719e8-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="719e8-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="719e8-789">daňové číslo</span></span>
  
<span data-ttu-id="719e8-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="719e8-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="719e8-791">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="719e8-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="719e8-792">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-792">Format</span></span>

<span data-ttu-id="719e8-793">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-794">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-794">Pattern</span></span>

<span data-ttu-id="719e8-795">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-796">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-796">Checksum</span></span>

<span data-ttu-id="719e8-797">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-798">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-798">Definition</span></span>

<span data-ttu-id="719e8-799">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-800">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-801">Se encuentra una `Keywords_slovenia_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-802">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-803">La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-804">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="719e8-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-806">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-806">tax id</span></span>
  
<span data-ttu-id="719e8-807">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-807">tax id number</span></span>
  
<span data-ttu-id="719e8-808">ID de estaño</span><span class="sxs-lookup"><span data-stu-id="719e8-808">tin id</span></span>
  
<span data-ttu-id="719e8-809">n.º de estaño</span><span class="sxs-lookup"><span data-stu-id="719e8-809">tin no</span></span>
  
<span data-ttu-id="719e8-810">ID de estaño de esloveno</span><span class="sxs-lookup"><span data-stu-id="719e8-810">slovenian tin id</span></span>
  
<span data-ttu-id="719e8-811">/</span><span class="sxs-lookup"><span data-stu-id="719e8-811">tin</span></span>
  
<span data-ttu-id="719e8-812">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-812">tax file no</span></span>
  
<span data-ttu-id="719e8-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="719e8-813">tax file number</span></span>
  
<span data-ttu-id="719e8-814">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-814">tax no</span></span>
  
<span data-ttu-id="719e8-815">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-815">tax number</span></span>
  
<span data-ttu-id="719e8-816">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-816">taxid#</span></span>
  
<span data-ttu-id="719e8-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-817">taxno#</span></span>
  
<span data-ttu-id="719e8-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="719e8-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="719e8-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="719e8-819">davčna številka</span></span>
  
<span data-ttu-id="719e8-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="719e8-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="719e8-821">España</span><span class="sxs-lookup"><span data-stu-id="719e8-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="719e8-822">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-822">Format</span></span>

<span data-ttu-id="719e8-823">Siete u ocho dígitos y una o dos letras en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="719e8-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-824">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-824">Pattern</span></span>

<span data-ttu-id="719e8-825">Personas físicas españolas con una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="719e8-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="719e8-826">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-826">Eight digits</span></span> 
    
- <span data-ttu-id="719e8-827">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="719e8-828">Spaniards no residente sin una tarjeta de identidad nacional de España</span><span class="sxs-lookup"><span data-stu-id="719e8-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="719e8-829">Una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="719e8-830">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="719e8-830">Seven digits</span></span>
    
- <span data-ttu-id="719e8-831">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="719e8-832">Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:</span><span class="sxs-lookup"><span data-stu-id="719e8-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="719e8-833">Una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="719e8-834">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="719e8-834">Seven digits</span></span> 
    
- <span data-ttu-id="719e8-835">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="719e8-836">Foreigners con un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="719e8-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="719e8-837">Una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="719e8-838">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="719e8-838">Seven digits</span></span>
    
- <span data-ttu-id="719e8-839">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="719e8-840">Foreigners sin un número de identificación de un extranjero</span><span class="sxs-lookup"><span data-stu-id="719e8-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="719e8-841">Una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="719e8-842">Siete dígitos </span><span class="sxs-lookup"><span data-stu-id="719e8-842">Seven digits</span></span>
    
- <span data-ttu-id="719e8-843">Una letra mayúscula (distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="719e8-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="719e8-844">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-844">Checksum</span></span>

<span data-ttu-id="719e8-845">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-846">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-846">Definition</span></span>

<span data-ttu-id="719e8-847">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-848">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-849">Se encuentra una `Keywords_spain_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-850">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-851">La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-852">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="719e8-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-854">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-854">tax id</span></span>
  
<span data-ttu-id="719e8-855">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-855">tax id number</span></span>
  
<span data-ttu-id="719e8-856">identificador CIF</span><span class="sxs-lookup"><span data-stu-id="719e8-856">cif id</span></span>
  
<span data-ttu-id="719e8-857">n.º CIF</span><span class="sxs-lookup"><span data-stu-id="719e8-857">cif no</span></span>
  
<span data-ttu-id="719e8-858">identificador CIF en Español</span><span class="sxs-lookup"><span data-stu-id="719e8-858">spanish cif id</span></span>
  
<span data-ttu-id="719e8-859">precio</span><span class="sxs-lookup"><span data-stu-id="719e8-859">cif</span></span>
  
<span data-ttu-id="719e8-860">n.º de archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-860">tax file no</span></span>
  
<span data-ttu-id="719e8-861">Número CIF en Español</span><span class="sxs-lookup"><span data-stu-id="719e8-861">spanish cif number</span></span>
  
<span data-ttu-id="719e8-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="719e8-862">tax file number</span></span>
  
<span data-ttu-id="719e8-863">Número CIF de Español</span><span class="sxs-lookup"><span data-stu-id="719e8-863">spanish cif no</span></span>
  
<span data-ttu-id="719e8-864">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-864">tax no</span></span>
  
<span data-ttu-id="719e8-865">número de impuesto</span><span class="sxs-lookup"><span data-stu-id="719e8-865">tax number</span></span>
  
<span data-ttu-id="719e8-866">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-866">taxid#</span></span>
  
<span data-ttu-id="719e8-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="719e8-867">taxno#</span></span>
  
<span data-ttu-id="719e8-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="719e8-868">cifid#</span></span>
  
<span data-ttu-id="719e8-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="719e8-869">spanishcifid#</span></span>
  
<span data-ttu-id="719e8-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="719e8-870">spanishcifno#</span></span>
  
<span data-ttu-id="719e8-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="719e8-871">número de contribuyente</span></span>
  
<span data-ttu-id="719e8-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="719e8-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="719e8-873">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="719e8-874">Número CIF</span><span class="sxs-lookup"><span data-stu-id="719e8-874">cif número</span></span>
  
<span data-ttu-id="719e8-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="719e8-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="719e8-876">Suecia</span><span class="sxs-lookup"><span data-stu-id="719e8-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="719e8-877">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-877">Format</span></span>

<span data-ttu-id="719e8-878">Diez dígitos y un símbolo en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="719e8-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-879">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-879">Pattern</span></span>

<span data-ttu-id="719e8-880">Diez dígitos y un símbolo:</span><span class="sxs-lookup"><span data-stu-id="719e8-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="719e8-881">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="719e8-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="719e8-882">Un signo más, un signo menos o una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="719e8-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="719e8-883">Tres dígitos que hacen que el número de identificación sea único donde:</span><span class="sxs-lookup"><span data-stu-id="719e8-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="719e8-884">Para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero</span><span class="sxs-lookup"><span data-stu-id="719e8-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="719e8-885">El dígito en la novena posición indica el género, ya sea impar o incluso para hembras</span><span class="sxs-lookup"><span data-stu-id="719e8-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="719e8-886">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="719e8-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="719e8-887">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-887">Checksum</span></span>

<span data-ttu-id="719e8-888">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-889">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-889">Definition</span></span>

<span data-ttu-id="719e8-890">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-891">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-892">Se encuentra una `Keywords_sweden_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="719e8-893">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-894">La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="719e8-895">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="719e8-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-897">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-897">tax id</span></span>
  
<span data-ttu-id="719e8-898">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-898">tax id no.</span></span>
  
<span data-ttu-id="719e8-899">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-899">tax id number</span></span>
  
<span data-ttu-id="719e8-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="719e8-900">tax identification</span></span>
  
<span data-ttu-id="719e8-901">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-901">tax identification#</span></span>
  
<span data-ttu-id="719e8-902">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-902">tax no.</span></span>
  
<span data-ttu-id="719e8-903">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-903">tax#</span></span>
  
<span data-ttu-id="719e8-904">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-904">taxid#</span></span>
  
<span data-ttu-id="719e8-905">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-905">tax file</span></span>
  
<span data-ttu-id="719e8-906">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-906">tax file no.</span></span>
  
<span data-ttu-id="719e8-907">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="719e8-907">personal id number</span></span>
  
<span data-ttu-id="719e8-908">Nummer de identificador de patinaje</span><span class="sxs-lookup"><span data-stu-id="719e8-908">skatt id nummer</span></span>
  
<span data-ttu-id="719e8-909">Identifikation de patinaje</span><span class="sxs-lookup"><span data-stu-id="719e8-909">skatt identifikation</span></span>
  
<span data-ttu-id="719e8-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="719e8-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="719e8-911">LIBRA</span><span class="sxs-lookup"><span data-stu-id="719e8-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="719e8-912">Formato</span><span class="sxs-lookup"><span data-stu-id="719e8-912">Format</span></span>

<span data-ttu-id="719e8-913">Referencia fiscal única (UTR): 10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="719e8-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="719e8-914">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="719e8-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="719e8-915">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="719e8-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="719e8-916">Patrón</span><span class="sxs-lookup"><span data-stu-id="719e8-916">Pattern</span></span>

<span data-ttu-id="719e8-917">Referencia de contribuyente única (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="719e8-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="719e8-918">Número de seguro nacional (NINO): para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="719e8-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="719e8-919">Número de seguro nacional (NINO) "en [lo que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="719e8-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="719e8-920">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="719e8-920">Checksum</span></span>

<span data-ttu-id="719e8-921">Sí</span><span class="sxs-lookup"><span data-stu-id="719e8-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="719e8-922">Definición</span><span class="sxs-lookup"><span data-stu-id="719e8-922">Definition</span></span>

<span data-ttu-id="719e8-923">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="719e8-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="719e8-924">La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="719e8-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="719e8-925">Se encuentra una `Keywords_uk_eu_tax_file_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="719e8-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="719e8-926">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="719e8-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="719e8-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="719e8-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="719e8-928">tax id</span><span class="sxs-lookup"><span data-stu-id="719e8-928">tax id</span></span>
  
<span data-ttu-id="719e8-929">Nº de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-929">tax id no.</span></span>
  
<span data-ttu-id="719e8-930">número de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-930">tax id number</span></span>
  
<span data-ttu-id="719e8-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="719e8-931">tax identification</span></span>
  
<span data-ttu-id="719e8-932">n.º de identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="719e8-932">tax identification#</span></span>
  
<span data-ttu-id="719e8-933">Nº de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-933">tax no.</span></span>
  
<span data-ttu-id="719e8-934">Tax</span><span class="sxs-lookup"><span data-stu-id="719e8-934">tax#</span></span>
  
<span data-ttu-id="719e8-935">n.º de taxis</span><span class="sxs-lookup"><span data-stu-id="719e8-935">taxid#</span></span>
  
<span data-ttu-id="719e8-936">archivo de impuestos</span><span class="sxs-lookup"><span data-stu-id="719e8-936">tax file</span></span>
  
<span data-ttu-id="719e8-937">Nº archivo impto.</span><span class="sxs-lookup"><span data-stu-id="719e8-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="719e8-938">Vea también</span><span class="sxs-lookup"><span data-stu-id="719e8-938">See also</span></span>

[<span data-ttu-id="719e8-939">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="719e8-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

