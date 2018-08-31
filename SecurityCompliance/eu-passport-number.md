---
title: Número de cuenta de Passport de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de la UE Passport número. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 71acc39b885c057e1771ec13b2f3c25017ac1bb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536280"
---
# <a name="eu-passport-number"></a><span data-ttu-id="d5bba-104">Número de cuenta de Passport de la UE</span><span class="sxs-lookup"><span data-stu-id="d5bba-104">EU Passport Number</span></span>

<span data-ttu-id="d5bba-p102">En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de la UE Passport número. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="d5bba-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d5bba-107">Austria</span><span class="sxs-lookup"><span data-stu-id="d5bba-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-108">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-108">Format</span></span>

<span data-ttu-id="d5bba-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-110">Pattern</span></span>

<span data-ttu-id="d5bba-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="d5bba-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="d5bba-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d5bba-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="d5bba-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="d5bba-113">One space (optional)</span></span>
    
- <span data-ttu-id="d5bba-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d5bba-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-115">Checksum</span></span>

<span data-ttu-id="d5bba-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="d5bba-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-117">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-117">Definition</span></span>

<span data-ttu-id="d5bba-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-119">La expresión regular `Regex_austria_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-120">Una palabra clave de `Keywords_austria_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-121">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-121">Keywords</span></span>

<span data-ttu-id="d5bba-122">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-122"></span></span>
|<span data-ttu-id="d5bba-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-124">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-124">passport number</span></span>  <br/> <span data-ttu-id="d5bba-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="d5bba-125">austrian passport number</span></span>  <br/> <span data-ttu-id="d5bba-126">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-126">passport no</span></span>  <br/> <span data-ttu-id="d5bba-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="d5bba-127">reisepass</span></span>  <br/> <span data-ttu-id="d5bba-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="d5bba-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="d5bba-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="d5bba-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-130">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-130">Format</span></span>

<span data-ttu-id="d5bba-131">Dos letras seguidas por seis dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-132">Pattern</span></span>

<span data-ttu-id="d5bba-133">Dos letras y seguido de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-134">Checksum</span></span>

<span data-ttu-id="d5bba-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="d5bba-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-136">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-136">Definition</span></span>

<span data-ttu-id="d5bba-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-138">La expresión regular `Regex_belgium_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-139">Una palabra clave de `Keywords_belgium_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-140">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-140">Keywords</span></span>

<span data-ttu-id="d5bba-141">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-141"></span></span>
|<span data-ttu-id="d5bba-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-143">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-143">passport number</span></span>  <br/> <span data-ttu-id="d5bba-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="d5bba-144">belgian passport number</span></span>  <br/> <span data-ttu-id="d5bba-145">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-145">passport no</span></span>  <br/> <span data-ttu-id="d5bba-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="d5bba-146">paspoort</span></span>  <br/> <span data-ttu-id="d5bba-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d5bba-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="d5bba-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="d5bba-148">reisepass kein</span></span>  <br/> <span data-ttu-id="d5bba-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="d5bba-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="d5bba-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="d5bba-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-151">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-151">Format</span></span>

<span data-ttu-id="d5bba-152">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-153">Pattern</span></span>

 <span data-ttu-id="d5bba-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d5bba-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-155">Checksum</span></span>

<span data-ttu-id="d5bba-156">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-157">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-157">Definition</span></span>

<span data-ttu-id="d5bba-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-159">La expresión regular `Regex_bulgaria_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-160">Una palabra clave de `Keywords_bulgaria_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-161">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-161">Keywords</span></span>

<span data-ttu-id="d5bba-162">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-162"></span></span>
|<span data-ttu-id="d5bba-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-164">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-164">passport number</span></span>  <br/> <span data-ttu-id="d5bba-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="d5bba-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="d5bba-166">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-166">passport no</span></span>  <br/> <span data-ttu-id="d5bba-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="d5bba-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="d5bba-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="d5bba-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-169">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-169">Format</span></span>

<span data-ttu-id="d5bba-170">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-171">Pattern</span></span>

 <span data-ttu-id="d5bba-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d5bba-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-173">Checksum</span></span>

<span data-ttu-id="d5bba-174">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-175">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-175">Definition</span></span>

<span data-ttu-id="d5bba-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-177">La expresión regular `Regex_croatia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-178">Una palabra clave de `Keywords_croatia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-179">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-179">Keywords</span></span>

<span data-ttu-id="d5bba-180">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-180"></span></span>
|<span data-ttu-id="d5bba-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-182">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-182">passport number</span></span>  <br/> <span data-ttu-id="d5bba-183">número de pasaporte croata</span><span class="sxs-lookup"><span data-stu-id="d5bba-183">croatian passport number</span></span>  <br/> <span data-ttu-id="d5bba-184">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-184">passport no</span></span>  <br/> <span data-ttu-id="d5bba-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="d5bba-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="d5bba-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="d5bba-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-187">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-187">Format</span></span>

<span data-ttu-id="d5bba-188">Una letra seguida de 6-8 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-189">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-189">Pattern</span></span>

<span data-ttu-id="d5bba-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-191">Checksum</span></span>

<span data-ttu-id="d5bba-192">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-193">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-193">Definition</span></span>

<span data-ttu-id="d5bba-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-195">La expresión regular `Regex_cyprus_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-196">Una palabra clave de `Keywords_cyprus_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-197">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-197">Keywords</span></span>

<span data-ttu-id="d5bba-198">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-198"></span></span>
|<span data-ttu-id="d5bba-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-200">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-200">passport number</span></span>  <br/> <span data-ttu-id="d5bba-201">número de cuenta de passport chipriota</span><span class="sxs-lookup"><span data-stu-id="d5bba-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="d5bba-202">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-202">passport no</span></span>  <br/> <span data-ttu-id="d5bba-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="d5bba-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="d5bba-204">República Checa</span><span class="sxs-lookup"><span data-stu-id="d5bba-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-205">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-205">Format</span></span>

<span data-ttu-id="d5bba-206">Ocho dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-207">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-207">Pattern</span></span>

<span data-ttu-id="d5bba-208">Ocho dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-209">Checksum</span></span>

<span data-ttu-id="d5bba-210">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-211">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-211">Definition</span></span>

<span data-ttu-id="d5bba-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-213">La expresión regular `Regex_czech_republic_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-214">Una palabra clave de `Keywords_czech_republic_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-215">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-215">Keywords</span></span>

<span data-ttu-id="d5bba-216">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-216"></span></span>
|<span data-ttu-id="d5bba-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-218">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-218">passport number</span></span>  <br/> <span data-ttu-id="d5bba-219">número de pasaporte checo</span><span class="sxs-lookup"><span data-stu-id="d5bba-219">czech passport number</span></span>  <br/> <span data-ttu-id="d5bba-220">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-220">passport no</span></span>  <br/> <span data-ttu-id="d5bba-221">pas cestovní</span><span class="sxs-lookup"><span data-stu-id="d5bba-221">cestovní pas</span></span>  <br/> <span data-ttu-id="d5bba-222">PAS</span><span class="sxs-lookup"><span data-stu-id="d5bba-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="d5bba-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="d5bba-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-224">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-224">Format</span></span>

<span data-ttu-id="d5bba-225">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-226">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-226">Pattern</span></span>

 <span data-ttu-id="d5bba-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d5bba-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-228">Checksum</span></span>

<span data-ttu-id="d5bba-229">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-230">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-230">Definition</span></span>

<span data-ttu-id="d5bba-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-232">La expresión regular `Regex_denmark_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-233">Una palabra clave de `Keywords_denmark_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-234">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-234">Keywords</span></span>

<span data-ttu-id="d5bba-235">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-235"></span></span>
|<span data-ttu-id="d5bba-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-237">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-237">passport number</span></span>  <br/> <span data-ttu-id="d5bba-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="d5bba-238">danish passport number</span></span>  <br/> <span data-ttu-id="d5bba-239">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-239">passport no</span></span>  <br/> <span data-ttu-id="d5bba-240">PAS</span><span class="sxs-lookup"><span data-stu-id="d5bba-240">pas</span></span>  <br/> <span data-ttu-id="d5bba-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="d5bba-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="d5bba-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="d5bba-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-243">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-243">Format</span></span>

<span data-ttu-id="d5bba-244">Una letra seguida de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-245">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-245">Pattern</span></span>

<span data-ttu-id="d5bba-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-247">Checksum</span></span>

<span data-ttu-id="d5bba-248">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-249">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-249">Definition</span></span>

<span data-ttu-id="d5bba-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-251">La expresión regular `Regex_estonia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-252">Una palabra clave de `Keywords_estonia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-253">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-253">Keywords</span></span>

<span data-ttu-id="d5bba-254">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-254"></span></span>
|<span data-ttu-id="d5bba-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-256">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-256">passport number</span></span>  <br/> <span data-ttu-id="d5bba-257">número de pasaporte estonio</span><span class="sxs-lookup"><span data-stu-id="d5bba-257">estonian passport number</span></span>  <br/> <span data-ttu-id="d5bba-258">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-258">passport no</span></span>  <br/> <span data-ttu-id="d5bba-259">eesti kodaniku pasada</span><span class="sxs-lookup"><span data-stu-id="d5bba-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="d5bba-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="d5bba-260">Finland</span></span>

<span data-ttu-id="d5bba-261">Para obtener información detallada, vea la sección "Número de pasaporte Finlandia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d5bba-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="d5bba-262">Francia</span><span class="sxs-lookup"><span data-stu-id="d5bba-262">France</span></span>

<span data-ttu-id="d5bba-263">Para obtener información detallada, vea la sección "Número de pasaporte Francia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d5bba-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d5bba-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="d5bba-264">Germany</span></span>

<span data-ttu-id="d5bba-265">Para obtener información detallada, vea la sección "Número de pasaporte Alemania" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d5bba-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d5bba-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="d5bba-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-267">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-267">Format</span></span>

<span data-ttu-id="d5bba-268">Dos letras seguidas de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-269">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-269">Pattern</span></span>

<span data-ttu-id="d5bba-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-271">Checksum</span></span>

<span data-ttu-id="d5bba-272">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-273">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-273">Definition</span></span>

<span data-ttu-id="d5bba-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-275">La expresión regular `Regex_greece_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-276">Una palabra clave de `Keywords_greece_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-277">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-277">Keywords</span></span>

<span data-ttu-id="d5bba-278">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-278"></span></span>
|<span data-ttu-id="d5bba-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-280">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-280">passport number</span></span>  <br/> <span data-ttu-id="d5bba-281">número de pasaporte griega</span><span class="sxs-lookup"><span data-stu-id="d5bba-281">greek passport number</span></span>  <br/> <span data-ttu-id="d5bba-282">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-282">passport no</span></span>  <br/> <span data-ttu-id="d5bba-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="d5bba-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="d5bba-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="d5bba-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-285">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-285">Format</span></span>

<span data-ttu-id="d5bba-286">Dos letras seguidas por seis o siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-287">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-287">Pattern</span></span>

<span data-ttu-id="d5bba-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-289">Checksum</span></span>

<span data-ttu-id="d5bba-290">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-291">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-291">Definition</span></span>

<span data-ttu-id="d5bba-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-293">La expresión regular `Regex_hungary_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-294">Una palabra clave de `Keywords_hungary_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-295">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-295">Keywords</span></span>

<span data-ttu-id="d5bba-296">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-296"></span></span>
|<span data-ttu-id="d5bba-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-298">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-298">passport number</span></span>  <br/> <span data-ttu-id="d5bba-299">número de pasaporte húngaro</span><span class="sxs-lookup"><span data-stu-id="d5bba-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="d5bba-300">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-300">passport no</span></span>  <br/> <span data-ttu-id="d5bba-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="d5bba-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="d5bba-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="d5bba-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-303">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-303">Format</span></span>

<span data-ttu-id="d5bba-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-305">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-305">Pattern</span></span>

<span data-ttu-id="d5bba-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="d5bba-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d5bba-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d5bba-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d5bba-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d5bba-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-309">Checksum</span></span>

<span data-ttu-id="d5bba-310">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-311">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-311">Definition</span></span>

<span data-ttu-id="d5bba-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-313">La expresión regular `Regex_ireland_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-314">Una palabra clave de `Keywords_ireland_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-315">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-315">Keywords</span></span>

<span data-ttu-id="d5bba-316">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-316"></span></span>
|<span data-ttu-id="d5bba-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-318">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-318">passport number</span></span>  <br/> <span data-ttu-id="d5bba-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="d5bba-319">irish passport number</span></span>  <br/> <span data-ttu-id="d5bba-320">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-320">passport no</span></span>  <br/> <span data-ttu-id="d5bba-321">PAS</span><span class="sxs-lookup"><span data-stu-id="d5bba-321">pas</span></span>  <br/> <span data-ttu-id="d5bba-322">passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-322">passport</span></span>  <br/> <span data-ttu-id="d5bba-323">passeport</span><span class="sxs-lookup"><span data-stu-id="d5bba-323">passeport</span></span>  <br/> <span data-ttu-id="d5bba-324">numero de passeport</span><span class="sxs-lookup"><span data-stu-id="d5bba-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="d5bba-325">Italia</span><span class="sxs-lookup"><span data-stu-id="d5bba-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-326">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-326">Format</span></span>

<span data-ttu-id="d5bba-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-328">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-328">Pattern</span></span>

<span data-ttu-id="d5bba-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="d5bba-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d5bba-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d5bba-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d5bba-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d5bba-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-332">Checksum</span></span>

<span data-ttu-id="d5bba-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="d5bba-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-334">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-334">Definition</span></span>

<span data-ttu-id="d5bba-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-336">La expresión regular `Regex_italy_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-337">Una palabra clave de `Keywords_italy_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-338">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-338">Keywords</span></span>

<span data-ttu-id="d5bba-339">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-339"></span></span>
|<span data-ttu-id="d5bba-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-341">número de pasaporte italiano</span><span class="sxs-lookup"><span data-stu-id="d5bba-341">italian passport number</span></span>  <br/> <span data-ttu-id="d5bba-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="d5bba-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="d5bba-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="d5bba-343">passaporto</span></span>  <br/> <span data-ttu-id="d5bba-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="d5bba-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="d5bba-345">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-345">passport number</span></span>  <br/> <span data-ttu-id="d5bba-346">numero de passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="d5bba-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="d5bba-347">numero de passaporto</span><span class="sxs-lookup"><span data-stu-id="d5bba-347">passaporto numero</span></span>  <br/> <span data-ttu-id="d5bba-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="d5bba-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="d5bba-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="d5bba-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="d5bba-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="d5bba-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-351">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-351">Format</span></span>

<span data-ttu-id="d5bba-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-353">Pattern</span></span>

<span data-ttu-id="d5bba-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="d5bba-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d5bba-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d5bba-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d5bba-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d5bba-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-357">Checksum</span></span>

<span data-ttu-id="d5bba-358">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-359">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-359">Definition</span></span>

<span data-ttu-id="d5bba-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-361">La expresión regular `Regex_latvia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-362">Una palabra clave de `Keywords_latvia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-363">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-363">Keywords</span></span>

<span data-ttu-id="d5bba-364">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-364"></span></span>
|<span data-ttu-id="d5bba-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-366">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-366">passport number</span></span>  <br/> <span data-ttu-id="d5bba-367">número de pasaporte letón</span><span class="sxs-lookup"><span data-stu-id="d5bba-367">latvian passport number</span></span>  <br/> <span data-ttu-id="d5bba-368">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-368">passport no</span></span>  <br/> <span data-ttu-id="d5bba-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="d5bba-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="d5bba-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="d5bba-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-371">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-371">Format</span></span>

<span data-ttu-id="d5bba-372">Ocho dígitos o letras sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-373">Pattern</span></span>

<span data-ttu-id="d5bba-374">Ocho dígitos o letras (no entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d5bba-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-375">Checksum</span></span>

<span data-ttu-id="d5bba-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="d5bba-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-377">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-377">Definition</span></span>

<span data-ttu-id="d5bba-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-379">La expresión regular `Regex_lithuania_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-380">Una palabra clave de `Keywords_lithuania_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-381">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-381">Keywords</span></span>

<span data-ttu-id="d5bba-382">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-382"></span></span>
|<span data-ttu-id="d5bba-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-384">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-384">passport number</span></span>  <br/> <span data-ttu-id="d5bba-385">número de cuenta de passport lithunian</span><span class="sxs-lookup"><span data-stu-id="d5bba-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="d5bba-386">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-386">passport no</span></span>  <br/> <span data-ttu-id="d5bba-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="d5bba-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="d5bba-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="d5bba-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-389">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-389">Format</span></span>

<span data-ttu-id="d5bba-390">Ocho dígitos o letras sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-391">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-391">Pattern</span></span>

<span data-ttu-id="d5bba-392">Ocho dígitos o letras (no entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d5bba-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-393">Checksum</span></span>

<span data-ttu-id="d5bba-394">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-395">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-395">Definition</span></span>

<span data-ttu-id="d5bba-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-397">La expresión regular `Regex_nation_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-398">Una palabra clave de `Keywords_nation_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-399">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-399">Keywords</span></span>

<span data-ttu-id="d5bba-400">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-400"></span></span>
|<span data-ttu-id="d5bba-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-402">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-402">passport number</span></span>  <br/> <span data-ttu-id="d5bba-403">número de pasaporte letón</span><span class="sxs-lookup"><span data-stu-id="d5bba-403">latvian passport number</span></span>  <br/> <span data-ttu-id="d5bba-404">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-404">passport no</span></span>  <br/> <span data-ttu-id="d5bba-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="d5bba-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="d5bba-406">Malta</span><span class="sxs-lookup"><span data-stu-id="d5bba-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-407">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-407">Format</span></span>

<span data-ttu-id="d5bba-408">Siete dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-409">Pattern</span></span>

 <span data-ttu-id="d5bba-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d5bba-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-411">Checksum</span></span>

<span data-ttu-id="d5bba-412">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-413">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-413">Definition</span></span>

<span data-ttu-id="d5bba-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-415">La expresión regular `Regex_malta_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-416">Una palabra clave de `Keywords_malta_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-417">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-417">Keywords</span></span>

<span data-ttu-id="d5bba-418">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-418"></span></span>
|<span data-ttu-id="d5bba-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-420">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-420">passport number</span></span>  <br/> <span data-ttu-id="d5bba-421">número de pasaporte Maltés</span><span class="sxs-lookup"><span data-stu-id="d5bba-421">maltese passport number</span></span>  <br/> <span data-ttu-id="d5bba-422">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-422">passport no</span></span>  <br/> <span data-ttu-id="d5bba-423">numru horizontal-passaport</span><span class="sxs-lookup"><span data-stu-id="d5bba-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="d5bba-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="d5bba-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-425">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-425">Format</span></span>

<span data-ttu-id="d5bba-426">Nueve letras o dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-427">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-427">Pattern</span></span>

<span data-ttu-id="d5bba-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-429">Checksum</span></span>

<span data-ttu-id="d5bba-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="d5bba-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-431">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-431">Definition</span></span>

<span data-ttu-id="d5bba-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-433">La expresión regular `Regex_netherlands_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-434">Una palabra clave de `Keywords_netherlands_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-435">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-435">Keywords</span></span>

<span data-ttu-id="d5bba-436">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-436"></span></span>
|<span data-ttu-id="d5bba-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-438">número de pasaporte neerlandés</span><span class="sxs-lookup"><span data-stu-id="d5bba-438">dutch passport number</span></span>  <br/> <span data-ttu-id="d5bba-439">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-439">passport number</span></span>  <br/> <span data-ttu-id="d5bba-440">número de cuenta de passport (Países Bajos)</span><span class="sxs-lookup"><span data-stu-id="d5bba-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="d5bba-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="d5bba-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="d5bba-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="d5bba-442">paspoort</span></span>  <br/> <span data-ttu-id="d5bba-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d5bba-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="d5bba-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d5bba-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="d5bba-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="d5bba-445">Poland</span></span>

<span data-ttu-id="d5bba-446">Para obtener información detallada, vea la sección "Número de pasaporte Polonia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d5bba-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d5bba-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="d5bba-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-448">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-448">Format</span></span>

<span data-ttu-id="d5bba-449">Una letra seguida de seis dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-450">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-450">Pattern</span></span>

<span data-ttu-id="d5bba-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="d5bba-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="d5bba-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d5bba-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="d5bba-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d5bba-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-454">Checksum</span></span>

<span data-ttu-id="d5bba-455">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-456">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-456">Definition</span></span>

<span data-ttu-id="d5bba-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-458">La expresión regular `Regex_portugal_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-459">Una palabra clave de `Keywords_portugal_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-460">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-460">Keywords</span></span>

<span data-ttu-id="d5bba-461">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-461"></span></span>
|<span data-ttu-id="d5bba-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-463">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-463">passport number</span></span>  <br/> <span data-ttu-id="d5bba-464">número de cuenta de passport portugués</span><span class="sxs-lookup"><span data-stu-id="d5bba-464">portugese passport number</span></span>  <br/> <span data-ttu-id="d5bba-465">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-465">passport no</span></span>  <br/> <span data-ttu-id="d5bba-466">número passaporte</span><span class="sxs-lookup"><span data-stu-id="d5bba-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="d5bba-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="d5bba-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-468">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-468">Format</span></span>

<span data-ttu-id="d5bba-469">Ocho o nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-470">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-470">Pattern</span></span>

<span data-ttu-id="d5bba-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-472">Checksum</span></span>

<span data-ttu-id="d5bba-473">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-474">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-474">Definition</span></span>

<span data-ttu-id="d5bba-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-476">La expresión regular `Regex_romania_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-477">Una palabra clave de `Keywords_romania_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-478">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-478">Keywords</span></span>

<span data-ttu-id="d5bba-479">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-479"></span></span>
|<span data-ttu-id="d5bba-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-481">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-481">passport number</span></span>  <br/> <span data-ttu-id="d5bba-482">número de pasaporte rumano</span><span class="sxs-lookup"><span data-stu-id="d5bba-482">romanian passport number</span></span>  <br/> <span data-ttu-id="d5bba-483">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-483">passport no</span></span>  <br/> <span data-ttu-id="d5bba-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="d5bba-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="d5bba-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="d5bba-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-486">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-486">Format</span></span>

<span data-ttu-id="d5bba-487">Un dígito o letra seguido de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-488">Pattern</span></span>

<span data-ttu-id="d5bba-489">Un dígito o letra (no entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d5bba-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-490">Checksum</span></span>

<span data-ttu-id="d5bba-491">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-492">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-492">Definition</span></span>

<span data-ttu-id="d5bba-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-494">La expresión regular `Regex_slovakia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-495">Una palabra clave de `Keywords_slovakia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-496">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-496">Keywords</span></span>

<span data-ttu-id="d5bba-497">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-497"></span></span>
|<span data-ttu-id="d5bba-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-499">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-499">passport number</span></span>  <br/> <span data-ttu-id="d5bba-500">número de cuenta de passport eslovaco</span><span class="sxs-lookup"><span data-stu-id="d5bba-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="d5bba-501">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-501">passport no</span></span>  <br/> <span data-ttu-id="d5bba-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="d5bba-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="d5bba-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="d5bba-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-504">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-504">Format</span></span>

<span data-ttu-id="d5bba-505">Dos letras seguidas de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-506">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-506">Pattern</span></span>

<span data-ttu-id="d5bba-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="d5bba-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="d5bba-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="d5bba-508">The letter "P"</span></span>
    
- <span data-ttu-id="d5bba-509">Una letra en mayúsculas</span><span class="sxs-lookup"><span data-stu-id="d5bba-509">One uppercase letter</span></span>
    
- <span data-ttu-id="d5bba-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d5bba-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-511">Checksum</span></span>

<span data-ttu-id="d5bba-512">No</span><span class="sxs-lookup"><span data-stu-id="d5bba-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-513">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-513">Definition</span></span>

<span data-ttu-id="d5bba-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-515">La expresión regular `Regex_slovenia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-516">Una palabra clave de `Keywords_slovenia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-517">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-517">Keywords</span></span>

<span data-ttu-id="d5bba-518">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-518"></span></span>
|<span data-ttu-id="d5bba-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-520">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-520">passport number</span></span>  <br/> <span data-ttu-id="d5bba-521">número de cuenta de passport esloveno</span><span class="sxs-lookup"><span data-stu-id="d5bba-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="d5bba-522">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-522">passport no</span></span>  <br/> <span data-ttu-id="d5bba-523">Lista de potnega številka</span><span class="sxs-lookup"><span data-stu-id="d5bba-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="d5bba-524">España</span><span class="sxs-lookup"><span data-stu-id="d5bba-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="d5bba-525">Formato</span><span class="sxs-lookup"><span data-stu-id="d5bba-525">Format</span></span>

<span data-ttu-id="d5bba-526">Una combinación de ocho o nueve caracteres de letras y números sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="d5bba-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d5bba-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="d5bba-527">Pattern</span></span>

<span data-ttu-id="d5bba-528">Una combinación de ocho o nueve caracteres de letras y números:</span><span class="sxs-lookup"><span data-stu-id="d5bba-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="d5bba-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="d5bba-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="d5bba-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="d5bba-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="d5bba-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="d5bba-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d5bba-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d5bba-532">Checksum</span></span>

<span data-ttu-id="d5bba-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="d5bba-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d5bba-534">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bba-534">Definition</span></span>

<span data-ttu-id="d5bba-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d5bba-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d5bba-536">La expresión regular `Regex_spain_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5bba-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d5bba-537">Una palabra clave de `Keywords_spain_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d5bba-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5bba-538">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5bba-538">Keywords</span></span>

<span data-ttu-id="d5bba-539">| |</span><span class="sxs-lookup"><span data-stu-id="d5bba-539"></span></span>
|<span data-ttu-id="d5bba-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d5bba-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d5bba-541">passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-541">passport</span></span>  <br/> <span data-ttu-id="d5bba-542">cuenta de passport de España</span><span class="sxs-lookup"><span data-stu-id="d5bba-542">spain passport</span></span>  <br/> <span data-ttu-id="d5bba-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-543">passport book</span></span>  <br/> <span data-ttu-id="d5bba-544">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="d5bba-544">passport number</span></span>  <br/> <span data-ttu-id="d5bba-545">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="d5bba-545">passport no</span></span>  <br/> <span data-ttu-id="d5bba-546">Libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="d5bba-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="d5bba-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="d5bba-547">número pasaporte</span></span>  <br/> <span data-ttu-id="d5bba-548">España pasaporte</span><span class="sxs-lookup"><span data-stu-id="d5bba-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="d5bba-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="d5bba-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="d5bba-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="d5bba-550">Sweden</span></span>

<span data-ttu-id="d5bba-551">Para obtener información detallada, vea la sección "Número de pasaporte Suecia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d5bba-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="d5bba-552">REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="d5bba-552">UK</span></span>

<span data-ttu-id="d5bba-p103">Para obtener información detallada, vea la sección "Número de pasaporte de Estados Unidos / Reino Unido" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d5bba-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d5bba-555">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5bba-555">See also</span></span>

[<span data-ttu-id="d5bba-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="d5bba-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

