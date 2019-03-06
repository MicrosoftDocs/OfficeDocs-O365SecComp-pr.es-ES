---
title: Número de pasaporte de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 3ab92e87607f41cffa8c15f1179a4eef5369cb29
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410935"
---
# <a name="eu-passport-number"></a><span data-ttu-id="6ca39-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="6ca39-104">EU Passport Number</span></span>

<span data-ttu-id="6ca39-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="6ca39-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="6ca39-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="6ca39-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="6ca39-107">Austria</span><span class="sxs-lookup"><span data-stu-id="6ca39-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-108">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-108">Format</span></span>

<span data-ttu-id="6ca39-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-110">Pattern</span></span>

<span data-ttu-id="6ca39-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="6ca39-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="6ca39-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6ca39-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="6ca39-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="6ca39-113">One space (optional)</span></span>
    
- <span data-ttu-id="6ca39-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6ca39-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-115">Checksum</span></span>

<span data-ttu-id="6ca39-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6ca39-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-117">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-117">Definition</span></span>

<span data-ttu-id="6ca39-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-121">Keywords</span></span>

<span data-ttu-id="6ca39-122">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-122"></span></span>
|<span data-ttu-id="6ca39-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-124">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-124">passport number</span></span>  <br/> <span data-ttu-id="6ca39-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="6ca39-125">austrian passport number</span></span>  <br/> <span data-ttu-id="6ca39-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-126">passport no</span></span>  <br/> <span data-ttu-id="6ca39-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="6ca39-127">reisepass</span></span>  <br/> <span data-ttu-id="6ca39-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="6ca39-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="6ca39-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="6ca39-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-130">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-130">Format</span></span>

<span data-ttu-id="6ca39-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-132">Pattern</span></span>

<span data-ttu-id="6ca39-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-134">Checksum</span></span>

<span data-ttu-id="6ca39-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6ca39-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-136">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-136">Definition</span></span>

<span data-ttu-id="6ca39-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-140">Keywords</span></span>

<span data-ttu-id="6ca39-141">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-141"></span></span>
|<span data-ttu-id="6ca39-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-143">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-143">passport number</span></span>  <br/> <span data-ttu-id="6ca39-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="6ca39-144">belgian passport number</span></span>  <br/> <span data-ttu-id="6ca39-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-145">passport no</span></span>  <br/> <span data-ttu-id="6ca39-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="6ca39-146">paspoort</span></span>  <br/> <span data-ttu-id="6ca39-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6ca39-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="6ca39-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="6ca39-148">reisepass kein</span></span>  <br/> <span data-ttu-id="6ca39-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="6ca39-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="6ca39-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="6ca39-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-151">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-151">Format</span></span>

<span data-ttu-id="6ca39-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-153">Pattern</span></span>

 <span data-ttu-id="6ca39-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6ca39-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-155">Checksum</span></span>

<span data-ttu-id="6ca39-156">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-157">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-157">Definition</span></span>

<span data-ttu-id="6ca39-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-161">Keywords</span></span>

<span data-ttu-id="6ca39-162">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-162"></span></span>
|<span data-ttu-id="6ca39-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-164">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-164">passport number</span></span>  <br/> <span data-ttu-id="6ca39-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="6ca39-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="6ca39-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-166">passport no</span></span>  <br/> <span data-ttu-id="6ca39-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="6ca39-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="6ca39-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="6ca39-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-169">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-169">Format</span></span>

<span data-ttu-id="6ca39-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-171">Pattern</span></span>

 <span data-ttu-id="6ca39-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6ca39-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-173">Checksum</span></span>

<span data-ttu-id="6ca39-174">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-175">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-175">Definition</span></span>

<span data-ttu-id="6ca39-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-179">Keywords</span></span>

<span data-ttu-id="6ca39-180">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-180"></span></span>
|<span data-ttu-id="6ca39-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-182">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-182">passport number</span></span>  <br/> <span data-ttu-id="6ca39-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="6ca39-183">croatian passport number</span></span>  <br/> <span data-ttu-id="6ca39-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-184">passport no</span></span>  <br/> <span data-ttu-id="6ca39-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="6ca39-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="6ca39-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="6ca39-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-187">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-187">Format</span></span>

<span data-ttu-id="6ca39-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-189">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-189">Pattern</span></span>

<span data-ttu-id="6ca39-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-191">Checksum</span></span>

<span data-ttu-id="6ca39-192">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-193">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-193">Definition</span></span>

<span data-ttu-id="6ca39-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-197">Keywords</span></span>

<span data-ttu-id="6ca39-198">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-198"></span></span>
|<span data-ttu-id="6ca39-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-200">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-200">passport number</span></span>  <br/> <span data-ttu-id="6ca39-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="6ca39-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="6ca39-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-202">passport no</span></span>  <br/> <span data-ttu-id="6ca39-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="6ca39-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="6ca39-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="6ca39-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-205">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-205">Format</span></span>

<span data-ttu-id="6ca39-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-207">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-207">Pattern</span></span>

<span data-ttu-id="6ca39-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-209">Checksum</span></span>

<span data-ttu-id="6ca39-210">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-211">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-211">Definition</span></span>

<span data-ttu-id="6ca39-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-215">Keywords</span></span>

<span data-ttu-id="6ca39-216">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-216"></span></span>
|<span data-ttu-id="6ca39-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-218">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-218">passport number</span></span>  <br/> <span data-ttu-id="6ca39-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="6ca39-219">czech passport number</span></span>  <br/> <span data-ttu-id="6ca39-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-220">passport no</span></span>  <br/> <span data-ttu-id="6ca39-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="6ca39-221">cestovní pas</span></span>  <br/> <span data-ttu-id="6ca39-222">PAS</span><span class="sxs-lookup"><span data-stu-id="6ca39-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="6ca39-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="6ca39-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-224">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-224">Format</span></span>

<span data-ttu-id="6ca39-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-226">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-226">Pattern</span></span>

 <span data-ttu-id="6ca39-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6ca39-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-228">Checksum</span></span>

<span data-ttu-id="6ca39-229">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-230">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-230">Definition</span></span>

<span data-ttu-id="6ca39-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-234">Keywords</span></span>

<span data-ttu-id="6ca39-235">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-235"></span></span>
|<span data-ttu-id="6ca39-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-237">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-237">passport number</span></span>  <br/> <span data-ttu-id="6ca39-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="6ca39-238">danish passport number</span></span>  <br/> <span data-ttu-id="6ca39-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-239">passport no</span></span>  <br/> <span data-ttu-id="6ca39-240">PAS</span><span class="sxs-lookup"><span data-stu-id="6ca39-240">pas</span></span>  <br/> <span data-ttu-id="6ca39-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="6ca39-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="6ca39-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="6ca39-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-243">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-243">Format</span></span>

<span data-ttu-id="6ca39-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-245">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-245">Pattern</span></span>

<span data-ttu-id="6ca39-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-247">Checksum</span></span>

<span data-ttu-id="6ca39-248">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-249">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-249">Definition</span></span>

<span data-ttu-id="6ca39-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-253">Keywords</span></span>

<span data-ttu-id="6ca39-254">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-254"></span></span>
|<span data-ttu-id="6ca39-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-256">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-256">passport number</span></span>  <br/> <span data-ttu-id="6ca39-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="6ca39-257">estonian passport number</span></span>  <br/> <span data-ttu-id="6ca39-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-258">passport no</span></span>  <br/> <span data-ttu-id="6ca39-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="6ca39-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="6ca39-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="6ca39-260">Finland</span></span>

<span data-ttu-id="6ca39-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6ca39-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="6ca39-262">Francia</span><span class="sxs-lookup"><span data-stu-id="6ca39-262">France</span></span>

<span data-ttu-id="6ca39-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6ca39-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="6ca39-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="6ca39-264">Germany</span></span>

<span data-ttu-id="6ca39-265">Para obtener más información, consulte la sección "número de pasaporte de Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6ca39-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="6ca39-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="6ca39-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-267">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-267">Format</span></span>

<span data-ttu-id="6ca39-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-269">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-269">Pattern</span></span>

<span data-ttu-id="6ca39-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-271">Checksum</span></span>

<span data-ttu-id="6ca39-272">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-273">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-273">Definition</span></span>

<span data-ttu-id="6ca39-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-277">Keywords</span></span>

<span data-ttu-id="6ca39-278">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-278"></span></span>
|<span data-ttu-id="6ca39-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-280">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-280">passport number</span></span>  <br/> <span data-ttu-id="6ca39-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="6ca39-281">greek passport number</span></span>  <br/> <span data-ttu-id="6ca39-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-282">passport no</span></span>  <br/> <span data-ttu-id="6ca39-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="6ca39-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="6ca39-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="6ca39-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-285">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-285">Format</span></span>

<span data-ttu-id="6ca39-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-287">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-287">Pattern</span></span>

<span data-ttu-id="6ca39-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-289">Checksum</span></span>

<span data-ttu-id="6ca39-290">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-291">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-291">Definition</span></span>

<span data-ttu-id="6ca39-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-295">Keywords</span></span>

<span data-ttu-id="6ca39-296">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-296"></span></span>
|<span data-ttu-id="6ca39-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-298">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-298">passport number</span></span>  <br/> <span data-ttu-id="6ca39-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="6ca39-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="6ca39-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-300">passport no</span></span>  <br/> <span data-ttu-id="6ca39-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="6ca39-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="6ca39-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="6ca39-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-303">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-303">Format</span></span>

<span data-ttu-id="6ca39-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-305">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-305">Pattern</span></span>

<span data-ttu-id="6ca39-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6ca39-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6ca39-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6ca39-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6ca39-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6ca39-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-309">Checksum</span></span>

<span data-ttu-id="6ca39-310">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-311">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-311">Definition</span></span>

<span data-ttu-id="6ca39-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-315">Keywords</span></span>

<span data-ttu-id="6ca39-316">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-316"></span></span>
|<span data-ttu-id="6ca39-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-318">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-318">passport number</span></span>  <br/> <span data-ttu-id="6ca39-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="6ca39-319">irish passport number</span></span>  <br/> <span data-ttu-id="6ca39-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-320">passport no</span></span>  <br/> <span data-ttu-id="6ca39-321">PAS</span><span class="sxs-lookup"><span data-stu-id="6ca39-321">pas</span></span>  <br/> <span data-ttu-id="6ca39-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="6ca39-322">passport</span></span>  <br/> <span data-ttu-id="6ca39-323">passeport</span><span class="sxs-lookup"><span data-stu-id="6ca39-323">passeport</span></span>  <br/> <span data-ttu-id="6ca39-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="6ca39-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="6ca39-325">Italia</span><span class="sxs-lookup"><span data-stu-id="6ca39-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-326">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-326">Format</span></span>

<span data-ttu-id="6ca39-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-328">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-328">Pattern</span></span>

<span data-ttu-id="6ca39-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6ca39-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6ca39-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6ca39-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6ca39-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6ca39-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-332">Checksum</span></span>

<span data-ttu-id="6ca39-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6ca39-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-334">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-334">Definition</span></span>

<span data-ttu-id="6ca39-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-338">Keywords</span></span>

<span data-ttu-id="6ca39-339">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-339"></span></span>
|<span data-ttu-id="6ca39-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="6ca39-341">italian passport number</span></span>  <br/> <span data-ttu-id="6ca39-342">Repubblica Italiana Passaporto</span><span class="sxs-lookup"><span data-stu-id="6ca39-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="6ca39-343">Passaporto</span><span class="sxs-lookup"><span data-stu-id="6ca39-343">passaporto</span></span>  <br/> <span data-ttu-id="6ca39-344">Passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="6ca39-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="6ca39-345">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-345">passport number</span></span>  <br/> <span data-ttu-id="6ca39-346">italiana Passaporto numero</span><span class="sxs-lookup"><span data-stu-id="6ca39-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="6ca39-347">Passaporto numero</span><span class="sxs-lookup"><span data-stu-id="6ca39-347">passaporto numero</span></span>  <br/> <span data-ttu-id="6ca39-348">numéro passeport Italien</span><span class="sxs-lookup"><span data-stu-id="6ca39-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="6ca39-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="6ca39-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="6ca39-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="6ca39-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-351">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-351">Format</span></span>

<span data-ttu-id="6ca39-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-353">Pattern</span></span>

<span data-ttu-id="6ca39-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6ca39-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6ca39-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6ca39-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6ca39-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6ca39-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-357">Checksum</span></span>

<span data-ttu-id="6ca39-358">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-359">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-359">Definition</span></span>

<span data-ttu-id="6ca39-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-363">Keywords</span></span>

<span data-ttu-id="6ca39-364">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-364"></span></span>
|<span data-ttu-id="6ca39-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-366">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-366">passport number</span></span>  <br/> <span data-ttu-id="6ca39-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="6ca39-367">latvian passport number</span></span>  <br/> <span data-ttu-id="6ca39-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-368">passport no</span></span>  <br/> <span data-ttu-id="6ca39-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="6ca39-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="6ca39-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="6ca39-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-371">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-371">Format</span></span>

<span data-ttu-id="6ca39-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-373">Pattern</span></span>

<span data-ttu-id="6ca39-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6ca39-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-375">Checksum</span></span>

<span data-ttu-id="6ca39-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6ca39-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-377">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-377">Definition</span></span>

<span data-ttu-id="6ca39-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-381">Keywords</span></span>

<span data-ttu-id="6ca39-382">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-382"></span></span>
|<span data-ttu-id="6ca39-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-384">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-384">passport number</span></span>  <br/> <span data-ttu-id="6ca39-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="6ca39-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="6ca39-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-386">passport no</span></span>  <br/> <span data-ttu-id="6ca39-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="6ca39-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="6ca39-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="6ca39-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-389">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-389">Format</span></span>

<span data-ttu-id="6ca39-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-391">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-391">Pattern</span></span>

<span data-ttu-id="6ca39-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6ca39-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-393">Checksum</span></span>

<span data-ttu-id="6ca39-394">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-395">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-395">Definition</span></span>

<span data-ttu-id="6ca39-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-399">Keywords</span></span>

<span data-ttu-id="6ca39-400">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-400"></span></span>
|<span data-ttu-id="6ca39-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-402">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-402">passport number</span></span>  <br/> <span data-ttu-id="6ca39-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="6ca39-403">latvian passport number</span></span>  <br/> <span data-ttu-id="6ca39-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-404">passport no</span></span>  <br/> <span data-ttu-id="6ca39-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="6ca39-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="6ca39-406">Malta</span><span class="sxs-lookup"><span data-stu-id="6ca39-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-407">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-407">Format</span></span>

<span data-ttu-id="6ca39-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-409">Pattern</span></span>

 <span data-ttu-id="6ca39-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6ca39-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-411">Checksum</span></span>

<span data-ttu-id="6ca39-412">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-413">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-413">Definition</span></span>

<span data-ttu-id="6ca39-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-417">Keywords</span></span>

<span data-ttu-id="6ca39-418">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-418"></span></span>
|<span data-ttu-id="6ca39-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-420">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-420">passport number</span></span>  <br/> <span data-ttu-id="6ca39-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="6ca39-421">maltese passport number</span></span>  <br/> <span data-ttu-id="6ca39-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-422">passport no</span></span>  <br/> <span data-ttu-id="6ca39-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="6ca39-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="6ca39-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="6ca39-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-425">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-425">Format</span></span>

<span data-ttu-id="6ca39-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-427">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-427">Pattern</span></span>

<span data-ttu-id="6ca39-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-429">Checksum</span></span>

<span data-ttu-id="6ca39-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6ca39-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-431">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-431">Definition</span></span>

<span data-ttu-id="6ca39-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-435">Keywords</span></span>

<span data-ttu-id="6ca39-436">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-436"></span></span>
|<span data-ttu-id="6ca39-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="6ca39-438">dutch passport number</span></span>  <br/> <span data-ttu-id="6ca39-439">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-439">passport number</span></span>  <br/> <span data-ttu-id="6ca39-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="6ca39-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="6ca39-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="6ca39-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="6ca39-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="6ca39-442">paspoort</span></span>  <br/> <span data-ttu-id="6ca39-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6ca39-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="6ca39-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6ca39-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="6ca39-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="6ca39-445">Poland</span></span>

<span data-ttu-id="6ca39-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6ca39-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="6ca39-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="6ca39-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-448">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-448">Format</span></span>

<span data-ttu-id="6ca39-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-450">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-450">Pattern</span></span>

<span data-ttu-id="6ca39-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="6ca39-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="6ca39-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6ca39-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="6ca39-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6ca39-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-454">Checksum</span></span>

<span data-ttu-id="6ca39-455">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-456">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-456">Definition</span></span>

<span data-ttu-id="6ca39-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-460">Keywords</span></span>

<span data-ttu-id="6ca39-461">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-461"></span></span>
|<span data-ttu-id="6ca39-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-463">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-463">passport number</span></span>  <br/> <span data-ttu-id="6ca39-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="6ca39-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="6ca39-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-465">passport no</span></span>  <br/> <span data-ttu-id="6ca39-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="6ca39-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="6ca39-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-468">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-468">Format</span></span>

<span data-ttu-id="6ca39-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-470">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-470">Pattern</span></span>

<span data-ttu-id="6ca39-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-472">Checksum</span></span>

<span data-ttu-id="6ca39-473">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-474">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-474">Definition</span></span>

<span data-ttu-id="6ca39-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-478">Keywords</span></span>

<span data-ttu-id="6ca39-479">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-479"></span></span>
|<span data-ttu-id="6ca39-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-481">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-481">passport number</span></span>  <br/> <span data-ttu-id="6ca39-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="6ca39-482">romanian passport number</span></span>  <br/> <span data-ttu-id="6ca39-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-483">passport no</span></span>  <br/> <span data-ttu-id="6ca39-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="6ca39-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="6ca39-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="6ca39-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-486">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-486">Format</span></span>

<span data-ttu-id="6ca39-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-488">Pattern</span></span>

<span data-ttu-id="6ca39-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6ca39-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-490">Checksum</span></span>

<span data-ttu-id="6ca39-491">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-492">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-492">Definition</span></span>

<span data-ttu-id="6ca39-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-496">Keywords</span></span>

<span data-ttu-id="6ca39-497">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-497"></span></span>
|<span data-ttu-id="6ca39-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-499">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-499">passport number</span></span>  <br/> <span data-ttu-id="6ca39-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="6ca39-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="6ca39-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-501">passport no</span></span>  <br/> <span data-ttu-id="6ca39-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="6ca39-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="6ca39-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="6ca39-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-504">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-504">Format</span></span>

<span data-ttu-id="6ca39-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-506">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-506">Pattern</span></span>

<span data-ttu-id="6ca39-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="6ca39-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="6ca39-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="6ca39-508">The letter "P"</span></span>
    
- <span data-ttu-id="6ca39-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="6ca39-509">One uppercase letter</span></span>
    
- <span data-ttu-id="6ca39-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6ca39-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-511">Checksum</span></span>

<span data-ttu-id="6ca39-512">No</span><span class="sxs-lookup"><span data-stu-id="6ca39-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-513">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-513">Definition</span></span>

<span data-ttu-id="6ca39-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-517">Keywords</span></span>

<span data-ttu-id="6ca39-518">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-518"></span></span>
|<span data-ttu-id="6ca39-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-520">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-520">passport number</span></span>  <br/> <span data-ttu-id="6ca39-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="6ca39-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="6ca39-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-522">passport no</span></span>  <br/> <span data-ttu-id="6ca39-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="6ca39-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="6ca39-524">España</span><span class="sxs-lookup"><span data-stu-id="6ca39-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="6ca39-525">Dé</span><span class="sxs-lookup"><span data-stu-id="6ca39-525">Format</span></span>

<span data-ttu-id="6ca39-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="6ca39-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6ca39-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="6ca39-527">Pattern</span></span>

<span data-ttu-id="6ca39-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="6ca39-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="6ca39-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="6ca39-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="6ca39-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="6ca39-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6ca39-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6ca39-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="6ca39-532">Checksum</span></span>

<span data-ttu-id="6ca39-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="6ca39-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6ca39-534">Definición</span><span class="sxs-lookup"><span data-stu-id="6ca39-534">Definition</span></span>

<span data-ttu-id="6ca39-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6ca39-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6ca39-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="6ca39-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6ca39-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="6ca39-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6ca39-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6ca39-538">Keywords</span></span>

<span data-ttu-id="6ca39-539">| |</span><span class="sxs-lookup"><span data-stu-id="6ca39-539"></span></span>
|<span data-ttu-id="6ca39-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6ca39-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6ca39-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="6ca39-541">passport</span></span>  <br/> <span data-ttu-id="6ca39-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="6ca39-542">spain passport</span></span>  <br/> <span data-ttu-id="6ca39-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="6ca39-543">passport book</span></span>  <br/> <span data-ttu-id="6ca39-544">passport number</span><span class="sxs-lookup"><span data-stu-id="6ca39-544">passport number</span></span>  <br/> <span data-ttu-id="6ca39-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-545">passport no</span></span>  <br/> <span data-ttu-id="6ca39-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="6ca39-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-547">número pasaporte</span></span>  <br/> <span data-ttu-id="6ca39-548">España pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="6ca39-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="6ca39-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="6ca39-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="6ca39-550">Sweden</span></span>

<span data-ttu-id="6ca39-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6ca39-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="6ca39-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="6ca39-552">UK</span></span>

<span data-ttu-id="6ca39-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="6ca39-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="6ca39-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6ca39-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ca39-555">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ca39-555">See also</span></span>

[<span data-ttu-id="6ca39-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="6ca39-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

