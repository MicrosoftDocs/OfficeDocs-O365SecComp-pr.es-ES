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
ms.openlocfilehash: 7a7fc1ff826aab4096c46535686eb0fd68173c6f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "25840329"
---
# <a name="eu-passport-number"></a><span data-ttu-id="6e951-104">Número de cuenta de Passport de la UE</span><span class="sxs-lookup"><span data-stu-id="6e951-104">EU Passport Number</span></span>

<span data-ttu-id="6e951-p102">En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de la UE Passport número. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="6e951-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="6e951-107">Austria</span><span class="sxs-lookup"><span data-stu-id="6e951-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="6e951-108">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-108">Format</span></span>

<span data-ttu-id="6e951-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-110">Pattern</span></span>

<span data-ttu-id="6e951-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="6e951-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="6e951-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6e951-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="6e951-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="6e951-113">One space (optional)</span></span>
    
- <span data-ttu-id="6e951-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e951-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-115">Checksum</span></span>

<span data-ttu-id="6e951-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6e951-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-117">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-117">Definition</span></span>

<span data-ttu-id="6e951-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-119">La expresión regular `Regex_austria_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-120">Una palabra clave de `Keywords_austria_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-121">Keywords</span></span>

<span data-ttu-id="6e951-122">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-122"></span></span>
|<span data-ttu-id="6e951-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-124">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-124">passport number</span></span>  <br/> <span data-ttu-id="6e951-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="6e951-125">austrian passport number</span></span>  <br/> <span data-ttu-id="6e951-126">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-126">passport no</span></span>  <br/> <span data-ttu-id="6e951-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="6e951-127">reisepass</span></span>  <br/> <span data-ttu-id="6e951-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="6e951-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="6e951-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="6e951-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="6e951-130">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-130">Format</span></span>

<span data-ttu-id="6e951-131">Dos letras seguidas por seis dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-132">Pattern</span></span>

<span data-ttu-id="6e951-133">Dos letras y seguido de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-134">Checksum</span></span>

<span data-ttu-id="6e951-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6e951-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-136">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-136">Definition</span></span>

<span data-ttu-id="6e951-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-138">La expresión regular `Regex_belgium_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-139">Una palabra clave de `Keywords_belgium_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-140">Keywords</span></span>

<span data-ttu-id="6e951-141">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-141"></span></span>
|<span data-ttu-id="6e951-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-143">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-143">passport number</span></span>  <br/> <span data-ttu-id="6e951-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="6e951-144">belgian passport number</span></span>  <br/> <span data-ttu-id="6e951-145">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-145">passport no</span></span>  <br/> <span data-ttu-id="6e951-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="6e951-146">paspoort</span></span>  <br/> <span data-ttu-id="6e951-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6e951-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="6e951-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="6e951-148">reisepass kein</span></span>  <br/> <span data-ttu-id="6e951-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="6e951-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="6e951-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="6e951-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="6e951-151">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-151">Format</span></span>

<span data-ttu-id="6e951-152">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-153">Pattern</span></span>

 <span data-ttu-id="6e951-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6e951-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-155">Checksum</span></span>

<span data-ttu-id="6e951-156">No</span><span class="sxs-lookup"><span data-stu-id="6e951-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-157">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-157">Definition</span></span>

<span data-ttu-id="6e951-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-159">La expresión regular `Regex_bulgaria_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-160">Una palabra clave de `Keywords_bulgaria_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-161">Keywords</span></span>

<span data-ttu-id="6e951-162">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-162"></span></span>
|<span data-ttu-id="6e951-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-164">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-164">passport number</span></span>  <br/> <span data-ttu-id="6e951-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="6e951-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="6e951-166">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-166">passport no</span></span>  <br/> <span data-ttu-id="6e951-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="6e951-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="6e951-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="6e951-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="6e951-169">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-169">Format</span></span>

<span data-ttu-id="6e951-170">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-171">Pattern</span></span>

 <span data-ttu-id="6e951-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6e951-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-173">Checksum</span></span>

<span data-ttu-id="6e951-174">No</span><span class="sxs-lookup"><span data-stu-id="6e951-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-175">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-175">Definition</span></span>

<span data-ttu-id="6e951-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-177">La expresión regular `Regex_croatia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-178">Una palabra clave de `Keywords_croatia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-179">Keywords</span></span>

<span data-ttu-id="6e951-180">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-180"></span></span>
|<span data-ttu-id="6e951-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-182">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-182">passport number</span></span>  <br/> <span data-ttu-id="6e951-183">número de pasaporte croata</span><span class="sxs-lookup"><span data-stu-id="6e951-183">croatian passport number</span></span>  <br/> <span data-ttu-id="6e951-184">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-184">passport no</span></span>  <br/> <span data-ttu-id="6e951-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="6e951-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="6e951-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="6e951-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="6e951-187">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-187">Format</span></span>

<span data-ttu-id="6e951-188">Una letra seguida de 6-8 dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-189">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-189">Pattern</span></span>

<span data-ttu-id="6e951-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-191">Checksum</span></span>

<span data-ttu-id="6e951-192">No</span><span class="sxs-lookup"><span data-stu-id="6e951-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-193">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-193">Definition</span></span>

<span data-ttu-id="6e951-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-195">La expresión regular `Regex_cyprus_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-196">Una palabra clave de `Keywords_cyprus_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-197">Keywords</span></span>

<span data-ttu-id="6e951-198">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-198"></span></span>
|<span data-ttu-id="6e951-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-200">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-200">passport number</span></span>  <br/> <span data-ttu-id="6e951-201">número de cuenta de passport chipriota</span><span class="sxs-lookup"><span data-stu-id="6e951-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="6e951-202">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-202">passport no</span></span>  <br/> <span data-ttu-id="6e951-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="6e951-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="6e951-204">República Checa</span><span class="sxs-lookup"><span data-stu-id="6e951-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="6e951-205">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-205">Format</span></span>

<span data-ttu-id="6e951-206">Ocho dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-207">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-207">Pattern</span></span>

<span data-ttu-id="6e951-208">Ocho dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-209">Checksum</span></span>

<span data-ttu-id="6e951-210">No</span><span class="sxs-lookup"><span data-stu-id="6e951-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-211">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-211">Definition</span></span>

<span data-ttu-id="6e951-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-213">La expresión regular `Regex_czech_republic_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-214">Una palabra clave de `Keywords_czech_republic_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-215">Keywords</span></span>

<span data-ttu-id="6e951-216">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-216"></span></span>
|<span data-ttu-id="6e951-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-218">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-218">passport number</span></span>  <br/> <span data-ttu-id="6e951-219">número de pasaporte checo</span><span class="sxs-lookup"><span data-stu-id="6e951-219">czech passport number</span></span>  <br/> <span data-ttu-id="6e951-220">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-220">passport no</span></span>  <br/> <span data-ttu-id="6e951-221">pas cestovní</span><span class="sxs-lookup"><span data-stu-id="6e951-221">cestovní pas</span></span>  <br/> <span data-ttu-id="6e951-222">PAS</span><span class="sxs-lookup"><span data-stu-id="6e951-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="6e951-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="6e951-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="6e951-224">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-224">Format</span></span>

<span data-ttu-id="6e951-225">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-226">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-226">Pattern</span></span>

 <span data-ttu-id="6e951-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6e951-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-228">Checksum</span></span>

<span data-ttu-id="6e951-229">No</span><span class="sxs-lookup"><span data-stu-id="6e951-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-230">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-230">Definition</span></span>

<span data-ttu-id="6e951-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-232">La expresión regular `Regex_denmark_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-233">Una palabra clave de `Keywords_denmark_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-234">Keywords</span></span>

<span data-ttu-id="6e951-235">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-235"></span></span>
|<span data-ttu-id="6e951-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-237">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-237">passport number</span></span>  <br/> <span data-ttu-id="6e951-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="6e951-238">danish passport number</span></span>  <br/> <span data-ttu-id="6e951-239">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-239">passport no</span></span>  <br/> <span data-ttu-id="6e951-240">PAS</span><span class="sxs-lookup"><span data-stu-id="6e951-240">pas</span></span>  <br/> <span data-ttu-id="6e951-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="6e951-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="6e951-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="6e951-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="6e951-243">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-243">Format</span></span>

<span data-ttu-id="6e951-244">Una letra seguida de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-245">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-245">Pattern</span></span>

<span data-ttu-id="6e951-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-247">Checksum</span></span>

<span data-ttu-id="6e951-248">No</span><span class="sxs-lookup"><span data-stu-id="6e951-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-249">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-249">Definition</span></span>

<span data-ttu-id="6e951-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-251">La expresión regular `Regex_estonia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-252">Una palabra clave de `Keywords_estonia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-253">Keywords</span></span>

<span data-ttu-id="6e951-254">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-254"></span></span>
|<span data-ttu-id="6e951-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-256">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-256">passport number</span></span>  <br/> <span data-ttu-id="6e951-257">número de pasaporte estonio</span><span class="sxs-lookup"><span data-stu-id="6e951-257">estonian passport number</span></span>  <br/> <span data-ttu-id="6e951-258">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-258">passport no</span></span>  <br/> <span data-ttu-id="6e951-259">eesti kodaniku pasada</span><span class="sxs-lookup"><span data-stu-id="6e951-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="6e951-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="6e951-260">Finland</span></span>

<span data-ttu-id="6e951-261">Para obtener información detallada, vea la sección "Número de pasaporte Finlandia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e951-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="6e951-262">Francia</span><span class="sxs-lookup"><span data-stu-id="6e951-262">France</span></span>

<span data-ttu-id="6e951-263">Para obtener información detallada, vea la sección "Número de pasaporte Francia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e951-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="6e951-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="6e951-264">Germany</span></span>

<span data-ttu-id="6e951-265">Para obtener información detallada, vea la sección "Número de pasaporte Alemania" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e951-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="6e951-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="6e951-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="6e951-267">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-267">Format</span></span>

<span data-ttu-id="6e951-268">Dos letras seguidas de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-269">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-269">Pattern</span></span>

<span data-ttu-id="6e951-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-271">Checksum</span></span>

<span data-ttu-id="6e951-272">No</span><span class="sxs-lookup"><span data-stu-id="6e951-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-273">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-273">Definition</span></span>

<span data-ttu-id="6e951-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-275">La expresión regular `Regex_greece_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-276">Una palabra clave de `Keywords_greece_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-277">Keywords</span></span>

<span data-ttu-id="6e951-278">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-278"></span></span>
|<span data-ttu-id="6e951-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-280">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-280">passport number</span></span>  <br/> <span data-ttu-id="6e951-281">número de pasaporte griega</span><span class="sxs-lookup"><span data-stu-id="6e951-281">greek passport number</span></span>  <br/> <span data-ttu-id="6e951-282">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-282">passport no</span></span>  <br/> <span data-ttu-id="6e951-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="6e951-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="6e951-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="6e951-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="6e951-285">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-285">Format</span></span>

<span data-ttu-id="6e951-286">Dos letras seguidas por seis o siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-287">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-287">Pattern</span></span>

<span data-ttu-id="6e951-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-289">Checksum</span></span>

<span data-ttu-id="6e951-290">No</span><span class="sxs-lookup"><span data-stu-id="6e951-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-291">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-291">Definition</span></span>

<span data-ttu-id="6e951-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-293">La expresión regular `Regex_hungary_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-294">Una palabra clave de `Keywords_hungary_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-295">Keywords</span></span>

<span data-ttu-id="6e951-296">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-296"></span></span>
|<span data-ttu-id="6e951-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-298">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-298">passport number</span></span>  <br/> <span data-ttu-id="6e951-299">número de pasaporte húngaro</span><span class="sxs-lookup"><span data-stu-id="6e951-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="6e951-300">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-300">passport no</span></span>  <br/> <span data-ttu-id="6e951-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="6e951-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="6e951-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="6e951-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="6e951-303">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-303">Format</span></span>

<span data-ttu-id="6e951-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-305">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-305">Pattern</span></span>

<span data-ttu-id="6e951-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6e951-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6e951-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6e951-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6e951-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e951-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-309">Checksum</span></span>

<span data-ttu-id="6e951-310">No</span><span class="sxs-lookup"><span data-stu-id="6e951-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-311">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-311">Definition</span></span>

<span data-ttu-id="6e951-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-313">La expresión regular `Regex_ireland_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-314">Una palabra clave de `Keywords_ireland_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-315">Keywords</span></span>

<span data-ttu-id="6e951-316">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-316"></span></span>
|<span data-ttu-id="6e951-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-318">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-318">passport number</span></span>  <br/> <span data-ttu-id="6e951-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="6e951-319">irish passport number</span></span>  <br/> <span data-ttu-id="6e951-320">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-320">passport no</span></span>  <br/> <span data-ttu-id="6e951-321">PAS</span><span class="sxs-lookup"><span data-stu-id="6e951-321">pas</span></span>  <br/> <span data-ttu-id="6e951-322">passport</span><span class="sxs-lookup"><span data-stu-id="6e951-322">passport</span></span>  <br/> <span data-ttu-id="6e951-323">passeport</span><span class="sxs-lookup"><span data-stu-id="6e951-323">passeport</span></span>  <br/> <span data-ttu-id="6e951-324">numero de passeport</span><span class="sxs-lookup"><span data-stu-id="6e951-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="6e951-325">Italia</span><span class="sxs-lookup"><span data-stu-id="6e951-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="6e951-326">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-326">Format</span></span>

<span data-ttu-id="6e951-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-328">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-328">Pattern</span></span>

<span data-ttu-id="6e951-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6e951-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6e951-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6e951-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6e951-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e951-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-332">Checksum</span></span>

<span data-ttu-id="6e951-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6e951-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-334">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-334">Definition</span></span>

<span data-ttu-id="6e951-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-336">La expresión regular `Regex_italy_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-337">Una palabra clave de `Keywords_italy_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-338">Keywords</span></span>

<span data-ttu-id="6e951-339">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-339"></span></span>
|<span data-ttu-id="6e951-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-341">número de pasaporte italiano</span><span class="sxs-lookup"><span data-stu-id="6e951-341">italian passport number</span></span>  <br/> <span data-ttu-id="6e951-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="6e951-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="6e951-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="6e951-343">passaporto</span></span>  <br/> <span data-ttu-id="6e951-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="6e951-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="6e951-345">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-345">passport number</span></span>  <br/> <span data-ttu-id="6e951-346">numero de passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="6e951-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="6e951-347">numero de passaporto</span><span class="sxs-lookup"><span data-stu-id="6e951-347">passaporto numero</span></span>  <br/> <span data-ttu-id="6e951-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="6e951-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="6e951-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="6e951-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="6e951-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="6e951-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="6e951-351">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-351">Format</span></span>

<span data-ttu-id="6e951-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-353">Pattern</span></span>

<span data-ttu-id="6e951-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6e951-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6e951-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6e951-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6e951-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e951-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-357">Checksum</span></span>

<span data-ttu-id="6e951-358">No</span><span class="sxs-lookup"><span data-stu-id="6e951-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-359">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-359">Definition</span></span>

<span data-ttu-id="6e951-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-361">La expresión regular `Regex_latvia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-362">Una palabra clave de `Keywords_latvia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-363">Keywords</span></span>

<span data-ttu-id="6e951-364">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-364"></span></span>
|<span data-ttu-id="6e951-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-366">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-366">passport number</span></span>  <br/> <span data-ttu-id="6e951-367">número de pasaporte letón</span><span class="sxs-lookup"><span data-stu-id="6e951-367">latvian passport number</span></span>  <br/> <span data-ttu-id="6e951-368">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-368">passport no</span></span>  <br/> <span data-ttu-id="6e951-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="6e951-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="6e951-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="6e951-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="6e951-371">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-371">Format</span></span>

<span data-ttu-id="6e951-372">Ocho dígitos o letras sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-373">Pattern</span></span>

<span data-ttu-id="6e951-374">Ocho dígitos o letras (no entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6e951-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-375">Checksum</span></span>

<span data-ttu-id="6e951-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6e951-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-377">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-377">Definition</span></span>

<span data-ttu-id="6e951-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-379">La expresión regular `Regex_lithuania_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-380">Una palabra clave de `Keywords_lithuania_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-381">Keywords</span></span>

<span data-ttu-id="6e951-382">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-382"></span></span>
|<span data-ttu-id="6e951-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-384">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-384">passport number</span></span>  <br/> <span data-ttu-id="6e951-385">número de cuenta de passport lithunian</span><span class="sxs-lookup"><span data-stu-id="6e951-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="6e951-386">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-386">passport no</span></span>  <br/> <span data-ttu-id="6e951-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="6e951-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="6e951-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="6e951-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="6e951-389">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-389">Format</span></span>

<span data-ttu-id="6e951-390">Ocho dígitos o letras sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-391">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-391">Pattern</span></span>

<span data-ttu-id="6e951-392">Ocho dígitos o letras (no entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6e951-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-393">Checksum</span></span>

<span data-ttu-id="6e951-394">No</span><span class="sxs-lookup"><span data-stu-id="6e951-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-395">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-395">Definition</span></span>

<span data-ttu-id="6e951-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-397">La expresión regular `Regex_nation_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-398">Una palabra clave de `Keywords_nation_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-399">Keywords</span></span>

<span data-ttu-id="6e951-400">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-400"></span></span>
|<span data-ttu-id="6e951-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-402">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-402">passport number</span></span>  <br/> <span data-ttu-id="6e951-403">número de pasaporte letón</span><span class="sxs-lookup"><span data-stu-id="6e951-403">latvian passport number</span></span>  <br/> <span data-ttu-id="6e951-404">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-404">passport no</span></span>  <br/> <span data-ttu-id="6e951-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="6e951-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="6e951-406">Malta</span><span class="sxs-lookup"><span data-stu-id="6e951-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="6e951-407">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-407">Format</span></span>

<span data-ttu-id="6e951-408">Siete dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-409">Pattern</span></span>

 <span data-ttu-id="6e951-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6e951-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-411">Checksum</span></span>

<span data-ttu-id="6e951-412">No</span><span class="sxs-lookup"><span data-stu-id="6e951-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-413">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-413">Definition</span></span>

<span data-ttu-id="6e951-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-415">La expresión regular `Regex_malta_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-416">Una palabra clave de `Keywords_malta_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-417">Keywords</span></span>

<span data-ttu-id="6e951-418">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-418"></span></span>
|<span data-ttu-id="6e951-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-420">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-420">passport number</span></span>  <br/> <span data-ttu-id="6e951-421">número de pasaporte Maltés</span><span class="sxs-lookup"><span data-stu-id="6e951-421">maltese passport number</span></span>  <br/> <span data-ttu-id="6e951-422">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-422">passport no</span></span>  <br/> <span data-ttu-id="6e951-423">numru horizontal-passaport</span><span class="sxs-lookup"><span data-stu-id="6e951-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="6e951-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="6e951-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="6e951-425">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-425">Format</span></span>

<span data-ttu-id="6e951-426">Nueve letras o dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-427">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-427">Pattern</span></span>

<span data-ttu-id="6e951-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-429">Checksum</span></span>

<span data-ttu-id="6e951-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6e951-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-431">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-431">Definition</span></span>

<span data-ttu-id="6e951-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-433">La expresión regular `Regex_netherlands_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-434">Una palabra clave de `Keywords_netherlands_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-435">Keywords</span></span>

<span data-ttu-id="6e951-436">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-436"></span></span>
|<span data-ttu-id="6e951-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-438">número de pasaporte neerlandés</span><span class="sxs-lookup"><span data-stu-id="6e951-438">dutch passport number</span></span>  <br/> <span data-ttu-id="6e951-439">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-439">passport number</span></span>  <br/> <span data-ttu-id="6e951-440">número de cuenta de passport (Países Bajos)</span><span class="sxs-lookup"><span data-stu-id="6e951-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="6e951-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="6e951-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="6e951-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="6e951-442">paspoort</span></span>  <br/> <span data-ttu-id="6e951-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6e951-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="6e951-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6e951-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="6e951-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="6e951-445">Poland</span></span>

<span data-ttu-id="6e951-446">Para obtener información detallada, vea la sección "Número de pasaporte Polonia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e951-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="6e951-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="6e951-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="6e951-448">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-448">Format</span></span>

<span data-ttu-id="6e951-449">Una letra seguida de seis dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-450">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-450">Pattern</span></span>

<span data-ttu-id="6e951-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="6e951-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="6e951-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6e951-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="6e951-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e951-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-454">Checksum</span></span>

<span data-ttu-id="6e951-455">No</span><span class="sxs-lookup"><span data-stu-id="6e951-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-456">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-456">Definition</span></span>

<span data-ttu-id="6e951-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-458">La expresión regular `Regex_portugal_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-459">Una palabra clave de `Keywords_portugal_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-460">Keywords</span></span>

<span data-ttu-id="6e951-461">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-461"></span></span>
|<span data-ttu-id="6e951-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-463">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-463">passport number</span></span>  <br/> <span data-ttu-id="6e951-464">número de pasaporte portugués</span><span class="sxs-lookup"><span data-stu-id="6e951-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="6e951-465">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-465">passport no</span></span>  <br/> <span data-ttu-id="6e951-466">número passaporte</span><span class="sxs-lookup"><span data-stu-id="6e951-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="6e951-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="6e951-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="6e951-468">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-468">Format</span></span>

<span data-ttu-id="6e951-469">Ocho o nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-470">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-470">Pattern</span></span>

<span data-ttu-id="6e951-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-472">Checksum</span></span>

<span data-ttu-id="6e951-473">No</span><span class="sxs-lookup"><span data-stu-id="6e951-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-474">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-474">Definition</span></span>

<span data-ttu-id="6e951-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-476">La expresión regular `Regex_romania_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-477">Una palabra clave de `Keywords_romania_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-478">Keywords</span></span>

<span data-ttu-id="6e951-479">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-479"></span></span>
|<span data-ttu-id="6e951-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-481">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-481">passport number</span></span>  <br/> <span data-ttu-id="6e951-482">número de pasaporte rumano</span><span class="sxs-lookup"><span data-stu-id="6e951-482">romanian passport number</span></span>  <br/> <span data-ttu-id="6e951-483">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-483">passport no</span></span>  <br/> <span data-ttu-id="6e951-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="6e951-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="6e951-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="6e951-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="6e951-486">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-486">Format</span></span>

<span data-ttu-id="6e951-487">Un dígito o letra seguido de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-488">Pattern</span></span>

<span data-ttu-id="6e951-489">Un dígito o letra (no entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e951-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-490">Checksum</span></span>

<span data-ttu-id="6e951-491">No</span><span class="sxs-lookup"><span data-stu-id="6e951-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-492">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-492">Definition</span></span>

<span data-ttu-id="6e951-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-494">La expresión regular `Regex_slovakia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-495">Una palabra clave de `Keywords_slovakia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-496">Keywords</span></span>

<span data-ttu-id="6e951-497">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-497"></span></span>
|<span data-ttu-id="6e951-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-499">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-499">passport number</span></span>  <br/> <span data-ttu-id="6e951-500">número de cuenta de passport eslovaco</span><span class="sxs-lookup"><span data-stu-id="6e951-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="6e951-501">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-501">passport no</span></span>  <br/> <span data-ttu-id="6e951-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="6e951-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="6e951-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="6e951-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="6e951-504">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-504">Format</span></span>

<span data-ttu-id="6e951-505">Dos letras seguidas de siete dígitos sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-506">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-506">Pattern</span></span>

<span data-ttu-id="6e951-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6e951-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="6e951-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="6e951-508">The letter "P"</span></span>
    
- <span data-ttu-id="6e951-509">Una letra en mayúsculas</span><span class="sxs-lookup"><span data-stu-id="6e951-509">One uppercase letter</span></span>
    
- <span data-ttu-id="6e951-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e951-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-511">Checksum</span></span>

<span data-ttu-id="6e951-512">No</span><span class="sxs-lookup"><span data-stu-id="6e951-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-513">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-513">Definition</span></span>

<span data-ttu-id="6e951-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-515">La expresión regular `Regex_slovenia_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-516">Una palabra clave de `Keywords_slovenia_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-517">Keywords</span></span>

<span data-ttu-id="6e951-518">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-518"></span></span>
|<span data-ttu-id="6e951-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-520">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-520">passport number</span></span>  <br/> <span data-ttu-id="6e951-521">número de cuenta de passport esloveno</span><span class="sxs-lookup"><span data-stu-id="6e951-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="6e951-522">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-522">passport no</span></span>  <br/> <span data-ttu-id="6e951-523">Lista de potnega številka</span><span class="sxs-lookup"><span data-stu-id="6e951-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="6e951-524">España</span><span class="sxs-lookup"><span data-stu-id="6e951-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="6e951-525">Formato</span><span class="sxs-lookup"><span data-stu-id="6e951-525">Format</span></span>

<span data-ttu-id="6e951-526">Una combinación de ocho o nueve caracteres de letras y números sin espacios ni los delimitadores</span><span class="sxs-lookup"><span data-stu-id="6e951-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e951-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="6e951-527">Pattern</span></span>

<span data-ttu-id="6e951-528">Una combinación de ocho o nueve caracteres de letras y números:</span><span class="sxs-lookup"><span data-stu-id="6e951-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="6e951-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="6e951-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="6e951-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="6e951-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="6e951-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6e951-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e951-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6e951-532">Checksum</span></span>

<span data-ttu-id="6e951-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6e951-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e951-534">Definición</span><span class="sxs-lookup"><span data-stu-id="6e951-534">Definition</span></span>

<span data-ttu-id="6e951-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6e951-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e951-536">La expresión regular `Regex_spain_eu_passport_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6e951-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e951-537">Una palabra clave de `Keywords_spain_eu_passport_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="6e951-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e951-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e951-538">Keywords</span></span>

<span data-ttu-id="6e951-539">| |</span><span class="sxs-lookup"><span data-stu-id="6e951-539"></span></span>
|<span data-ttu-id="6e951-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6e951-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6e951-541">passport</span><span class="sxs-lookup"><span data-stu-id="6e951-541">passport</span></span>  <br/> <span data-ttu-id="6e951-542">cuenta de passport de España</span><span class="sxs-lookup"><span data-stu-id="6e951-542">spain passport</span></span>  <br/> <span data-ttu-id="6e951-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-543">passport book</span></span>  <br/> <span data-ttu-id="6e951-544">número de cuenta de Passport</span><span class="sxs-lookup"><span data-stu-id="6e951-544">passport number</span></span>  <br/> <span data-ttu-id="6e951-545">cuenta de Passport no</span><span class="sxs-lookup"><span data-stu-id="6e951-545">passport no</span></span>  <br/> <span data-ttu-id="6e951-546">Libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="6e951-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="6e951-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="6e951-547">número pasaporte</span></span>  <br/> <span data-ttu-id="6e951-548">España pasaporte</span><span class="sxs-lookup"><span data-stu-id="6e951-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="6e951-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="6e951-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="6e951-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="6e951-550">Sweden</span></span>

<span data-ttu-id="6e951-551">Para obtener información detallada, vea la sección "Número de pasaporte Suecia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e951-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="6e951-552">REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="6e951-552">UK</span></span>

<span data-ttu-id="6e951-p103">Para obtener información detallada, vea la sección "Número de pasaporte de Estados Unidos / Reino Unido" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e951-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e951-555">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6e951-555">See also</span></span>

[<span data-ttu-id="6e951-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="6e951-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

