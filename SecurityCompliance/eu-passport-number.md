---
title: Número de pasaporte de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: c46f683bd1baf651bcf13c1766dfff3cb953b341
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218270"
---
# <a name="eu-passport-number"></a><span data-ttu-id="84f2b-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="84f2b-104">EU Passport Number</span></span>

<span data-ttu-id="84f2b-p102">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="84f2b-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="84f2b-107">Austria</span><span class="sxs-lookup"><span data-stu-id="84f2b-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-108">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-108">Format</span></span>

<span data-ttu-id="84f2b-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-110">Pattern</span></span>

<span data-ttu-id="84f2b-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="84f2b-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="84f2b-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="84f2b-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="84f2b-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="84f2b-113">One space (optional)</span></span>
    
- <span data-ttu-id="84f2b-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="84f2b-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-115">Checksum</span></span>

<span data-ttu-id="84f2b-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="84f2b-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-117">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-117">Definition</span></span>

<span data-ttu-id="84f2b-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-121">Keywords</span></span>

<span data-ttu-id="84f2b-122">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-122"></span></span>
|<span data-ttu-id="84f2b-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-124">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-124">passport number</span></span>  <br/> <span data-ttu-id="84f2b-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="84f2b-125">austrian passport number</span></span>  <br/> <span data-ttu-id="84f2b-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-126">passport no</span></span>  <br/> <span data-ttu-id="84f2b-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="84f2b-127">reisepass</span></span>  <br/> <span data-ttu-id="84f2b-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="84f2b-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="84f2b-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="84f2b-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-130">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-130">Format</span></span>

<span data-ttu-id="84f2b-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-132">Pattern</span></span>

<span data-ttu-id="84f2b-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-134">Checksum</span></span>

<span data-ttu-id="84f2b-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="84f2b-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-136">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-136">Definition</span></span>

<span data-ttu-id="84f2b-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-140">Keywords</span></span>

<span data-ttu-id="84f2b-141">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-141"></span></span>
|<span data-ttu-id="84f2b-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-143">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-143">passport number</span></span>  <br/> <span data-ttu-id="84f2b-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="84f2b-144">belgian passport number</span></span>  <br/> <span data-ttu-id="84f2b-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-145">passport no</span></span>  <br/> <span data-ttu-id="84f2b-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="84f2b-146">paspoort</span></span>  <br/> <span data-ttu-id="84f2b-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="84f2b-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="84f2b-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="84f2b-148">reisepass kein</span></span>  <br/> <span data-ttu-id="84f2b-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="84f2b-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="84f2b-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="84f2b-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-151">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-151">Format</span></span>

<span data-ttu-id="84f2b-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-153">Pattern</span></span>

 <span data-ttu-id="84f2b-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="84f2b-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-155">Checksum</span></span>

<span data-ttu-id="84f2b-156">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-157">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-157">Definition</span></span>

<span data-ttu-id="84f2b-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-161">Keywords</span></span>

<span data-ttu-id="84f2b-162">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-162"></span></span>
|<span data-ttu-id="84f2b-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-164">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-164">passport number</span></span>  <br/> <span data-ttu-id="84f2b-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="84f2b-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="84f2b-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-166">passport no</span></span>  <br/> <span data-ttu-id="84f2b-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="84f2b-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="84f2b-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="84f2b-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-169">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-169">Format</span></span>

<span data-ttu-id="84f2b-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-171">Pattern</span></span>

 <span data-ttu-id="84f2b-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="84f2b-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-173">Checksum</span></span>

<span data-ttu-id="84f2b-174">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-175">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-175">Definition</span></span>

<span data-ttu-id="84f2b-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-179">Keywords</span></span>

<span data-ttu-id="84f2b-180">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-180"></span></span>
|<span data-ttu-id="84f2b-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-182">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-182">passport number</span></span>  <br/> <span data-ttu-id="84f2b-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="84f2b-183">croatian passport number</span></span>  <br/> <span data-ttu-id="84f2b-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-184">passport no</span></span>  <br/> <span data-ttu-id="84f2b-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="84f2b-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="84f2b-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="84f2b-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-187">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-187">Format</span></span>

<span data-ttu-id="84f2b-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-189">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-189">Pattern</span></span>

<span data-ttu-id="84f2b-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-191">Checksum</span></span>

<span data-ttu-id="84f2b-192">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-193">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-193">Definition</span></span>

<span data-ttu-id="84f2b-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-197">Keywords</span></span>

<span data-ttu-id="84f2b-198">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-198"></span></span>
|<span data-ttu-id="84f2b-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-200">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-200">passport number</span></span>  <br/> <span data-ttu-id="84f2b-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="84f2b-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="84f2b-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-202">passport no</span></span>  <br/> <span data-ttu-id="84f2b-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="84f2b-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="84f2b-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="84f2b-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-205">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-205">Format</span></span>

<span data-ttu-id="84f2b-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-207">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-207">Pattern</span></span>

<span data-ttu-id="84f2b-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-209">Checksum</span></span>

<span data-ttu-id="84f2b-210">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-211">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-211">Definition</span></span>

<span data-ttu-id="84f2b-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-215">Keywords</span></span>

<span data-ttu-id="84f2b-216">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-216"></span></span>
|<span data-ttu-id="84f2b-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-218">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-218">passport number</span></span>  <br/> <span data-ttu-id="84f2b-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="84f2b-219">czech passport number</span></span>  <br/> <span data-ttu-id="84f2b-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-220">passport no</span></span>  <br/> <span data-ttu-id="84f2b-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="84f2b-221">cestovní pas</span></span>  <br/> <span data-ttu-id="84f2b-222">PAS</span><span class="sxs-lookup"><span data-stu-id="84f2b-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="84f2b-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="84f2b-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-224">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-224">Format</span></span>

<span data-ttu-id="84f2b-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-226">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-226">Pattern</span></span>

 <span data-ttu-id="84f2b-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="84f2b-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-228">Checksum</span></span>

<span data-ttu-id="84f2b-229">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-230">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-230">Definition</span></span>

<span data-ttu-id="84f2b-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-234">Keywords</span></span>

<span data-ttu-id="84f2b-235">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-235"></span></span>
|<span data-ttu-id="84f2b-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-237">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-237">passport number</span></span>  <br/> <span data-ttu-id="84f2b-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="84f2b-238">danish passport number</span></span>  <br/> <span data-ttu-id="84f2b-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-239">passport no</span></span>  <br/> <span data-ttu-id="84f2b-240">PAS</span><span class="sxs-lookup"><span data-stu-id="84f2b-240">pas</span></span>  <br/> <span data-ttu-id="84f2b-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="84f2b-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="84f2b-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="84f2b-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-243">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-243">Format</span></span>

<span data-ttu-id="84f2b-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-245">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-245">Pattern</span></span>

<span data-ttu-id="84f2b-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-247">Checksum</span></span>

<span data-ttu-id="84f2b-248">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-249">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-249">Definition</span></span>

<span data-ttu-id="84f2b-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-253">Keywords</span></span>

<span data-ttu-id="84f2b-254">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-254"></span></span>
|<span data-ttu-id="84f2b-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-256">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-256">passport number</span></span>  <br/> <span data-ttu-id="84f2b-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="84f2b-257">estonian passport number</span></span>  <br/> <span data-ttu-id="84f2b-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-258">passport no</span></span>  <br/> <span data-ttu-id="84f2b-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="84f2b-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="84f2b-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="84f2b-260">Finland</span></span>

<span data-ttu-id="84f2b-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="84f2b-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="84f2b-262">Francia</span><span class="sxs-lookup"><span data-stu-id="84f2b-262">France</span></span>

<span data-ttu-id="84f2b-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="84f2b-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="84f2b-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="84f2b-264">Germany</span></span>

<span data-ttu-id="84f2b-265">Para obtener más información, consulte la sección "número de pasaporte de Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="84f2b-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="84f2b-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="84f2b-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-267">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-267">Format</span></span>

<span data-ttu-id="84f2b-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-269">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-269">Pattern</span></span>

<span data-ttu-id="84f2b-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-271">Checksum</span></span>

<span data-ttu-id="84f2b-272">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-273">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-273">Definition</span></span>

<span data-ttu-id="84f2b-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-277">Keywords</span></span>

<span data-ttu-id="84f2b-278">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-278"></span></span>
|<span data-ttu-id="84f2b-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-280">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-280">passport number</span></span>  <br/> <span data-ttu-id="84f2b-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="84f2b-281">greek passport number</span></span>  <br/> <span data-ttu-id="84f2b-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-282">passport no</span></span>  <br/> <span data-ttu-id="84f2b-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="84f2b-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="84f2b-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="84f2b-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-285">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-285">Format</span></span>

<span data-ttu-id="84f2b-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-287">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-287">Pattern</span></span>

<span data-ttu-id="84f2b-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-289">Checksum</span></span>

<span data-ttu-id="84f2b-290">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-291">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-291">Definition</span></span>

<span data-ttu-id="84f2b-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-295">Keywords</span></span>

<span data-ttu-id="84f2b-296">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-296"></span></span>
|<span data-ttu-id="84f2b-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-298">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-298">passport number</span></span>  <br/> <span data-ttu-id="84f2b-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="84f2b-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="84f2b-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-300">passport no</span></span>  <br/> <span data-ttu-id="84f2b-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="84f2b-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="84f2b-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="84f2b-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-303">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-303">Format</span></span>

<span data-ttu-id="84f2b-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-305">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-305">Pattern</span></span>

<span data-ttu-id="84f2b-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="84f2b-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="84f2b-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="84f2b-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="84f2b-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="84f2b-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-309">Checksum</span></span>

<span data-ttu-id="84f2b-310">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-311">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-311">Definition</span></span>

<span data-ttu-id="84f2b-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-315">Keywords</span></span>

<span data-ttu-id="84f2b-316">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-316"></span></span>
|<span data-ttu-id="84f2b-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-318">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-318">passport number</span></span>  <br/> <span data-ttu-id="84f2b-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="84f2b-319">irish passport number</span></span>  <br/> <span data-ttu-id="84f2b-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-320">passport no</span></span>  <br/> <span data-ttu-id="84f2b-321">PAS</span><span class="sxs-lookup"><span data-stu-id="84f2b-321">pas</span></span>  <br/> <span data-ttu-id="84f2b-322">passport</span><span class="sxs-lookup"><span data-stu-id="84f2b-322">passport</span></span>  <br/> <span data-ttu-id="84f2b-323">passeport</span><span class="sxs-lookup"><span data-stu-id="84f2b-323">passeport</span></span>  <br/> <span data-ttu-id="84f2b-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="84f2b-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="84f2b-325">Italia</span><span class="sxs-lookup"><span data-stu-id="84f2b-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-326">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-326">Format</span></span>

<span data-ttu-id="84f2b-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-328">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-328">Pattern</span></span>

<span data-ttu-id="84f2b-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="84f2b-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="84f2b-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="84f2b-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="84f2b-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="84f2b-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-332">Checksum</span></span>

<span data-ttu-id="84f2b-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="84f2b-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-334">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-334">Definition</span></span>

<span data-ttu-id="84f2b-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-338">Keywords</span></span>

<span data-ttu-id="84f2b-339">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-339"></span></span>
|<span data-ttu-id="84f2b-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="84f2b-341">italian passport number</span></span>  <br/> <span data-ttu-id="84f2b-342">Repubblica Italiana Passaporto</span><span class="sxs-lookup"><span data-stu-id="84f2b-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="84f2b-343">Passaporto</span><span class="sxs-lookup"><span data-stu-id="84f2b-343">passaporto</span></span>  <br/> <span data-ttu-id="84f2b-344">Passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="84f2b-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="84f2b-345">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-345">passport number</span></span>  <br/> <span data-ttu-id="84f2b-346">italiana Passaporto numero</span><span class="sxs-lookup"><span data-stu-id="84f2b-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="84f2b-347">Passaporto numero</span><span class="sxs-lookup"><span data-stu-id="84f2b-347">passaporto numero</span></span>  <br/> <span data-ttu-id="84f2b-348">numéro passeport Italien</span><span class="sxs-lookup"><span data-stu-id="84f2b-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="84f2b-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="84f2b-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="84f2b-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="84f2b-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-351">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-351">Format</span></span>

<span data-ttu-id="84f2b-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-353">Pattern</span></span>

<span data-ttu-id="84f2b-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="84f2b-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="84f2b-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="84f2b-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="84f2b-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="84f2b-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-357">Checksum</span></span>

<span data-ttu-id="84f2b-358">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-359">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-359">Definition</span></span>

<span data-ttu-id="84f2b-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-363">Keywords</span></span>

<span data-ttu-id="84f2b-364">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-364"></span></span>
|<span data-ttu-id="84f2b-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-366">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-366">passport number</span></span>  <br/> <span data-ttu-id="84f2b-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="84f2b-367">latvian passport number</span></span>  <br/> <span data-ttu-id="84f2b-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-368">passport no</span></span>  <br/> <span data-ttu-id="84f2b-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="84f2b-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="84f2b-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="84f2b-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-371">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-371">Format</span></span>

<span data-ttu-id="84f2b-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-373">Pattern</span></span>

<span data-ttu-id="84f2b-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="84f2b-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-375">Checksum</span></span>

<span data-ttu-id="84f2b-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="84f2b-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-377">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-377">Definition</span></span>

<span data-ttu-id="84f2b-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-381">Keywords</span></span>

<span data-ttu-id="84f2b-382">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-382"></span></span>
|<span data-ttu-id="84f2b-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-384">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-384">passport number</span></span>  <br/> <span data-ttu-id="84f2b-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="84f2b-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="84f2b-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-386">passport no</span></span>  <br/> <span data-ttu-id="84f2b-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="84f2b-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="84f2b-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="84f2b-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-389">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-389">Format</span></span>

<span data-ttu-id="84f2b-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-391">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-391">Pattern</span></span>

<span data-ttu-id="84f2b-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="84f2b-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-393">Checksum</span></span>

<span data-ttu-id="84f2b-394">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-395">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-395">Definition</span></span>

<span data-ttu-id="84f2b-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-399">Keywords</span></span>

<span data-ttu-id="84f2b-400">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-400"></span></span>
|<span data-ttu-id="84f2b-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-402">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-402">passport number</span></span>  <br/> <span data-ttu-id="84f2b-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="84f2b-403">latvian passport number</span></span>  <br/> <span data-ttu-id="84f2b-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-404">passport no</span></span>  <br/> <span data-ttu-id="84f2b-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="84f2b-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="84f2b-406">Malta</span><span class="sxs-lookup"><span data-stu-id="84f2b-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-407">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-407">Format</span></span>

<span data-ttu-id="84f2b-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-409">Pattern</span></span>

 <span data-ttu-id="84f2b-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="84f2b-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-411">Checksum</span></span>

<span data-ttu-id="84f2b-412">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-413">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-413">Definition</span></span>

<span data-ttu-id="84f2b-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-417">Keywords</span></span>

<span data-ttu-id="84f2b-418">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-418"></span></span>
|<span data-ttu-id="84f2b-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-420">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-420">passport number</span></span>  <br/> <span data-ttu-id="84f2b-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="84f2b-421">maltese passport number</span></span>  <br/> <span data-ttu-id="84f2b-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-422">passport no</span></span>  <br/> <span data-ttu-id="84f2b-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="84f2b-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="84f2b-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="84f2b-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-425">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-425">Format</span></span>

<span data-ttu-id="84f2b-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-427">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-427">Pattern</span></span>

<span data-ttu-id="84f2b-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-429">Checksum</span></span>

<span data-ttu-id="84f2b-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="84f2b-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-431">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-431">Definition</span></span>

<span data-ttu-id="84f2b-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-435">Keywords</span></span>

<span data-ttu-id="84f2b-436">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-436"></span></span>
|<span data-ttu-id="84f2b-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="84f2b-438">dutch passport number</span></span>  <br/> <span data-ttu-id="84f2b-439">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-439">passport number</span></span>  <br/> <span data-ttu-id="84f2b-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="84f2b-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="84f2b-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="84f2b-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="84f2b-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="84f2b-442">paspoort</span></span>  <br/> <span data-ttu-id="84f2b-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="84f2b-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="84f2b-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="84f2b-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="84f2b-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="84f2b-445">Poland</span></span>

<span data-ttu-id="84f2b-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="84f2b-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="84f2b-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="84f2b-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-448">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-448">Format</span></span>

<span data-ttu-id="84f2b-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-450">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-450">Pattern</span></span>

<span data-ttu-id="84f2b-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="84f2b-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="84f2b-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="84f2b-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="84f2b-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="84f2b-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-454">Checksum</span></span>

<span data-ttu-id="84f2b-455">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-456">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-456">Definition</span></span>

<span data-ttu-id="84f2b-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-460">Keywords</span></span>

<span data-ttu-id="84f2b-461">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-461"></span></span>
|<span data-ttu-id="84f2b-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-463">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-463">passport number</span></span>  <br/> <span data-ttu-id="84f2b-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="84f2b-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="84f2b-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-465">passport no</span></span>  <br/> <span data-ttu-id="84f2b-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="84f2b-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="84f2b-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-468">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-468">Format</span></span>

<span data-ttu-id="84f2b-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-470">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-470">Pattern</span></span>

<span data-ttu-id="84f2b-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-472">Checksum</span></span>

<span data-ttu-id="84f2b-473">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-474">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-474">Definition</span></span>

<span data-ttu-id="84f2b-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-478">Keywords</span></span>

<span data-ttu-id="84f2b-479">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-479"></span></span>
|<span data-ttu-id="84f2b-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-481">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-481">passport number</span></span>  <br/> <span data-ttu-id="84f2b-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="84f2b-482">romanian passport number</span></span>  <br/> <span data-ttu-id="84f2b-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-483">passport no</span></span>  <br/> <span data-ttu-id="84f2b-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="84f2b-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="84f2b-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="84f2b-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-486">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-486">Format</span></span>

<span data-ttu-id="84f2b-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-488">Pattern</span></span>

<span data-ttu-id="84f2b-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="84f2b-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-490">Checksum</span></span>

<span data-ttu-id="84f2b-491">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-492">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-492">Definition</span></span>

<span data-ttu-id="84f2b-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-496">Keywords</span></span>

<span data-ttu-id="84f2b-497">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-497"></span></span>
|<span data-ttu-id="84f2b-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-499">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-499">passport number</span></span>  <br/> <span data-ttu-id="84f2b-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="84f2b-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="84f2b-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-501">passport no</span></span>  <br/> <span data-ttu-id="84f2b-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="84f2b-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="84f2b-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="84f2b-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-504">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-504">Format</span></span>

<span data-ttu-id="84f2b-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-506">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-506">Pattern</span></span>

<span data-ttu-id="84f2b-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="84f2b-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="84f2b-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="84f2b-508">The letter "P"</span></span>
    
- <span data-ttu-id="84f2b-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="84f2b-509">One uppercase letter</span></span>
    
- <span data-ttu-id="84f2b-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="84f2b-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-511">Checksum</span></span>

<span data-ttu-id="84f2b-512">No</span><span class="sxs-lookup"><span data-stu-id="84f2b-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-513">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-513">Definition</span></span>

<span data-ttu-id="84f2b-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-517">Keywords</span></span>

<span data-ttu-id="84f2b-518">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-518"></span></span>
|<span data-ttu-id="84f2b-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-520">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-520">passport number</span></span>  <br/> <span data-ttu-id="84f2b-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="84f2b-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="84f2b-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-522">passport no</span></span>  <br/> <span data-ttu-id="84f2b-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="84f2b-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="84f2b-524">España</span><span class="sxs-lookup"><span data-stu-id="84f2b-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="84f2b-525">Formato</span><span class="sxs-lookup"><span data-stu-id="84f2b-525">Format</span></span>

<span data-ttu-id="84f2b-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="84f2b-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="84f2b-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="84f2b-527">Pattern</span></span>

<span data-ttu-id="84f2b-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="84f2b-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="84f2b-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="84f2b-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="84f2b-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="84f2b-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="84f2b-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="84f2b-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="84f2b-532">Checksum</span></span>

<span data-ttu-id="84f2b-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="84f2b-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="84f2b-534">Definición</span><span class="sxs-lookup"><span data-stu-id="84f2b-534">Definition</span></span>

<span data-ttu-id="84f2b-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="84f2b-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="84f2b-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="84f2b-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="84f2b-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="84f2b-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="84f2b-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84f2b-538">Keywords</span></span>

<span data-ttu-id="84f2b-539">| |</span><span class="sxs-lookup"><span data-stu-id="84f2b-539"></span></span>
|<span data-ttu-id="84f2b-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="84f2b-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="84f2b-541">passport</span><span class="sxs-lookup"><span data-stu-id="84f2b-541">passport</span></span>  <br/> <span data-ttu-id="84f2b-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="84f2b-542">spain passport</span></span>  <br/> <span data-ttu-id="84f2b-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="84f2b-543">passport book</span></span>  <br/> <span data-ttu-id="84f2b-544">número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-544">passport number</span></span>  <br/> <span data-ttu-id="84f2b-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-545">passport no</span></span>  <br/> <span data-ttu-id="84f2b-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="84f2b-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-547">número pasaporte</span></span>  <br/> <span data-ttu-id="84f2b-548">España pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="84f2b-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="84f2b-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="84f2b-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="84f2b-550">Sweden</span></span>

<span data-ttu-id="84f2b-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="84f2b-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="84f2b-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="84f2b-552">UK</span></span>

<span data-ttu-id="84f2b-p103">Para obtener más información, consulte la sección "número de pasaporte de Estados Unidos/Reino Unido" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="84f2b-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84f2b-555">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84f2b-555">See also</span></span>

[<span data-ttu-id="84f2b-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="84f2b-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

