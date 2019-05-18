---
title: Número de pasaporte de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152972"
---
# <a name="eu-passport-number"></a><span data-ttu-id="f1741-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="f1741-104">EU Passport Number</span></span>

<span data-ttu-id="f1741-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="f1741-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="f1741-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="f1741-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f1741-107">Austria</span><span class="sxs-lookup"><span data-stu-id="f1741-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f1741-108">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-108">Format</span></span>

<span data-ttu-id="f1741-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-110">Pattern</span></span>

<span data-ttu-id="f1741-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="f1741-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="f1741-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f1741-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="f1741-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="f1741-113">One space (optional)</span></span>
    
- <span data-ttu-id="f1741-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f1741-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-115">Checksum</span></span>

<span data-ttu-id="f1741-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f1741-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-117">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-117">Definition</span></span>

<span data-ttu-id="f1741-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-121">Keywords</span></span>

<span data-ttu-id="f1741-122">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-122"></span></span>
|<span data-ttu-id="f1741-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-124">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-124">passport number</span></span>  <br/> <span data-ttu-id="f1741-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="f1741-125">austrian passport number</span></span>  <br/> <span data-ttu-id="f1741-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-126">passport no</span></span>  <br/> <span data-ttu-id="f1741-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="f1741-127">reisepass</span></span>  <br/> <span data-ttu-id="f1741-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="f1741-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="f1741-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="f1741-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f1741-130">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-130">Format</span></span>

<span data-ttu-id="f1741-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-132">Pattern</span></span>

<span data-ttu-id="f1741-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-134">Checksum</span></span>

<span data-ttu-id="f1741-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f1741-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-136">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-136">Definition</span></span>

<span data-ttu-id="f1741-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-140">Keywords</span></span>

<span data-ttu-id="f1741-141">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-141"></span></span>
|<span data-ttu-id="f1741-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-143">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-143">passport number</span></span>  <br/> <span data-ttu-id="f1741-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="f1741-144">belgian passport number</span></span>  <br/> <span data-ttu-id="f1741-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-145">passport no</span></span>  <br/> <span data-ttu-id="f1741-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="f1741-146">paspoort</span></span>  <br/> <span data-ttu-id="f1741-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f1741-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="f1741-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="f1741-148">reisepass kein</span></span>  <br/> <span data-ttu-id="f1741-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="f1741-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="f1741-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="f1741-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f1741-151">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-151">Format</span></span>

<span data-ttu-id="f1741-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-153">Pattern</span></span>

 <span data-ttu-id="f1741-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f1741-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-155">Checksum</span></span>

<span data-ttu-id="f1741-156">No</span><span class="sxs-lookup"><span data-stu-id="f1741-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-157">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-157">Definition</span></span>

<span data-ttu-id="f1741-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-161">Keywords</span></span>

<span data-ttu-id="f1741-162">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-162"></span></span>
|<span data-ttu-id="f1741-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-164">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-164">passport number</span></span>  <br/> <span data-ttu-id="f1741-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="f1741-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="f1741-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-166">passport no</span></span>  <br/> <span data-ttu-id="f1741-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="f1741-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="f1741-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="f1741-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f1741-169">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-169">Format</span></span>

<span data-ttu-id="f1741-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-171">Pattern</span></span>

 <span data-ttu-id="f1741-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f1741-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-173">Checksum</span></span>

<span data-ttu-id="f1741-174">No</span><span class="sxs-lookup"><span data-stu-id="f1741-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-175">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-175">Definition</span></span>

<span data-ttu-id="f1741-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-179">Keywords</span></span>

<span data-ttu-id="f1741-180">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-180"></span></span>
|<span data-ttu-id="f1741-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-182">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-182">passport number</span></span>  <br/> <span data-ttu-id="f1741-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="f1741-183">croatian passport number</span></span>  <br/> <span data-ttu-id="f1741-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-184">passport no</span></span>  <br/> <span data-ttu-id="f1741-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="f1741-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="f1741-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="f1741-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f1741-187">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-187">Format</span></span>

<span data-ttu-id="f1741-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-189">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-189">Pattern</span></span>

<span data-ttu-id="f1741-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-191">Checksum</span></span>

<span data-ttu-id="f1741-192">No</span><span class="sxs-lookup"><span data-stu-id="f1741-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-193">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-193">Definition</span></span>

<span data-ttu-id="f1741-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-197">Keywords</span></span>

<span data-ttu-id="f1741-198">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-198"></span></span>
|<span data-ttu-id="f1741-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-200">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-200">passport number</span></span>  <br/> <span data-ttu-id="f1741-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="f1741-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="f1741-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-202">passport no</span></span>  <br/> <span data-ttu-id="f1741-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="f1741-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="f1741-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="f1741-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f1741-205">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-205">Format</span></span>

<span data-ttu-id="f1741-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-207">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-207">Pattern</span></span>

<span data-ttu-id="f1741-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-209">Checksum</span></span>

<span data-ttu-id="f1741-210">No</span><span class="sxs-lookup"><span data-stu-id="f1741-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-211">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-211">Definition</span></span>

<span data-ttu-id="f1741-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-215">Keywords</span></span>

<span data-ttu-id="f1741-216">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-216"></span></span>
|<span data-ttu-id="f1741-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-218">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-218">passport number</span></span>  <br/> <span data-ttu-id="f1741-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="f1741-219">czech passport number</span></span>  <br/> <span data-ttu-id="f1741-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-220">passport no</span></span>  <br/> <span data-ttu-id="f1741-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="f1741-221">cestovní pas</span></span>  <br/> <span data-ttu-id="f1741-222">PAS</span><span class="sxs-lookup"><span data-stu-id="f1741-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="f1741-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="f1741-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f1741-224">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-224">Format</span></span>

<span data-ttu-id="f1741-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-226">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-226">Pattern</span></span>

 <span data-ttu-id="f1741-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f1741-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-228">Checksum</span></span>

<span data-ttu-id="f1741-229">No</span><span class="sxs-lookup"><span data-stu-id="f1741-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-230">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-230">Definition</span></span>

<span data-ttu-id="f1741-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-234">Keywords</span></span>

<span data-ttu-id="f1741-235">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-235"></span></span>
|<span data-ttu-id="f1741-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-237">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-237">passport number</span></span>  <br/> <span data-ttu-id="f1741-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="f1741-238">danish passport number</span></span>  <br/> <span data-ttu-id="f1741-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-239">passport no</span></span>  <br/> <span data-ttu-id="f1741-240">PAS</span><span class="sxs-lookup"><span data-stu-id="f1741-240">pas</span></span>  <br/> <span data-ttu-id="f1741-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="f1741-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="f1741-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="f1741-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f1741-243">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-243">Format</span></span>

<span data-ttu-id="f1741-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-245">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-245">Pattern</span></span>

<span data-ttu-id="f1741-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-247">Checksum</span></span>

<span data-ttu-id="f1741-248">No</span><span class="sxs-lookup"><span data-stu-id="f1741-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-249">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-249">Definition</span></span>

<span data-ttu-id="f1741-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-253">Keywords</span></span>

<span data-ttu-id="f1741-254">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-254"></span></span>
|<span data-ttu-id="f1741-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-256">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-256">passport number</span></span>  <br/> <span data-ttu-id="f1741-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="f1741-257">estonian passport number</span></span>  <br/> <span data-ttu-id="f1741-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-258">passport no</span></span>  <br/> <span data-ttu-id="f1741-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="f1741-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="f1741-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="f1741-260">Finland</span></span>

<span data-ttu-id="f1741-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f1741-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="f1741-262">Francia</span><span class="sxs-lookup"><span data-stu-id="f1741-262">France</span></span>

<span data-ttu-id="f1741-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f1741-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="f1741-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="f1741-264">Germany</span></span>

<span data-ttu-id="f1741-265">Para obtener más información, consulte la sección "número de pasaporte de Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f1741-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="f1741-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="f1741-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f1741-267">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-267">Format</span></span>

<span data-ttu-id="f1741-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-269">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-269">Pattern</span></span>

<span data-ttu-id="f1741-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-271">Checksum</span></span>

<span data-ttu-id="f1741-272">No</span><span class="sxs-lookup"><span data-stu-id="f1741-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-273">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-273">Definition</span></span>

<span data-ttu-id="f1741-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-277">Keywords</span></span>

<span data-ttu-id="f1741-278">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-278"></span></span>
|<span data-ttu-id="f1741-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-280">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-280">passport number</span></span>  <br/> <span data-ttu-id="f1741-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="f1741-281">greek passport number</span></span>  <br/> <span data-ttu-id="f1741-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-282">passport no</span></span>  <br/> <span data-ttu-id="f1741-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="f1741-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="f1741-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="f1741-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f1741-285">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-285">Format</span></span>

<span data-ttu-id="f1741-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-287">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-287">Pattern</span></span>

<span data-ttu-id="f1741-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-289">Checksum</span></span>

<span data-ttu-id="f1741-290">No</span><span class="sxs-lookup"><span data-stu-id="f1741-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-291">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-291">Definition</span></span>

<span data-ttu-id="f1741-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-295">Keywords</span></span>

<span data-ttu-id="f1741-296">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-296"></span></span>
|<span data-ttu-id="f1741-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-298">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-298">passport number</span></span>  <br/> <span data-ttu-id="f1741-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="f1741-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="f1741-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-300">passport no</span></span>  <br/> <span data-ttu-id="f1741-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="f1741-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="f1741-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="f1741-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f1741-303">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-303">Format</span></span>

<span data-ttu-id="f1741-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-305">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-305">Pattern</span></span>

<span data-ttu-id="f1741-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f1741-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f1741-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f1741-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f1741-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f1741-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-309">Checksum</span></span>

<span data-ttu-id="f1741-310">No</span><span class="sxs-lookup"><span data-stu-id="f1741-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-311">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-311">Definition</span></span>

<span data-ttu-id="f1741-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-315">Keywords</span></span>

<span data-ttu-id="f1741-316">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-316"></span></span>
|<span data-ttu-id="f1741-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-318">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-318">passport number</span></span>  <br/> <span data-ttu-id="f1741-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="f1741-319">irish passport number</span></span>  <br/> <span data-ttu-id="f1741-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-320">passport no</span></span>  <br/> <span data-ttu-id="f1741-321">PAS</span><span class="sxs-lookup"><span data-stu-id="f1741-321">pas</span></span>  <br/> <span data-ttu-id="f1741-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="f1741-322">passport</span></span>  <br/> <span data-ttu-id="f1741-323">passeport</span><span class="sxs-lookup"><span data-stu-id="f1741-323">passeport</span></span>  <br/> <span data-ttu-id="f1741-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="f1741-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="f1741-325">Italia</span><span class="sxs-lookup"><span data-stu-id="f1741-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="f1741-326">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-326">Format</span></span>

<span data-ttu-id="f1741-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-328">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-328">Pattern</span></span>

<span data-ttu-id="f1741-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f1741-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f1741-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f1741-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f1741-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f1741-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-332">Checksum</span></span>

<span data-ttu-id="f1741-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f1741-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-334">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-334">Definition</span></span>

<span data-ttu-id="f1741-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-338">Keywords</span></span>

<span data-ttu-id="f1741-339">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-339"></span></span>
|<span data-ttu-id="f1741-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="f1741-341">italian passport number</span></span>  <br/> <span data-ttu-id="f1741-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="f1741-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="f1741-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="f1741-343">passaporto</span></span>  <br/> <span data-ttu-id="f1741-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="f1741-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="f1741-345">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-345">passport number</span></span>  <br/> <span data-ttu-id="f1741-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="f1741-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="f1741-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="f1741-347">passaporto numero</span></span>  <br/> <span data-ttu-id="f1741-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="f1741-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="f1741-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="f1741-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="f1741-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="f1741-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f1741-351">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-351">Format</span></span>

<span data-ttu-id="f1741-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-353">Pattern</span></span>

<span data-ttu-id="f1741-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f1741-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f1741-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f1741-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f1741-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f1741-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-357">Checksum</span></span>

<span data-ttu-id="f1741-358">No</span><span class="sxs-lookup"><span data-stu-id="f1741-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-359">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-359">Definition</span></span>

<span data-ttu-id="f1741-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-363">Keywords</span></span>

<span data-ttu-id="f1741-364">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-364"></span></span>
|<span data-ttu-id="f1741-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-366">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-366">passport number</span></span>  <br/> <span data-ttu-id="f1741-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="f1741-367">latvian passport number</span></span>  <br/> <span data-ttu-id="f1741-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-368">passport no</span></span>  <br/> <span data-ttu-id="f1741-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="f1741-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="f1741-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="f1741-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f1741-371">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-371">Format</span></span>

<span data-ttu-id="f1741-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-373">Pattern</span></span>

<span data-ttu-id="f1741-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f1741-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-375">Checksum</span></span>

<span data-ttu-id="f1741-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f1741-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-377">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-377">Definition</span></span>

<span data-ttu-id="f1741-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-381">Keywords</span></span>

<span data-ttu-id="f1741-382">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-382"></span></span>
|<span data-ttu-id="f1741-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-384">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-384">passport number</span></span>  <br/> <span data-ttu-id="f1741-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="f1741-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="f1741-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-386">passport no</span></span>  <br/> <span data-ttu-id="f1741-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="f1741-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="f1741-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="f1741-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f1741-389">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-389">Format</span></span>

<span data-ttu-id="f1741-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-391">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-391">Pattern</span></span>

<span data-ttu-id="f1741-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f1741-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-393">Checksum</span></span>

<span data-ttu-id="f1741-394">No</span><span class="sxs-lookup"><span data-stu-id="f1741-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-395">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-395">Definition</span></span>

<span data-ttu-id="f1741-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-399">Keywords</span></span>

<span data-ttu-id="f1741-400">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-400"></span></span>
|<span data-ttu-id="f1741-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-402">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-402">passport number</span></span>  <br/> <span data-ttu-id="f1741-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="f1741-403">latvian passport number</span></span>  <br/> <span data-ttu-id="f1741-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-404">passport no</span></span>  <br/> <span data-ttu-id="f1741-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="f1741-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="f1741-406">Malta</span><span class="sxs-lookup"><span data-stu-id="f1741-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f1741-407">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-407">Format</span></span>

<span data-ttu-id="f1741-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-409">Pattern</span></span>

 <span data-ttu-id="f1741-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f1741-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-411">Checksum</span></span>

<span data-ttu-id="f1741-412">No</span><span class="sxs-lookup"><span data-stu-id="f1741-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-413">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-413">Definition</span></span>

<span data-ttu-id="f1741-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-417">Keywords</span></span>

<span data-ttu-id="f1741-418">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-418"></span></span>
|<span data-ttu-id="f1741-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-420">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-420">passport number</span></span>  <br/> <span data-ttu-id="f1741-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="f1741-421">maltese passport number</span></span>  <br/> <span data-ttu-id="f1741-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-422">passport no</span></span>  <br/> <span data-ttu-id="f1741-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="f1741-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="f1741-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="f1741-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f1741-425">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-425">Format</span></span>

<span data-ttu-id="f1741-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-427">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-427">Pattern</span></span>

<span data-ttu-id="f1741-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-429">Checksum</span></span>

<span data-ttu-id="f1741-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f1741-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-431">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-431">Definition</span></span>

<span data-ttu-id="f1741-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-435">Keywords</span></span>

<span data-ttu-id="f1741-436">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-436"></span></span>
|<span data-ttu-id="f1741-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="f1741-438">dutch passport number</span></span>  <br/> <span data-ttu-id="f1741-439">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-439">passport number</span></span>  <br/> <span data-ttu-id="f1741-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="f1741-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="f1741-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="f1741-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="f1741-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="f1741-442">paspoort</span></span>  <br/> <span data-ttu-id="f1741-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f1741-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="f1741-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f1741-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="f1741-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="f1741-445">Poland</span></span>

<span data-ttu-id="f1741-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f1741-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="f1741-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="f1741-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f1741-448">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-448">Format</span></span>

<span data-ttu-id="f1741-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-450">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-450">Pattern</span></span>

<span data-ttu-id="f1741-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f1741-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="f1741-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f1741-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="f1741-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f1741-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-454">Checksum</span></span>

<span data-ttu-id="f1741-455">No</span><span class="sxs-lookup"><span data-stu-id="f1741-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-456">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-456">Definition</span></span>

<span data-ttu-id="f1741-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-460">Keywords</span></span>

<span data-ttu-id="f1741-461">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-461"></span></span>
|<span data-ttu-id="f1741-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-463">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-463">passport number</span></span>  <br/> <span data-ttu-id="f1741-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="f1741-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="f1741-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-465">passport no</span></span>  <br/> <span data-ttu-id="f1741-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="f1741-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="f1741-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f1741-468">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-468">Format</span></span>

<span data-ttu-id="f1741-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-470">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-470">Pattern</span></span>

<span data-ttu-id="f1741-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-472">Checksum</span></span>

<span data-ttu-id="f1741-473">No</span><span class="sxs-lookup"><span data-stu-id="f1741-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-474">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-474">Definition</span></span>

<span data-ttu-id="f1741-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-478">Keywords</span></span>

<span data-ttu-id="f1741-479">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-479"></span></span>
|<span data-ttu-id="f1741-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-481">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-481">passport number</span></span>  <br/> <span data-ttu-id="f1741-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="f1741-482">romanian passport number</span></span>  <br/> <span data-ttu-id="f1741-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-483">passport no</span></span>  <br/> <span data-ttu-id="f1741-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="f1741-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="f1741-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="f1741-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f1741-486">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-486">Format</span></span>

<span data-ttu-id="f1741-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-488">Pattern</span></span>

<span data-ttu-id="f1741-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f1741-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-490">Checksum</span></span>

<span data-ttu-id="f1741-491">No</span><span class="sxs-lookup"><span data-stu-id="f1741-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-492">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-492">Definition</span></span>

<span data-ttu-id="f1741-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-496">Keywords</span></span>

<span data-ttu-id="f1741-497">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-497"></span></span>
|<span data-ttu-id="f1741-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-499">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-499">passport number</span></span>  <br/> <span data-ttu-id="f1741-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="f1741-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="f1741-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-501">passport no</span></span>  <br/> <span data-ttu-id="f1741-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="f1741-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="f1741-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="f1741-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f1741-504">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-504">Format</span></span>

<span data-ttu-id="f1741-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-506">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-506">Pattern</span></span>

<span data-ttu-id="f1741-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="f1741-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="f1741-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="f1741-508">The letter "P"</span></span>
    
- <span data-ttu-id="f1741-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="f1741-509">One uppercase letter</span></span>
    
- <span data-ttu-id="f1741-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f1741-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-511">Checksum</span></span>

<span data-ttu-id="f1741-512">No</span><span class="sxs-lookup"><span data-stu-id="f1741-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-513">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-513">Definition</span></span>

<span data-ttu-id="f1741-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-517">Keywords</span></span>

<span data-ttu-id="f1741-518">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-518"></span></span>
|<span data-ttu-id="f1741-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-520">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-520">passport number</span></span>  <br/> <span data-ttu-id="f1741-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="f1741-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="f1741-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-522">passport no</span></span>  <br/> <span data-ttu-id="f1741-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="f1741-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="f1741-524">España</span><span class="sxs-lookup"><span data-stu-id="f1741-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f1741-525">Formato</span><span class="sxs-lookup"><span data-stu-id="f1741-525">Format</span></span>

<span data-ttu-id="f1741-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="f1741-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f1741-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="f1741-527">Pattern</span></span>

<span data-ttu-id="f1741-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="f1741-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="f1741-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="f1741-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="f1741-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="f1741-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f1741-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f1741-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f1741-532">Checksum</span></span>

<span data-ttu-id="f1741-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f1741-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f1741-534">Definición</span><span class="sxs-lookup"><span data-stu-id="f1741-534">Definition</span></span>

<span data-ttu-id="f1741-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f1741-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f1741-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f1741-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f1741-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="f1741-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f1741-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f1741-538">Keywords</span></span>

<span data-ttu-id="f1741-539">| |</span><span class="sxs-lookup"><span data-stu-id="f1741-539"></span></span>
|<span data-ttu-id="f1741-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f1741-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f1741-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="f1741-541">passport</span></span>  <br/> <span data-ttu-id="f1741-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="f1741-542">spain passport</span></span>  <br/> <span data-ttu-id="f1741-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="f1741-543">passport book</span></span>  <br/> <span data-ttu-id="f1741-544">passport number</span><span class="sxs-lookup"><span data-stu-id="f1741-544">passport number</span></span>  <br/> <span data-ttu-id="f1741-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-545">passport no</span></span>  <br/> <span data-ttu-id="f1741-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="f1741-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-547">número pasaporte</span></span>  <br/> <span data-ttu-id="f1741-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="f1741-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="f1741-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="f1741-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="f1741-550">Sweden</span></span>

<span data-ttu-id="f1741-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f1741-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="f1741-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="f1741-552">UK</span></span>

<span data-ttu-id="f1741-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="f1741-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="f1741-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f1741-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f1741-555">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1741-555">See also</span></span>

[<span data-ttu-id="f1741-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="f1741-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

